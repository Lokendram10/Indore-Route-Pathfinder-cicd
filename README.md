# 🚦 Indore Route Pathfinder

<div align="center">

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge\&logo=react\&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge\&logo=node.js\&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge\&logo=mongodb\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge\&logo=docker\&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge\&logo=jenkins\&logoColor=white)

**A web application to plan routes between stations in Indore using Dijkstra's Algorithm**

[🚀 Live Demo](https://indore-route.vercel.app)

</div>

---

> **Note**: This project was originally created by Harshit Singh. I forked the repository and made additional changes (Docker, Docker Compose, and Jenkins pipeline) in the **main** branch. The **master** branch contains the original code.

---

## ✨ Features

* 📍 **Add Stations**: Create new stations/locations
* 🔗 **Connect Stations**: Link stations with distance and cost
* 🧭 **Find Routes**: Calculate shortest path by distance or cheapest path by cost
* 📊 **View All**: See all stations and connections at a glance
* 🐳 **Dockerized**: Run frontend and backend with Docker & Docker Compose
* 🤖 **CI/CD**: Automated deployment pipeline with Jenkins

---

## 🛠️ Tech Stack

* **Frontend**: React.js, Tailwind CSS
* **Backend**: Node.js, Express.js
* **Database**: MongoDB
* **Algorithm**: Dijkstra's Shortest Path
* **Containerization**: Docker, Docker Compose
* **CI/CD**: Jenkins

---

## 🏃‍♂️ Quick Start

### 1. Clone Repository

```bash
git clone https://github.com/Lokendram10/Indore-Route-Pathfinder-cicd
cd Indore-Route-Pathfinder-cicd
```

### 2. Install Docker & Docker Compose (Linux)

```bash
sudo apt-get update
sudo apt-get install docker.io -y
sudo apt-get install docker-compose -y

# Give permission to current user to run docker without sudo
sudo usermod -aG docker $USER && newgrp docker
```

>⚠️ Logout and login again for group changes to take effect if newgrp docker does not work.

### 3. Docker Setup

```bash
# Build and run containers
docker-compose up --build
```

* Backend API: `http://localhost:5000`
* Frontend App: `http://localhost:3000`

### 4. Environment Variables

Create a `.env` file inside the `backend` folder:

```env
MONGO_URI=your_mongodb_connection_string
PORT=5000
```

---

## 🎯 How to Use

1. **Add Stations**: Enter station name and click "Add Station"
2. **Connect Stations**: Select two stations, enter distance (km) and cost (₹), click "Add Connection"
3. **Find Route**: Choose start/end stations, select "Distance" or "Cost" optimization, click "Find Route"
4. **View Results**: See the optimal path with total distance and cost

---

## 📁 Project Structure

```
indore-route-planner/
├── frontend/                # React app
│   ├── Dockerfile           # Dockerfile for frontend
│   ├── src/
│   └── package.json
├── backend/                 # Express API
│   ├── Dockerfile           # Dockerfile for backend
│   ├── models/              # MongoDB schemas  
│   ├── routes/              # API routes
│   ├── utils/               # Dijkstra algorithm
│   └── server.js
├── docker-compose.yml       # Docker Compose setup
├── Jenkinsfile              # CI/CD pipeline configuration
└── README.md
```

---

## 🔌 API Endpoints

```bash
GET    /api/stations       # Get all stations
POST   /api/stations       # Add new station
GET    /api/connections    # Get all connections
POST   /api/connections    # Add new connection
POST   /api/route          # Calculate optimal route
```

---

## 🧮 Algorithm

Uses **Dijkstra's Algorithm** to find:

* **Shortest Distance**: Minimum total kilometers
* **Cheapest Cost**: Minimum total rupees

---

## 🚀 Deployment

* **Docker**: Run frontend and backend via Docker Compose
* **CI/CD**: Jenkins pipeline automates building, testing, and deployment
* **Frontend**: Vercel - [https://indore-metro.vercel.app](https://indore-metro.vercel.app)
* **Backend**: Render - [https://indore-metro.onrender.com](https://indore-metro.onrender.com)
* Configure `.env` in deployment environments

---

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -m 'Add feature'`
4. Push branch: `git push origin feature-name`
5. Open Pull Request

---

## 📬 Contact

**Made by Harshit Singh**

* 📧 Email: [harshitsingh789123@gmail.com](mailto:harshitsingh789123@gmail.com)
* 💻 GitHub: [harshitsingh4321](https://github.com/harshitsingh4321)

---

## 📄 License

MIT License - feel free to use this project!
