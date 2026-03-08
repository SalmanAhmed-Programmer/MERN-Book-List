# MERN-BOOK-LIST
# 📚 MERN Book Management Application

A full-stack web application built with the **MERN stack** (MongoDB, Express.js, React, Node.js) that allows users to manage a collection of books. The app supports full **CRUD operations** — Create, Read, Update, and Delete — with a clean, responsive UI powered by React and Tailwind CSS.

---

## 🚀 Features

- View all books in **Table** or **Card** layout
- **Add** a new book with title, author, and publish year
- **View** detailed information for a single book
- **Edit** existing book records
- **Delete** books with confirmation
- Toast notifications for user feedback (via Notistack)
- Loading spinners during API calls
- CORS-enabled REST API
- MongoDB Atlas or local MongoDB support

---

## 🛠️ Tech Stack

| Layer     | Technology                          |
|-----------|--------------------------------------|
| Frontend  | React 18, Vite, Tailwind CSS, Axios  |
| Routing   | React Router DOM v6                  |
| Icons     | React Icons                          |
| Alerts    | Notistack (Snackbar notifications)   |
| Backend   | Node.js, Express.js                  |
| Database  | MongoDB with Mongoose ODM            |
| Dev Tools | Nodemon, ESLint                      |

---

## 📁 Folder Structure

```
MERN-TODO-List/
│
├── backend/                        # Express.js REST API
│   ├── controller/
│   │   └── books.controller.js     # CRUD logic for books (getBooks, createBook, updateBook, deleteBook)
│   ├── models/
│   │   └── bookModel.js            # Mongoose schema: title, author, publishYear + timestamps
│   ├── routes/
│   │   └── books.route.js          # Route definitions mapped to controller functions
│   ├── config.js                   # Environment config (PORT, MONGODB_URL)
│   ├── index.js                    # App entry: Express setup, MongoDB connection, middleware
│   ├── .env                        # Environment variables (not committed)
│   ├── .gitignore
│   └── package.json                # Backend dependencies (express, mongoose, cors, nodemon)
│
├── client/                         # React frontend (Vite)
│   ├── public/
│   │   └── vite.svg
│   ├── src/
│   │   ├── components/
│   │   │   ├── home/
│   │   │   │   ├── bookCard.jsx    # Card view component for a single book
│   │   │   │   ├── bookModel.jsx   # Modal popup component for book preview
│   │   │   │   ├── bookTable.jsx   # Table view listing all books with action buttons
│   │   │   │   └── singleCard.jsx  # Detailed card layout with icons and actions
│   │   │   ├── backButton.jsx      # Reusable back navigation button
│   │   │   └── spinner.jsx         # Loading spinner component
│   │   ├── pages/
│   │   │   ├── home.jsx            # Home page — lists books in table or card view
│   │   │   ├── createBook.jsx      # Form page to add a new book
│   │   │   ├── showBook.jsx        # Page showing full details of a single book
│   │   │   ├── editBook.jsx        # Form page to update an existing book
│   │   │   ├── deleteBook.jsx      # Confirmation page to delete a book
│   │   │   └── index.js            # Barrel export for all pages
│   │   ├── App.jsx                 # Root component with React Router route definitions
│   │   ├── main.jsx                # React entry point — renders App with BrowserRouter
│   │   └── index.css               # Global Tailwind CSS imports
│   ├── index.html                  # HTML shell for Vite
│   ├── vite.config.js              # Vite build configuration
│   ├── tailwind.config.js          # Tailwind CSS configuration
│   ├── postcss.config.js           # PostCSS configuration
│   ├── .eslintrc.cjs               # ESLint rules for React
│   ├── .gitignore
│   └── package.json                # Frontend dependencies (react, axios, react-router-dom, etc.)
│
├── .gitignore
└── Readme.md
```

---

## 🔌 API Endpoints

All routes are prefixed with `/api`.

| Method | Endpoint         | Description              |
|--------|------------------|--------------------------|
| GET    | `/api/books`     | Get all books            |
| GET    | `/api/books/:id` | Get a single book by ID  |
| POST   | `/api/books`     | Create a new book        |
| PUT    | `/api/books/:id` | Update a book by ID      |
| DELETE | `/api/books/:id` | Delete a book by ID      |

---

## ⚙️ Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [MongoDB](https://www.mongodb.com/) (local or Atlas)
- npm

---

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd MERN-TODO-List
```

---

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file in the `backend/` directory:

```env
PORT=5000
MONGODB_URL=mongodb://localhost:27017/mern-books
```

Start the backend server:

```bash
# Development (with hot reload)
npm run dev

# Production
npm start
```

The backend will run at: `http://localhost:5000`

---

### 3. Frontend Setup

```bash
cd client
npm install
npm run dev
```

The frontend will run at: `http://localhost:5173`

---

## 📖 Usage

1. Open `http://localhost:5173` in your browser
2. The **Home** page shows all books — toggle between **Table** and **Card** view
3. Click the **➕** icon to add a new book
4. Use the action icons on each book to **view**, **edit**, or **delete**
5. All actions show toast notifications confirming success or failure

---

## 📦 Book Data Model

```javascript
{
  title:       String,   // required
  author:      String,   // required
  publishYear: Number,   // required
  createdAt:   Date,     // auto-generated
  updatedAt:   Date      // auto-generated
}
```

---

## 🧰 Scripts Reference

### Backend (`/backend`)

| Command       | Description                        |
|---------------|------------------------------------|
| `npm run dev` | Start with Nodemon (hot reload)    |
| `npm start`   | Start with Node.js                 |

### Frontend (`/client`)

| Command         | Description                        |
|-----------------|------------------------------------|
| `npm run dev`   | Start Vite dev server              |
| `npm run build` | Build for production               |
| `npm run lint`  | Run ESLint                         |
| `npm run preview` | Preview production build         |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).