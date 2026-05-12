# RXNOW Backend Visual Representations

## 1. Backend System Architecture

```mermaid
flowchart TD
    A[Front-End] --> B[API]

    B --> C[Authentication Service]
    B --> D[Medication Service]
    B --> E[Refill Service]
    B --> F[Notification Service]

    C --> G[(Database)]
    D --> G
    E --> G
    F --> G
```

---

# 2. Backend Server Components

```mermaid
flowchart LR
    subgraph Backend_Server
        A[Auth Service] --> B[Session Management]
        C[Medication Service] --> D[Supply Calculator]
        E[Notification Service]
        F[Refill Service]
    end
```

---

# 3. Medication CRUD Flow

```mermaid
flowchart TD
    A[User Request] --> B[Medications]
    B --> C[Validation]
    C --> D[Medication Service]

    D --> E[(Database)]
    D --> F[Supply Calculator]

    E --> G[Response]
    F --> G
```

---

# 4. Authentication Workflow

```mermaid
sequenceDiagram
    participant Client
    participant API as API/Auth
    participant DB as Database
    participant Auth as Token Generator

    Client->>API: Login Request
    API->>DB: Validate Credentials
    DB-->>API: User Found
    API->>Auth: Generate Token
    Auth-->>API: JWT Token
    API-->>Client: Authentication Response
```

---

# 5. Refill Workflow Diagram

```mermaid
flowchart TD
    A[User Selects Medication] --> B[Check Supply Level]
    B --> C{Low Supply?}

    C -- Yes --> D[Show Refill Button]
    D --> E[Create Refill Request]
    E --> F[Set Status = Pending]
    F --> G[Save to Database]
    G --> H[Return Confirmation]

    C -- No --> I[Continue Monitoring]
```

---

# 6. Notification Engine Logic

```mermaid
flowchart TD
    A[Medication Updated] --> B[Calculate Days Remaining]
    B --> C{Days Remaining <= 7?}

    C -- Yes --> D[Alert]
    D --> E[Send Notification]

    C -- No --> F[No Notification Needed]
```
---

# 7. Initial Backend Folder Structure (js example)

```text
backend/
│
├── controllers/
│   ├── authController.js
│   ├── medicationController.js
│   ├── refillController.js
│   └── notificationController.js
│
├── services/
│   ├── authService.js
│   ├── medicationService.js
│   ├── refillService.js
│   └── notificationService.js
|
├── database/
│   ├── schema.sql
│   └── connection.js
│
└── server.js
```

---

# 8. Backend Responsibilities Summary

| Backend Area        | Responsibility                        |
| ------------------- | ------------------------------------- |
| Authentication      | Login, registration, token validation |
| Medication Service  | CRUD operations for medications       |
| Supply Calculator   | Calculate remaining medication days   |
| Notification Engine | Generate alerts                       |
| Refill Workflow     | Create refill requests                |
| API                 | Handle communication from front-end   |
| Database            | Handle communication with database    |
| Validation          | Ensure clean and safe input           |
| Logging             | Record backend events and errors      |
