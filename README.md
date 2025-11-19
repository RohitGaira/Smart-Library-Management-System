# Smart-Library-Management-System
# Smart Library Management System (SLMS)

A full-stack, AI-enhanced library automation platform designed to modernize cataloguing, borrowing, reservations, fines, and book discovery with ACID-compliant reliability and intelligent recommendations.

---

## 📌 Overview
The **Smart Library Management System (SLMS)** combines a robust relational backend with AI-powered search and recommendations to deliver an efficient, scalable digital library solution. It supports role-based user access, real-time book availability, secure transactions, and intelligent discovery features such as natural-language search, book comparison, and personalized recommendations.

Designed primarily for universities and research institutions, SLMS solves issues of inconsistent metadata, double-issuance, slow search, and poor user discovery by integrating a normalized PostgreSQL schema with AI embeddings and a responsive frontend.

---

## 🚀 Features

### Core Library Operations
- User authentication & JWT-based authorization  
- Book catalog with filtering, sorting, natural-language search  
- Borrowing, returning, and reservations with ACID-compliant workflows  
- Real-time availability and conflict-free issuance  
- Automated fine calculation and tracking  
- Complete audit history of transactions  

### AI/ML Intelligence
- Semantic book search using embeddings  
- Personalized recommendations using FAISS  
- Fallback mechanisms for cold-start users  
- Metadata enrichment using external APIs (Open Library, Google Books)

### Admin Controls
- Add/update/delete books, authors, publishers  
- Monitor system activity, fines, and overdue books  
- Validate/catalogue metadata through librarian workflow  

---

## 🛠 Tech Stack

### Backend
- FastAPI (Python)  
- SQLAlchemy ORM  
- PostgreSQL  
- Pydantic  
- JWT Authentication  
- Docker  

### Frontend
- Responsive HTML/CSS/JS  
- User & Admin Dashboards  
- WebSockets (for Real-Time Updates)

### AI/ML
- FAISS  
- Google Gemini API (Embeddings)  
- NumPy  

---

## 📐 System Architecture
```
backend/
├── app/
│ ├── main.py # FastAPI entry point
│ ├── config.py # Environment configuration
│ ├── database.py # DB connection + ORM session
│ ├── schemas/ # Pydantic models
│ ├── routes/ # REST endpoints
│ │ ├── auth.py
│ │ ├── books.py
│ │ ├── users.py
│ │ └── search.py
│ └── services/
│ ├── recommender/ # AI recommendation engine
│ │ └── engine.py
│ └── embeddings.py # Embedding utilities
```
.env.example # Environment configuration template
requirements.txt # Python dependencies
Dockerfile # Backend container
docker-compose.yml # Multi-service orchestration

markdown
Copy code

---

## 🔌 API Highlights

### Authentication
- POST `/auth/login`
- POST `/auth/register`

### Books
- GET `/books/`
- POST `/books/`
- PUT `/books/{id}`
- DELETE `/books/{id}`

### Borrowing
- POST `/borrow/{book_id}`
- POST `/return/{book_id}`

### Search
- GET `/search?q=keyword`
- GET `/recommend/{user_id}`

OpenAPI docs available at:  
`/docs` or `/redoc`

---

## 📊 Database Schema

Core tables:
- `users`
- `books`
- `authors`
- `publishers`
- `borrow_records`
- `reservations`
- `fines`

Key properties:
- Referential integrity  
- ACID-compliant transactions  
- Index-optimized search  
- Conflict-free concurrent borrowing  

---

## 📦 Installation & Setup

### Clone the Repository
```bash
git clone https://github.com/AmERonX/Smart-Library-Management-System.git
cd Smart-Library-Management-System
Create Environment File
bash
Copy code
cp .env.example .env
Start with Docker
bash
Copy code
docker-compose up --build
Run Locally
bash
Copy code
pip install -r requirements.txt
uvicorn app.main:app --reload
🧪 Testing
Unit tests for services and routes

Integration tests for borrow/return flows

End-to-end tests for entire system

AI/ML evaluation tests

Status: 90% Completed

📈 Project Status
Overall Completion: 95%

Completed:

Backend: FastAPI + PostgreSQL + SQLAlchemy

Core Features: Auth, catalog, borrowing, reservations, fines

AI/ML: FAISS recommender + embeddings

Responsive frontend dashboards

Docker deployment setup

Pending:

Final E2E tests

Production deployment

Documentation polish

