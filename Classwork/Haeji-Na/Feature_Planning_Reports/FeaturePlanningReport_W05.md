# Feature Planning Report - Detail Design

## Reference Information

- **Feature Title:** User Authentication and Frontend Architecture Setup
- **Feature Number:** 01
- **Date:** May 23, 2026
- **Author:** Haeji Na
- **Team Members:** Parker Morgan, Haeji Na, Joshua Palmer, Joseph Howard Tolley, Xander Weibel

| Role | Team Member |
| :--- | :--- |
| Product Owner | Xander Weibel |
| Scrum Master | Xander Weibel |
| Tech Lead (Front-End) | Parker Morgan |
| Tech Lead (Back-End) | Joseph Howard Tolley |
| Tech Lead (Database) | Haeji Na |
| Quality Assurance | Joshua Palmer |
| CM/DM | Joshua Palmer |

---

## Traceability

- **Requirement Number (SRS Ref #):** FR1, FR2, FR3, FR4, FR5; IR1, IR2, IR4; SA3, SA4; DB1, DB8
- **Design Number (SDD Ref #):** SDD Section 2, Section 3, Section 4, Component C1, Component C5, Component C6
- **Test Plan (TPD Ref #):** FR1-FR5 verification through inspection, demonstration, unit, integration, and system testing
- **User Document:** SRS Section 1.3 and Section 3.1
- **Installation Document:** SDD Section 7
- **Software Developer Guide:** `API-README.md` and `openapi.yaml`

---

## Agile Tasking Information

### Epic Story

As a patient user,  
I want to create an account and securely log in,  
so that I can access my personal medication dashboard and manage my prescriptions.

### Value

Authentication is required before users can access medication-management features. This feature establishes the user-account structure, frontend routing, backend authentication contract, and database support required for the rest of the MVP.

### Planned Delivery

- **Version:** 1.0
- **Week:** Week 05
- **Iteration Focus:** Architecture and initial build

### Known Dependencies and Obstacles

- The `/auth/*` endpoints in `openapi.yaml` must be finalized before frontend and backend integration.
- Backend JWT behavior must match the documented authentication response.
- Password rules must be enforced by both the frontend and backend.
- Passwords must be stored as hashes rather than plain text.
- The frontend currently depends on a mock API until the real backend is connected.
- Database structure must remain aligned with the SRS and backend requirements.

### Task Tracking

- [RxNOW Kanban Board](https://miro.com/app/board/uXjVHW1B9x4=/)
- **GitHub Branch:** `feature/01-auth-frontend`
- **GitHub Project:** RXNow MVP - Iteration 1

---

# Detailed Design

## Front-End

### Workflow Description

The frontend authentication flow supports registration, login, logout, and password reset. The frontend sends requests through an authentication service and stores the returned session token after successful authentication.

### Agile Information

- **Story:** As a user, I want registration and login screens so that I can create and access my account.
- **Estimated Story Points:** 5
- **Assigned Responsible Engineer:** Parker Morgan
- **Task Tracking:** [RxNOW Kanban Board](https://miro.com/app/board/uXjVHW1B9x4=/)

### Planned Components

- `UserModel`
- `AuthState`
- `AuthController`
- Register screen
- Login screen
- Password reset screen
- Authentication service

### Planned Code Locations

- `src/models/UserModel.ts`
- `src/state/AuthState.ts`
- `src/controllers/AuthController.ts`
- `src/views/RegisterView.tsx`
- `src/views/LoginView.tsx`
- `src/views/PasswordResetView.tsx`
- `src/services/AuthService.ts`

---

## Back-End

### Business Logic

The backend must validate registration and login requests, enforce password requirements, hash passwords before storage, locate users by email, and return authentication tokens after successful login.

### Agile Information

- **Story:** As the system, I need to validate credentials and issue authentication tokens so that user sessions are secure.
- **Estimated Story Points:** 5
- **Assigned Responsible Engineer:** Joseph Howard Tolley
- **Task Tracking:** [RxNOW Kanban Board](https://miro.com/app/board/uXjVHW1B9x4=/)

### Required Operations

- Create a user account
- Authenticate a user
- Request a password reset
- Confirm a password reset
- Log out a user

### Expected API Endpoints

- `POST /auth/register`
- `POST /auth/login`
- `POST /auth/password-reset/request`
- `POST /auth/password-reset/confirm`
- `POST /auth/logout`

---

## Database

### Data Relationship Logic

One user can own multiple medication records.

```mermaid
erDiagram
  USER {
    int user_id PK
    string email UK
    string password_hash
    datetime created_at
  }

  USER ||--o{ MEDICATION : owns
```

### Agile Information

- **Story:** As the system, I need a user table with securely stored password hashes so that user credentials can be managed safely.
- **Estimated Story Points:** 2
- **Assigned Responsible Engineer:** Haeji Na
- **Task Tracking:** [RxNOW Kanban Board](https://miro.com/app/board/uXjVHW1B9x4=/)

### Week 05 Database Work

During Week 05, I completed or worked on the following database-planning tasks:

1. Prepared the database tasks for Feature 01.
2. Created a database data-flow diagram.
3. Reviewed authentication database requirements.
4. Designed the `USER` table structure.
5. Defined the primary key and unique email constraint.
6. Researched secure password storage.
7. Reviewed the one-to-many user-to-medication relationship.
8. Updated the database schema to align with SRS requirements.

### Table Description

The `USER` table stores registered user accounts.

| Column | Purpose |
| :--- | :--- |
| `user_id` | Primary key for each user |
| `email` | Unique user email address |
| `password_hash` | One-way hash of the user's password |
| `created_at` | Date and time the account was created |

### Planned Database Operations

- **Create:** Insert a new user
- **Read:** Find a user by email
- **Update:** Update a password hash
- **Delete:** Not required for the Week 05 MVP scope

### Planned Database Artifacts

- `db/migrations/001_create_users.sql`
- `db/seeds/dev_seed.sql`
- `EntityRelationshipDiagram.md`
- `src/repositories/UserRepository.py`

---

## Review

- [x] Reference information is completed.
- [x] Traceability information is documented.
- [x] Agile information is documented.
- [x] Frontend, backend, and database design responsibilities are identified.
- [x] The database responsible engineer is listed as Haeji Na.
- [x] Week 05 database work is listed.
- [x] Task tracking is linked to the RxNOW Kanban board.
- [ ] Add direct GitHub issue numbers if separate feature sub-issues are created.
- [ ] Add direct links to completed SQL, ERD, commit, or pull request artifacts when available.
- [ ] Confirm final review with all team members.
