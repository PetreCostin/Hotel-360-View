# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please report it by emailing the repository owner directly. Please do not open a public issue.

### What to include in your report:

- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact
- Suggested fix (if any)

### What to expect:

- Acknowledgment of your report within 48 hours
- Regular updates on the progress of fixing the vulnerability
- Credit in the security advisory (unless you prefer to remain anonymous)

## Security Best Practices

### Frontend (Angular)
- All user inputs are sanitized using Angular's built-in DomSanitizer
- Content Security Policy (CSP) headers are configured
- Environment variables are used for sensitive configuration
- Never commit `.env` files or secrets to version control

### Backend (Django)
- SECRET_KEY and sensitive settings are stored in environment variables
- CORS is configured to allow only specific origins
- JWT authentication is used for API endpoints
- Rate limiting is enabled to prevent abuse
- Password validation requires minimum 8 characters
- HTTPS is enforced in production
- CSRF protection is enabled
- XSS and clickjacking protections are active

## Dependencies

Both frontend and backend dependencies are regularly updated to patch security vulnerabilities. Consider enabling Dependabot for automated security updates.