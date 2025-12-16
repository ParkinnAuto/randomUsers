This project is a simple full-stack web application that demonstrates how to use React, Node.js (Express), and MySQL together using Docker Compose.
Each service runs in its own container and communicates through a Docker network.

----------------------------------------------------------------------------------------------------

🧱 System Architecture:

- Frontend: React (Vite) + Nginx

- Backend API: Node.js + Express

- Database: MySQL

- Container Orchestration: Docker Compose

----------------------------------------------------------------------------------------------------


📦 Services and Ports:

Service	    |       Technology	    |   Container Port   |        Local URL
Frontend	|     React + Nginx	    |          80	     |  http://localhost:8000
            |                       |                    |
Backend API |   Node.js + Express	|         3000	     |  http://localhost:3000
            |                       |                    |
Database	|         MySQL	        |         3306	     |      localhost:3306

Note 1: All containers must be running before performing any experiments or tests.

Note 2: Database Data Retrieval Test = http://localhost:3000/api/users/db

----------------------------------------------------------------------------------------------------

📁 Project Structure:

randomUsers/
├─ client/                 # Frontend (React + Vite)
│  ├─ Dockerfile
│  └─ src/
├─ server/                 # Backend (Node.js + Express)
│  ├─ Dockerfile
│  └─ server.js
├─ docker-compose.yml
└─ README.md

----------------------------------------------------------------------------------------------------

▶️ How to Run the Project:

    1️⃣ Prerequisites:
        Docker Desktop installed

        Docker Compose enabled
    
    2️⃣ Start all services:
        Open a terminal in the project root directory = docker-compose up --build

    This command will do these followings

    1. Build Docker images

    2. Start frontend, backend, and database containers

    3. Create a Docker network and volume automatically

    3️⃣ Access the application:
    Frontend (Web UI) = http://localhost:8000
    
    Backend API (Test) = http://localhost:3000/ 
        (expected response: { "message": "Server is running" })

    Backend API (Get users from database) = http://localhost:3000/api/users/db
    
    4️⃣ Fetch and store new users
        Open the following URL in your browser or click the button on the frontend:
        http://localhost:3000/api/users

        This will:

        Fetch random users from an external API

        Insert them into the MySQL database

        Return the fetched data

----------------------------------------------------------------------------------------------------

🗄️ Database Information: 

- Database name: randomusers

- Table: users

- Data persistence is handled using a Docker volume

Even if containers are removed, the database data will not be lost as long as the volume exists.

----------------------------------------------------------------------------------------------------

🧪 Useful Commands:

- Stop all containers = docker-compose down

- Stop containers and remove database data = docker-compose down -v

- View logs = 
    docker logs api-server

    docker logs frontend-web

    docker logs mysql-db

----------------------------------------------------------------------------------------------------

🧠 Key Concepts Demonstrated: 

- Containerized frontend, backend, and database

- Service-to-service communication using Docker network

- Use of Docker volumes for persistent data

- Separation of development and production environments

- REST API integration with external services

----------------------------------------------------------------------------------------------------

🚀 Future Improvements: 

- Deploy services using Kubernetes

- Add authentication and authorization

- Create edit, delete, add users function

- Add database migrations

- Improve error handling and validation

----------------------------------------------------------------------------------------------------

✅ Summary: 

This project demonstrates a complete cloud-ready application using Docker Compose, where each component is isolated, scalable, and easy to manage.
