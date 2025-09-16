# docker-compose-mini

Simple Docker Compose stack: **Flask (web)** + **MySQL (db)** + **Adminer**.

## Quick start

```bash
# from this folder
docker compose up -d

⚠️ Note: if ports 5000 or 8080 are already in use edit docker-compose.yml and change mappings,
 e.g. 5001:5000, 8081:8080.


Endpoints & Example Outputs

Web app (Flask):

Health: http://localhost:5000/healthz

Example:

{"status":"ok"}


Users (queries MySQL): http://localhost:5000/users

Example:

[
  {"email":"alice@example.com","id":1,"name":"Alice"},
  {"email":"bob@example.com","id":2,"name":"Bob"},
  {"email":"charlie@example.com","id":3,"name":"Charlie"}
]


Adminer: http://localhost:8080

Credentials:

System: MySQL

Server: db

Username: appuser

Password: apppass

Database: appdb

Common commands
# View running services
docker compose ps

# View logs
docker compose logs -f web
docker compose logs -f db

# Rebuild the web image after code changes
docker compose build web && docker compose up -d web

# Stop and remove containers
docker compose down

# Stop, remove containers + volumes (removes MySQL data)
docker compose down -v

Flow

docker compose up -d

Open the browser to the web app (/users) and Adminer

Confirm data seed from db/init.sql appears
