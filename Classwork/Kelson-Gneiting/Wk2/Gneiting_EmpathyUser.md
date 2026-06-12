# \<Student Name> Empathy User Analysis

## User Types
1.
2.
3.
4. 
5. 

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

Based on the previous techniques, determine five more workflows that would be available to the user after the user has logged in and has a session key.
1.
2.
3.
4.
5. 
 

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
1.
2.
3. 
4.
5.
6. 
7. 
8.
9. 
10. 

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
1. 
2. 
3.
4. 
5.
6.
7. 
8.
9.
10.

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
1. \<Data Structure>
    * **Structure**
    * **CRUD**
2.
3.
4.
5. 
6.
7. 
8.
9.
10. 

## Questions
* Answer the following questions:
    * What are the different user's roles?
        > i.e. Using iLearn as an example
        > * Student: Default, user is assigned this role by default and has limited access to features, but has access to Submit assignments and account grades
        > * Teacher: Can create content/assignments, and modify grades
        > * TA: Can only modify assignment grades
        >* Admin: Modify all elements of the user's account and content. 
        
        Roles
        * \<Role 1>
        * 
        *   
        *  

    * (Front-end) How are the user interface's connected?
        > i.e What pages are linked to what pages?
    * (Back-end) What logical decisions need to be made within the workflows (i.e. control flow, security)?
        > i.e. What decisions need to be made for each workflow?
    * (Database) How are the data models connected?
        > i.e. Describe the connectivity to the models, either relations or association. 

## Summary (100-200 words)
> What did you learn about the project?
? 
