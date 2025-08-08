# 🚀 Task 6 – Persist App Logs Using Docker Volumes

This project demonstrates how to log HTTP requests from a Node.js application using Morgan and persist those logs on the host machine using Docker bind mounts.

---

## 📁 Project Structure

persist-logs-task/
│
├── Dockerfile # Builds the Docker image
├── docker-compose.yml # Sets up the container with volume mapping
├── index.js # Express server with logging using Morgan
├── package.json # Node.js dependencies and metadata
├── package-lock.json # Auto-generated lock file
├── .gitignore # Excludes node_modules and logs
│
└── logs/ # Host-mapped directory for log files (auto-created)
└── access.log # Request logs (generated during runtime)


---

## ✨ Key Features

- Logs every HTTP request made to the server using Morgan.
- Stores all logs persistently in a host folder using Docker bind mounts.
- Clean and minimal project structure suitable for beginners and professionals.
- Fully containerized Node.js application.

---

## 🧰 Technologies Used

- **Node.js**
- **Express.js**
- **Morgan** – HTTP request logger middleware
- **Docker**
- **Docker Compose**

---

## ⚙️ How It Works

1. The Node.js app logs incoming HTTP requests using Morgan into a file at `/usr/src/app/logs/access.log` (inside the container).
2. Docker Compose maps this path to a local `./logs/` folder on the host using a **bind mount**.
3. Logs are persisted even after stopping or removing the container.

---

## 🧪 How to Run & Test

### 1️⃣ Build and Start the App

```bash
docker-compose up --build
