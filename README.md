# Node.js CRUD API with JWT, Docker, CI/CD, and Nginx

## Features
- Register/Login users with JWT
- CRUD for Tasks
- MongoDB (Docker)
- GitHub Actions CI/CD
- Docker Compose for app + DB
- Nginx Reverse Proxy

## Local Setup

### 1. Environment Variables
Rename `.env.example` to `.env` and update if needed.

### 2. Run with Docker Compose
```bash
docker-compose up --build
```
App: [http://localhost:3000](http://localhost:3000)

### 3. Nginx (Optional)
```bash
# Run nginx with the provided config
docker run --name nginx-proxy -v $(pwd)/nginx.conf:/etc/nginx/conf.d/default.conf:ro -p 80:80 --network host -d nginx
```

### 4. GitHub Actions
- Push to GitHub.
- CI builds, tests, and runs Docker Compose.

### API Endpoints
- `POST /auth/register`
- `POST /auth/login`
- `POST /tasks` *(auth)*
- `GET /tasks` *(auth)*
- `PUT /tasks/:id` *(auth)*
- `DELETE /tasks/:id` *(auth)*