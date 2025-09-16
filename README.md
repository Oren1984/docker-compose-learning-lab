# docker-compose-mini

Simple Docker Compose stack: **Flask (web)** + **MySQL (db)** + **Adminer**.

## Quick start

```bash
# from this folder
docker compose up -d
```

- Web app: http://localhost:5000  
  - Health: http://localhost:5000/healthz  
  - Users (queries MySQL): http://localhost:5000/users
- Adminer: http://localhost:8080  
  - System: `MySQL`
  - Server: `db`
  - Username: `appuser`
  - Password: `apppass`
  - Database: `appdb`

## Common commands

```bash
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
```

## Flow

1. `docker compose up -d`
2. Open the browser to the **web** app (`/users`) and **Adminer**
3. Confirm data seed from `db/init.sql` appears