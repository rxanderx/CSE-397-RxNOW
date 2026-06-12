# Role Responsiblities 
In each phase of the DevOps Software Methodology, you have a set of responsilbities. 

Generally speaking, each role is responsible for 
* PO → backlog + acceptance criteria
* Scrum Master → sprint report + retro summary
* FE/BE/DB Leads → architecture + implementation
* QA → test plan + defect log
* CM/DM → pipeline + deployment proof

# DevOps Lifecycle × Roles

| Stage ↓ / Role → | Product Owner | Scrum Master | Tech Lead (FE) | Tech Lead (BE) | Tech Lead (DB) | QA | CM/DM |
|---|---|---|---|---|---|---|---|
| **Plan** | Define requirements, prioritize backlog, write user stories | Facilitate sprint planning, remove blockers | Estimate UI work, define FE architecture | Design APIs, define service architecture | Design schema, relationships, migrations | Define test strategy, write test cases | Define branching, versioning strategy |
| **Code** | Clarify requirements, answer dev questions | Ensure collaboration, enforce process | Implement UI, enforce standards | Implement APIs, services | Implement schema, queries, migrations | Review code for testability | Enforce repo structure, integration |
| **Build** | Validate build meets requirements | Keep pipeline flowing, remove blockers | Ensure FE builds compile, manage dependencies | Ensure BE builds succeed | Validate DB scripts and migrations | Validate build is testable | Manage CI pipelines, automate builds |
| **Test** | Define acceptance criteria, review results | Ensure testing process is followed | Support UI testing, fix defects | Support API testing, fix defects | Support data validation testing | Execute tests, log defects | Integrate automated tests |
| **Release** | Approve release scope | Coordinate release ceremonies | Validate UI readiness | Validate API readiness | Ensure data integrity before release | Validate release quality | Manage versioning and artifacts |
| **Deploy** | Approve deployment readiness | Coordinate deployment activities | Support frontend deployment | Support backend deployment | Run and validate migrations | Perform smoke tests post-deploy | Automate deployments (CD) |
| **Operate** | Gather user feedback, adjust backlog | Facilitate retrospectives | Handle UI bugs and usability issues | Handle runtime errors and service issues | Maintain data integrity and backups | Perform regression testing | Maintain environments |
| **Monitor** | Review metrics, reprioritize features | Track team performance, improve process | Monitor UI performance and errors | Monitor API performance and logs | Monitor database performance and queries | Track defects and quality metrics | Monitor pipeline health and deployment success |

# DevOps Phases (Refined with Roles and Responsibilities)

## **Plan**
- Within this phase, the Software Lifecycle phases **Concept of Operations, Requirements, Architecture, and Design** are performed, producing artifacts such as **ConOps, SRS, and SDD**.
- Agile activities include **Sprint Planning**, where user stories are selected and scoped for the upcoming iteration.
- Focus is on defining **what to build and why**, along with initial system structure.

**Primary Roles:**
- **Product Owner**: Defines requirements, prioritizes backlog, owns user stories.
- **Scrum Master**: Facilitates planning, ensures process adherence, removes blockers.
- **Tech Leads (FE/BE/DB)**: Provide estimates and contribute to architecture/design decisions.
- **QA Lead**: Defines test strategy and acceptance criteria.

---

## **Code**
- Corresponds to the **Implementation phase** of the Software Lifecycle and Agile’s **execution/implementation** activities.
- The majority of feature development occurs here, following defined architecture and standards.
- Emphasis on **clean code, modularity (MVC), and API contract adherence between tiers**.

**Primary Roles:**
- **Tech Leads (FE/BE/DB)**: Lead implementation, enforce standards, guide developers.
- **Scrum Master**: Ensures progress and removes blockers.
- **Product Owner**: Clarifies requirements during development.
- **QA Lead**: Ensures code is testable and aligned with acceptance criteria.

---

## **Build**
- Individual components are **integrated, compiled, and prepared for testing**.
- Occurs in a **controlled environment (CI pipeline)**, not on developer machines—this is the **first level of objective quality control**.
- Part of both **Implementation (SDLC)** and **Agile execution**.

**Primary Roles:**
- **CM/DM Lead**: Owns CI pipelines, build automation, and artifact generation.
- **Tech Leads**: Ensure code integrates correctly and resolves build issues.
- **QA Lead**: Verifies builds are suitable for testing.

---

## **Test**
- The system is validated through multiple levels:
  - **Unit**
  - **Integration**
  - **System**
  - **Regression**
  - **Acceptance**
- Testing is performed in environments **separate from development**.

**Primary Roles:**
- **QA Lead**: Owns test planning, execution, and defect tracking.
- **Tech Leads**: Support defect resolution and ensure test coverage.
- **Product Owner**: Validates acceptance criteria (acceptance testing).

---

## **Release**
- The product is **packaged for delivery**.
- Includes creation of:
  - **Version Description Document (VDD)**
  - Updated **user and customer documentation**
- Ensures the product is **ready for distribution**, not yet deployed.

**Primary Roles:**
- **CM/DM Lead**: Manages versioning, artifacts, and release packaging.
- **QA Lead**: Confirms release quality.
- **Product Owner**: Approves release scope and readiness.

---

## **Deploy**
- The product is **installed in a target environment** (staging or production).
- Issues may arise such as:
  - Environment mismatches
  - Configuration errors
  - Hardware/software compatibility
