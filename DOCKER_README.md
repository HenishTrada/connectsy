# 🐳 Docker Setup for Connectsy

Simple Docker configuration for showcasing in interviews.

## 📋 Prerequisites

- Docker and Docker Compose installed
- Node.js project with package.json files

## 🚀 Quick Start

### 1. Create Environment File
Create a `.env` file in the root directory:
```bash
NODE_ENV=production
PORT=3000
JWT_SECRET=your-secret-key
DB_SECRET=your-mongodb-connection-string
```

### 2. Build and Run
```bash
# Build and start all services
docker-compose up --build

# Or run in background
docker-compose up --build -d
```

### 3. Access Your Application
- **Frontend**: http://localhost:80
- **Backend API**: http://localhost:3000

## 🏗️ Architecture

- **Frontend**: React app served by Nginx (port 80)
- **Backend**: Node.js API (internal port 3000)
- **Nginx Proxy**: Routes API calls to backend (port 3000)

## 📁 File Structure

```
connectsy/
├── docker-compose.yml          # Main orchestration
├── nginx.conf                  # Backend API proxy
├── .dockerignore               # Global ignore rules
├── backend/
│   └── Dockerfile             # Backend container
└── frontend/
    ├── Dockerfile             # Frontend container
    └── nginx.conf             # Frontend server
```

## 🛠️ Basic Commands

```bash
# Start services
docker-compose up

# Stop services
docker-compose down

# View logs
docker-compose logs

# Rebuild
docker-compose up --build
```

## 🔧 Configuration

- **Frontend**: Serves React app on port 80
- **Backend**: Runs Node.js API internally on port 3000
- **Nginx Proxy**: Exposes backend API on port 3000 with CORS support

---

