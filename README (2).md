# 📨 Private Messaging App (Next.js + Socket.io + MongoDB)

## 📘 Overview

This project is a **one-to-one private messaging web application** built using **Next.js**, **Socket.io**, and **MongoDB**.  
It allows users to log in with a username, chat privately with other users in real-time, and retrieve chat history when reconnected.

This project was developed as part of the **"Introduction to Cryptography (ITC)"** course (Session: July–Dec 2025), **Lab Assignment 3**.

---

## 🎯 Objectives

- Implement **real-time private messaging** using WebSockets.
- Persist messages in **MongoDB** for chat history and offline delivery.
- Build a **Next.js full-stack app** with both frontend and backend logic.
- Understand **user sessions** and **message routing** for private communication.

---

## 🧠 Learning Outcomes

By completing this project, you will learn how to:

1. Develop a **full-stack app** using Next.js (pages + API routes).
2. Implement **Socket.io** for real-time message transfer.
3. Store and retrieve messages from a **MongoDB** database.
4. Manage user **connections and message delivery** privately.
5. Display chat history and maintain **stateful sessions**.

---

## ⚙️ Tech Stack

| Layer | Technology |
|-------|-------------|
| Frontend | Next.js, React, Tailwind CSS |
| Backend | Node.js, Socket.io |
| Database | MongoDB (Mongoose) |
| Deployment | Vercel / Render (optional) |

---

## 🧩 Project Architecture

```
/project-root
│
├── /pages
│   ├── index.js           → Login Page
│   ├── chat.js            → Chat Interface
│   └── /api
│       ├── messages.js    → Fetch chat history
│       └── socket.js      → WebSocket backend setup
│
├── /models
│   └── Message.js         → MongoDB schema for messages
│
├── /utils
│   └── db.js              → MongoDB connection logic
│
├── /styles
│   └── globals.css        → Optional styling
│
├── package.json
└── README.md
```

---

## 🪄 Features

- 🔐 Login with username  
- 💬 One-to-one real-time private chat  
- 🕒 Message persistence (MongoDB)  
- 📜 Chat history on login  
- 🟢 Online/Offline detection *(optional)*  
- ✏️ Message editing/deleting *(optional)*  

---

## 🚀 Setup & Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/<your-username>/private-chat-app.git
cd private-chat-app
```

### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Configure environment variables

Create a `.env.local` file in the project root:

```
MONGODB_URI=your_mongodb_connection_string
NEXT_PUBLIC_SOCKET_URL=http://localhost:3000
```

### 4️⃣ Run the development server

```bash
npm run dev
```

The app will run on **http://localhost:3000**

---

## 🧱 How It Works

### 🔹 User Flow
1. User enters a **username** on the login page.  
2. Gets redirected to **chat page**.  
3. Enters recipient’s username and sends a message.  
4. The message is:
   - Stored in MongoDB.
   - Sent to recipient if online.
   - Displayed in sender’s chat window.

### 🔹 Socket.io Events
```js
// Register new user
socket.emit("register_user", username);

// Send message
socket.emit("send_message", { sender, receiver, text });

// Receive message
socket.on("receive_message", ({ sender, text }) => {
  // Display message in chat window
});
```

---

## 🗄️ MongoDB Schema Example

```js
const MessageSchema = new mongoose.Schema({
  sender: String,
  receiver: String,
  text: String,
  timestamp: { type: Date, default: Date.now }
});
```

---

## 🖼️ Screenshots

*(Add your own screenshots here)*  
1️⃣ Login Page  
2️⃣ Chat Interface  
3️⃣ Message History  

---

## 💡 Optional Enhancements

- Show “User is typing…” notifications.  
- Display online/offline status.  
- Edit or delete messages.  
- Add message encryption (for cryptography concept).

---

## 📚 Course Details

- **Course:** Introduction to Cryptography (ITC)  
- **Assignment:** Lab Assignment 3  
- **Session:** July – December 2025  
- **Deadline:** 02 November 2025  

---

## 🧑‍💻 Author

**Name:** Meharvan Verma  
**Course:** B.Tech IT (Cryptography Lab)  
**GitHub:** [github.com/your-username](https://github.com/your-username)
