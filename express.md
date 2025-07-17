Here's a clean, well-structured **`guide.md`** tailored for setting up a new **Express.js** project. It assumes beginner-level familiarity, just like your GPA guide:

---

# 🚀 Express.js Project Guide

> Beginner-friendly setup for building a Node.js + Express backend from scratch.

---

## 🛠 Step 1: Initialize the Project

```bash
mkdir express-app
cd express-app
npm init -y
```

This creates a folder and initializes `package.json`.

---

## 📦 Step 2: Install Dependencies

### Runtime Dependencies:

```bash
npm install express dotenv
```

### Dev Dependencies (for auto-reload):

```bash
npm install --save-dev nodemon
```

---

## 📁 Suggested Folder Structure

```
express-app/
├── controllers/      # Route logic (optional)
│   └── example.js
├── routes/           # Route definitions
│   └── example.js
├── public/           # Static files (e.g., HTML, CSS, JS)
│   └── index.html
├── .env              # Environment variables
├── .gitignore
├── index.js          # Main server file
├── package.json
└── README.md / guide.md
```

---

## 🌍 .env File Example

Create a `.env` file in the root and add your environment variables:

```env
PORT=3000
```

---

## ⚙️ package.json Script

Update your scripts for `nodemon`:

```json
"scripts": {
  "start": "nodemon index.js"
}
```

Also add (if missing):

```json
"type": "module"
```

---

## 🚀 Start the Server

```bash
npm run start
```

---

## 🧠 Basic `index.js` (Main Server File)

```js
// index.js

import express from 'express'
import dotenv from 'dotenv'
import path from 'path'
import { fileURLToPath } from 'url'

dotenv.config()

const app = express()
const port = process.env.PORT || 3000

// ES module compatibility
const __filename = fileURLToPath(import.meta.url)
const __dirname = path.dirname(__filename)

// Middleware
app.use(express.json())
app.use(express.static(path.join(__dirname, 'public')))

// Routes
app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'index.html'))
})

// Start server
app.listen(port, () => {
  console.log(`🚀 Server running at http://localhost:${port}`)
})
```

---

## 🧪 Optional Example Route File

`routes/example.js`

```js
import express from 'express'
const router = express.Router()

router.get('/hello', (req, res) => {
  res.send('Hello from Express Router!')
})

export default router
```

And then use it in `index.js`:

```js
import exampleRoute from './routes/example.js'
app.use('/api', exampleRoute)
```

---

## 📝 .gitignore (Recommended)

```
node_modules/
.env
```

---

## ✅ Summary of Commands

| Task                 | Command               |
| -------------------- | --------------------- |
| Init project         | `npm init -y`         |
| Install dependencies | `npm install express` |
| Install dev tools    | `npm i -D nodemon`    |
| Start dev server     | `npm run start`       |

---

Let me know if you want Alpine.js or PostgreSQL integration added in this base.
