# Backend Technology Stack

The Rwooga backend is a robust RESTful API built with Python and Django.

## Core Framework
- **Language**: Python 3.12.3
- **Framework**: Django 5.x
- **API Toolkit**: Django REST Framework (DRF)
- **Database**: PostgreSQL (Relational data)

## Authentication & Security
- **JWT**: `djangorestframework-simplejwt` for stateless token authentication.
- **Documentation**: `drf-spectacular` for OpenAPI 3.0 schema generation and Swagger UI.
- **CORS**: `django-cors-headers` for cross-origin security management.

## External Integrations
- **Media Storage**: Cloudinary (Optimized image and video delivery).
- **Payments**: Paypack (MoMo integration).
- **Email**: SMTP with branded HTML templates.

## Infrastructure
- **Deployment**: Koyeb (Cloud hosting).
- **Web Server**: Gunicorn (WSGI HTTP Server).
- **Containerization**: Docker (Optional for development/staging consistency).
