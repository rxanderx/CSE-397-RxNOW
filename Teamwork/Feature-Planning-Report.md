# Feature Planning Report - Detail Design

### Reference Information
---
* **Team Members**: Xander Weibel, Parker Morgan, Joe Tolley, Haeji Na, Josh Palmer
* **SDD**: [RxNOW SDD](https://github.com/louisramos23/RXNOW/blob/main/delv/SoftwareDesignDocumentSDD.md)

| Role | Team member name|
-- | --
| Product Owner | Xander |
| Scrum Master | Xander |
| Tech Lead (Front-End) | Parker |
| Tech Lead (Back-End) | Joe |
| Tech Lead (Database) | Haeji |
| Quality Assurance | Josh | 
| CM/DM | Josh | 



# Front-End Features Planned
 <!--- Please add the features planned in the SDD for front end here --->

# Back-End Features Planned
<!--- Please add the features planned in the SDD for back end here --->

# Database Features Planned
### Database (20 pts)

**Data Relationship Logic:**  
The Medication Management feature uses a one-to-many relationship between the User and Medication entities. One User can have many Medication records, but each Medication record belongs to exactly one User. This relationship is enforced by `Medication.user_id` referencing `User.user_id`. The database will store the medication information needed for tracking medication supply, including medication name, dosage, pills remaining, and pills per day.

- **Agile Info:**
  - **Story:** As a database role owner, I want to define the database structure for medication management so that user medication records can be stored, updated, retrieved, and deleted correctly.
  - **Est Story Points:** 3
  - **Assigned Responsible Engineer:** Haeji Na
  - **GitHub Issue Number:** #[add database sub-issue number]

**Classes:**

* **Models:** (Table/Doc Descriptions)

  **User Table:** Stores user account information.
  - `user_id` — Primary Key
  - `email`
  - `password_hash`

  **Medication Table:** Stores medication records associated with a user.
  - `medication_id` — Primary Key
  - `user_id` — Foreign Key referencing `User.user_id`
  - `name`
  - `dosage`
  - `pills_remaining`
  - `pills_per_day`

  ***Code Location:*** TBD / future database schema or migration script location

* **Control:** DBMS  
  *Setup, Maintenance, Trigger Scripts*
  - **Create** (Function name): `createMedication`
  - **Read** (Function name): `getMedicationsByUser`
  - **Update** (Function name): `updateMedication`
  - **Delete** (Function name): `deleteMedication`
  - ***Code Location:*** TBD / future database access layer or SQL script location

* **View** (UML Class)

  **Back-End API/Queries:**
  - **Create** (Function name): `POST /medications`
  - **Read** (Function name): `GET /medications`
  - **Update** (Function name): `PUT /medications/{medication_id}`
  - **Delete** (Function name): `DELETE /medications/{medication_id}`
  - ***Code Location:*** TBD / future backend API and data access layer location
