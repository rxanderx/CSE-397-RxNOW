# Kelson Gneiting Empathy User Analysis

## User Types
1. Primary Patient User - manages daily medications and refill timing.
2. Caregiver User - helps another user maintain medication data and schedules.
3. QA/Test User - validates workflows, error states, and requirement compliance.
4. Support/Admin User (future-facing) - resolves account problems and data issues.
5. Product/Clinical Reviewer (future-facing) - reviews workflow clarity and refill message quality.

## Workflows: Data in motion
As you saw with the example user account, there are actions and responses with in a system. 
Example workflow: User account creation and loggin. 
Certain decision need to be made in order to connect the different interfaces together. Describe different workflows based on the different features you have gathered.
> A. User Account Creation
* Username - validate username does not exist.
* Password - follows security limitations.
* Role - default role assignment
> B. User Log-In 
* Username - validate that the user is not already logged in
* Password - hash is correct 
* Validated responds either as an error or with a session key
> C. User Preference
* User's contact information is up to date
* User's visual preferences are determined
* User's notifications are determined

To satisfy the full empathy checklist, the software should include ten workflows. A-C above are the first three. The seven additional workflows are listed below.
1. Medication Record Creation
* User opens Add Medication form.
* System validates name, dosage, pills_remaining, and pills_per_day.
* If valid, record is persisted and shown on dashboard.
2. Medication Record Edit
* User selects existing medication and edits fields.
* System validates changed fields and updates record.
* Dashboard refreshes with updated values.
3. Medication Record Deletion
* User selects delete action.
* System confirms request and removes medication record.
* Dashboard and related status indicators update.
4. Supply Calculation and Dashboard Refresh
* System computes days_remaining using stored values.
* Dashboard displays low-supply indicators where threshold applies.
* User sees current status in one view.
5. Low-Supply Notification Trigger
* System detects threshold crossing at 7, 3, or 1 days remaining.
* One notification event is generated per threshold crossing.
* Repeated notifications are prevented unless threshold is crossed again.
6. Refill Request Initiation
* User starts refill workflow from a medication item.
* User associates provider name.
* System creates a structured refill request and assigns initial status.
7. Refill Send Simulation and Status Tracking
* User confirms simulated send.
* System updates status and timestamp.
* User sees confirmation and current refill status in UI.
 

# User Interfaces
The following are already defined, and do not count toward the 10 you need to come up with: 
> A. Welcome landing page
   * Contains information about the product
    * Link to user account creation
    * Link to User login page
> B. User account creation
 * Contains minimual information to register as a user
    * User's email and/or username
    * User's new password (with security checks)
    * Option to login using different SSO
    * Response return user back to Welcome landing page
> C. User login page
* User is prompted for username
* User is prompted for password
    * Response: 
        * If username is not validate, error message appears to retry. (if more than 5 tries, system locks the account for X minutes)
        * If username is validated, and user's preferences are not complete, user is sent to User Preference Page.
        * If username is validated, and user's preferences are complete, user is sent to Logged-in Homepage with a session key.
> D. User preference page
   * User's preference can be updated.
        * User's contact information
        * User's visual preference
        * User's notifications
> E. Logged-in Homepage
   * User's now has access to a subset of features available based on their role.
        * User's logout option

Define 10 additional User interface. Describe the interface based on access from the Logged-in Homepage. Describe the basic purpose of the user interface, and the major elements. Remember, that the session key is part of the logic. 
1. Medication List View
* Purpose: List all medications for authenticated account.
* Elements: medication cards/rows, low-supply badges, quick actions.
2. Add Medication Form
* Purpose: Create a new medication record.
* Elements: name, dosage, pills_remaining, pills_per_day, submit/cancel.
3. Edit Medication Form
* Purpose: Modify an existing medication record.
* Elements: prefilled fields, validation messages, save action.
4. Medication Detail View
* Purpose: View complete medication context.
* Elements: current values, days_remaining, refill actions.
5. Delete Confirmation Modal
* Purpose: Prevent accidental data deletion.
* Elements: warning text, confirm, cancel.
6. Notification Center
* Purpose: Display low-supply alerts and read/unread state.
* Elements: notification list, threshold labels, mark-as-read action.
7. Refill Request Form
* Purpose: Associate provider and build refill request.
* Elements: provider field, generated message preview, submit.
8. Refill Confirmation View
* Purpose: Confirm send simulation and show status update.
* Elements: success message, status badge, timestamp.
9. Refill History and Status View
* Purpose: Track pending/sent refill requests.
* Elements: filter by status, medication reference, request timeline.
10. Account and Session Management View
* Purpose: Manage account details and session/logout actions.
* Elements: email display, password reset entry, logout control.

