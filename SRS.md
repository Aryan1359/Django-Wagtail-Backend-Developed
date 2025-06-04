## 📘 Software Requirements Specification (SRS)

**Project Title:** Django + Wagtail + React + Bootstrap Base Template

**Development Environment:** Anaconda VM (local), Docker (deployment), AWS (cloud hosting)

---

### 1. Introduction

**1.1 Purpose**
The purpose of this SRS is to define a reusable web application template that includes Django, Wagtail CMS, React frontend, and Bootstrap for styling. This base template should be easy to clone and use for new projects, support local development using Anaconda, and be deployable using Docker on AWS or similar platforms.

**1.2 Scope**
This template will:

- Support CMS-based content management using Wagtail
- Provide modern frontend UI with React and Bootstrap
- Offer headless/hybrid architecture via REST APIs or Wagtail’s content API
- Be easily deployable with Docker and configurable with environment variables
- Include useful Wagtail extensions like StreamField, Image Gallery, and Forms

**1.3 Audience**
Targeted at beginner to intermediate developers who want a fast and scalable foundation for full-stack Django applications with CMS features and rich front-end interactivity.

**1.4 Definitions**

- **SRS:** Software Requirements Specification
- **CMS:** Content Management System
- **DRF:** Django REST Framework

---

### 2. Overall Description

**2.1 System Features**

- Modular architecture with clearly separated backend and frontend
- Editable content pages via Wagtail admin
- REST API endpoints for frontend integration
- Styled UI components using Bootstrap 5
- Dockerized for consistent environment

**2.2 User Classes and Characteristics**

- **Developers:** Use the base to create new projects
- **Content Editors:** Use Wagtail admin to manage site content
- **End Users:** Visit and interact with the deployed site

**2.3 Operating Environment**

- Python 3.11+ (Conda)
- Node.js (LTS version)
- Django 5.x
- Wagtail 6.x
- React 18.x
- Bootstrap 5.x
- Redis (for Celery)
- PostgreSQL (default DB)
- Docker (v20+), Docker Compose (v2+)
- AWS, Heroku, Render, or DigitalOcean for deployment

**2.4 Design and Implementation Constraints**

- Must run on Anaconda virtual environments
- Must be compatible with Docker for deployment
- Code should be modular, readable, and reusable

**2.5 Assumptions and Dependencies**

- Developer has basic familiarity with Python, Django, and terminal usage
- Internet connection is available for fetching packages

---

### 3. System Features

**3.1 Wagtail CMS Features**

- StreamField for rich flexible content
- Custom page types (e.g., HomePage, BlogPage)
- Image gallery using ImageChooserBlock
- Contact form using `wagtail.contrib.forms`
- Site-wide settings using `wagtail.contrib.settings`
- Admin interface extensions via `wagtail.contrib.modeladmin`

**3.2 Frontend (React + Bootstrap)**

- Separate React app with `create-react-app` or Vite
- Bootstrap styling
- Axios or Fetch API to call Django/Wagtail API
- Basic reusable components (e.g., Navbar, Footer, Form components)

**3.3 API Layer**

- Django REST Framework (DRF) endpoints for core data
- Wagtail Content API for headless integration

**3.4 User Authentication**

- Django-based login/signup with optional token support for frontend auth (JWT or Session)

**3.5 DevOps & Deployment**

- Dockerfile for Django and frontend
- Docker Compose for local dev and CI
- `.env` file support for secrets/config
- Optional AWS ECS/Lightsail deploy script

---

### 4. External Interface Requirements

**4.1 User Interfaces**

- Django Admin: Superuser and staff content editing
- Wagtail Admin: CMS editors create/update pages
- React Frontend: Dynamic pages and components

**4.2 Hardware Interfaces**

- Local machine with Conda
- AWS or similar platform for hosting

**4.3 Software Interfaces**

- PostgreSQL (local or cloud DB)
- Redis (for Celery)
- SMTP/SendGrid for email delivery

**4.4 Communications Interfaces**

- HTTPS for all APIs and public-facing web access

---

### 5. Nonfunctional Requirements

**5.1 Performance**

- Load time < 2s on AWS-hosted version
- Asynchronous task handling via Celery

**5.2 Scalability**

- Scalable using Docker containers and cloud instances

**5.3 Security**

- HTTPS, CSRF protection, secure session handling
- Environment variables for secrets

**5.4 Maintainability**

- Modular code layout
- Comments and docstrings required for key files

**5.5 Portability**

- Compatible with any cloud platform supporting Docker
- Runs on Windows/Linux/macOS (via Conda or Docker)

---

### 6. Future Enhancements

- Add support for GraphQL
- Add multi-language (i18n) support via Wagtail locales
- Add image optimization and CDN integration
- Create a Cookiecutter version for easier reuse

---

### 7. Appendices

- `environment.yml` for Conda
- `requirements.txt` for pip
- Folder structure diagram
- Deployment checklist (Docker + AWS)
- `.env.example` configuration template
