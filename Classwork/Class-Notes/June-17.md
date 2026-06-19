# CSE 397 Professional Career Project

## Meeting Minutes – June 17, 2026

### Instructor

**Brother William Clements**

### Opening

* Opening prayer offered by **Glen Kelley**.
* Brother Clements opened the floor for questions before proceeding with project presentations.

---

# Team Status Presentations

## 1. Department Portfolio Team

**Presenter:** Jared Nash

### Project Purpose

Develop a portfolio website for the BYU-Idaho Computer Science department to showcase:

* Student projects
* Faculty projects
* Internship work
* Personal projects
* Society and department contributions

### Current Progress

**Status:** Yellow

### Completed / In Progress

* Homepage development
* Recent submissions functionality
* BYU-Idaho branding alignment
* Backend stabilization
* Analytics dashboard development
* Photo gallery implementation

### End-of-Semester Goal

* Complete and deploy a functional department portfolio website.

---

## 2. Spa's Grooming Mobile Application

**Presenter:** Spencer

### Project Purpose

Create a mobile application for a local dog grooming business that serves:

* Customers
* Employees

### Technology Stack

* .NET MAUI
* C#
* Square integration
* Supabase

### Key Features

* Appointment management
* Employee task tracking
* Customer notifications
* Authentication
* Role-based permissions

### Demonstrated Functionality

* Employee login
* Appointment dashboard
* Grooming workflow tracking
* Status updates that notify customers

### Status

**Green**

* Core framework completed
* Most functionality in place
* Remaining work focused on feature completion and refinement

---

## 3. iCrew (Formerly Rec Services)

**Presenter:** Jake Rammell

### Project Purpose

Develop a centralized employee management platform for BYU-Idaho.

### Features

* Employee scheduling
* Clock-in functionality
* Announcements
* Notifications
* Administrative controls

### Major Accomplishments

* Full Docker migration completed
* Security-focused redesign underway
* Architecture refactoring

### Current Priorities

#### MVP #1

* Isolate Supabase behind abstraction layers (facades)

#### MVP #2

* Route all API traffic through proper security pipelines

#### Stretch Goal

* Implement final customer-requested feature

### Demonstration

Showed:

* Employee management dashboard
* Location management
* Attendance tracking
* Administrative role controls

### Status

**Yellow-Green**

* Docker migration complete
* Supabase abstraction work actively progressing

---

## 4. RXNow

**Presenter:** Xander Weibel

### Stakeholder

University of Utah Healthcare administrator/clinic manager.

### Project Purpose

Medication management and refill request application.

### Target Users

* Elderly patients
* Pregnant mothers
* Individuals managing multiple medications

### Technology

* Flutter
* Dart
* Mobile-first architecture
* Local-first data storage model

### Recent Architectural Change

* Most patient data now stored locally on-device
* Minimal information stored in backend systems
* Improved scalability and privacy

### Demonstrated Features

* Medication tracking
* Dosage management
* Supply monitoring
* Low-medication alerts
* Refill request workflow

### Current Challenge

Securely sending refill requests to providers:

* Many providers rely on eFax
* HIPAA compliance requirements
* Preventing user-entry errors

### Status

**Green**

* Approximately 80% complete
* Core functionality finished
* Remaining work focused on polish and deployment readiness

### End-of-Semester Goal

* Finalize remaining features
* Work with stakeholder toward real-world deployment

---

## 5. Redesign Team

**Presenter:** Hayley Branchflower

### Status

**Red**

### Current Situation

* Team still working toward first project completion
* No demonstration available
* Experiencing development challenges

### Instructor Notes

* Encouraged team to reach out for assistance as needed.

---

# Instructor Discussion

## Software Version Milestones

### Version 1 (Pre-Alpha)

* Frontend, backend, and database communicate successfully
* Tested on external environments (Docker, VMs)

### Version 2 (Alpha)

* One or two features fully implemented
* Initial quality testing begins

### Version 3

* Three to four features implemented
* User testing begins

### Version 4

* Bug fixing
* Additional feature development

### Version 5

* Final bug fixes
* Customer demonstrations

---

# Upcoming Deliverables

## Software Installation Guide

Due during upcoming project milestones.

Should include:

* Setup instructions
* Environment configuration
* Deployment process

---

## User Guide

Should include:

* Getting started tutorial
* Core features
* Advanced features
* FAQ
* Troubleshooting
* Security and permissions
* Support contact information

---

## Software Development Guide

Audience:
Future development teams.

Should document:

* Setup procedures
* Development workflow
* Version control strategy
* Testing processes
* Security practices
* Deployment procedures
* Monitoring and logging
* Architecture decisions
* Historical project decisions

---

# Weekly Status Reports

Brother Clements emphasized:

### Reports Must Include

* Evidence of completed work
* Artifacts demonstrating progress
* More than just GitHub issue links

### ISO-9000 Principle

1. Say what you're going to do.
2. Do it.
3. Prove you did it.

This approach was highlighted as an important professional practice.

---

# White Paper / Research Topics

### Current Topic

Software Concepts

Including:

* Algorithms
* Design patterns
* System architecture
* Data structures
* AI tools
* Hardware considerations

### Upcoming Topic

Networking

Including:

* Network layers
* Communication protocols
* Connectivity concepts

### Future Topic

Quality Assurance

Including:

* Testing
* Security
* Logging
* Encryption
* Code quality
* Coupling and cohesion

---

# Final Presentation Expectations

Final presentations will be structured as an **infomercial**.

### Required Sections

1. Problem statement
2. Customer pain point
3. Research/expert analysis
4. Alternative solutions considered
5. Proposed solution
6. Product demonstration
7. User testimonials
8. Additional features
9. Lessons learned
10. Sense of urgency/value proposition

---

# Technical Lecture Highlights

Brother Clements delivered an overview of:

### Three-Tier Architecture

* Frontend
* Backend
* Database

### Interfaces and APIs

* REST
* SOAP
* RPC

### Networking Fundamentals

* OSI Model
* Physical layer
* Data link layer
* Network layer
* Transport layer
* Session layer
* Presentation layer
* Application layer

### Backend Architecture Concepts

* API gateways
* Pub/Sub systems
* Microservices
* Docker
* Kubernetes
* Logging and monitoring

### Database Concepts

* SQL and NoSQL systems
* Facades and adapters
* Database abstraction
* ACID properties:

  * Atomicity
  * Consistency
  * Isolation
  * Durability

---

# Announcements

* Thursday classes will follow the **Friday schedule**.
* Students with Friday classes should attend on Thursday.
* No regular Friday classes that week.

---

# Key Takeaways

### Project Health

* RXNow: Green (~80% complete)
* Spa's Grooming: Green
* iCrew: Yellow-Green
* Department Portfolio: Yellow
* Redesign Team: Red

### Common Themes Across Teams

* Architecture refactoring
* API design
* Database abstraction
* Security concerns
* Docker adoption
* Supabase integration challenges
* Deployment readiness

### Instructor Emphasis

* Documentation is critical.
* Evidence-based reporting is expected.
* Separation of concerns and abstraction layers are valuable architectural practices.
* Teams should begin preparing for final infomercial-style presentations now.

---

**Meeting Adjourned**
Brother Clements encouraged students to contact him with questions and wished everyone a productive week.
