
# 💸 Expense Tracker App (MERN Stack)

A full-featured Expense Tracker built with the **MERN stack** — MongoDB, Express.js, React, and Node.js. This app allows users to track income, expenses, and view insights through dynamic charts.

---

## 🚀 Features

- 👤 User authentication (JWT-based)
- 💾 MongoDB data persistence
- 💸 Track income and expenses with descriptions, categories & dates
- 📊 Visual charts and stats (using Recharts)
- 🧠 Context API for global state management
- 📁 File upload support (profile pictures)
- 📤 Export to Excel (via `xlsx`)
- ⚡ Fast frontend powered by **Vite + React + TailwindCSS**

---

## 🛠️ Tech Stack

| Tech             | Used For             |
|------------------|----------------------|
| MongoDB          | Database             |
| Express.js       | Backend framework    |
| React + Vite     | Frontend framework   |
| Node.js          | Backend runtime      |
| TailwindCSS      | UI styling           |
| Recharts         | Data visualizations  |
| Multer           | File uploads         |
| JWT              | Auth & security      |

---

## 📁 Project Structure

```
expense-tracker-app/
├── backend/
│   ├── controllers/
│   ├── routes/
│   ├── models/
│   ├── middleware/
│   ├── config/
│   ├── uploads/
│   ├── .env
│   └── server.js
└── frontend/
    └── expense-tracker/
        ├── public/
        ├── src/
        │   ├── components/
        │   ├── pages/
        │   ├── hooks/
        │   ├── utils/
        │   └── context/
```

---

## ⚙️ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/AcheampongStephen/fullstack-expense-tracker.git
cd fullstack-expense-tracker
```

### 2. Setup Backend

```bash
cd backend
npm install
cp .env.example .env   # Set your MongoDB URI and JWT_SECRET
npm run dev            # Starts the server using nodemon
```

### 3. Setup Frontend

```bash
cd frontend/expense-tracker
npm install
npm run dev            # Starts Vite development server
```

---

## 🔐 Environment Variables

In `backend/.env`:

```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
PORT=5000
```

---

## 📦 Backend Scripts

| Script     | Purpose                 |
|------------|-------------------------|
| `npm start` | Start server (production) |
| `npm run dev` | Start server with Nodemon |

---

## 🧪 Frontend Scripts

| Script        | Purpose                        |
|---------------|--------------------------------|
| `npm run dev` | Run Vite dev server            |
| `npm run build` | Build for production         |
| `npm run preview` | Preview production build   |
| `npm run lint` | Lint project using ESLint     |

---

## 📷 Screenshots

> _You can include screenshots or GIFs of the dashboard, charts, or login flow here._

---

## 📝 License

This project is licensed under the **ISC License**.

---

## 🙌 Credits

Built by **Stephen Acheampong** – contributions welcome!
