# Meeting Summary: RxNow Team Coordination

**Meeting Details**
* **Project:** RxNow (Mobile Medication Tracking Application)
* **Date & Time:** June 10, 2026, 9:33 PM
* **Duration:** 23 minutes 29 seconds
* **Participants:** Xander Weibel, Joe Tolley, Haeji Na, Josh Palmer, Kelson Gneiting

---

## 1. Welcome & Team Icebreaker
The team welcomed **Kelson Gneiting** as a new member joining mid-semester. Kelson is a 22-year-old Computer Science major getting married in August, who joined the class midway to complete his bachelor's degree for a government contract job offer. 

The rest of the team shared brief introductions:
* **Xander:** 25, turning 26 next week; enjoys volleyball and music.
* **Joe:** 36, returning student with four kids; aiming to graduate by the end of next semester.
* **Josh:** 24, married, graduating soon and starting an electrical apprenticeship.
* **Haeji:** 24, graduating this semester and excited to return home to South Korea.

---

## 2. Project Vision & Architecture Pivot
Xander debriefed the team on a meeting with the client, **Louis** (a BYU Medical Management graduate), and Louis's father, who has a strong tech background.

### Target Audience & Core Niche
* Focuses on elderly users and young pregnant mothers.
* Aims to replace traditional phone calls and electronic faxes for medication refills, consolidating details so users don't have to rely on sticky notes.

### Architectural Shift: Local Storage vs. Cloud
To simplify HIPAA compliance and data security in transit, the team is pivoting to a hybrid storage model:
* **Cloud Database (Render):** Will hold only login credentials and generic profile information.
* **Local On-App Storage:** Will store all sensitive patient data, including medication lists, dosages, refill frequencies, and nearby provider details.

### UI & Feature Updates
* **Low-Stock Logic:** The request page must flag low medications based on **doses per day** rather than just the total pill count.
* **Expiration Alerts:** Feature implementation is required.
* **Flexible Login:** Users must be able to log in using either their username or email without choosing a specific field. 
    * *Technical Note (Josh):* The front end will send the input string blindly. If it contains an `@` symbol, the back end will scan the email column; otherwise, it will scan the username column. Xander noted this requires adding a username field to the sign-up flow.

---

## 3. GitHub Repository Cleanup
* The current repository structure inherited from the previous team is disorganized (e.g., `project/app/` nested folders).
* Xander plans to consolidate and pull core application pieces out into the main root folder, leaving documentation in a clean subfolder.

---

## 4. Immediate Action Items & Task Delegation

### Technical & Feature Assignments
* **Back-End Adjustments:** **Joe** will manage back-end modifications and coordinate with Xander regarding recent branch updates.
* **Cloud Database Restructuring:** **Haeji** will update the cloud database to remove sensitive fields according to the new local-storage architecture.
* **E-Fax Research:** **Xander** will investigate how to generate and transmit refill requests via e-fax (determining if it can be handled entirely on-app or via the server).
* **Local Data Storage:** Deferred to later in the week; Xander will take it on or ping the team if he needs bandwidth assistance.

### Documentation & Onboarding
* **Installation Guide:** **Josh** is leading the creation of a clean installation guide so Louis can begin user-testing the app.
* **Onboarding (Kelson):** **Kelson** will spend his day off getting the Flutter app built and running locally on his machine. He will document his setup steps to compare notes with Josh, helping ensure the installation guide is clear for non-technical users.
* **Role Reports:** Kelson needs to fulfill weekly role requirements to catch up. Xander will hand over one of his current roles (Scrum Master or Front-End Lead) to Kelson starting next week. For this current week, Kelson will focus on standard engineering/onboarding tasks.

---

> **Next Steps:** Xander will drop a summary text of local vs. cloud items in MS Teams, along with repository links to past role planning reports for Kelson's reference.
