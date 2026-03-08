# 🚀 Yakup Task API

A professional REST API for task management built with **Django REST Framework**, **PostgreSQL**, and **Docker Compose**.

## 📋 About

This project is a full-stack task management API that demonstrates modern backend development practices including containerization, database management, and RESTful API design.

**Built as part of a 4-Week AWS & DevOps Production Plan — Week 2: Docker & Container Networking**

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python 3.12 | Programming Language |
| Django 6.0 | Web Framework |
| Django REST Framework | API Development |
| PostgreSQL 15 | Database |
| Docker | Containerization |
| Docker Compose | Multi-Container Orchestration |

## 🏗️ Architecture

```
┌──────────────┐     ┌──────────────┐
│              │     │              │
│  Django App  │────▶│  PostgreSQL  │
│  (Port 8000) │     │  (Port 5432) │
│              │     │              │
└──────────────┘     └──────────────┘
     web                   db
         Docker Compose Network
```

## 📡 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/tasks/` | List all tasks |
| POST | `/api/tasks/` | Create a new task |
| GET | `/api/tasks/{id}/` | Retrieve a task |
| PUT | `/api/tasks/{id}/` | Update a task |
| DELETE | `/api/tasks/{id}/` | Delete a task |

## 🚀 Quick Start

### Prerequisites
- Docker & Docker Compose installed

### Run the project

```bash
# Clone the repository
git clone https://github.com/atlas-ops0/yakup-task-api.git
cd yakup-task-api

# Start all services
docker compose up --build

# In a new terminal, run migrations
docker compose exec web python manage.py migrate

# Access the API
# Open http://localhost:8000/api/tasks/ in your browser
```

## 📦 API Usage Examples

```bash
# List all tasks
curl http://localhost:8000/api/tasks/

# Create a new task
curl -X POST http://localhost:8000/api/tasks/ \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn Docker", "description": "Docker Compose with PostgreSQL"}'

# Update a task
curl -X PUT http://localhost:8000/api/tasks/1/ \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn Docker", "completed": true}'

# Delete a task
curl -X DELETE http://localhost:8000/api/tasks/1/
```

## 📁 Project Structure

```
yakup-task-api/
├── config/                 # Project settings
│   ├── settings.py         # Django configuration
│   ├── urls.py             # Main URL routing
│   └── wsgi.py             # WSGI config
├── tasks/                  # Task application
│   ├── models.py           # Task database model
│   ├── serializers.py      # JSON serialization
│   ├── views.py            # API logic (ViewSet)
│   └── urls.py             # App URL routing
├── Dockerfile              # Container image recipe
├── docker-compose.yml      # Multi-container setup
├── requirements.txt        # Python dependencies
└── manage.py               # Django CLI tool
```

## 🔮 Roadmap

- [ ] React frontend with dark/light theme
- [ ] User authentication (JWT)
- [ ] Task filtering and search
- [ ] Push Docker image to AWS ECR
- [ ] CI/CD pipeline with GitHub Actions
- [ ] Deploy to AWS EC2
- [ ] Terraform infrastructure as code

## 👨‍💻 Author

**Yakup Atlas** — Aspiring Cloud & DevOps Engineer

- GitHub: [@atlas-ops0](https://github.com/atlas-ops0)

---

*This project is part of my journey from Backend Development to Cloud/DevOps Engineering* ☁️
