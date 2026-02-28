# FARM Stack Project

A full-stack web application using the **FARM stack** — FastAPI, React, and MongoDB — demonstrating a modern, decoupled architecture with a Python async backend, React frontend, and NoSQL database.

## 🚀 Features

- Async REST API with FastAPI + Motor (async MongoDB driver)
- Auto-generated **Swagger UI** at `/docs`
- React frontend consuming the FastAPI backend
- MongoDB Atlas for cloud-hosted NoSQL storage
- Full CRUD operations

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, FastAPI, Uvicorn |
| Database | MongoDB (Atlas) + Motor (async driver) |
| Frontend | React |
| API Docs | Swagger / OpenAPI (built into FastAPI) |
| Package mgmt | pipenv |

## 📦 Getting Started

### Prerequisites

- Python 3.9+
- Node.js 16+
- A [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) free cluster

### Backend Setup

```bash
cd backend

# Install pipenv
pip install pipenv

# Create virtual environment and install dependencies
pipenv install -r requirements.txt

# Activate virtual environment
pipenv shell

# Start the API server
uvicorn main:app --reload
```

Backend runs at **http://localhost:8000**  
Swagger UI at **http://localhost:8000/docs**

### Frontend Setup

```bash
cd frontend

npm install
npm start
```

Frontend runs at **http://localhost:3000**

## 📁 Project Structure

```
farmstack_project/
├── backend/
│   ├── main.py         # FastAPI app entry point
│   ├── models.py       # MongoDB document models
│   ├── routes/         # API route handlers
│   └── requirements.txt
└── frontend/
    ├── src/
    │   ├── components/
    │   └── App.js
    └── package.json
```

## 🐳 Docker (DevOps)

Run the entire stack with Docker Compose:

```yaml
# docker-compose.yml
version: '3.8'
services:
  backend:
    build: ./backend
    ports:
      - "8000:8000"
    environment:
      MONGODB_URL: mongodb+srv://<user>:<pass>@cluster.mongodb.net/farmdb
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    depends_on:
      - backend
```

```bash
docker-compose up --build
```

## 🔗 Author

**Vignesh Joshi** — [github.com/joshivignesh](https://github.com/joshivignesh)