- Aligns with **Deployment and Transition to Operations** phases in SDLC/Agile.

**Primary Roles:**
- **CM/DM Lead**: Executes and automates deployment.
- **Tech Leads**: Support deployment troubleshooting.
- **QA Lead**: Performs smoke testing post-deployment.
- **Product Owner**: Confirms deployment meets expectations and gathers initial feedback.

---

## **Operate**
- The system is now **in use by end users**.
- Focus shifts to:
  - Supporting users
  - Capturing enhancement requests
  - Identifying usability improvements

**Primary Roles:**
- **Product Owner**: Collects feedback, updates backlog.
- **Tech Leads**: Address operational issues and improvements.
- **Scrum Master**: Facilitates retrospectives and continuous improvement.

---

## **Monitor**
- Focuses on **system health, reliability, and diagnostics**.
- Key questions:
  - What failed?
  - Can it be reproduced?
  - What do logs and metrics show?
- Requires visibility into:
  - Logs
  - Metrics
  - User behavior

**Primary Roles:**
- **Tech Leads (FE/BE/DB)**: Analyze logs, diagnose issues, implement fixes.
- **QA Lead**: Reproduces issues, validates fixes.
- **CM/DM Lead**: Monitors pipeline, system uptime, and deployment health.
- **Product Owner**: Prioritizes fixes based on impact.

As you look closer to each phase, each role has some aspect that that person needs to address for each delivery. 

# 📦 Deliverables by DevOps Phase

## 🧭 Plan Deliverables

**Goal:** Define *what* is being built and *how*

### Required Artifacts

* **Product Backlog**

  * User stories (with acceptance criteria)
  * Prioritized for the sprint
* **Sprint Plan**

  * Selected stories + task breakdown
  * Role assignments
* **Architecture Overview**

  * FE / BE / DB components
  * MVC mapping per tier
* **API Contracts**

  * Defined between tiers
  * Endpoints, request/response models
* **Data Model**

  * ER diagram or schema definition

### Role Ownership

* Product Owner → backlog, acceptance criteria
* Scrum Master → sprint plan
* Tech Leads → architecture, API, schema
* QA → acceptance criteria, test planning

---

## 💻 Code Deliverables

**Goal:** Implement features correctly

### Required Artifacts

* **Source Code (by tier)**

  * FE: Views/components
  * BE: Controllers/services
  * DB: Models/migrations
* **MVC Mapping Evidence**

  * Clear separation of Model / View / Controller
* **API Implementation**

  * Endpoints match defined contracts
* **Code Reviews**

  * Pull requests with comments and approvals

### Role Ownership

* Tech Leads → implementation, standards
* QA → testability review
* Scrum Master → process tracking

---

## 🏗️ Build Deliverables

**Goal:** Prove the system compiles and integrates outside dev machines

### Required Artifacts

* **CI Pipeline**

  * Automated build (e.g., GitHub Actions)
* **Build Logs**

  * Evidence of successful builds
* **Artifacts**

  * Compiled frontend
  * Backend build/package
* **Dependency Management**

  * Lock files, reproducible builds

### Role Ownership

* CM/DM → pipeline, automation
* Tech Leads → resolve build issues

---

## 🧪 Test Deliverables

**Goal:** Prove the system works correctly

### Required Artifacts

* **Test Plan**

  * Unit, integration, system, acceptance
* **Test Cases**

  * Mapped to user stories
* **Test Results**

  * Pass/fail evidence
* **Defect Log**

  * Bugs with status and severity

### Role Ownership

* QA → all test artifacts
* Tech Leads → bug fixes
* Product Owner → acceptance validation

---

## 📦 Release Deliverables

**Goal:** Package a version for delivery

### Required Artifacts

* **Version Description Document (VDD)**

  * Features included
  * Known issues
* **Release Notes**

  * User-facing summary
* **User Documentation**

  * How to use the feature(s)
* **Version Tag in Repository**

### Role Ownership

* CM/DM → versioning, packaging
* QA → release validation
* Product Owner → approval

---

## 🚀 Deploy Deliverables

**Goal:** Prove the system runs in a target environment

### Required Artifacts

* **Deployment Scripts / Configuration**

  * Docker, scripts, or manual steps
* **Deployed Environment**

  * URL or runnable system
* **Smoke Test Results**

  * Basic functionality verified post-deploy
* **Deployment Report**

  * Issues encountered and resolutions

### Role Ownership

* CM/DM → deployment execution
* QA → smoke testing
* Tech Leads → troubleshooting

---

## ⚙️ Operate Deliverables

**Goal:** Capture real usage and feedback

### Required Artifacts

* **User Feedback Log**

  * Feature requests, usability issues
* **Support Issues**

  * Bugs found during use
* **Updated Backlog**

  * New or modified stories

### Role Ownership

* Product Owner → feedback, backlog updates
* Scrum Master → retrospective notes
* Tech Leads → operational fixes

---

## 📊 Monitor Deliverables

**Goal:** Understand system behavior and failures

### Required Artifacts

* **Logs**

  * Application logs (FE/BE)
* **Error Reports**

  * Captured failures with context
* **Metrics / Observability**

  * Response times, errors, usage
* **Incident Report**

  * Root cause analysis (what failed, why, fix)

### Role Ownership

* Tech Leads → diagnostics, fixes
* QA → reproduce issues
* CM/DM → pipeline/system monitoring
* Product Owner → prioritize fixes
