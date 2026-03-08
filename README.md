# SPENDWISE-NM-BACKEND-PROJECT
This is a Learning Backend Project called SPENDWISE (SMART EXPENSE TRACKER).
# 💸 SpendWise — Backend API

> A clean, beginner-friendly REST API built with **Node.js**, **Express**, **MongoDB**, and **JWT Authentication**.  
> Designed to help developers learn how to build secure backend systems with real-world patterns.



##  Table of Contents

1. [Overview]
2. [Tech Stack]
3. [Features]
4. [Project Structure]
5. [Getting Started]
6. [Environment Variables]
7. [API Endpoints]
8. [Output Screenshots]
9. [Project Documents]

## Overview

**SpendWise** is a backend-only application that allows users to:
1. Register and login securely using **JWT-based authentication**
2. Perform full **CRUD operations** on their personal transaction records
3. Access **protected routes** enforced by middleware
4. Store and retrieve data from **MongoDB** using **Mongoose**

This project is ideal for beginners learning REST API design, token-based authentication, and NoSQL database integration.


## Tech Stack

| Layer | Technology |
|---|---|
| Runtime | Node.js |
| Framework | Express.js |
| Database | MongoDB + Mongoose |
| Authentication | JWT (jsonwebtoken) + bcrypt |
| Environment Config | dotenv |
| API Testing | Postman / Thunder Client |



##  Features

1. 🔐 **User Registration & Login** — Secure auth with hashed passwords and JWT tokens
2. 🛡️ **Protected Routes** — Middleware verifies JWT before granting access
3. 📋 **CRUD Operations** — Create, Read, Update, Delete on transaction records
4. 🔒 **Data Isolation** — Users can only access their own records
5. 🗄️ **MongoDB Integration** — Persistent storage via Mongoose ODM
6. ⚙️ **Modular Architecture** — Clean separation of routes, controllers, models, middleware


## Project Structure

```
spendwise/
│
├── config/
│   └── db.js                 # MongoDB connection
│
├── controllers/
│   ├── authController.js     # Register & Login logic
│   └── transactionController.js  # CRUD logic
│
├── middleware/
│   └── authMiddleware.js     # JWT verification
│
├── models/
│   ├── User.js               # User schema
│   └── Transaction.js        # Transaction schema
│
├── routes/
│   ├── authRoutes.js         # /api/auth endpoints
│   └── transactionRoutes.js  # /api/transactions endpoints
│
├── .env                      # Environment variables (not committed)
├── .gitignore
├── package.json
└── server.js                 # Entry point
```

---

## 🚀 Getting Started

### Prerequisites

1. [Node.js](https://nodejs.org/) v14+
2. [MongoDB](https://www.mongodb.com/) (local or Atlas)
3. [Git](https://git-scm.com/)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/spendwise.git

# 2. Navigate into the project directory
cd spendwise

# 3. Install dependencies
npm install

# 4. Create your .env file (see below)
cp .env.example .env

# 5. Start the development server
npm run dev
```

Server runs at: `http://localhost:5000`


## 🔑 Environment Variables

Create a `.env` file in the root directory with the following:

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/spendwise
JWT_SECRET=your_super_secret_key
```

> ⚠️ Never commit your `.env` file. It is included in `.gitignore`.

## 📡 API Endpoints

### 🔓 Auth Routes — `/api/auth`

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/api/auth/register` | Register a new user | ❌ |
| `POST` | `/api/auth/login` | Login and receive JWT token | ❌ |

#### Register — Request Body
```json
{
  "name": "Nobita N",
  "email": "nobita@gmail.com",
  "password": "Nobita@07"
}
```

#### Login — Request Body
```json
{
  "email": "nobita@gmail.com",
  "password": "Nobita@07"
}
```

### 🔐 Transaction Routes — `/api/transactions`

> All routes require `Authorization: Bearer <token>` header

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/transactions` | Create a new transaction |
| `GET` | `/api/transactions` | Get all transactions for logged-in user |
| `PUT` | `/api/transactions/:id` | Update a transaction by ID |
| `DELETE` | `/api/transactions/:id` | Delete a transaction by ID |

#### Create Transaction — Request Body
```json
{
  "amount": 50000,
  "type": "income",
  "category": "Salary",
  "note": "This is my first salary"
}
```


## 📸 Output Screenshots

| # | API | Status |
|---|-----|--------|
| 1 | Server Start | ✅ Running on port 5000 |
| 2 | Register API | ✅ 201 Created |
| 3 | Login API | ✅ 200 OK + JWT Token |
| 4 | JWT Token | ✅ Bearer token |
| 5 | Create Transaction | ✅ 201 Created |
| 6 | Get Records | ✅ 200 OK |
| 7 | Update Record | ✅ 200 OK |
| 8 | Delete Record | ✅ 200 OK — "Transaction removed" |

> Screenshots are available in the `SpendWise (Project Docs)/docs` folder and in the project documentation.


## 📄 Project Documents

All project documents are available in all phases:

| Document | Description |
|----------|-------------|
| [`Solution_Requirements.docx`](./docs/SpendWise_Solution_Requirements.docx) | Functional & Non-Functional Requirements |
| [`Technology_Stack.docx`](./docs/SpendWise_Technology_Stack.docx) | Architecture, Components & Tech Stack |
| [`UAT_Report.docx`](./docs/SpendWise_UAT_Report.docx) | User Acceptance Testing — all test cases & sign-off |
| [`Project_Docs.docx`](./docs/SpendWise_Project_Docs.docx) | Full project documentation with screenshots |


## 📝 License

This project is built for educational purposes as part of **Project Design Phase-II**.

<p align="center">
  Built with ❤️ using Node.js · Express · MongoDB · JWT
</p>