# **Data Objects: Data in Motion**: 
Documents different data models that would be used to store the user's actions. Make sure you include the data structurals that need to be passed to the backend server for each interface. For example:
>A. User account creation
>* User name: Either an validated email format, or verified non-existing user name.
>* Password hash: Before sending the password needs to be uniquely hashed
>* Data is encrypted before sent to the backend server. (Note: Data is not sent directly to the database, it first must be verified and validated, before check with the datas system.)
>B. User loggin
>* User name and password hash
>* Data is encripted before sending to the backend server. Validation of formats is done on the server and verification is done from the database.
>C. User preference
>* Valid user session is present
>* Data structures:
    * UserContactInformation: Email, Phone number
    * UserVisualPreferences: Darkmode, Lighmode, default
    * UserNotification: Email option, Text option
    * UserNotifications: \<determined based on features of product>
* **Objects**:
1. AccountRegistrationRequest { email, password }
2. LoginRequest { email, password }
3. SessionTokenPayload { user_id, session_token, expiry }
4. MedicationCreateRequest { user_id, name, dosage, pills_remaining, pills_per_day }
5. MedicationUpdateRequest { medication_id, name, dosage, pills_remaining, pills_per_day }
6. MedicationDeleteRequest { medication_id, user_id }
7. DashboardMedicationView { medication_id, name, dosage, pills_remaining, days_remaining, low_supply }
8. NotificationEventPayload { user_id, medication_id, threshold, message, created_at }
9. RefillRequestCreatePayload { user_id, medication_id, provider_name, generated_message }
10. RefillStatusUpdatePayload { refill_id, status, sent_at }

# Data Objects: Data at Rest: 
This section is mainly concerned with the database portion of the system. Once the data is processed and transmitted to the backend, what changes are need to be made to the state of the system. The best approach is to define the fields and CRUD for each data structure. List the data structure field and for each element of CRUD, list the potenital workflow states or interfaces that handle each. 
>*  **User Account**
    * **Structure**
        Username
        Password
        Role
    * **CRUD**
        * Create:   User Account Creation
        * Read:     User Login
        * Update:   Role Change (Feature not mention in previous sections)
        * Delete:   User Account Deletion (Interface not mention in previous sections)
>* **User Session**
    * **Structure**
        * Username
        * Session key
        * Timeout
        * State
    * **CRUD**
        * Create:   User login
        * Read:     Valid session check
        * Update:   Any operation with timeout threshold or indication of logged out. 
        * Delete:   Logged out of system
>* **User perferences** (This is a simplified example, and required more information that what is provided based the field indicated)
>    * **Structure**
        * UserContactInformation: Email, Phone number
        * UserVisualPreferences: Darkmode, Lighmode, default
        * UserNotification: Email option, Text option
        * UserNotifications: \<determined based on features of product>
    * **CRUD**
        * Create:   User Account Creation
        * Read:     User Preference page
        * Update:   User Preference page
        * Delete:   User Account Deletion
List each data state structure and the associated fields and CRUD operations with Workflow and Interface associations.
1. User
    * **Structure**: user_id, email, password_hash, created_at
    * **CRUD**:
        * Create: Account Creation interface
        * Read: Login/Auth checks
        * Update: Password reset/account changes
        * Delete: Future account deletion interface
2. Session
    * **Structure**: session_id, user_id, token, expires_at, state
    * **CRUD**:
        * Create: Login flow
        * Read: Session validation middleware
        * Update: Session refresh/timeout updates
        * Delete: Logout
3. Medication
    * **Structure**: medication_id, user_id, name, dosage, pills_remaining, pills_per_day, created_at, updated_at
    * **CRUD**:
        * Create: Add Medication form
        * Read: Dashboard/List/Detail views
        * Update: Edit Medication form
        * Delete: Delete Confirmation modal
