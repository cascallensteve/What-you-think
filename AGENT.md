# AGENT.md - WhisperLink Anonymous Feedback Platform

## Commands
- **Development server**: `python manage.py runserver`
- **Tests**: `python manage.py test` (single app: `python manage.py test feedback`)
- **Migrations**: `python manage.py makemigrations` then `python manage.py migrate`
- **Static files**: `python manage.py collectstatic --noinput`
- **Admin user**: `python manage.py createsuperuser`
- **Setup**: `python setup.py` (installs dependencies and runs initial setup)

## Architecture
- Django 5.1.5 backend with PostgreSQL (Supabase)
- Single Django app: `feedback` (anonymous feedback system)
- WhiteNoise for static files, Vercel deployment ready
- Together AI integration for feedback processing
- Templates in `feedback/templates/`, static files in `feedback/static/`

## Code Style
- Django conventions: snake_case for variables/functions, PascalCase for models
- Models use UUID fields for security (unique_link, delete_token)
- Environment variables for secrets (.env file)
- Error handling middleware in `feedback.middleware.DatabaseErrorMiddleware`
- Templates extend base.html, use Django forms for validation
- Use `login_required` decorator for protected views
