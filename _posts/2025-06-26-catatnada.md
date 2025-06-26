---
title: "CatatNada"
date: 2025-06-26
draft: false
categories: ["Projects"]
tags: ["CatatNada"]
description: "A modern Android application for music discovery and personal playlist management"

image:
  path: /assets/catatnada.jpg
---

[![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://developer.android.com/)
[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.java.com/)
[![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![Retrofit](https://img.shields.io/badge/Retrofit-2.9.0-000000?style=for-the-badge&logo=retrofit&logoColor=white)](https://square.github.io/retrofit/)

[![GitHub stars](https://img.shields.io/github/stars/jih89/CatatNada?style=social)](https://github.com/jih89/CatatNada)
[![GitHub forks](https://img.shields.io/github/forks/jih89/CatatNada?style=social)](https://github.com/jih89/CatatNada)

---

## 📱 Overview

**CatatNada** is a feature-rich Android music application that combines the power of music discovery with personal playlist curation. Built as a final project for mobile development lab, this app demonstrates comprehensive Android development skills including UI/UX design, API integration, local database management, and modern Android architecture patterns.

The app leverages the **Last.fm API** to provide users with trending music discovery while offering robust local playlist management capabilities, all wrapped in a beautiful Material Design interface.

---

## ✨ Key Features

### 🎯 Music Discovery
- **Global Trending Tracks**: Discover what's hot worldwide
- **Genre-based Discovery**: Explore trending music by specific genres/tags
- **Advanced Search**: Find specific tracks and artists with real-time search
- **Rich Track Information**: Detailed track info including artist details and album artwork

### 📝 Playlist Management
- **Create Custom Playlists**: Build personalized music collections
- **Full CRUD Operations**: Create, Read, Update, and Delete playlists and tracks
- **Local Storage**: All data stored locally using SQLite for offline access
- **Intuitive Interface**: Easy-to-use playlist management with drag-and-drop functionality

### 🎨 User Experience
- **Theme Customization**: Light, Dark, and System theme support
- **Responsive Design**: Optimized for various screen sizes
- **Smooth Navigation**: Modern navigation using Android Jetpack Navigation Component
- **Error Handling**: Robust error handling with retry mechanisms

---

## 🛠️ Technical Architecture

### Core Technologies
- **Language**: Java 11
- **Minimum SDK**: API 24 (Android 7.0)
- **Target SDK**: API 35 (Android 15)
- **Architecture**: MVC Pattern with Repository Pattern

### Key Libraries & Dependencies

| Category | Technology | Purpose |
|----------|------------|---------|
| **Networking** | Retrofit 2.9.0 + GSON | REST API communication with Last.fm |
| **UI Components** | Material Components | Modern Material Design interface |
| **Navigation** | Android Jetpack Navigation | Fragment-based navigation |
| **Database** | SQLite + SQLiteOpenHelper | Local data persistence |
| **Image Loading** | Glide 4.16.0 | Efficient image caching and loading |
| **Background Processing** | ExecutorService + Handler | Asynchronous operations |

### Project Structure
```
app/src/main/java/com/imam/catatnada/
├── api/                    # API integration layer
│   ├── ApiService.java     # Retrofit interface
│   ├── LastFmModels.java   # Data models
│   └── RetrofitClient.java # HTTP client configuration
├── database/               # Data persistence layer
│   ├── DatabaseHelper.java # SQLite database management
│   ├── Playlist.java       # Playlist entity
│   ├── Track.java          # Track entity
│   └── PlaylistDataSource.java # Data access layer
├── ui/                     # User interface layer
│   ├── activity/           # Android activities
│   ├── fragment/           # UI fragments
│   └── adapter/            # RecyclerView adapters
└── utils/                  # Utility classes
    └── ThemeManager.java   # Theme management
```

---

## 📸 Screenshots

### Main Interface
<img src="/assets/catatnada/main_screen.png" alt="Screenshot" style="max-width:450px; height:auto;">

### Search Functionality
<img src="/assets/catatnada/search_screen.png" alt="Screenshot" style="max-width:450px; height:auto;">

### Playlist Management
<img src="/assets/catatnada/playlist_screen.png" alt="Screenshot" style="max-width: 450px; height: auto;">
<img src="/assets/catatnada/playlist_detail.png" alt="Screenshot" style="max-width: 450px; height: auto;">

### Track Details
<img src="/assets/catatnada/track_detail.png" alt="Screenshot" style="max-width:450px; height:auto;">

### Theme Switcher
<img src="/assets/catatnada/settings_screen.png" alt="Screenshot" style="max-width:450px; height:auto;">

---

## 🙏 Acknowledgments

- [Last.fm API](https://www.last.fm/api) for providing music data
- [Material Design](https://material.io/) for design guidelines
- [Android Jetpack](https://developer.android.com/jetpack) for modern Android development tools
- My mobile development lab instructors for guidance and support

---

## ✍️ Source Code

<a href="https://github.com/jih89/CatatNada" target="_blank" class="btn btn-primary" mb-2>
  <i class="fas fa-fw fa-code"></i>
  Click Here
</a>