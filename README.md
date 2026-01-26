# Hotel 360 View

An interactive web page for showcasing hotels through 360-degree virtual tours.

## Tech Stack

- **Frontend**: Angular with built-in i18n (en-US)
- **Backend**: Django with i18n support (en-us)

## Setup

### Frontend
```bash
cd frontend
npm install
npm start
```

### Backend
```bash
cd backend
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## Internationalization

- Frontend uses Angular's built-in i18n with `en-US` as the source locale
- Backend uses Django's i18n framework with `en-us` as the default language
