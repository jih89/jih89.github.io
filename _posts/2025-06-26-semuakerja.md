---
title: "SemuaKerja"
date: 2025-06-25
draft: false
categories: ["Projects"]
tags: ["SemuaKerja"]
description: "Laravel-based web platform for job searching and recruitment"
---

![Main Screen](assets/semuakerja.png)

**SemuaKerja** is a Laravel-based web platform for job searching and recruitment, connecting job seekers with employers and providing an admin panel for managing users and job postings.

---

## ✨ Main Features

### For Job Seekers
- Register & log in as a job seeker
- Browse the latest job postings
- View job details and company information
- Apply for jobs by uploading a CV (PDF/DOCX)
- Track the status of submitted applications

### For Employers
- Register & log in as an employer
- Employer dashboard to manage posted jobs
- Create, edit, and delete job postings
- View applicants for each job posting
- View and download applicants' CVs
- Update application status (accepted/rejected)

### For Admins
- Admin dashboard for monitoring user and job statistics
- Manage user data (add, edit, delete users)
- Manage job postings (edit, delete jobs)
- Cannot delete own admin account

### General Features
- Multi-role authentication and authorization (admin, employer, job seeker)
- Responsive UI with Tailwind CSS & Bootstrap
- Success/error notifications for important actions
- Job search and filtering features
- Role-based access security

---

## 🧭 User Flow

1. **Job Seekers** register, log in, browse, and apply for jobs.
2. **Employers** register, log in, create and manage job postings, and process incoming applications.
3. **Admins** manage user and job data, and monitor application statistics.

---

## ⚙️ Technology Stack

- **Backend:** Laravel 11.x
- **Frontend:** Blade, Tailwind CSS, Bootstrap
- **Database:** MySQL 
- **Build Tools:** Vite, PostCSS

---

## 🚀 Getting Started

1. Clone this repository.
2. Install PHP and JS dependencies:
   ```bash
   composer install
   npm install
   ```
3. Copy `.env.example` to `.env` and adjust your database configuration.
4. Generate the app key and run migrations:
   ```bash
   php artisan key:generate
   php artisan migrate
   ```
5. Start the development servers:
   ```bash
   php artisan serve
   npm run dev
   ```
6. Access the app at `http://localhost:8000`.

---

## ✍️ Source Code

<a href="https://github.com/jih89/semuakerja" target="_blank" class="btn btn-primary" mb-2>
  <i class="fas fa-fw fa-code"></i>
  Click Here
</a>
