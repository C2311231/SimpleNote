# Simple Note

A small Flask notes application with user authentication and note creation that I found in a old backup.

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

Start the Flask application:

```bash
python main.py
```

Then open `http://127.0.0.1:5000` in your browser.

## Database

The app uses SQLite and creates `instance/database.db` automatically on first run.

## Notes

- The app currently uses a hard-coded `SECRET_KEY` in `app/__init__.py`. For public deployments please, change this to a secure randomly generated secret key.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

