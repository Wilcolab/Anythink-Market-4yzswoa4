# 🛍️ Anythink Market

<div align="center">

**A modern, full-stack e-commerce marketplace application**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.9.13-blue.svg)](https://www.python.org/)
[![React](https://img.shields.io/badge/React-17.0-61DAFB.svg)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.73-009688.svg)](https://fastapi.tiangolo.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED.svg)](https://www.docker.com/)

*Powered by [Wilco](https://www.trywilco.com)*

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Development](#-development)
- [Testing](#-testing)
- [Contributing](#-contributing)
- [License](#-license)
- [Support](#-support)

---

## 🎯 Overview

Anythink Market is a full-featured e-commerce marketplace application built with modern web technologies. It provides a complete platform for buying and selling items, featuring user authentication, item listings, comments, favorites, and user profiles.

The application is designed with a microservices architecture, featuring a React-based frontend and a FastAPI Python backend, all containerized with Docker for easy deployment and development.

---

## ✨ Features

- 🔐 **User Authentication** - Secure JWT-based authentication system
- 📝 **Item Listings** - Create, edit, and browse marketplace items
- 💬 **Comments** - Interactive comment system for items
- ⭐ **Favorites** - Save and organize favorite items
- 👤 **User Profiles** - Personalized user profiles with activity tracking
- 🏷️ **Tags & Categories** - Organize items with tags for easy discovery
- 📱 **Responsive Design** - Mobile-friendly interface
- 🔍 **Search & Filter** - Advanced search and filtering capabilities
- 📄 **Markdown Support** - Rich text formatting for item descriptions

---

## 🛠️ Technology Stack

### Frontend
- **React** 17.0 - UI library
- **Redux** - State management
- **React Router** - Navigation
- **Bootstrap** 4.6 - UI components
- **Sass** - Styling
- **Marked** - Markdown parsing

### Backend
- **Python** 3.9.13
- **FastAPI** - Modern, fast web framework
- **PostgreSQL** - Database
- **SQLAlchemy** - ORM
- **Alembic** - Database migrations
- **Pydantic** - Data validation
- **JWT** - Authentication
- **Poetry** - Dependency management

### DevOps
- **Docker** & **Docker Compose** - Containerization
- **GitHub Actions** - CI/CD
- **Kubernetes** - Orchestration (optional)

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Docker** (v20.10 or higher) - [Install Docker](https://docs.docker.com/get-docker/)
- **Docker Compose** (v2.0 or higher) - [Install Docker Compose](https://docs.docker.com/compose/install/)
- **Git** - [Install Git](https://git-scm.com/downloads)

Optional (for local development without Docker):
- **Node.js** v16+ and **Yarn**
- **Python** 3.9.13 and **Poetry**
- **PostgreSQL** 12+

---

## 🚀 Getting Started

### Quick Start with Docker (Recommended)

1. **Clone the repository**
   ```bash
   git clone https://github.com/Wilcolab/Anythink-Market-4yzswoa4.git
   cd Anythink-Market-4yzswoa4
   ```

2. **Start the application**
   ```bash
   docker compose up
   ```

3. **Access the application**
   - Frontend: [http://localhost:3001](http://localhost:3001)
   - Backend API: [http://localhost:3000](http://localhost:3000)
   - API Documentation: [http://localhost:3000/docs](http://localhost:3000/docs)

### Using GitHub Codespaces

1. Open the repository in GitHub Codespaces
2. Run the following command:
   ```bash
   docker compose up
   ```
3. The application will be available through the forwarded ports

---

## 📁 Project Structure

```
anythink-market/
├── backend/                 # Python FastAPI backend
│   ├── app/                # Application code
│   │   ├── api/           # API routes and endpoints
│   │   ├── core/          # Core configuration
│   │   ├── db/            # Database models and repositories
│   │   ├── models/        # Pydantic models
│   │   └── services/      # Business logic
│   ├── tests/             # Backend tests
│   ├── pyproject.toml     # Python dependencies
│   └── README.md          # Backend documentation
│
├── frontend/               # React frontend
│   ├── public/            # Static assets
│   ├── src/               # Source code
│   │   ├── components/   # React components
│   │   ├── agent/        # Redux store and actions
│   │   └── imgs/         # Images
│   ├── package.json       # Node dependencies
│   └── readme.md          # Frontend documentation
│
├── tests/                  # End-to-end tests
├── charts/                 # Kubernetes charts
├── .github/               # GitHub workflows and templates
├── docker-compose.yml     # Docker composition
└── readme.md              # This file
```

---

## 💻 Development

### Running in Development Mode

The application is configured for hot-reloading in development mode. Any changes you make to the code will automatically restart the relevant service.

### Creating a New Feature

1. Create a new branch from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. Make your changes and commit:
   ```bash
   git add .
   git commit -m "feat: add your feature description"
   ```

3. Push your branch and create a Pull Request:
   ```bash
   git push origin feature/your-feature-name
   ```

4. The Wilco app will review your PR automatically

### Component Documentation

- **Frontend Details**: See [frontend/readme.md](frontend/readme.md)
- **Backend Details**: See [backend/README.md](backend/README.md)

### API Documentation

The backend provides interactive API documentation:
- **Swagger UI**: [http://localhost:3000/docs](http://localhost:3000/docs)
- **ReDoc**: [http://localhost:3000/redoc](http://localhost:3000/redoc)

---

## 🧪 Testing

### End-to-End Tests

Documentation for running E2E tests can be found in the [`/tests`](tests) directory.

### Backend Tests

```bash
cd backend
poetry install
poetry run pytest
```

### Frontend Tests

```bash
cd frontend
yarn install
yarn test
```

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your changes** (`git commit -m 'feat: Add some AmazingFeature'`)
4. **Push to the branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Pull Request Guidelines

- Create PRs against the `main` branch
- Follow the existing code style and conventions
- Include tests for new features
- Update documentation as needed
- Use the provided [PR template](.github/pull_request_template.md)

### Code Style

- **Frontend**: ESLint + Prettier (run `yarn lint`)
- **Backend**: Black, isort, flake8 (configured in `pyproject.toml`)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License - Copyright (c) 2019 Nik Sidnev
```

---

## 💬 Support

- 🐛 **Issues**: [GitHub Issues](https://github.com/Wilcolab/Anythink-Market-4yzswoa4/issues)
- 💡 **Discussions**: [GitHub Discussions](https://github.com/Wilcolab/Anythink-Market-4yzswoa4/discussions)
- 📧 **Wilco Platform**: [trywilco.com](https://www.trywilco.com)

---

<div align="center">

**Made with ❤️ by the Anythink Team**

⭐ Star this repository if you find it helpful!

</div>
