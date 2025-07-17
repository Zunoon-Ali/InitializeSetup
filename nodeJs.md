Here's a complete **Node.js Project Setup + Prerequisites Guide** in Markdown format for you:

---

# 📘 Node.js Project Setup Guide

> A complete step-by-step guide to set up a **Node.js** backend project with prerequisites, folder structure, and basic configuration.

---

## ⚙️ Prerequisites

Before starting, ensure the following are installed:

| Tool        | Version         | Website                                                        |
| ----------- | --------------- | -------------------------------------------------------------- |
| **Node.js** | ≥ 18.x.x        | [https://nodejs.org](https://nodejs.org)                       |
| **npm**     | ≥ 9.x.x         | Bundled with Node.js                                           |
| **VS Code** | Recommended     | [https://code.visualstudio.com](https://code.visualstudio.com) |
| **Postman** | For API testing | [https://postman.com](https://postman.com)                     |
| **MongoDB** | (Optional)      | [https://mongodb.com](https://mongodb.com)                     |

To check versions:

```bash
node -v
npm -v
```

---

## 📁 Project Initialization

```bash
mkdir my-node-app
cd my-node-app
npm init -y
```

---

## 📦 Common Dependencies to Install

```bash
# Main dependencies
npm install express dotenv cors

# Dev tools
npm install --save-dev nodemon
```

---

## 🔧 package.json Configuration

Update your `package.json`:

```json
"type": "module",
"scripts": {
  "start": "node index.js",
  "dev": "nodemon index.js"
}
```

---

## 🌿 Suggested Folder Structure

```
my-node-app/
├── config/             # Database or server config
├── controllers/        # Logic/handlers for routes
├── middleware/         # Middleware functions
├── models/             # Mongoose models or DB schemas
├── routes/             # API route definitions
├── .env                # Environment variables
├── .gitignore
├── index.js            # Entry point of app
├── package.json
```

---

## 🧪 Sample Hello World – `index.js`

```js
import express from 'express'
import dotenv from 'dotenv'

dotenv.config()

const app = express()
const PORT = process.env.PORT || 3000

app.get('/', (req, res) => {
  res.send('Hello from Node.js backend!')
})

app.listen(PORT, () => {
  console.log(`🚀 Server running on http://localhost:${PORT}`)
})
```

---

## 🔐 .env File

```env
PORT=3000
```

---

## 🧾 .gitignore

```gitignore
node_modules/
.env
```

---

## 🧰 Useful Dev Commands

| Task                   | Command             |
| ---------------------- | ------------------- |
| Start server (prod)    | `npm start`         |
| Start with live reload | `npm run dev`       |
| Install a package      | `npm install xyz`   |
| Uninstall a package    | `npm uninstall xyz` |

---

## ✅ Optional Tools to Add

* `morgan` – HTTP request logging
  `npm install morgan`

* `helmet` – Set security headers
  `npm install helmet`

* `express-validator` – Input validation
  `npm install express-validator`

* `mongoose` – MongoDB ODM (if needed)
  `npm install mongoose`

---

Let me know if you want:

* CRUD API setup
* Swagger documentation
* Authentication boilerplate
* MongoDB connection
* Docker setup

I’ll generate those next.
