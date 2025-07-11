# 📋 Project Requirements – Airbnb Backend Clone

This document outlines the core requirements for building the backend clone of Airbnb. It includes functional and non-functional requirements, technology stack, and system design expectations.

---

## 🧩 Functional Requirements

### 1. User Management
- Users must be able to register and log in securely.
- Users must have roles (guest, host, admin).
- JWT-based authentication system.
- Users can view, edit, or delete their profile.

### 2. Property Management
- Hosts can list new properties with fields: title, description, location, price per night, images.
- Hosts can update and delete their properties.
- All users can browse and search for properties with filters.

### 3. Booking System
- Guests can book properties for specific date ranges.
- Users can view, cancel, or manage their bookings.
- Bookings must prevent date conflicts for the same property.

### 4. Payment Integration
- Users can make payments via a simulated or real gateway.
- Payment records must be linked to bookings.
- Payment status (pending, success, failed) must be tracked.

### 5. Review System
- Users can leave reviews only after staying at a property.
- Each property displays aggregated ratings and individual reviews.

### 6. Admin Capabilities
- Admins can manage users, properties, and reviews.
- Admin dashboard to monitor transactions and system status.

---

## 🛠️ Non-Functional Requirements

- **Performance**: APIs should respond within 300ms under average load.
- **Scalability**: Architecture must allow horizontal scaling using Docker and container orchestration.
- **Security**:
  - Encrypted passwords and sensitive data.
  - Input validation and protection from common vulnerabilities (SQL injection, CSRF, XSS).
- **Reliability**: CI/CD pipelines must ensure automated tests run on every push.
- **Usability**: API documentation should be available via Swagger or Postman.

---

## 🏗️ Technology Stack

| Component        | Technology              |
|------------------|--------------------------|
| Framework        | Django                   |
| API Layer        | Django REST Framework / GraphQL |
| Database         | PostgreSQL               |
| Async Tasks      | Celery + Redis           |
| Caching/Session  | Redis                    |
| Auth             | JWT (SimpleJWT or similar) |
| DevOps           | Docker, GitHub Actions   |
| Testing          | Pytest / Django TestCase |
| API Docs         | DRF Docs / Swagger       |

---

## 🗄️ Database Models Overview

### Users
- id, name, email, password, role, date_joined

### Properties
- id, owner_id, title, description, location, price_per_night

### Bookings
- id, user_id, property_id, start_date, end_date, total_price

### Reviews
- id, user_id, property_id, rating, comment, created_at

### Payments
- id, booking_id, user_id, amount, payment_date, status

---

## 🧪 Testing Requirements

- Unit tests for all major modules (user, booking, property, payment).
- Integration tests for critical flows.
- Test coverage goal: **≥ 80%**.

---

## 🚀 Deployment Requirements

- Use Docker for local and production deployment.
- GitHub Actions to run tests and deploy to production server.
- Use environment variables for secrets and config.

---

## 📜 API Documentation

- All endpoints must be documented.
- Use Django REST Framework's built-in docs or Swagger/OpenAPI.
- Include:
  - Request/response examples
  - Auth instructions
  - Error codes

---

## ✅ Success Criteria

- All core features implemented with a secure, scalable backend.
- Clear documentation and test coverage.
- CI/CD pipeline functional and tested.
- System able to handle at least 100 concurrent users.

---

> 🧠 This document evolves as the project grows. Update as needed for changes in scope or features.
