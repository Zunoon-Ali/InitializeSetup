Here is a complete `mysql.md` Markdown file for setting up **MySQL**, including prerequisites, installation instructions, CLI usage, GUI tools, and Node.js integration:

---

````md
# 🐬 MySQL Setup & Usage Guide

MySQL is one of the most widely used open-source relational database management systems.

---

## ✅ Prerequisites

| Requirement      | Details                             |
|------------------|-------------------------------------|
| OS               | Windows, macOS, Linux               |
| Admin Privileges | Required for installing services    |
| Tools (optional) | MySQL Workbench, phpMyAdmin         |

---

## 📥 Installation

### 🪟 Windows

1. Download from: [https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/)
2. Use **MySQL Installer** to install:
   - MySQL Server
   - MySQL Workbench
   - MySQL Shell
3. Set a root password during setup.

### 🍎 macOS

```bash
brew install mysql
brew services start mysql
````

### 🐧 Ubuntu/Debian

```bash
sudo apt update
sudo apt install mysql-server
sudo mysql_secure_installation
```

---

## ▶️ Start & Stop MySQL

| OS    | Start Command               | Stop Command                     |
| ----- | --------------------------- | -------------------------------- |
| Linux | `sudo service mysql start`  | `sudo service mysql stop`        |
| macOS | `brew services start mysql` | `brew services stop mysql`       |
| Win   | Starts via Windows Services | Use Task Manager or Services app |

---

## 🔐 Accessing MySQL CLI

```bash
mysql -u root -p
```

* Enter the root password when prompted.

---

## 🧪 Basic SQL Commands

```sql
-- Create a new database
CREATE DATABASE mydb;

-- Create a new user
CREATE USER 'myuser'@'localhost' IDENTIFIED BY 'mypassword';

-- Grant privileges to the user
GRANT ALL PRIVILEGES ON mydb.* TO 'myuser'@'localhost';

-- Use a database
USE mydb;

-- Show tables
SHOW TABLES;

-- Exit
EXIT;
```

---

## 🧩 GUI Tools

| Tool            | Description             | Link                                                                 |
| --------------- | ----------------------- | -------------------------------------------------------------------- |
| MySQL Workbench | Official GUI tool       | [https://dev.mysql.com/workbench/](https://dev.mysql.com/workbench/) |
| DBeaver         | Universal DB GUI client | [https://dbeaver.io/](https://dbeaver.io/)                           |
| phpMyAdmin      | Web-based MySQL GUI     | [https://www.phpmyadmin.net/](https://www.phpmyadmin.net/)           |

---

## 🔗 Connect from Node.js

### Install MySQL package:

```bash
npm install mysql2
```

### Example Code:

```js
const mysql = require('mysql2');

const connection = mysql.createConnection({
  host: 'localhost',
  user: 'myuser',
  password: 'mypassword',
  database: 'mydb'
});

connection.connect((err) => {
  if (err) throw err;
  console.log('Connected to MySQL!');
});
```

---

## 🔐 Reset Root Password (Linux)

```bash
sudo mysql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'newpassword';
FLUSH PRIVILEGES;
EXIT;
```

---

## 📦 Backup & Restore

```bash
-- Backup a database
mysqldump -u root -p mydb > backup.sql

-- Restore a database
mysql -u root -p mydb < backup.sql
```

---

## 📚 Resources

* 🔗 [Official Site](https://www.mysql.com/)
* 📘 [MySQL Documentation](https://dev.mysql.com/doc/)
* 🎓 [SQL Tutorial (w3schools)](https://www.w3schools.com/sql/)

---

✅ You’re all set to build projects using MySQL as your backend database.

```

---

Let me know if you'd like a `.md` for **MySQL + Express**, **MySQL + Sequelize**, or **MySQL + PHP (PDO/MySQLi)** integration.
```
