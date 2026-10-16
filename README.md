# Foodie — Run Instructions

## Prerequisites

Choose one setup method:

- **Docker:** Docker Desktop and Docker Compose.
- **Manual:** Node.js 16+, npm (or Yarn), and MongoDB (local or cloud).

## Environment and database setup

Configure the following values before starting the relevant services:

| Service | Variables |
| --- | --- |
| Backend | `MONGODB_URI` (MongoDB connection string), `JWT_SECRET`, `PORT` (defaults to `4000`) |
| Frontend | `REACT_APP_API_URL` (backend API URL) |
| Admin | `VITE_API_URL` (backend API URL) |

For a manual database, start MongoDB locally and set the backend connection in `backend/config/db.js` as needed:

```bash
mongod
```

With Docker, MongoDB starts automatically. Its configured credentials are:

- Username: `admin`
- Password: `password123`
- Database: `foodie`

## Install dependencies (manual setup)

From the project root:

```bash
cd frontend && npm install && cd ..
cd backend && npm install && cd ..
cd admin && npm install && cd ..
```

## Start locally (manual setup)

Run each command in a separate terminal.

### Frontend

```bash
cd frontend
npm run dev
```

### Admin panel

```bash
cd admin
npm run dev
```

### Backend

```bash
cd backend
npm run server
```

The backend runs at <http://localhost:4000>.

## Run with Docker

From the project root:

```bash
npm install
docker-compose up --build
```

Useful Docker commands:

```bash
# Start services
docker-compose up

# Start in the background
docker-compose up -d

# Stop services
docker-compose down

# View service logs
docker-compose logs

# View a specific service's logs
docker-compose logs -f frontend

# Rebuild the backend
docker-compose build backend
```

## Local URLs

| Service | URL |
| --- | --- |
| Frontend | <http://localhost:3000> |
| Admin panel | <http://localhost:5173> |
| Backend API | <http://localhost:4000> |
| MongoDB | `localhost:27017` |
