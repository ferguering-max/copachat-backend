# CopaBot — Backend Flask

## Local setup

Requirements: Python 3.11+ and `uv`.

```bash
uv sync
```

Copy `.env.example` to `.env`, then set your real `GROQ_API_KEY`.
Set `FRONTEND_ORIGIN` to the exact frontend URL. For local static testing this can be `http://127.0.0.1:5500`; for production use your deployed website origin, e.g. `https://meu-copabot.netlify.app`.

```bash
uv run python app.py
```

The API listens on port 5000. Health endpoint: `/api/health`.

## Deploy

Deploy this directory as a Python web service on a host that supports Flask. Build/install command: `uv sync`; start command: `uv run python app.py` (or use the provider's recommended WSGI server for production).

Set environment variables in the hosting dashboard:
- `GROQ_API_KEY` (secret)
- `GROQ_MODEL` (optional)
- `FRONTEND_ORIGIN` (your published frontend origin)
- `PORT` (usually supplied by the host)
- `FLASK_DEBUG=false`

Do not upload `.env` or expose the Groq key in the frontend.
