# 📨 Private Messaging App (Next.js + Socket.io + MongoDB)

## 🧾 Project Overview

This project is a **one-to-one private messaging web application** built using **Next.js**, **Socket.io**, and **MongoDB**.  
It allows users to log in with a username, start a private chat with another user, and exchange messages in real-time.  
All messages are stored in a database, so users can view their **previous chat history** when they log back in.

> 📚 This project was developed for **Introduction to Cryptography (ITC)** — **Lab Assignment 3** (Session: July–Dec 2025).

---

## ⚙️ Steps to Install and Run Locally

Follow these steps to set up and run the project on your system:

### 1️⃣ Clone the repository
```bash
git clone https://github.com/<your-username>/private-chat-app.git
cd private-chat-app
```

### 2️⃣ Install dependencies
```bash
npm install
```

### 3️⃣ Setup environment variables  
Create a `.env.local` file in the root directory and add:
```
MONGODB_URI=your_mongodb_connection_string
NEXT_PUBLIC_SOCKET_URL=http://localhost:3000
```

### 4️⃣ Run the development server
```bash
npm run dev
```

The application will start on **http://localhost:3000**

---

## 🖼️ Screenshots of Chat Interface

> *(Add screenshots in this section once you have UI running — e.g. `/public/screenshots` folder)*  

**Example placeholders:**
1️⃣ Login Page  
2️⃣ Chat Interface (Sending & Receiving Messages)  
3️⃣ Chat History Display  

---

## 🏗️ Architecture

```
/project-root
│
├── /pages
│   ├── index.js           → Login Page
│   ├── chat.js            → Chat Page (UI + Socket.io client)
│   └── /api
│       ├── socket.js      → Socket.io server logic
│       └── messages.js    → Fetch and return chat history
│
├── /models
│   └── Message.js         → MongoDB message schema
│
├── /utils
│   └── db.js              → Database connection helper
│
├── /styles
│   └── globals.css        → Tailwind / CSS styling
│
├── package.json
└── README.md
```

**Flow Explanation:**
1. User logs in → redirected to chat page.  
2. Client connects to **Socket.io** → registers username.  
3. When user sends a message:
   - Message is **stored in MongoDB**.
   - Sent to **receiver’s socket** if online.
4. On reload, chat history is fetched via `/api/messages`.

---

## 🧰 Technologies Used

| Category | Technology |
|-----------|-------------|
| Frontend | Next.js, React, Tailwind CSS |
| Backend | Node.js, Socket.io |
| Database | MongoDB (Mongoose ORM) |
| Language | JavaScript |
| Hosting (optional) | Vercel / Render |

---

## 🎓 Learning Outcomes

By completing this project, you will:

1. Understand **full-stack application** development using Next.js.  
2. Learn to implement **real-time communication** using Socket.io.  
3. Gain experience in **storing and retrieving chat data** with MongoDB.  
4. Practice **private message routing** and user session handling.  
5. Be able to **build and deploy** interactive full-stack web apps.

---

## 👨‍💻 Author

**Name:** Meharvan Verma  
**Course:** Introduction to Cryptography (ITC)  
**Assignment:** Lab 3 (July–Dec 2025)  
**GitHub:** [github.com/your-username](https://github.com/your-username)
