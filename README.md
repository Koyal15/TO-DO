# MERN To-Do List Application

A full-stack, authenticated To-Do List app built with the MERN stack.

![MERN](https://img.shields.io/badge/MERN-Stack-blue)
![React](https://img.shields.io/badge/React-v18.2.0-blueviolet)
![Node.js](https://img.shields.io/badge/Node.js-18.x-brightgreen)
![Express](https://img.shields.io/badge/Express.js-4.x-yellow)
![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-success)
![Vite](https://img.shields.io/badge/Vite-Dev%20Server-cyan)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 📌 Overview

A full‑stack, authenticated To‑Do List application built with the MERN stack.  
Users can register/login, create and manage personal tasks, toggle completion, edit and delete tasks. The app uses JWT for authentication, bcrypt for secure passwords, and a responsive, modern React (Vite) frontend.

---

## ✨ Highlights & UX

- Secure user registration and login (bcrypt + JWT)
- Per-user tasks (each task belongs to a user)
- CRUD operations for tasks (protected API)
- Visual, responsive UI (Vite + React)
- Live updates with React Hooks (useState, useEffect)
- Task completion UX:
  - Each task shows a circular toggle button at the left.
  - Clicking it toggles completion and displays ✅ for completed tasks.
  - Completed tasks show line-through text, a faded container, and hide the Edit option (only Delete remains).
  - UI updates dynamically without full page refresh.

---

## 🧰 Tech Stack

- Frontend: React, Vite, React Router, axios, CSS Modules / Tailwind (optional)
- Backend: Node.js, Express.js, Mongoose (MongoDB)
- Auth: JWT, bcrypt
- Dev: nodemon (backend), Vite (frontend)

---

## 📁 Suggested Folder Structure

```
e:/TO-DO/
├── backend/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   ├── index.js
│   └── .env
├── frontend/
│   ├── index.html
│   ├── package.json
│   └── src/
│       ├── main.jsx
│       ├── App.jsx
│       ├── pages/
│       └── components/
└── README.md
```

---

## ⚙️ Getting Started

Prerequisites:
- Node.js v18+
- npm
- MongoDB URI (Atlas or local)

1. Clone repository
```bash
git clone <your-repo-url>
cd e:/TO-DO
```

2. Backend setup
```bash
cd backend
npm install
# create .env with values below
npm run dev        # starts nodemon -> runs index.js on default port 5000
```

3. Frontend setup
```bash
cd ../frontend
npm install
npm run dev        # starts Vite dev server (default http://localhost:5173)
```

Open the Vite URL in your browser and use the app.

---

## Environment (.env) — Backend

Create `backend/.env` with:

```
PORT=5000
MONGO_URI=mongodb+srv://<user>:<pass>@cluster0.mongodb.net/todos?retryWrites=true&w=majority
JWT_SECRET=your_jwt_secret_here
```

Important: keep .env out of version control.

---

## API Reference (backend)

All task routes are protected and require Authorization: Bearer <token>.

Auth:
- POST /api/auth/register — register { username, email, password }
- POST /api/auth/login — login { email, password } → returns JWT

Tasks:
- POST /api/tasks — create task { content, completed? } (associated with authenticated user)
- GET /api/tasks — list tasks for authenticated user
- PUT /api/tasks/:id — update task (content, completed)
- DELETE /api/tasks/:id — delete task

Responses follow JSON format and include proper HTTP status codes.

---

## Frontend Notes

- JWT is stored in localStorage after login and included in axios Authorization header for protected requests.
- Protected routes enforce authentication (redirect to Login when no valid token).
- Components use React Hooks (useState/useEffect/useContext or custom hooks for auth).
- UI behavior for completion:
  - Circle toggle (left) — toggles completed boolean via PUT /api/tasks/:id
  - When completed: show ✅ inside the circle, apply line-through to text, fade the task container, hide Edit button (only Delete visible).

---

## Scripts

Backend (in backend/):
- npm run dev — start dev server with nodemon
- npm start — start production server (node index.js)

Frontend (in frontend/):
- npm run dev — start Vite dev server
- npm run build — build for production
- npm run preview — preview production build

You can use concurrently or a custom script to run both servers during development.

---

## Testing & Debugging

- Verify backend connection: ensure MONGO_URI is valid; server logs "Connected to MongoDB".
- Use Postman or curl to test auth and task endpoints.
- Frontend: open browser console / network tab to inspect API requests and token header.
- Common error: "Invalid scheme" indicates an incorrect MONGO_URI — ensure it starts with mongodb:// or mongodb+srv://

---

## Deployment

- Build frontend (npm run build) and serve statically (e.g., Nginx, Netlify, Vercel). Or serve frontend build from Express static folder.
- Host backend on Heroku / Render / Railway; use environment variables for MONGO_URI and JWT_SECRET.
- Use a managed MongoDB (Atlas) for production.

---

## Contributing

- Make frequent commits with clear messages.
- Open issues or PRs for improvements or bug fixes.
- Ensure sensitive data is never committed.

---

## License

MIT

---

If you want, I can:
- Add a ready-to-commit `.env.example`
- Generate Postman collection for the API
- Add a "run both" script using `concurrently`
- Implement optimistic UI for toggle-completion

```// filepath: e:\TO-DO\README.md
...existing code...
# MERN To-Do List Application

![MERN](https://img.shields.io/badge/MERN-Stack-blue)
![React](https://img.shields.io/badge/React-v18.2.0-blueviolet)
![Node.js](https://img.shields.io/badge/Node.js-18.x-brightgreen)
![Express](https://img.shields.io/badge/Express.js-4.x-yellow)
![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-success)
![Vite](https://img.shields.io/badge/Vite-Dev%20Server-cyan)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 📌 Overview

A full‑stack, authenticated To‑Do List application built with the MERN stack.  
Users can register/login, create and manage personal tasks, toggle completion, edit and delete tasks. The app uses JWT for authentication, bcrypt for secure passwords, and a responsive, modern React (Vite) frontend.

---

## ✨ Highlights & UX

- Secure user registration and login (bcrypt + JWT)
- Per-user tasks (each task belongs to a user)
- CRUD operations for tasks (protected API)
- Visual, responsive UI (Vite + React)
- Live updates with React Hooks (useState, useEffect)
- Task completion UX:
  - Each task shows a circular toggle button at the left.
  - Clicking it toggles completion and displays ✅ for completed tasks.
  - Completed tasks show line-through text, a faded container, and hide the Edit option (only Delete remains).
  - UI updates dynamically without full page refresh.

---

## 🧰 Tech Stack

- Frontend: React, Vite, React Router, axios, CSS Modules / Tailwind (optional)
- Backend: Node.js, Express.js, Mongoose (MongoDB)
- Auth: JWT, bcrypt
- Dev: nodemon (backend), Vite (frontend)

---

## 📁 Suggested Folder Structure

```
e:/TO-DO/
├── backend/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   ├── index.js
│   └── .env
├── frontend/
│   ├── index.html
│   ├── package.json
│   └── src/
│       ├── main.jsx
│       ├── App.jsx
│       ├── pages/
│       └── components/
└── README.md
```

---

## ⚙️ Getting Started

Prerequisites:
- Node.js v18+
- npm
- MongoDB URI (Atlas or local)

1. Clone repository
```bash
git clone <your-repo-url>
cd e:/TO-DO
```

2. Backend setup
```bash
cd backend
npm install
# create .env with values below
npm run dev        # starts nodemon -> runs index.js on default port 5000
```

3. Frontend setup
```bash
cd ../frontend
npm install
npm run dev        # starts Vite dev server (default http://localhost:5173)
```

Open the Vite URL in your browser and use the app.

---

## Environment (.env) — Backend

Create `backend/.env` with:

```
PORT=5000
MONGO_URI=mongodb+srv://<user>:<pass>@cluster0.mongodb.net/todos?retryWrites=true&w=majority
JWT_SECRET=your_jwt_secret_here
```

Important: keep .env out of version control.

---

## API Reference (backend)

All task routes are protected and require Authorization: Bearer <token>.

Auth:
- POST /api/auth/register — register { username, email, password }
- POST /api/auth/login — login { email, password } → returns JWT

Tasks:
- POST /api/tasks — create task { content, completed? } (associated with authenticated user)
- GET /api/tasks — list tasks for authenticated user
- PUT /api/tasks/:id — update task (content, completed)
- DELETE /api/tasks/:id — delete task

Responses follow JSON format and include proper HTTP status codes.

---

## Frontend Notes

- JWT is stored in localStorage after login and included in axios Authorization header for protected requests.
- Protected routes enforce authentication (redirect to Login when no valid token).
- Components use React Hooks (useState/useEffect/useContext or custom hooks for auth).
- UI behavior for completion:
  - Circle toggle (left) — toggles completed boolean via PUT /api/tasks/:id
  - When completed: show ✅ inside the circle, apply line-through to text, fade the task container, hide Edit button (only Delete visible).

---

## Scripts

Backend (in backend/):
- npm run dev — start dev server with nodemon
- npm start — start production server (node index.js)

Frontend (in frontend/):
- npm run dev — start Vite dev server
- npm run build — build for production
- npm run preview — preview production build

You can use concurrently or a custom script to run both servers during development.

---

## Testing & Debugging

- Verify backend connection: ensure MONGO_URI is valid; server logs "Connected to MongoDB".
- Use Postman or curl to test auth and task endpoints.
- Frontend: open browser console / network tab to inspect API requests and token header.
- Common error: "Invalid scheme" indicates an incorrect MONGO_URI — ensure it starts with mongodb:// or mongodb+srv://

---

## Deployment

- Build frontend (npm run build) and serve statically (e.g., Nginx, Netlify, Vercel). Or serve frontend build from Express static folder.
- Host backend on Heroku / Render / Railway; use environment variables for MONGO_URI and JWT_SECRET.
- Use a managed MongoDB (Atlas) for production.

---

## Contributing

- Make frequent commits with clear messages.
- Open issues or PRs for improvements or bug fixes.
- Ensure sensitive data is never committed.

---
