Here is a full **Laravel Setup Guide** in clean `.md` (Markdown) format — covering prerequisites, installation, and running your first Laravel app:

---

````md
# 🚀 Laravel Project Setup Guide

This guide will walk you through setting up a **Laravel project** from scratch using Composer and Laravel CLI.

---

## ✅ Prerequisites

| Tool             | Purpose                        | Recommended Version |
|------------------|--------------------------------|---------------------|
| **PHP**          | Laravel runtime                | >= 8.1              |
| **Composer**     | Dependency manager             | Latest              |
| **Node.js & NPM**| Frontend tooling (for Vite)    | Node 18+            |
| **MySQL / SQLite** | Database (optional)          | Any                 |
| **Laravel CLI**  | (Optional) Laravel installer   | Latest              |
| **VS Code / Editor** | Code editing               | Any                 |

---

## 🧰 Installation Steps

### 1. Install PHP

- [Windows PHP Setup Guide](https://windows.php.net/download)
- Or install via XAMPP / Laragon (recommended for local dev)

### 2. Install Composer

- Download: [https://getcomposer.org](https://getcomposer.org)
- Check:
  ```bash
  composer -v
````

### 3. Create New Laravel Project

#### Option A: Using Laravel Installer

```bash
composer global require laravel/installer
laravel new blog-app
cd blog-app
```

#### Option B: Via Composer Directly

```bash
composer create-project laravel/laravel blog-app
cd blog-app
```

---

## 🛠️ Project Structure

```
blog-app/
├── app/               # Application logic
├── bootstrap/         # App bootstrap files
├── config/            # Configuration files
├── database/          # Migrations, seeders, factories
├── public/            # Public-facing files (index.php)
├── resources/         # Views, CSS, JS (Vite)
├── routes/            # All route files (web.php, api.php)
├── storage/           # Logs, cache, etc.
└── tests/             # Unit and Feature tests
```

---

## 🔄 Run Laravel Project

```bash
php artisan serve
```

> Visit: `http://127.0.0.1:8000`

---

## 🧪 Sample Route

Edit `routes/web.php`:

```php
Route::get('/', function () {
    return view('welcome');
});
```

---

## 🗃️ Environment Setup

Edit `.env` file:

```
APP_NAME=Laravel
APP_URL=http://localhost:8000
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```

Then run:

```bash
php artisan config:cache
```

---

## 📦 Frontend (Optional)

Laravel uses **Vite** for frontend assets.

```bash
npm install
npm run dev
```

To build production assets:

```bash
npm run build
```

---

## ⚙️ Useful Artisan Commands

| Command                       | Purpose                       |
| ----------------------------- | ----------------------------- |
| `php artisan serve`           | Run local dev server          |
| `php artisan make:controller` | Create a controller           |
| `php artisan make:model`      | Create a model                |
| `php artisan migrate`         | Run database migrations       |
| `php artisan route:list`      | Show all registered routes    |
| `php artisan tinker`          | Interactive shell for testing |

---

## 📚 Resources

* [Laravel Docs](https://laravel.com/docs)
* [Laracasts](https://laracasts.com/)
* [Laravel News](https://laravel-news.com/)
* [Awesome Laravel GitHub](https://github.com/chiraggude/awesome-laravel)

---

**You're all set! 🎉 Start building awesome web apps with Laravel.**

```

---

Let me know if you want a separate `.md` for **Laravel + Inertia**, **Laravel + Vue/React**, **REST API in Laravel**, or **Laravel authentication** setup!
```
