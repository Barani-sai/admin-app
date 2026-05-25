# Admin App

A simple professional admin dashboard built with React.js, Python, and MySQL running in Docker.

## Project Overview

This project contains a frontend admin panel and a backend API. Admin users can log in, view dashboard statistics, and manage users.

## Tech Stack

- React.js: Frontend UI
- Vite: Frontend development server and build tool
- CSS: Custom professional responsive UI and animations
- Python: Backend API server
- MySQL: Database
- Docker: Runs MySQL database container
- mysql-connector-python: Python package used to connect backend with MySQL

## Features

- Admin login
- Dashboard summary cards
- Recent activity list
- Role mix section
- User management
- Add user
- Edit user
- Delete user
- Search users
- Active and inactive user status
- MySQL database persistence
- Responsive design
- Smooth UI animations

## Folder Structure

```text
admin-app/
  backend/
    app.py
    requirements.txt
  frontend/
    src/
      App.jsx
      main.jsx
      styles.css
    index.html
    package.json
    package-lock.json
  docker-compose.yml
  README.md
```

## Requirements

Install these before running the project:

- Node.js
- Python 3.10 or newer
- Docker Desktop
- VS Code

Check installation:

```powershell
node --version
npm --version
python --version
docker --version
```

## Database Setup

Start Docker Desktop first. Wait until Docker is running.

From the main project folder, run:

```powershell
cd "C:\Users\saiba\Documents\Codex\2026-05-25\simple-admin-app-using-react-js"
docker compose up -d
```

Check the MySQL container:

```powershell
docker ps
```

You should see a container named:

```text
admin-mysql
```

## MySQL Details

```text
Host: 127.0.0.1
Port: 3306
Database: admin_db
Username: admin
Password: admin123
Root password: root123
```

## Backend Setup

Open a terminal in VS Code and run:

```powershell
cd "C:\Users\saiba\Documents\Codex\2026-05-25\simple-admin-app-using-react-js\backend"
pip install -r requirements.txt
python app.py
```

The backend API will run at:

```text
http://localhost:8000
```

When the backend starts, it automatically creates these MySQL tables if they do not exist:

- users
- activity

It also adds sample users and activity data on the first run.

## Frontend Setup

Open another terminal in VS Code and run:

```powershell
cd "C:\Users\saiba\Documents\Codex\2026-05-25\simple-admin-app-using-react-js\frontend"
npm install
npm run dev
```

The frontend will run at:

```text
http://localhost:5173
```

## Login Details

```text
Email: admin@example.com
Password: admin123
```

## API Routes

```text
POST   /api/login
GET    /api/dashboard
GET    /api/users
POST   /api/users
PUT    /api/users/:id
DELETE /api/users/:id
```

## Useful Docker Commands

Start MySQL:

```powershell
docker compose up -d
```

Stop MySQL:

```powershell
docker compose down
```

Stop MySQL and delete database data:

```powershell
docker compose down -v
```

View running containers:

```powershell
docker ps
```

View MySQL logs:

```powershell
docker logs admin-mysql
```

## Troubleshooting

### docker is not recognized

Docker Desktop is not installed or not added to PATH. Install Docker Desktop, restart your computer, then try:

```powershell
docker --version
```

### ModuleNotFoundError: No module named mysql

Install backend dependencies:

```powershell
cd backend
pip install -r requirements.txt
```

### Can't connect to MySQL server

Make sure Docker Desktop is running, then start MySQL:

```powershell
docker compose up -d
```

Wait 30 seconds and run the backend again.

### Port 3306 already in use

Another MySQL server may already be running. Stop the other MySQL service or change the port in `docker-compose.yml`.

## Build Frontend For Production

```powershell
cd frontend
npm run build
```

The production files will be created inside:

```text
frontend/dist
```

## Sharing The Project

Before sharing, you can delete these generated folders to reduce ZIP size:

```text
frontend/node_modules
frontend/dist
backend/__pycache__
```

Do not delete:

```text
frontend/package.json
frontend/package-lock.json
backend/requirements.txt
docker-compose.yml
```

After receiving the project, another developer should run:

```powershell
docker compose up -d
cd backend
pip install -r requirements.txt
python app.py
```

Then in another terminal:

```powershell
cd frontend
npm install
npm run dev
```

## Future Improvements

- Use FastAPI or Flask for a more structured backend
- Add password hashing
- Add JWT authentication
- Add delete confirmation popup
- Add toast notifications
- Add pagination and filters
- Add dark mode
- Add user profile page
- Add role-based access control
