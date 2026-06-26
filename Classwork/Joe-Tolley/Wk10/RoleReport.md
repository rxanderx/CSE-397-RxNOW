# Role Planning Report - Week 10 RxNow

### Reference Information (5 pts)

---

* **Role**: Back-End Lead

* **Date**: 2026-06-26

* **Author**: Joe Tolley

* **Team Members**:

| Role                  | Team member name |
| --------------------- | ---------------- |
| Product Owner         | Xander Weibel    |
| Scrum Master          | Kelson Gneiting  |
| Tech Lead (Front-End) | Xander Weibel    |
| Tech Lead (Back-End)  | Joseph Tolley    |
| Tech Lead (Database)  | Haeji Na         |
| Quality Assurance     | Joshua Palmer    |
| CM/DM                 | Joshua Palmer    |

---

### Agile Tasking Information (10 pts)

* **Epic Story**:

As Back-End Lead, I wanted to complete the transition to the local-first architecture by integrating the `authorization_local` branch into `main`, validating the localized authentication workflow, and updating the project documentation so it accurately reflects the current implementation. This iteration focused on stabilizing the application's architecture, supporting offline functionality, and ensuring the entire team is working from the same design documents.

* **Story Point/Value**: **5**

* **Planned Delivery**: **v4.0 — Weeks 10–11**

* **Schedule**:

- Merge `local_authorization` into `main`
- Verify localized authentication and offline functionality
- Update SRS documentation to reflect the new architecture
- Rewrite SDD to document the local-first design
- Update architecture diagrams and repository documentation
- Coordinate with teammates to ensure documentation matches implementation

* **Known Dependencies/Obstacles**:

The largest dependency was ensuring the entire team was aligned on the architectural transition. Documentation, implementation, and repository organization all needed to reflect the same local-first design after the merge. Provider redesign and local authentication also required coordination with the front-end and database leads.

---

### Implementation (80 pts: 10 pts each)

The following tasks were completed during this iteration:

* [x] Merged the **`local_authorization`** branch into [**`main`**](https://github.com/louisramos23/RXNOW/tree/main)
* [x] Verified localized authentication workflow and offline application functionality
* [x] Updated the [**Software Requirements Specification (SRS)**](https://github.com/louisramos23/RXNOW/blob/main/Documents/SoftwareRequirementsSpecification.md) to document the local-first architecture and provider entity redesign
* [x] Rewrote the [**Software Design Document (SDD)**](https://github.com/louisramos23/RXNOW/blob/main/Documents/SoftwareDesignDocumentSDD.md) to reflect the current implementation using Flutter, Hive, and Flutter Secure Storage
* [x] [Updated architecture diagrams](https://github.com/rxanderx/CSE-397-RxNOW/blob/main/Teamwork/backEnd-visuals.md) to remove the previous backend-centric design
* [x] [Implemented test plan to check valid functionality](https://github.com/louisramos23/RXNOW/blob/main/Documents/RxNow-Test-Plan-v0.2.pdf)
* [x] Contribution to the User Guide
* [x] Reviewed the completed architecture to support future expansion such as cloud synchronization and provider integration

---

### Review (5 pts)

* [x] All elements of the form are filled out

  * [x] Reference
  * [x] Agile
  * [x] Implementation

* [x] Epic Story has been planned for the project repository

* [x] Implementation tasks have been coordinated with the development team

* [x] Documentation has been updated to reflect the merged architecture

* [x] Team members have reviewed or will review the completed changes during the next planning meeting