4. SupplyMetrics
    * **Structure**: medication_id, days_remaining, low_supply_status
    * **CRUD**:
        * Create: Derived on medication create
        * Read: Dashboard/Detail display
        * Update: Recomputed on medication update/intake changes
        * Delete: Removed when medication is deleted
5. Notification
    * **Structure**: notification_id, user_id, medication_id, threshold, message, is_read, created_at
    * **CRUD**:
        * Create: Low-supply threshold crossing logic
        * Read: Notification Center
        * Update: Mark-as-read action
        * Delete: Optional retention cleanup
6. RefillRequest
    * **Structure**: refill_id, user_id, medication_id, provider_name, generated_message, status, created_at, sent_at
    * **CRUD**:
        * Create: Refill Request Form
        * Read: Refill History view
        * Update: Pending to Sent transition
        * Delete: Optional future cancellation/archive workflow
7. ProviderReference
    * **Structure**: provider_id, provider_name, optional contact fields
    * **CRUD**:
        * Create: Provider association during refill setup
        * Read: Refill form suggestion/display
        * Update: Provider detail edits
        * Delete: Cleanup when no longer referenced
8. AuditLog
    * **Structure**: event_id, user_id, event_type, event_time, metadata
    * **CRUD**:
        * Create: Security and operational event logging
        * Read: Admin/support troubleshooting
        * Update: Not typically updated
        * Delete: Retention lifecycle management
9. PasswordResetToken
    * **Structure**: token_id, user_id, token_hash, expires_at, used_at
    * **CRUD**:
        * Create: Password reset request
        * Read: Token validation
        * Update: Mark token used
        * Delete: Expired token cleanup
10. DevicePreference (future-facing)
    * **Structure**: preference_id, user_id, notification_mode, theme, locale
    * **CRUD**:
        * Create: Preference initialization
        * Read: UI personalization fetch
        * Update: Preference edits
        * Delete: Account deletion cleanup

## Questions
* Answer the following questions:
    * What are the different user's roles?
        > i.e. Using iLearn as an example
        > * Student: Default, user is assigned this role by default and has limited access to features, but has access to Submit assignments and account grades
        > * Teacher: Can create content/assignments, and modify grades
        > * TA: Can only modify assignment grades
        >* Admin: Modify all elements of the user's account and content. 
        
        Roles
        * Patient (primary user)
        * Caregiver (assisted-use user)
        * Support/Admin (future operations)
        * QA/Test user (validation role)

    * (Front-end) How are the user interface's connected?
        > i.e What pages are linked to what pages?
        * Welcome -> Account Creation or Login
        * Login -> Dashboard (on success)
        * Dashboard -> Add/Edit/Delete Medication, Notification Center, Refill Request, Account/Logout
        * Refill Request -> Refill Confirmation -> Refill History/Status
        * Dashboard -> Medication Detail -> Edit or Refill actions
    * (Back-end) What logical decisions need to be made within the workflows (i.e. control flow, security)?
        > i.e. What decisions need to be made for each workflow?
        * Is user authenticated and authorized for requested resource?
        * Do inputs satisfy validation constraints before processing?
        * Is request attempting access to another user's data?
        * Does low-supply threshold crossing produce a new notification event?
        * Is refill request state transition valid (for example, Pending to Sent only once)?
    * (Database) How are the data models connected?
        > i.e. Describe the connectivity to the models, either relations or association. 
        * User 1-to-many Medication
        * User 1-to-many Session
        * Medication 1-to-many Notification
        * Medication 1-to-many RefillRequest
        * RefillRequest optional many-to-1 ProviderReference

## Summary (100-200 words)
> What did you learn about the project?
This empathy exercise clarified that RXNOW should be designed around low-friction daily use by real people managing medication routines. The primary user does not need a complex system; they need fast, clear actions and trustworthy status feedback. That perspective makes dashboard clarity, threshold-based notifications, and refill status visibility central to the user experience. I also learned that data quality and workflow reliability matter as much as visual design, because small backend mistakes can create confusion at critical points like low-supply alerts or refill status transitions. Mapping user interfaces to backend decisions and database relationships showed where consistency is required across all tiers. It also highlighted that scope discipline is important: if core workflows are stable, useful, and understandable, the MVP will satisfy both user needs and customer expectations. Overall, empathy analysis reinforced a user-first approach where speed, clarity, and dependable behavior are the defining qualities of a successful release.
