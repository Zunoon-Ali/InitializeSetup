Here’s a complete and clean **Markdown (.md) file for basic PHP project setup**, focused **only on PHP** (no MySQL, no frameworks):

---

```md
# 🐘 PHP Project Setup Guide (Basic)

This guide will help you set up and run a **pure PHP project** without any framework or database.

---

## ✅ Prerequisites

Make sure you have the following installed:

| Tool     | Purpose                         | Recommended Version |
|----------|----------------------------------|---------------------|
| **PHP**  | Core language engine             | 8.1 or newer        |
| **Editor** | Code editor (VS Code, Sublime) | Latest              |
| **Web Server** | Apache or PHP built-in     | Any                 |

---

## 🖥️ Installing PHP

### 🔹 Windows (Option 1: XAMPP)

- Download XAMPP: [https://www.apachefriends.org](https://www.apachefriends.org)
- Start **Apache** server from XAMPP Control Panel.
- Place your project in:
```

C:\xampp\htdocs\my-php-project\\

```
- Access in browser:  
```

[http://localhost/my-php-project/](http://localhost/my-php-project/)

````

### 🔹 Windows (Option 2: PHP Standalone + VS Code)

1. Download PHP: [https://windows.php.net/download](https://windows.php.net/download)
2. Extract and add to PATH
3. Run a dev server:
 ```bash
 php -S localhost:8000
````

### 🔹 macOS

```bash
brew install php
php -v
php -S localhost:8000
```

### 🔹 Linux (Debian/Ubuntu)

```bash
sudo apt update
sudo apt install php
php -v
php -S localhost:8000
```

---

## 📁 Project Structure

```
my-php-project/
├── index.php
├── about.php
├── includes/
│   └── header.php
└── functions/
    └── helpers.php
```

---

## 🧪 Basic Example

### `index.php`

```php
<?php
include 'includes/header.php';

echo "<h1>Welcome to My PHP Project</h1>";

?>
```

### `includes/header.php`

```php
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>PHP Project</title>
</head>
<body>
```

---

## ▶️ Run the Project

If using built-in PHP server:

```bash
php -S localhost:8000
```

Then open in browser:
**[http://localhost:8000](http://localhost:8000)**

---

## ✅ Good Practices

* Use `.php` file extension
* Organize code in folders (`includes/`, `functions/`)
* Use `require` / `include` for reusable files
* Comment your code using `//` or `/* */`

---

## 🧠 Learn More

* [PHP Manual](https://www.php.net/manual/en/)
* [w3schools PHP](https://www.w3schools.com/php/)
* [PHP The Right Way](https://phptherightway.com/)

---

**Happy Coding! 💻**

```

---

Let me know if you want a `.md` setup guide for **PHP + MySQL**, **Laravel**, or **PHP + Bootstrap** next.
```
