# 🚀 MERN App Dockerization Template

This repository provides a **production-ready template** for Dockerizing a full-stack MERN (MongoDB, Express, React, Node.js) application. It uses **multi-stage builds** for optimized frontend and backend images, and orchestrates everything with **Docker Compose**.

---

## 📦 Project Structure

. ├── backend/ │ ├── Dockerfile │ └── ... (Node.js/Express API) ├── frontend/ │ ├── Dockerfile │ ├── nginx.conf │ └── ... (React app) ├── docker-compose.prod.yml └── README.md


---

## 🐳 How It Works

- **Frontend**: Built with React, served via Nginx for performance.
- **Backend**: Node.js/Express API, connected to MongoDB.
- **MongoDB**: Official MongoDB image with persistent volume.

---

## 🚦 Quick Start

### 1. Clone the Repository
```sh
git clone https://github.com/your-username/mern-docker-template.git
cd mern-docker-template
```

### 2. Configure Environment Variables
Create .env files in both backend/ and frontend/ as needed.
Set MONGODB_URI in backend/.env (for local dev) or use Docker Compose's MONGO_URL.

### 3. Build & Run with Docker Compose
docker compose -f [docker-compose.prod.yml](http://_vscodecontentref_/3) up --build

  Frontend: http://localhost
  Backend API: http://localhost:3000

🛠️ File Highlights
frontend/Dockerfile
Multi-stage: Builds React app, then serves with Nginx.
Uses custom nginx.conf for SPA routing.
backend/Dockerfile
Installs only production dependencies.
Runs Node.js server on port 3000.
docker-compose.prod.yml
Orchestrates frontend, backend, and MongoDB.
Sets up persistent storage for MongoDB.
🌐 Nginx Configuration
The frontend uses a custom nginx.conf to ensure all routes are handled by React Router:

location / {
  root   /usr/share/nginx/html;
  index  index.html;
  try_files $uri /index.html;
}

📋 Tips
Development: Use separate Docker Compose files or run frontend/backend locally for hot-reloading.
Environment Variables: Pass secrets via .env files or Docker Compose environment section.
Scaling: Add more services (e.g., Redis, worker queues) as needed.
🎨 Screenshots
<!-- Add screenshots/gifs of your app running in Docker here! --> <p align="center"> <img src="https://user-images.githubusercontent.com/your-screenshot.png" width="600" alt="App Screenshot"/> </p>
🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first.

📄 License
MIT

Made with ❤️ for modern MERN deployments
