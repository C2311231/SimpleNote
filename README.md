# Simple Note

A small Flask notes application with user authentication and note creation that I recovered an old backup.

## Features

- Email/password based sign-up and login
- Password hashing with Werkzeug
- User session management with Flask-Login
- SQLite database via Flask-SQLAlchemy
- Create notes from the homepage
- Delete notes via AJAX request

## Project structure

- `main.py` - application entry point
- `app/__init__.py` - app factory, database setup, and login manager
- `app/auth.py` - authentication routes (`/login`, `/logout`, `/sign-up`)
- `app/models.py` - SQLAlchemy models for `User` and `Note`
- `app/views.py` - authenticated homepage and note deletion logic
- `app/templates/` - Jinja2 templates for login, sign-up, and home pages
- `requirements.txt` - pinned Python dependencies

## Requirements

- Python 3.11+ (recommended)
- `pip` package manager

## Installation

1. Clone or copy the repository.

2. Create and activate a virtual environment:

    ```bash
    python -m venv .venv
    source .venv/bin/activate
    ```

3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## Running the app

Before starting the app, set a secure `SECRET_KEY` in your environment:

### Linux/macos

```bash
export SECRET_KEY="$(python -c 'import secrets; print(secrets.token_urlsafe(32))')"
```

### Windows

```powershell
$env:SECRET_KEY = python -c "import secrets; print(secrets.token_urlsafe(32))"
```

Then start the Flask application:

```bash
python main.py
```

Then open `http://127.0.0.1:5000` in your browser.

## Database

The app uses SQLite and creates `instance/database.db` automatically on first run.

## Notes

- The app reads `SECRET_KEY` from the `SECRET_KEY` environment variable in `app/__init__.py`.
- If `SECRET_KEY` is not set, the app falls back to a placeholder value, which is not safe for production.
- For public deployments, always generate and use a strong random secret key.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
