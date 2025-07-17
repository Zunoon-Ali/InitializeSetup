Here’s a **complete and clean `guide.md`** file for setting up **MongoDB in a Node + Express.js project** (without Mongoose). This will use the **native MongoDB Node.js driver**.

---

# 📘 Node.js + Express + MongoDB (Native Driver) Setup Guide

> This guide helps you integrate **MongoDB** with **Node.js + Express** using the **native MongoDB driver** (not Mongoose).

---

## 📦 Step 1: Project Initialization

### 1. Create and Initialize Project

```bash
mkdir mongo-native-app
cd mongo-native-app
npm init -y
```

### 2. Install Dependencies

```bash
npm install express mongodb dotenv
npm install --save-dev nodemon
```

---

## 📁 Suggested Folder Structure

```
mongo-native-app/
├── db/                 # DB connection
│   └── connect.js
├── routes/             # Express routes
│   └── taskRoutes.js
├── .env
├── .gitignore
├── index.js            # Main entry point
├── guide.md            # This guide
└── package.json
```

---

## 🔧 package.json Scripts

Add this inside `package.json`:

```json
"type": "module",
"scripts": {
  "start": "nodemon index.js"
}
```

---

## 🔐 .env File

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/myapp
```

> Replace URI with your **MongoDB Atlas** connection string if needed.

---

## 🧠 DB Connection – `db/connect.js`

```js
import { MongoClient } from 'mongodb'
import dotenv from 'dotenv'

dotenv.config()

const client = new MongoClient(process.env.MONGO_URI)

export async function connectDB() {
  try {
    await client.connect()
    console.log('✅ MongoDB connected')
    return client.db() // returns the default database from URI
  } catch (err) {
    console.error('❌ Failed to connect MongoDB:', err)
    process.exit(1)
  }
}
```

---

## 🚀 index.js – Entry File

```js
import express from 'express'
import dotenv from 'dotenv'
import { connectDB } from './db/connect.js'
import taskRoutes from './routes/taskRoutes.js'

dotenv.config()

const app = express()
const port = process.env.PORT || 3000

app.use(express.json())

// Connect DB and start server
connectDB().then((db) => {
  app.locals.db = db // pass db to request via app.locals
  app.use('/api/tasks', taskRoutes)

  app.listen(port, () => {
    console.log(`🚀 Server running at http://localhost:${port}`)
  })
})
```

---

## 🔗 routes/taskRoutes.js

```js
import express from 'express'
const router = express.Router()

// GET all tasks
router.get('/', async (req, res) => {
  const db = req.app.locals.db
  const tasks = await db.collection('tasks').find().toArray()
  res.json(tasks)
})

// POST a task
router.post('/', async (req, res) => {
  const db = req.app.locals.db
  const result = await db.collection('tasks').insertOne(req.body)
  res.status(201).json(result)
})

export default router
```

---

## 🧪 Test API (Using Thunder Client / Postman)

### ➕ Add a Task

```http
POST http://localhost:3000/api/tasks
Content-Type: application/json

{
  "title": "Learn MongoDB Native Driver"
}
```

### 📃 Get Tasks

```http
GET http://localhost:3000/api/tasks
```

---

## 🧾 .gitignore

```bash
node_modules/
.env
```

---

## 📌 MongoDB Notes

* Make sure MongoDB is running (`mongod`) or Atlas is connected.
* `db.collection('name')` directly accesses any collection.
* No schema enforcement; it's flexible.

---

## ✅ Recap Commands

| Task                   | Command                              |
| ---------------------- | ------------------------------------ |
| Initialize project     | `npm init -y`                        |
| Install dependencies   | `npm install express mongodb dotenv` |
| Dev start with nodemon | `npm start`                          |
| Start Mongo locally    | `mongod`                             |

---

Let me know if you'd like a **version using Mongoose**, **CRUD operations for users**, or **RESTful API docs generation**.
