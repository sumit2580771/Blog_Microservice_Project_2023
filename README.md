🚀 Blog Platform – Full Stack Microservices Architecture

A scalable full-stack blog platform built using Next.js (Frontend) and Node.js + Express (Microservices Backend).

The backend follows a service-oriented architecture, where User, Author, and Blog are independent services for better scalability and modularity.

🏗 Architecture Overview
blog-platform/
│
├── frontend/                # Next.js 15 Frontend (App Router)
│
├── services/
│   ├── user/                # User Service (Authentication & Profiles)
│   ├── author/              # Author Service
│   └── blog/                # Blog Service
│
└── README.md


This project is designed using a decoupled architecture, enabling independent deployment and horizontal scaling of services.

🖥 Frontend
⚡ Tech Stack

Next.js 15 (App Router)

React 19

TypeScript

Axios (API abstraction layer)

Context API (State Management)

Radix UI

Google OAuth

JWT Authentication

React Hot Toast

CSS (globals.css)

✨ Features

Blog listing page

Blog detail page

Dynamic routing

Authentication (Login / Register)

User profile page

Author filtering

Responsive UI

Toast notifications

Centralized API configuration

▶ Run Frontend
cd frontend
npm install
npm run dev


Frontend runs on:

http://localhost:3000

⚙ Backend – Microservices

Each service is an independent Express + TypeScript application.

All services follow:

RESTful API structure

MVC pattern

Environment-based configuration

MongoDB (Mongoose ORM)

JWT-based authentication

🔹 User Service

Handles:

User registration

Login

JWT generation

Profile management

Google OAuth integration

📦 Tech Stack

Express 5

TypeScript

MongoDB + Mongoose

JWT

dotenv

CORS

Cloudinary (image uploads)

Google APIs

▶ Run User Service
cd services/user
npm install
npm run dev


Runs on:

http://localhost:5001

🔹 Author Service

Handles:

Author creation

Author profile management

Author-blog linking

▶ Run Author Service
cd services/author
npm install
npm run dev


Runs on:

http://localhost:5002

🔹 Blog Service

Handles:

Create blog

Update blog

Delete blog

Fetch all blogs

Fetch single blog

Image upload support

▶ Run Blog Service
cd services/blog
npm install
npm run dev


Runs on:

http://localhost:5003

🔐 Environment Variables

Each backend service should have its own .env file.

Example:

PORT=5001
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_super_secret_key

CLOUDINARY_NAME=xxxx
CLOUDINARY_KEY=xxxx
CLOUDINARY_SECRET=xxxx


Frontend .env.local:

NEXT_PUBLIC_API_URL=http://localhost:5001

🔄 Service Communication

Frontend communicates with services using Axios:

axios.get(`${process.env.NEXT_PUBLIC_API_URL}/api/blogs`)


Services can also communicate internally via REST APIs.

📜 Scripts (Example – User Service)
"scripts": {
  "build": "npm install && tsc",
  "start": "node dist/server.js",
  "dev": "concurrently \"tsc -w\" \"nodemon dist/server.js\""
}

🧠 Design Principles

Separation of Concerns

Independent service deployment

Scalable architecture

RESTful API design

Environment-based configuration

Centralized API handling in frontend

🚀 Deployment Strategy

Frontend:

Vercel

Backend Services:

Render / Railway / AWS

Database:

MongoDB Atlas

Media Storage:

Cloudinary

🔒 Security Measures

JWT authentication

Secure environment variables

CORS configuration

Input validation

Password hashing (recommended: bcrypt)

Secure cookie handling

📈 Future Improvements

API Gateway

Docker & Docker Compose

Redis caching

Role-based access control

Rate limiting

Logging & monitoring

CI/CD pipeline

Kubernetes deployment

🎯 Project Summary

This project follows a microservices-based full-stack architecture using Next.js for the frontend and Express with TypeScript for backend services. User, Author, and Blog services are independently structured for scalability and maintainability. Authentication is handled via JWT and OAuth integration. The architecture is designed for production readiness and future cloud-native expansion.
