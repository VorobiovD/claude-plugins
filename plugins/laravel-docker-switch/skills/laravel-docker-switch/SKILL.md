---
name: laravel-docker-switch
description: Switch a Laravel app between local and Docker environments. Invoke with /laravel-docker-switch.
argument-hint: "[local|docker]"
---

Switch the Laravel application between running locally and running inside Docker.
The user provides the target mode: `local` or `docker`.

## Local mode (Laravel runs on host, services in Docker)
1. Update `.env`:
   - `DB_HOST=127.0.0.1`
   - `REDIS_HOST=127.0.0.1` (if applicable)
   - Any other service hosts → `localhost` or `127.0.0.1`
2. Stop the Laravel app container (keep database/service containers running):
   ```
   docker compose stop app
   ```
3. Clear cached config:
   ```
   php artisan config:clear
   ```
4. Start Laravel locally:
   ```
   php artisan serve
   ```

## Docker mode (everything in Docker)
1. Update `.env`:
   - `DB_HOST=db` (or the service name from `docker-compose.yml`)
   - `REDIS_HOST=redis` (if applicable)
   - Any other service hosts → their Docker service names
2. Stop local Laravel if running
3. Start all containers:
   ```
   docker compose up -d
   ```
4. Clear cached config inside the container:
   ```
   docker compose exec app php artisan config:clear
   ```

## Rules
- Read `docker-compose.yml` first to determine the correct service names
- Read the current `.env` to understand which services are configured
- Only change host-related variables — do not modify ports, credentials, or other settings
- Show the user what will change before making edits
- After switching, verify the app is reachable
