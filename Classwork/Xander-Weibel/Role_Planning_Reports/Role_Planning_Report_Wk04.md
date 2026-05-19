# Role Planning Report - Detail Design

### Reference Information (5 pts)

---
* **Role**: Product Owner / Scrum Master / Tech Lead (Front-End)
* **Date**: May 19, 2026
* **Author**: Xander Weibel
* **Team Members**: Haejin Na, Joshua Palmer, Joseph Howard Tolley, Xander Weibel

| Role | Team member name |
| :--- | :--- |
| **Product Owner** | Xander Weibel |
| **Scrum Master** | Xander Weibel |
| **Tech Lead (Front-End)** | Xander Weibel |
| Tech Lead (Back-End) | Joe Tolley |
| Tech Lead (Database) | Haeji Na |
| Quality Assurance | Joshua Palmer |
| CM/DM | Joshua Palmer |

----
### Agile Tasking Information (10 pts)

* **Epic Story**: 
  > As a unified Product Owner, Scrum Master, and Front-End Tech Lead,  
  > I want to plan, manage, and execute systemic sprint objectives spanning product backlogs, agile team coordination, and front-end user interfaces throughout the iteration cycles,  
  > so that our project maintains traceable quality assurance, strict adherence to milestone dates, and results in a functional, stakeholder-approved core MVP.
* **Story Point/Value**: 5 (Reflects complex multi-role collaboration and cross-functional dependency management)
* **Planned Delivery**: Versions 0.0 through 6.0 (Full Semester Lifecycle)
* **Schedule**: Weeks 3 through 14
* **Known Dependencies/Obstacles**: 
    * Fast turnaround needed on asset/NDA sign-offs from team members.
    * Balancing strict course structural deadlines with Louis's agile philosophy of prioritizing "core features first."
    * Minimizing code block bottlenecks between front-end UI components and underlying back-end APIs.
* **GitHub**
    * **GitHub Issue Number**: #101
    * **GitHub Branch**: '[RXNOW](https://github.com/louisramos23/RXNOW)'
    * **GitHub Project**: `RXNOW Core MVP`

---

### Implementation (80 pts: 10 pts each)

The following 8 core sub-tasks map out my specific responsibilities across the entire software development lifecycle, utilizing the mandatory timeline benchmarks provided by the stakeholder and instructor.

- [ ] **(1) Plan Tasking: #102_Backlog Prioritization & Elicitation Alignment (Week 3 / v0.0)**
    * **Role Focus:** Product Owner / Scrum Master
    * **Description:** Facilitate the initial brainstorming and empathy analysis phases. Explicitly structure the GitHub project board around Louis’s mandate: prioritizing the 6 Core MVP items (User Auth, Medication CRUD, Scheduling, Daily View, Low-Supply Tracking, and Core Reminders) while moving stretch goals (refill alerts, advanced notification hooks) to a secondary tier.
    * **Story Points:** 3

- [ ] **(2) Code Tasking: #103_UI Component Library Architecture & Auth Shell (Week 5 / v1.0)**
    * **Role Focus:** Tech Lead (Front-End)
    * **Description:** Establish the project's base visual layout, style guides, and design patterns. Implement the functional routing boilerplate and front-end interface containers for the secure user onboarding, sign-up, and log-in pages (REQ-001) to support initial back-end integration hooks.
    * **Story Points:** 5

- [ ] **(3) Build Tasking: #104_Sprint Velocity Verification & Frontend Workspace Build (Week 7 / v2.0)**
    * **Role Focus:** Scrum Master / Tech Lead (Front-End)
    * **Description:** Align with the CM/DM manager to establish stable automated software build steps. Ensure that front-end dependencies are strictly isolated, optimized, and build reliably alongside the back-end environments within the repository's continuous integration engine.
    * **Story Points:** 2

