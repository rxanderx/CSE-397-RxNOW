# RXNOW Database Visual Representations

## Purpose

This document provides a visual overview of the RXNOW database design. It shows the main data entities, their relationships, and how the database supports medication tracking, refill requests, and low-supply notification workflows.


---

## 1. Database System Architecture

```mermaid
flowchart TD
    A[Authentication Service] --> DB[(RXNOW Database)]
    B[Medication Service] --> DB
    C[Refill Service] --> DB
    D[Notification Service] --> DB
```

---

## 2. Main Entity Relationship Diagram

```mermaid
erDiagram
    USER ||--o{ MEDICATION : owns
    PROVIDER ||--o{ MEDICATION : associated_with
    MEDICATION ||--o{ REFILL_REQUEST : creates
    PROVIDER ||--o{ REFILL_REQUEST : receives
    MEDICATION ||--o{ NOTIFICATION_EVENT : triggers

    USER {
        int user_id PK
        string email
        string password_hash
    }

    MEDICATION {
        int medication_id PK
        int user_id FK
        int provider_id FK
        string name
        string dosage
        int pills_remaining
        int pills_per_day
    }

    PROVIDER {
        int provider_id PK
        string provider_name
    }

    REFILL_REQUEST {
        int refill_request_id PK
        int medication_id FK
        int provider_id FK
        string request_message
        string status
        datetime created_at
    }

    NOTIFICATION_EVENT {
        int notification_id PK
        int medication_id FK
        int threshold_days
        datetime triggered_at
    }
```

---

## 3. Database Entity / Table Descriptions

### User

Stores account information for each RXNOW user. The email is used as the login identifier, and the password is stored only as a secure hash.

| Column | Description |
| --- | --- |
| `user_id` | Primary key for the user |
| `email` | Unique login email for the user |
| `password_hash` | Hashed password used for authentication |

---

### Medication

Stores each medication record tracked by a user. A medication record belongs to one specific user, even if other users take a medication with the same name.

| Column | Description |
| --- | --- |
| `medication_id` | Primary key for the medication record |
| `user_id` | Foreign key linking the medication to the user |
| `provider_id` | Foreign key linking the medication to a provider |
| `name` | Medication name |
| `dosage` | Medication dosage |
| `pills_remaining` | Number of pills currently remaining |
| `pills_per_day` | Number of pills taken each day |

**Calculated value:**  
`days_remaining = pills_remaining / pills_per_day`

This value can be calculated by the system rather than permanently stored in the table.

---

### Provider

Stores provider information connected to a medication or refill request.

| Column | Description |
| --- | --- |
| `provider_id` | Primary key for the provider |
| `provider_name` | Name of the medical provider |

---

### RefillRequest

Stores refill request information created from a medication record.

| Column | Description |
| --- | --- |
| `refill_request_id` | Primary key for the refill request |
| `medication_id` | Foreign key linking the request to a medication |
| `provider_id` | Foreign key linking the request to the provider |
| `request_message` | Refill message generated for the request |
| `status` | Current status, such as Pending or Sent |
| `created_at` | Date and time the request was created |

---

### NotificationEvent

Tracks low-supply notification events for a medication.

| Column | Description |
| --- | --- |
| `notification_id` | Primary key for the notification event |
| `medication_id` | Foreign key linking the event to a medication |
| `threshold_days` | Low-supply level that triggered the event, such as 7, 3, or 1 |
| `triggered_at` | Date and time the notification was triggered |

---

## 4. Relationship Summary

| Relationship | Meaning |
| --- | --- |
| `User 1 → many Medication` | One user can track many medication records |
| `Provider 1 → many Medication` | One provider can be connected to many medications |
| `Medication 1 → many RefillRequest` | One medication can create multiple refill requests over time |
| `Provider 1 → many RefillRequest` | One provider can receive many refill requests |
| `Medication 1 → many NotificationEvent` | One medication can trigger multiple low-supply notification events |

---

## 5. Overall Database Workflow

```mermaid
flowchart TD
    A[User Creates Account or Logs In] --> B[(User Table)]

    C[User Adds or Updates Medication] --> D[Medication Service]
    D --> E[(Medication Table)]
    E --> F[Medication Data Returned to Dashboard]

    F --> G[Calculate Days Remaining]
    G --> H{Low Supply Threshold Reached?}

    H -- Yes --> I[(NotificationEvent Table)]
    I --> J[Notification Displayed to User]

    H -- No --> K[Continue Monitoring]

    L[User Starts Refill Request] --> M[Refill Service]
    M --> N[(RefillRequest Table)]
    N --> O[Refill Status Displayed to User]
```

---

## 6. Refill Request Database Storage Flow

```mermaid
flowchart TD
    A[User Selects Medication] --> B[Refill Service Reads Medication Data]
    B --> C[(Medication Table)]
    C --> D[Generate Refill Request Message]
    D --> E[Create Refill Request Record]
    E --> F[(RefillRequest Table)]
    F --> G[Set Status to Pending or Sent]
    G --> H[Display Confirmation to User]
```

---

## 7. Notification Event Database Storage Flow

```mermaid
flowchart TD
    A[Medication Supply Updated] --> B[Calculate Days Remaining]
    B --> C{Days Remaining less than or equal to 7, 3, or 1?}

    C -- No --> D[No Notification Needed]
    C -- Yes --> E[Check Notification History]
    E --> F[(NotificationEvent Table)]
    F --> G{Already Triggered at This Threshold?}

    G -- Yes --> H[Do Not Repeat Notification]
    G -- No --> I[Create Notification Event]
    I --> J[Display Low-Supply Alert]
```

---

## 8. Proposed SQL / Database Folder Structure

```text
database/
│
├── schema.sql
├── seed.sql
├── migrations/
│   └── initial_schema.sql
│
├── queries/
│   ├── user_queries.sql
│   ├── medication_queries.sql
│   ├── provider_queries.sql
│   ├── refill_request_queries.sql
│   └── notification_queries.sql
│
└── README.md
```

---

## 9. Database Responsibilities Summary

| Database Area | Responsibility |
| --- | --- |
| User Data | Store account login information |
| Medication Data | Store medications tracked by each user |
| Provider Data | Store provider names connected to medications/refills |
| Refill Requests | Store refill messages and request status |
| Notification Events | Track low-supply alert events and prevent repeated alerts |
| Relationships | Connect users, medications, providers, refill requests, and notifications |
| Validation Support | Help enforce clean and usable data |
| Query Support | Provide reliable data for backend services |
