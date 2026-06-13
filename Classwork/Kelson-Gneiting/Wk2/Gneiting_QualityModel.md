# Kelson Gneiting Quality Characteristic Analysis and Model

## Quality Model 1: Performance and Responsiveness
### Goal
Provide a fast, low-friction user experience for medication workflows.

### Quality Attribute Focus
* Time-to-response for dashboard and medication actions
* Consistent behavior under normal and moderate data load

### Quality Scenarios
* Source: Authenticated user
* Stimulus: User logs in and opens dashboard
* Environment: Normal operating conditions
* Artifact: Front end + API + database response path
* Response: Dashboard is interactive within target time
* Response Measure: Dashboard load aligns with MVP performance target

* Source: Authenticated user
* Stimulus: User creates/edits/deletes medication
* Environment: Normal operating conditions
* Artifact: Medication CRUD workflow
* Response: Save confirmation returns quickly and accurately
* Response Measure: CRUD response aligns with defined timing expectations

### Design Tactics
* Keep API payloads minimal for dashboard and list calls.
* Validate early to reduce unnecessary backend processing.
* Optimize data queries for user-scoped medication retrieval.

### Summary
Performance quality is critical because user trust depends on quick and reliable feedback, especially for daily medication checks.

## Quality Model 2: Security and Data Protection
### Goal
Protect sensitive account and medication information while preserving usability.

### Quality Attribute Focus
* Authentication integrity
* Input validation and authorization
* Safe storage of credentials

### Quality Scenarios
* Source: User or attacker-equivalent invalid request
* Stimulus: Invalid login attempts or malformed input submission
* Environment: Production-like API behavior
* Artifact: Authentication and validation layers
* Response: Reject invalid requests with safe error handling
* Response Measure: No unauthorized access and stable system state

* Source: Internal storage inspection
* Stimulus: Review of persisted account records
* Environment: Database inspection context
* Artifact: User credential storage
* Response: Passwords exist only as one-way hashes
* Response Measure: No plaintext password values in persistent store

### Design Tactics
* Enforce password policy and secure hashing.
* Apply ownership checks on all user-scoped resources.
* Standardize validation and error responses across endpoints.

### Summary
Security quality must be built into every workflow so speed and simplicity do not create privacy or data integrity risks.

## Quality Model 3: Maintainability and Adaptability
### Goal
Ensure future teams can extend and maintain RXNOW without excessive rework.

### Quality Attribute Focus
* Modularity of system layers
* Requirement-to-test traceability
* Low coupling between components

### Quality Scenarios
* Source: Future student developer
* Stimulus: Add or modify a feature in one subsystem
* Environment: Ongoing semester-to-semester handoff
* Artifact: Front end, back end, and database module boundaries
* Response: Change remains localized with minimal side effects
* Response Measure: Limited file/module touch surface for feature updates

* Source: QA and release process
* Stimulus: Requirement update or API contract change
* Environment: Sprint integration and regression cycles
* Artifact: Traceability matrix and automated/manual tests
* Response: Impacted tests are quickly identified and updated
* Response Measure: Requirement coverage remains complete and verifiable

### Design Tactics
* Keep clear contracts between FE, BE, and DB layers.
* Use requirement IDs in tests and issue tracking.
* Prefer simple, explicit data models over hidden side effects.

### Summary
Maintainability quality is essential for this project context because continuity between teams is part of long-term product success.

