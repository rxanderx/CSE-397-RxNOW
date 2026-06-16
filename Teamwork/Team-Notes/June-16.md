# Meeting Summary: RxNow Team Check-in

**Date:** June 16, 2026  
**Time:** 10:34 PM  
**Duration:** 21 minutes  
**Recording Reference:** RxNow-20260616_163428  
**Transcription Started By:** Xander Weibel  

---

## 👥 Attendees
* **Xander Weibel** (Product Owner)
* **Haeji Na** (Research / Front-end Developer)
* **Joe Tolley** (Back-end Developer)
* **Josh Palmer** (Back-end / QA Developer)
* **Kelson Gneiting** (New Team Member / Scrum Master)

---

## 📌 Executive Summary
The RxNow team met to review technical progress, coordinate database strategy for the Minimum Viable Product (MVP), and onboard Kelson. Key architectural decisions were made to focus strictly on local device storage and front-end polishing for the immediate MVP, pushing complex cloud database scaling and backups to recommendations for future project cohorts. Roles were adjusted with Kelson stepping up as the team's Scrum Master for the remaining 5 weeks of the semester.

---

## 🔍 Key Discussion Points

### 1. Front-end Framework and State Management
* **Haeji** provided research updates on AI tool recommendations for their architecture. 
* The team agreed that leveraging **Hive CE** (Community Edition) is the optimal path forward for local persistence since it allows structural changes and name updates without requiring extensive configuration changes for colors and assets. 
* Haeji has already pushed the updated structural changes and name configurations to the repository.

### 2. Notification Functionality & E-Fax Challenges
* **Local Notifications:** Joe confirmed that local notification functionality is currently working as intended on Android emulators/devices.
* **E-Fax Evaluation:** Xander researched integrating eFax to keep the application HIPAA compliant via encrypted transfers. However, he raised a significant UX concern: if users input an incorrect provider eFax number, the request will disappear without delivery confirmation, causing severe patient frustration.
* **Alternative Approaches:** Kelson suggested adding a scan-in feature for provider info to minimize human input error, especially given the older target demographic. Xander noted that most providers gladly hand out printed sheets with setup details to patients and committed to consulting **Lewis** (Stakeholder) on local practice standards before committing to automation.

### 3. Database Architecture & MVP Scope Reduction
* **Current State Limitations:** Joe highlighted that the online database is virtually useless right now; any username/password combination unlocks the app locally, which fails security standards. Additionally, lacking centralized syncing means data stays strictly isolated per device (no cross-platform state).
* **Stakeholder Context:** Xander noted that Lewis wants statistical tracking, user frequency metrics, and general profile analytics on the admin/marketing side in the long run.
* **The Decision:** Josh points out that a fully fault-tolerant, industry-scale back-end (including AWS architectures for automated request handling and user data backups) represents a major bottleneck and compliance burden with only 5 weeks left in the semester. 
* **Action:** The team agreed to leave the current unfinished backend infrastructure code intact in the repository for future semesters to expand upon. For the immediate Semester MVP, the application will operate as a **fully localized offline application**. Xander will message Lewis to align on this scoping decision.

### 4. Codebase Maintenance & Git Best Practices
* **Ignore Files:** Josh implemented updated `.gitignore` and `.dockerignore` files today. 
* Previously, executing commands like `flutter pub get` generated over 5,000 localized environment and configuration files, causing significant tracking noise (Kelson reported a backlog of ~250 untracked shifts). Moving these ignores directly into the respective front-end and back-end subdirectories cleared up local workspaces and secured the local `.env` environment variables containing credentials.

### 5. Onboarding & Resource Allocation
* Kelson successfully configured Android Studio and compiled the Flutter application locally using `flutter pub get`. 
* Kelson caught up on the required course reading (*The Two-Hour Job Search*) and is currently progressing through class AWS training modules.
* Josh requested Kelson to share any dependency conflicts, compile exceptions, or structural document gaps (spec drift) discovered during local environmental setup to help align current engineering realities with formal documentation.

---

## 🛠️ Action Items & Assignments

| Assignee | Task Description | Priority | Due Date |
| :--- | :--- | :---: | :---: |
| **Xander** | Shoot a message to Lewis regarding the team consensus to freeze cloud backend sync and stick to a localized MVP. | 🚨 High | As soon as possible |
| **Xander** | Compile the weekly Version Description Document (VDD) by updating the historical files inside the main `rxnow` repository. | 🟡 Medium | End of Week 9 |
| **Kelson** | Take ownership of developing the **"Forgot Password"** UI flow and error verification logic this week. | 🟡 Medium | June 23, 2026 |
| **Kelson** | Send Josh a comprehensive list of compile warnings, dependency errors, or visual alignment hooks encountered during onboarding setup. | 🟢 Low | June 20, 2026 |
| **Kelson** | Assume the role of **Scrum Master** for the upcoming 5 weeks, leading sync agendas and unblocking team action items. | 🟡 Medium | Ongoing |
| **All Team** | Self-assign and log granular task breakdowns directly to the internal Kanban board for team tracking. | 🟢 Low | Ongoing |
