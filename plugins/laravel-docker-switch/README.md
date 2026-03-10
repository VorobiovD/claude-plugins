# laravel-docker-switch

User-invocable skill to toggle a Laravel app between local and Docker environments.

## Usage

```
/laravel-docker-switch local
/laravel-docker-switch docker
```

## What it does

- **Local mode**: Sets DB/service hosts to `localhost`/`127.0.0.1`, stops app container, starts `php artisan serve`
- **Docker mode**: Sets hosts to Docker service names, starts all containers with `docker compose up -d`
- Reads `docker-compose.yml` to determine correct service names
- Shows changes before applying them

## Install

```json
{
  "skills": {
    "laravel-docker-switch": {
      "source": "github:VorobiovD/claude-plugins/plugins/laravel-docker-switch"
    }
  }
}
```