- [ ] **(4) Test Tasking: #105_Front-End Unit Testing & Acceptance Criteria Validation (Week 7 / v2.0)**
    * **Role Focus:** Product Owner / Tech Lead (Front-End)
    * **Description:** Introduce client-side test suites to validate interactive UI logic (such as medication input verification and layout transformations). As Product Owner, verify that automated scripts mirror the formal user acceptance criteria established during week 3 requirements elicitation.
    * **Story Points:** 3

- [ ] **(5) Release Tasking: #106_Sandbox Version Tagging & Functional Core Review (Week 9 / v3.0)**
    * **Role Focus:** Scrum Master / Product Owner
    * **Description:** Coordinate with the team to bundle iteration features into stable release artifacts. Audit the build against the core project tracker to ensure all 4 engineers have functional code representations matching their assigned sprint issues. Make sure the product products.
    * **Story Points:** 2

- [ ] **(6) Deploy Tasking: #107_Client Deployment Setup & Baseline Environment Configuration (Week 9 / v3.0)**
    * **Role Focus:** Tech Lead (Front-End)
    * **Description:** Configure and implement repeatable delivery procedures for hosting the client application. Ensure cross-origin platform connections operate securely when connecting to web servers, and establish seamless routing paths for external endpoints.
    * **Story Points:** 3

- [ ] **(7) Operate Tasking: #108_Stakeholder Beta Feedback Loop & UX Audit (Week 11 / v4.0)**
    * **Role Focus:** Product Owner / Tech Lead (Front-End)
    * **Description:** Conduct a thorough user experience (UX) analysis, refining the layout beyond structural wires into a production-grade system interface. Orchestrate a paper and live interface walk-through with Louis to collect explicit operational feedback on the daily view layout and medication lifecycle mechanics.
    * **Story Points:** 3

- [ ] **(8) Monitor Tasking: #109_Process Maturity Evaluation & Final Core MVP Handoff (Weeks 13-14 / v5.0-v6.0)**
    * **Role Focus:** Scrum Master / Product Owner
    * **Description:** Audit the sprint metrics, issue closure velocity, and quality control indicators to assess project maturity. Ensure user manual documentation and developer onboarding notes are finalized so that subsequent developer cohorts can easily maintain and scale the application infrastructure. Deliver the completed, fully integrated RXNOW core build to Louis.
    * **Story Points:** 3

---

### Reference Material

* [Role Responsibility Breakdown](./rolePlanningReference.md)
* [Version Planning](./versionPlanning.md)
* [Software Lifecycle](../../engineering/practices/SWLifecycle/Readme.md)
* [DevOps](../../engineering/practices/Methodologies/Readme.md)

---

### Review (5 pts)
- [x] All elements of the form are filled out
    - [x] Reference 
    - [x] Agile
    - [x] Implementation
  
- [x] Sub stories are created as the project's repo Issues in the Kanban Board
    * **Issue Number1 [Plan](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:225b4f3a-13dd-4e76-a8e0-e4d9d97387a4::details):** 
    * **Issue Number2 [Code](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:78a44f94-c704-4de1-8c50-959d5e356815::details):** 
    * **Issue Number3 [Build](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:d9c53d4c-3d15-4f7c-a03c-47828505021c::details):** 
    * **Issue Number4 [Test](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:b0fac238-1da4-4f70-9d86-f8f01c430d76::details):** 
    * **Issue Number5 [Release](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:ed482249-6a37-40b0-a023-de9bcfaaaa81::details):**  
    * **Issue Number6 [Deploy](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:7f73a8f2-b971-4ebf-8e2b-1dd578d9d2af::details):** 
    * **Issue Number7 [Operate](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:01532da2-ffc9-4b7b-a14e-ee817f9a98d7::details):** 
    * **Issue Number8 [Monitor](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:536b06ba-151d-40a3-916e-2f1dcdce5721::details):** 
- [x] All stories/issues project attributes are filled out
- [x] Team members have reviewed the items
