# Meeting Summary: RxNow Team Sync

## Meeting Metadata
- **Project:** RxNow [cite: 1]
- **Date:** June 23, 2026, 10:24 PM [cite: 1]
- **Duration:** 20m 38s [cite: 1]
- **Attendees:**
  - Xander Weibel [cite: 1]
  - Kelson Gneiting [cite: 1]
  - Joe Tolley [cite: 52]
  - Haeji Na [cite: 5]
  - *Absent / Mentioned:* Josh [cite: 41, 61]

---

## 1. Executive Summary & Client Feedback
Xander provided updates regarding a recent meeting with the client, **Louis** [cite: 4]. Although Louis is not highly tech-savvy, he is setting up the environment to begin testing the app this week [cite: 4, 21]. 

Key strategic feedback from Louis includes:
- **MVP Validation:** Louis explicitly approved the decision to store data locally on the device for the Minimum Viable Product (MVP) [cite: 10, 57].
- **Core Focus:** The application's top priority must be an seamless user experience focused on solving the medication tracking problem with zero errors [cite: 11, 12].
- **Refill Workflow:** The primary endgame feature is a streamlined workflow for generating and sending refill requests associated with a provider record that contains a fax number [cite: 12, 18].
- **Data Expansion:** In addition to required provider details, Louis requested adding required pharmacy information (Pharmacy name, phone number, physical address, etc.) [cite: 14, 15].

---

## 2. Technical Architecture & Decisions

### Local Storage vs. Cloud Auth
Joe raised a question about whether the application should remain entirely local-based or preserve cloud authorization features [cite: 52, 54]. Xander confirmed that according to Louis's email feedback, local data storage is perfect for the MVP [cite: 55, 57]. The existing authentication structures can remain in place so that cloud/server syncing can be built on top of it in future iterations [cite: 58]. Joe will merge his local storage branch tonight [cite: 59].

### Notifications Upgrades
Joe suggested implementing proactive notifications so that users do not have to open the app every day to see their remaining medication supply [cite: 128]. He recommended sending a reminder 3 days prior to running out [cite: 128]. 
- Because remote push notifications are not viable without a cloud backend, the team agreed to implement **local banner notifications** using Flutter's native local notifications dependency (`flutter_local_notifications`) [cite: 133, 135]. Xander and Josh will pair up to implement this [cite: 136].

### Target Audience & Installation Support
Kelson brought up concerns regarding the setup complexity (e.g., installing external packages or configurations in Android Studio) considering their target audience includes older individuals [cite: 44, 45]. Xander clarified that the "Installation Guide" assignment is targeted toward end-users (e.g., side-loading instructions for Android or downloading from test environments), not development setup instructions [cite: 48, 49].

---

## 3. Roles & Process Alignment
- **Scrum Master Clarification:** Kelson raised questions regarding his responsibilities as Scrum Master, noting he initially thought the role was primarily focused on recording notes rather than coordinating task distributions [cite: 123]. Xander explained that the Scrum Master facilitates the workflow and team coordination [cite: 123]. Kelson set a personal goal to research Scrum fundamentals using official resources like `scrum.org` to better implement the framework moving forward [cite: 117, 119].

---

## 4. Kanban Action Items & Task Assignments
The team distributed **9 core tasks** from the Kanban board to be completed during the upcoming week [cite: 24, 76]:

| Assignee | Task Description | Dependencies / Notes |
| :--- | :--- | :--- |
| **Haeji Na** | Create Pharmacy Entity & Update Database Architecture [cite: 84] | Must be defined first [cite: 97] |
| **Haeji Na** | Update SRS Documentation (Pharmacy Specs) [cite: 86] | Natural follow-up to the entity design [cite: 86] |
| **Haeji Na** | Update ERD (Entity-Relationship Diagram) [cite: 89] | To reflect the new pharmacy data model [cite: 89] |
| **Kelson Gneiting** | Update "Generate Message" Functionality [cite: 100] | Dependent on Haeji's Pharmacy entity info [cite: 97] |
| **Kelson Gneiting** | Make Fax Number a Required Field on Provider Form [cite: 100] | Minor validation change on input forms [cite: 25, 27] |
| **Joe Tolley** | Resolve conflicts & merge local storage branch [cite: 59] | Planned for tonight [cite: 59] |
| **Joe Tolley** | Implement `mailto:` URI schemas [cite: 109] | For communication/triggering external mail client |
| **Xander Weibel** | Take remaining unassigned feature cards [cite: 110] | In coordination with backend tasks |
| **Xander & Josh** | Track down/update User Installation Guide [cite: 41, 110] | Simple user-facing instructions [cite: 42, 48] |
| **Xander & Josh** | Implement Flutter Local Banner Notifications [cite: 136] | Added following Joe's 3-day refill suggestion [cite: 128, 136] |

---

## 5. Next Steps
- **Client Testing:** Louis will begin actively testing user builds as updates deploy this week [cite: 21].
- **Estimates:** Haeji to provide timeline estimates for the Pharmacy Entity to allow Kelson to sequence his reliant "Generate Message" feature work [cite: 95, 97].
- **Next Sync:** Scheduled for next week to evaluate integration testing outcomes and track project scope adjustments [cite: 32, 142].
