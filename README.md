# 🚀 DevShala

> **A full-stack coding platform for learning, practicing, and improving programming skills.**

DevShala is a **LeetCode-inspired full-stack coding platform** built using the **MERN stack**. It provides an interactive environment where users can browse coding problems, write and execute code, submit solutions, track submission history, watch solution videos, and get AI-powered coding assistance.

The platform combines **real-time code execution through Judge0**, **AI assistance using Google Gemini**, secure authentication, role-based authorization, and an admin panel for managing coding content.

---

## 🌐 Live Demo

🚀 **[Open DevShala](https://devshala-rho.vercel.app/)**

---

## ✨ Features

### 👤 User Authentication

- User registration and login
- JWT-based authentication
- Secure password hashing using bcrypt
- Protected routes
- User authorization
- Role-based admin authorization

---

### 🧩 Coding Problems

- Browse coding problems
- View detailed problem statements
- Interactive coding environment
- Monaco Editor integration
- Submit coding solutions
- Multi-language code execution using **Judge0**
- Automated test-case evaluation
- View submission results
- Track previous submissions
- Runtime and memory information

---

### ⚡ Judge0 Code Execution

DevShala uses **Judge0** as the code execution engine for compiling and running user-submitted programs.

### Submission Flow

```text
User
 │
 ▼
Monaco Editor
 │
 │ Submit Code
 ▼
Express Backend
 │
 │ Create Submission
 ▼
Judge0 API
 │
 ├── Compile Code
 ├── Execute Test Cases
 └── Return Execution Result
 │
 ▼
Express Backend
 │
 ├── Evaluate Result
 ├── Store Submission
 └── Return Status
 │
 ▼
React Frontend
 │
 ▼
User
```

Judge0 allows DevShala to execute submitted programs against test cases and return execution results to the platform.

---

### 🤖 AI Coding Assistant

DevShala integrates the **Google Gemini API** to provide an AI-powered coding assistant.

Users can use the AI assistant to:

- Understand coding problems
- Ask programming-related questions
- Get hints
- Discuss possible approaches
- Clarify programming concepts
- Get help while solving problems

The Gemini API is accessed through the backend so sensitive API credentials are not exposed directly in the frontend.

---

### 🎥 Video Solutions

- Problem-specific solution videos
- Video-based explanations
- Admin video upload functionality
- Video management through the admin panel
- Cloud-based media management using Cloudinary

---

### 🛠️ Admin Panel

DevShala includes a dedicated admin panel for managing the coding platform.

Admins can:

- Create coding problems
- Delete coding problems
- Manage problem information
- Upload solution videos
- Manage solution videos
- Perform protected administrative operations

Administrative operations are protected using role-based authorization.

---

### 📊 Submission History

Users can view their previous submissions and track their coding activity.

Submission information includes:

- Problem
- Submitted code
- Programming language
- Execution status
- Test cases
- Runtime
- Memory usage
- Error information

---

# 🧰 Tech Stack

## Frontend

- **React**
- **Vite**
- **JavaScript**
- **Tailwind CSS**
- **DaisyUI**
- **Redux Toolkit**
- **React Redux**
- **React Router**
- **Axios**
- **Monaco Editor**
- **React Hook Form**
- **Zod**
- **Lucide React**

---

## Backend

- **Node.js**
- **Express.js**
- **MongoDB**
- **Mongoose**
- **Redis**
- **JWT**
- **bcrypt**
- **Axios**
- **dotenv**
- **CORS**

---

## External Services

| Service | Purpose |
|---|---|
| **Judge0** | Code compilation and execution |
| **Google Gemini API** | AI-powered coding assistance |
| **Cloudinary** | Solution video/media management |
| **Redis** | Token management and backend support |
| **Vercel** | Frontend deployment |
| **Render** | Backend deployment |

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────────┐
                         │          User           │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │     React Frontend      │
                         │                         │
                         │ • React                 │
                         │ • Redux Toolkit         │
                         │ • Tailwind CSS          │
                         │ • Monaco Editor         │
                         │ • React Router          │
                         └────────────┬────────────┘
                                      │
                                  REST APIs
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │    Express Backend      │
                         │                         │
                         │ • Authentication        │
                         │ • Problems              │
                         │ • Submissions           │
                         │ • Judge0 Integration     │
                         │ • AI Chat               │
                         │ • Videos                │
                         │ • Admin                  │
                         └───────┬─────────┬───────┘
                                 │         │
                    ┌────────────┘         └───────────────┐
                    ▼                                      ▼
             ┌───────────────┐                    ┌─────────────────┐
             │    MongoDB    │                    │ External APIs  │
             │               │                    │                 │
             │ • Users       │                    │ • Judge0        │
             │ • Problems    │                    │ • Gemini AI     │
             │ • Submissions │                    │ • Cloudinary    │
             │ • Videos      │                    └─────────────────┘
             └───────────────┘
```

---

# 🔐 Authentication & Authorization

DevShala uses **JWT-based authentication** with protected routes and role-based authorization.

### Authentication Flow

```text
User
 │
 ▼
Login / Signup
 │
 ▼
Express API
 │
 ├── Validate Credentials
 │
 ├── bcrypt Password Verification
 │
 └── Generate JWT
 │
 ▼
Authenticated User
 │
 ▼
Protected API Routes
```

Passwords are securely hashed using **bcrypt** before being stored.

JWT tokens are used to authenticate users when accessing protected resources.

Administrative operations are protected using dedicated admin authorization middleware.

---

# 🗄️ Database

DevShala uses **MongoDB** with **Mongoose** for database management.

The application manages data such as:

```text
User
 │
 ├── Authentication details
 ├── Role
 └── User information


Problem
 │
 ├── Problem statement
 ├── Difficulty
 ├── Test cases
 └── Problem information


Submission
 │
 ├── User
 ├── Problem
 ├── Submitted code
 ├── Language
 ├── Execution status
 └── Submission information


Solution Video
 │
 ├── Problem
 ├── Video information
 └── Media URL
```

---

# 🤖 AI Integration

DevShala integrates the **Google Gemini API** to provide an AI-powered coding assistant.

### AI Request Flow

```text
User
 │
 │ Coding Question
 ▼
React AI Chat
 │
 │ API Request
 ▼
Express Backend
 │
 │ Gemini API Request
 ▼
Google Gemini
 │
 │ AI Response
 ▼
Express Backend
 │
 ▼
React AI Chat
 │
 ▼
User
```

The Gemini API key is stored in backend environment variables rather than being exposed in the frontend.

---

# ⚡ Judge0 Integration

Judge0 acts as the execution layer between the DevShala backend and submitted source code.

### Code Execution Process

```text
                    User
                      │
                      ▼
               Monaco Editor
                      │
                      │ Source Code
                      ▼
               Express Backend
                      │
                      │ Submission Request
                      ▼
                  Judge0 API
                      │
             ┌────────┴────────┐
             ▼                 ▼
        Compilation       Test Execution
             │                 │
             └────────┬────────┘
                      ▼
               Execution Result
                      │
                      ▼
               Express Backend
                      │
          ┌───────────┴───────────┐
          ▼                       ▼
     Save Submission        Return Result
          │                       │
          └───────────┬───────────┘
                      ▼
                React Frontend
                      │
                      ▼
                     User
```

This architecture keeps code execution separate from the main application server while allowing the platform to process programming submissions.

---

# 🎥 Video Solution Architecture

Solution videos are managed through the backend and cloud media storage.

```text
Admin
 │
 ▼
Upload Solution Video
 │
 ▼
Backend
 │
 ▼
Cloudinary
 │
 ▼
Media URL
 │
 ▼
Database
 │
 ▼
User
 │
 ▼
Watch Solution
```

---

# 🛠️ Admin Features

The admin panel provides protected functionality for managing platform content.

### Problem Management

- Create problems
- Delete problems
- Manage problem information
- Configure test cases

### Video Management

- Upload solution videos
- Manage solution videos
- Associate videos with coding problems

### Authorization

Only authorized administrators can access administrative operations.

---

# 📌 Project Highlights

| Feature | Technology |
|---|---|
| Frontend | React + Vite |
| Styling | Tailwind CSS + DaisyUI |
| State Management | Redux Toolkit |
| Code Editor | Monaco Editor |
| Code Execution | Judge0 |
| Backend | Node.js + Express |
| Database | MongoDB |
| ODM | Mongoose |
| Authentication | JWT + bcrypt |
| AI Assistant | Google Gemini |
| Media Storage | Cloudinary |
| Token Management | Redis |
| Deployment | Vercel + Render |

---

# 🔄 Overall Application Flow

```text
                         ┌───────────────┐
                         │     User      │
                         └───────┬───────┘
                                 │
                                 ▼
                    ┌────────────────────────┐
                    │    React Frontend      │
                    │                        │
                    │  Problems / Editor     │
                    │  AI Assistant          │
                    │  Videos / Submissions  │
                    └───────────┬────────────┘
                                │
                                ▼
                    ┌────────────────────────┐
                    │    Express Backend     │
                    │                        │
                    │ Authentication         │
                    │ Problem Management     │
                    │ Submission Management  │
                    │ AI Integration         │
                    │ Admin Operations       │
                    └───────┬───────┬────────┘
                            │       │
                 ┌──────────┘       └──────────┐
                 ▼                             ▼
          ┌─────────────┐               ┌─────────────┐
          │   MongoDB   │               │   Judge0    │
          │             │               │             │
          │ Users       │               │ Compile     │
          │ Problems    │               │ Execute     │
          │ Submissions │               │ Test Cases  │
          └─────────────┘               └─────────────┘
                            │
                            ▼
                    ┌────────────────┐
                    │ External APIs  │
                    │                │
                    │ Gemini         │
                    │ Cloudinary     │
                    └────────────────┘
```

---

# 🌐 Deployment

The DevShala frontend is deployed using **Vercel**.

### Production Application

🚀 **[https://devshala-rho.vercel.app/](https://devshala-rho.vercel.app/)**

The frontend communicates with the deployed backend through the configured API URL.

Required environment variables are configured through the deployment platform rather than being exposed in the public repository.

---

# 🔒 Security & Environment Variables

Sensitive credentials are **never included in the public documentation repository**.

Examples of sensitive values include:

```text
MongoDB connection string
JWT secret
Gemini API key
Cloudinary credentials
Judge0 API configuration
Other private API credentials
```

These values should be stored using environment variables.

Example:

```env
DB_CONNECTION_STRING=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key

CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

JUDGE0_API_URL=your_judge0_api_url
```

> Never commit real API keys, database credentials, JWT secrets, or other private configuration values to GitHub.

---

# 📚 Project Architecture

DevShala follows a separate **frontend + backend architecture**.

```text
DevShala
│
├── Frontend
│   ├── React
│   ├── Redux Toolkit
│   ├── React Router
│   ├── Monaco Editor
│   └── Tailwind CSS
│
└── Backend
    ├── Node.js
    ├── Express.js
    ├── MongoDB
    ├── Redis
    ├── JWT Authentication
    ├── Judge0 Integration
    ├── Gemini Integration
    └── Cloudinary Integration
```

---

# 🎯 Key Learning Outcomes

Through this project, I gained practical experience in:

- Full-stack MERN development
- REST API development
- React application architecture
- Redux Toolkit state management
- JWT authentication
- Role-based authorization
- Password hashing with bcrypt
- MongoDB and Mongoose
- Protected API routes
- Monaco Editor integration
- Judge0 code execution integration
- AI API integration
- Google Gemini API
- Cloudinary media management
- Redis-based token management
- Frontend-backend communication
- Environment variable management
- Admin dashboard development
- Full-stack deployment

---

# 🚀 Future Improvements

- [ ] Advanced code execution analytics
- [ ] More programming language support
- [ ] Problem filtering by difficulty
- [ ] Problem filtering by topic
- [ ] User profiles
- [ ] Coding statistics
- [ ] Leaderboard
- [ ] Daily coding challenges
- [ ] Coding contests
- [ ] Detailed submission analytics
- [ ] Automated testing improvements
- [ ] CI/CD pipeline
- [ ] Docker support

---

# 🔒 Source Code

The production source code is maintained in a **private repository**.

This public repository contains the **project documentation, architecture, features, technology stack, and project information**.

The application can be accessed through the live demo:

🚀 **[Open DevShala](https://devshala-rho.vercel.app/)**

---

# 👨‍💻 Author

## Raj Gupta

**B.Tech Computer Science Student**

Full-Stack MERN Developer

### Technologies

`React` `Node.js` `Express` `MongoDB` `Redux` `Judge0` `Gemini AI` `Redis`

---

## 🌐 Live Project

🚀 **[DevShala](https://devshala-rho.vercel.app/)**

---

## ⭐ Support

If you found this project useful or interesting, consider giving the documentation repository a ⭐ on GitHub.

---

### Built with ❤️ using the MERN stack
