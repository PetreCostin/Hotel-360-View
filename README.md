# Hotel 360 View

An interactive web page for showcasing hotels through 360-degree virtual tours.

## Tech Stack

- **Frontend**: Angular with built-in i18n (en-US)
- **Backend**: Django with i18n support (en-us)

## Security Features

### Frontend
- Content Security Policy (CSP)
- XSS protection headers
- Environment-based configuration
- Secure secret management

### Backend
- JWT authentication
- CORS protection
- Rate limiting
- Environment-based secrets
- Password validation
- HTTPS enforcement (production)

## Setup

### Prerequisites
- Node.js 18+ and npm
- Python 3.10+
- pip

### Frontend Setup

1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create environment file:
```bash
cp .env.example .env
# Edit .env with your configuration
```

4. Start development server:
```bash
npm start
```

Frontend will run on http://localhost:4200

### Backend Setup

1. Navigate to backend directory:
```bash
cd backend
```

2. Create virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create environment file:
```bash
cp .env.example .env
# Edit .env with your configuration
# IMPORTANT: Generate a new SECRET_KEY for production!
```

5. Run migrations:
```bash
python manage.py migrate
```

6. Create superuser (optional):
```bash
python manage.py createsuperuser
```

7. Start development server:
```bash
python manage.py runserver
```

Backend will run on http://localhost:8000

## Environment Variables

### Frontend (.env)
- `API_URL`: Backend API endpoint

### Backend (.env)
- `SECRET_KEY`: Django secret key (generate a new one!)
- `DEBUG`: Debug mode (True/False)
- `ALLOWED_HOSTS`: Comma-separated list of allowed hosts
- `CORS_ALLOWED_ORIGINS`: Comma-separated list of allowed CORS origins
- `JWT_SECRET_KEY`: JWT signing key
- Database settings (optional, defaults to SQLite)

## Security Considerations

⚠️ **IMPORTANT**: 
- Never commit `.env` files to version control
- Generate strong SECRET_KEY and JWT_SECRET_KEY for production
- Set DEBUG=False in production
- Configure proper ALLOWED_HOSTS and CORS_ALLOWED_ORIGINS
- Use HTTPS in production
- Keep dependencies updated

## Internationalization

- Frontend uses Angular's built-in i18n with `en-US` as the source locale
- Backend uses Django's i18n framework with `en-us` as the default language

### Extract translations

Frontend:
```bash
cd frontend
ng extract-i18n
```

Backend:
```bash
cd backend
python manage.py makemessages -l en_US
```

## API Documentation

JWT Authentication endpoints:
- POST `/api/token/` - Obtain token pair (access + refresh)
- POST `/api/token/refresh/` - Refresh access token

## Contributing

Please read SECURITY.md for details on our security policy and how to report vulnerabilities.

## License

This project is open source and available under the MIT License.