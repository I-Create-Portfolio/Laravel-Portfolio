# 🎯 Laravel Portfolio App with Admin Panel

A fully dynamic **portfolio website** built using **Laravel**, featuring an **admin dashboard** to manage all portfolio content like blogs, profile, skills, and user support chat — powered by **Laravel Reverb** and **Pusher**.

---

## 📹 Live Preview

▶️ **[Click here to watch demo video](https://drive.google.com/file/d/1NcGJWu6A8Mg5XEtCDLsElu8BYIK_-aG0/view?usp=sharing)**  
*(hosted on Google Drive)*

---

## 🧰 Tech Stack

| Technology     | Description                          |
|----------------|--------------------------------------|
| ![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white) | PHP Web Framework |
| ![Bootstrap](https://img.shields.io/badge/Bootstrap-563d7c?style=for-the-badge&logo=bootstrap&logoColor=white) | UI Library |
| ![HTML5](https://img.shields.io/badge/HTML5-e34c26?style=for-the-badge&logo=html5&logoColor=white) | Markup |
| ![CSS3](https://img.shields.io/badge/CSS3-264de4?style=for-the-badge&logo=css3&logoColor=white) | Styling |
| ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black) | Client-side Interactions |
| ![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white) | Database |
| ![Pusher](https://img.shields.io/badge/Pusher-0A0A0A?style=for-the-badge&logo=pusher&logoColor=white) | Real-time Messaging |
| ![Laravel Reverb](https://img.shields.io/badge/Reverb-WebSocket-red?style=for-the-badge&logo=laravel) | Laravel WebSocket Server |

---

## 📦 Key Features

- ✅ Fully **responsive** portfolio website
- 🛠️ **Dynamic admin panel** for full content management
- ✍️ Manage:
  - Blogs
  - About section
  - Skills
  - Contact details
  - Logo and favicon
  - Profile images
- 🔐 **Login & Register** system for admin access
- 📩 **User support chat** powered by **Laravel Reverb** and **Pusher**
- 📁 SEO-friendly and modular content structure

---

## 🚀 Installation Steps

### 🔧 Prerequisites

Ensure you have:

- PHP >= 8.1
- Composer
- Node.js & NPM
- MySQL
- Pusher account (for chat)

---

### 🧑‍💻 Setup Instructions

```bash
# 1. Clone the repo
git clone https://github.com/your-username/laravel-portfolio.git
cd laravel-portfolio

# 2. Install PHP dependencies
composer install

# 3. Install frontend dependencies
npm install

# 4. Setup environment
cp .env.example .env
php artisan key:generate

# 5. Configure .env file
# - Set database credentials
# - Add Pusher credentials
# - Set BROADCAST_DRIVER=pusher

# 6. Migrate the database
php artisan migrate

# 7. Build frontend assets
npm run dev

# 8. Run queue and websocket server
php artisan queue:work
php artisan reverb:start

# 9. Launch the application
php artisan serve
