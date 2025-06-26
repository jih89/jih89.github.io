---
title: "Web Scraping Data Negara dengan Python & BeautifulSoup"
date: 2025-03-02
categories: [project, web-scraping]
tags: [python, beautifulsoup, requests, portfolio, data-collection]
author_profile: true
description: "Proyek sederhana untuk mengekstrak data negara dari situs latihan scrapethissite.com"
---

### Ringkasan Proyek (TL;DR)

* **Tujuan:** Secara otomatis mengumpulkan data negara (nama, ibu kota, populasi, dan luas wilayah) dari halaman web statis.
* **Metode:** Menggunakan library `requests` untuk mengunduh konten halaman dan `BeautifulSoup` untuk mem-parsing dan mengekstrak data berdasarkan tag HTML dan kelas CSS.
* **Hasil:** Berhasil mengekstrak data dari 249 negara dan menyimpannya dalam sebuah file CSV yang terstruktur.
* **Teknologi:** Python, Requests, BeautifulSoup, Pandas.

---

### Konteks & Tujuan Proyek

Web scraping adalah teknik untuk mengekstrak sejumlah besar data dari situs web. Data ini kemudian dapat digunakan untuk berbagai keperluan, seperti analisis pasar, riset akademis, atau sebagai dataset untuk proyek *machine learning*.

Proyek ini bertujuan untuk mempraktikkan dasar-dasar web scraping pada halaman [Simple Page di Scrape This Site](https://www.scrapethissite.com/pages/simple/), sebuah situs yang memang dirancang untuk tujuan latihan.

---

### Proses & Metodologi

Berikut adalah langkah-langkah yang saya lakukan dalam proyek ini.

#### Langkah 1: Inspeksi Struktur Halaman Web

Sebelum menulis kode, langkah pertama dan terpenting adalah memahami struktur HTML dari halaman target. Dengan menggunakan fitur "Inspect Element" di browser, saya menemukan pola yang konsisten:

1.  Setiap negara dibungkus dalam sebuah elemen `<div>` dengan `class="country"`.
2.  Di dalam `div` tersebut, data spesifik berada di dalam tag dengan class yang jelas:
    * Nama Negara: `<h3>` dengan `class="country-name"`
    * Ibu Kota: `<span>` dengan `class="country-capital"`
    * Populasi: `<span>` dengan `class="country-population"`
    * Luas Wilayah: `<span>` dengan `class="country-area"`

Pola inilah yang akan menjadi panduan bagi skrip Python saya.

#### Langkah 2: Mengunduh & Mem-parsing Halaman

Saya menggunakan library `requests` untuk mengirim permintaan HTTP GET dan mengunduh konten mentah HTML. Kemudian, `BeautifulSoup` digunakan untuk mengubah teks HTML tersebut menjadi sebuah objek Python yang bisa "dimengerti" dan dinavigasi.

#### Langkah 3: Logika Ekstraksi Data

Setelah halaman berhasil di-parsing, saya menulis sebuah *loop* untuk mencari semua elemen `div` yang mewakili negara, lalu untuk setiap negara, saya mencari detail spesifiknya dan menyimpannya ke dalam *list*.

#### Langkah 4: Menyimpan Hasil ke CSV

Untuk membuat proyek ini benar-benar bermanfaat, data yang sudah diekstrak harus disimpan dalam format yang terstruktur. Saya menggunakan library `pandas` untuk mengubah *list* data menjadi sebuah DataFrame dan menyimpannya sebagai file CSV.

## Kode yang digunakan

```python
# 1. Import library yang dibutuhkan
import requests
from bs4 import BeautifulSoup
import pandas as pd

def scrape_country_data():
    """
    Fungsi untuk melakukan scraping data negara dari 'scrapethissite.com',
    lalu menyimpannya ke file CSV.
    """
    
    # 2. Tentukan URL target dan unduh halaman
    url = '[https://www.scrapethissite.com/pages/simple/](https://www.scrapethissite.com/pages/simple/)'
    
    try:
        print(f"Mengakses URL: {url}")
        response = requests.get(url, timeout=10)
        # Memberi error jika status code bukan 200 (OK)
        response.raise_for_status() 
    except requests.exceptions.RequestException as e:
        print(f"Error saat mengakses URL: {e}")
        return # Keluar dari fungsi jika URL gagal diakses

    # 3. Parsing HTML dengan BeautifulSoup
    soup = BeautifulSoup(response.text, 'html.parser')

    # 4. Siapkan list kosong untuk menampung data
    names, capitals, populations, areas = [], [], [], []

    # 5. Temukan semua elemen div yang berisi info negara
    countries = soup.find_all('div', class_='country')
    print(f"Menemukan {len(countries)} negara untuk diekstrak.")

    # 6. Looping untuk setiap negara dan ekstrak datanya
    for country in countries:
        try:
            name = country.find('h3', class_='country-name').text.strip()
            capital = country.find('span', class_='country-capital').text.strip()
            # Konversi populasi dan area ke integer untuk penggunaan di masa depan
            population = int(country.find('span', class_='country-population').text.strip())
            area = float(country.find('span', class_='country-area').text.strip())

            # Memasukkan data ke dalam list
            names.append(name)
            capitals.append(capital)
            populations.append(population)
            areas.append(area)
        except (AttributeError, ValueError) as e:
            # Menangani jika ada elemen yang tidak ditemukan atau gagal konversi tipe data
            print(f"Melewati satu entri karena ada data yang hilang atau format salah: {e}")
            continue

    print("Ekstraksi data dari halaman selesai.")

    # 7. Membuat DataFrame dengan Pandas
    if not names:
        print("Tidak ada data yang berhasil diekstrak. Proses dihentikan.")
        return
        
    df = pd.DataFrame({
        'Nama Negara': names,
        'Ibu Kota': capitals,
        'Populasi': populations,
        'Luas Wilayah (km2)': areas
    })

    # 8. Menyimpan DataFrame ke file CSV
    try:
        output_filename = 'data_negara_dunia.csv'
        df.to_csv(output_filename, index=False)
        print(f"Proses berhasil! Data telah disimpan ke '{output_filename}'")
    except Exception as e:
        print(f"Gagal menyimpan file CSV: {e}")

# Menjalankan fungsi utama
if __name__ == '__main__':
    scrape_country_data()
```