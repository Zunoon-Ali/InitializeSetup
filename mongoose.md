Here’s your complete **MongoDB + Mongoose setup guide (`guide.md`)** for a Node.js and Express project.

---

# 📘 Node.js + Express + MongoDB with Mongoose Setup Guide

> This guide walks you through connecting MongoDB with a Node + Express app using **Mongoose** (ODM for MongoDB).

---

## 📦 Step 1: Initialize Project

```bash
mkdir mongoose-app
cd mongoose-app
npm init -y
```

---

## 📥 Step 2: Install Required Packages

```bash
npm install express mongoose dotenv
npm install --save-dev nodemon
```

---

## 🧾 package.json Configuration

Edit `package.json` to add type and script:

```json
"type": "module",
"scripts": {
  "start": "nodemon index.js"
}
```

---

## 📁 Suggested Folder Structure

```
mongoose-app/
├── config/
│   └── db.js              # MongoDB connection using Mongoose
├── models/
│   └── Task.js            # Task schema/model
├── routes/
│   └── taskRoutes.js      # Task API routes
├── .env
├── .gitignore
├── index.js               # Entry point
└── package.json
```

---

## 🔐 .env File

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/taskflow
```

---

## 🔌 MongoDB Connection – `config/db.js`

```js
import mongoose from 'mongoose'
import dotenv from 'dotenv'

dotenv.config()

export const connectDB = async () => {
  try {
    await mongoose.connect(process.env.MONGO_URI, {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    })
    console.log('✅ MongoDB connected with Mongoose')
  } catch (err) {
    console.error('❌ MongoDB connection error:', err)
    process.exit(1)
  }
}
```

---

## 🧠 Mongoose Model – `models/Task.js`

```js
import mongoose from 'mongoose'

const taskSchema = new mongoose.Schema({
  title: {
    type: String,
    required: true,
  },
  completed: {
    type: Boolean,
    default: false,
  },
}, { timestamps: true })

const Task = mongoose.model('Task', taskSchema)

export default Task
```

---

## 🧪 Routes – `routes/taskRoutes.js`

```js
import express from 'express'
import Task from '../models/Task.js'

const router = express.Router()

// Get all tasks
router.get('/', async (req, res) => {
  const tasks = await Task.find()
  res.json(tasks)
})

// Create a task
router.post('/', async (req, res) => {
  const task = new Task(req.body)
  const saved = await task.save()
  res.status(201).json(saved)
})

// Delete a task
router.delete('/:id', async (req, res) => {
  await Task.findByIdAndDelete(req.params.id)
  res.status(204).send()
})

export default router
```

---

## 🚀 Main App – `index.js`

```js
import express from 'express'
import dotenv from 'dotenv'
import { connectDB } from './config/db.js'
import taskRoutes from './routes/taskRoutes.js'

dotenv.config()
const app = express()

app.use(express.json())

// Routes
app.use('/api/tasks', taskRoutes)

// DB & Server
const PORT = process.env.PORT || 3000
connectDB().then(() => {
  app.listen(PORT, () => {
    console.log(`🚀 Server running at http://localhost:${PORT}`)
  })
})
```

---

## 🧾 .gitignore

```
node_modules/
.env
```

---

## 🔁 Sample Test with Thunder Client/Postman

### ➕ Create Task

```http
POST /api/tasks
Content-Type: application/json

{
  "title": "Learn Mongoose"
}
```

### 📃 Get Tasks

```http
GET /api/tasks
```

### ❌ Delete Task

```http
DELETE /api/tasks/<id>
```

---

## ✅ Quick Command Recap

| Task                | Command                               |
| ------------------- | ------------------------------------- |
| Init Project        | `npm init -y`                         |
| Install deps        | `npm install express mongoose dotenv` |
| Dev start           | `npm start`                           |
| Start MongoDB local | `mongod`                              |

---

Let me know if you want:

* Full CRUD for Tasks
* Validation examples
* MongoDB Atlas setup
* Swagger docs or Postman collection export

Just say the word 👇
