# Tricky Heat - Salon Queue Management

**Live demo:** https://tricky-heat-salon.onrender.com

**Test PIN (Reception / Barber):** `5059`

Django serves the customer, reception, barber and waiting-area screens.

## Deploy on Render

1. Push this project to GitHub.
2. In Render, choose **New > Blueprint** and select the repository.
3. Render will read `render.yaml`, install dependencies, migrate SQLite, collect static assets and start Gunicorn.
4. Set `STAFF_PIN` to the desired staff PIN before first use. The demo PIN is `5059`.
5. The free-tier demo uses the default SQLite file. SQLite data may reset when Render replaces or recreates the instance.

## Deploy on Railway

1. Create a Python service from the repository.
2. Set `SECRET_KEY`, `DEBUG=False`, `STAFF_PIN=5059`, and `ALLOWED_HOSTS=.railway.app`.
3. Attach a volume and set `DATABASE_NAME=/data/db.sqlite3`.
4. Use `./build.sh` as the build command and `gunicorn salon_queue.wsgi:application` as the start command.
