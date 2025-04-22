# 💰 Fullstack Expense Tracker (MERN + Docker)

This is a full-stack **Expense Tracker** application built with the **MERN stack** (MongoDB, Express, React, Node.js) and fully dockerized using **Docker & Docker Compose**.

It allows users to track income and expenses through a clean and modern interface, with persistent data stored in MongoDB.

---

## 📦 Tech Stack

- **MongoDB** – NoSQL database
- **Express.js** – Backend API
- **React.js (Vite)** – Frontend UI
- **Node.js** – Runtime environment
- **Docker** – Containerization
- **Docker Compose** – Orchestration

---

## 📁 Folder Structure

```
fullstack-expense-tracker/
├── backend/                    # Express.js API
│   └── Dockerfile
├── frontend/
│   └── expense-tracker/       # Vite + React app
│       └── Dockerfile
├── docker-compose.yml         # Full app orchestration
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/AcheampongStephen/fullstack-expense-tracker.git
cd fullstack-expense-tracker
```

---

### 2. Run with Docker Compose

```bash
docker-compose up --build -d
```

This will:

- Build both frontend and backend Docker images
- Start MongoDB with a persistent volume
- Connect all services on the same custom Docker network (`expense`)
- Expose:
  - Frontend on `http://localhost:5173`
  - Backend API on `http://localhost:8000`
  - MongoDB (internally) as `mongodb://mongodb:27017`

---

## 🧪 Local Testing URLs

- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:8000

**Note**: Ensure API calls from the frontend are pointing to `http://backend:8000` inside the container network (use `.env` or Vite proxy).

---

## 🐳 Docker Overview

### Backend Dockerfile

```Dockerfile
FROM node:18.9.1
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8000
CMD ["npm", "start"]
```

### Frontend Dockerfile (Vite)

```Dockerfile
FROM node:18.9.1
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 5173
CMD ["npm", "run", "dev"]
```

### Docker Compose File

```yaml
version: "3.8"

services:
  frontend:
    build: frontend/expense-tracker
    ports:
      - "5173:5173"
    networks:
      - expense

  backend:
    build: ./backend
    ports:
      - "8000:8000"
    networks:
      - expense
    depends_on:
      - mongodb

  mongodb:
    image: mongo:latest
    ports:
      - "27017:27017"
    volumes:
      - mongo-data:/data/db
    networks:
      - expense

networks:
  expense:
    driver: bridge

volumes:
  mongo-data:
    driver: local
```

---

## 🧹 Clean Up

```bash
docker-compose down
docker volume rm fullstack-expense-tracker_mongo-data
```

---

## 🙋 Author

**Stephen Acheampong**  
🔗 GitHub: [@AcheampongStephen](https://github.com/AcheampongStephen)

---

## 📄 License

Licensed under the [MIT License](LICENSE).

---

## ⭐️ Support

If you find this project helpful, please ⭐️ the repo and share it!
