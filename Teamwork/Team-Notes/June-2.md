# RxNow Team Meeting Notes

**Date:** June 2, 2026
**Duration:** 17 minutes, 44 seconds
**Attendees:** Joe Tolley, Xander Weibel, Haeji Na, Josh Palmer

---

# Project Status Update

## Current Application Progress

The team reviewed the current state of the RxNow application and discussed feedback preparation for an upcoming stakeholder meeting.

### Current Features Implemented

* Medication tracking
* Medication inventory monitoring
* Automatic remaining-day calculations
* Low-medication notifications
* Refill request functionality

### Stakeholder Feedback

Xander will meet with Lewis to demonstrate the current application and gather feedback regarding:

* Desired feature additions
* User interface improvements
* Workflow changes
* Future project direction

The goal is to validate that the current functionality aligns with stakeholder expectations before expanding the feature set.

---

# Deployment & Hosting Discussion

## Current Challenges

Joe reported that deployment and updates remain difficult and somewhat unreliable.

### Current Deployment Process

The application currently involves multiple systems:

1. GitHub Repository
2. Docker Containerization
3. Hosting Platform (Render)
4. Database Hosting (Aiven)

This multi-step deployment pipeline has created challenges when pushing updates.

### Issues Identified

* Render deployments are not updating as expected
* Database connectivity issues are occurring
* Updating production requires several manual steps
* Troubleshooting deployment issues is time-consuming

### Proposed Solution

The team discussed:

* Continuing development locally
* Performing testing in local environments first
* Deploying only major milestones to production
* Improving deployment documentation

---

# Testing & Quality Assurance

## Test Plan Development

Josh reported progress on the project's formal test plan.

### Goals of the Test Plan

The document will provide:

* Clearly defined testing requirements
* Structured testing procedures
* Testing metadata requirements
* Verification steps for each feature

### Benefits

Developers will know exactly:

* What to test
* How to test it
* Expected outcomes
* Documentation requirements

This should reduce confusion and improve overall software quality.

---

# Integration & Review Phase

## Current Sprint Status

### Completed

* Implementation Sprint 1
* Implementation Sprint 2

### Current Phase

**Integration and Review**

### Upcoming Phase

**Testing & Quality Assurance**

Expected activities include:

* Executing test plans
* User acceptance testing
* UI feedback collection
* Bug identification and correction

---

# Class Deliverables

## Integration & Review Requirements

The team reviewed course expectations for the current week.

### Required Objectives

1. Create reproducible installation procedures
2. Create reproducible setup procedures
3. Verify installations across environments
4. Document platform differences
5. Provide containerized builds if necessary

### Deliverables

#### Installation Guide

Must include:

* Setup instructions
* Environment configuration
* Troubleshooting documentation

#### Smoke Tests

Simple verification tests to ensure:

* Application launches successfully
* Core functionality works correctly
* Installation completed properly

---

# Documentation Responsibilities

## Installation Guide Ownership

Josh volunteered to own the installation guide documentation.

### Team Responsibilities

Each team member will provide:

* Setup requirements
* Configuration steps
* Technical notes
* Troubleshooting information

Josh will compile these contributions into the formal project document.

---

# Database Discussion

## Current Database Hosting

The RxNow database is currently hosted on Aiven.

### Planned Work

Haeji offered assistance with:

* Database troubleshooting
* Database testing
* Database validation
* Deployment verification

### Immediate Concern

The team agreed that database connectivity issues must be resolved before meaningful testing can occur.

---

# AWS Certification Progress

## Course Requirements

The team discussed progress toward AWS certification requirements.

### Notes

* Job-searching requirements have been completed
* Focus is now on AWS certification completion
* Xander plans to submit an existing AWS certification
* Team members were encouraged to use online practice tools and study resources

---

# Stakeholder Questions for Lewis

The team generated several questions to discuss during the upcoming stakeholder meeting.

## Database & Schema Questions

### Notification Tracking

Should the system store:

* Notification status
* Notification history
* Notification delivery records

### Provider Information

Currently stored:

* Provider name

Potential additions:

* Phone number
* Email address
* Contact information
* Additional provider metadata

---

## Provider Management Questions

The team discussed two possible approaches:

### Option 1: Shared Provider Directory

A centralized list of providers available to all users.

### Option 2: User-Managed Providers

Allow users to create and maintain their own provider records.

### Question for Stakeholder

Which approach better matches the intended product vision?

---

## Deployment & Hosting Questions

The team wants clarification regarding long-term deployment plans.

### Topics to Discuss

* Future hosting environment
* Deployment strategy
* Maintenance responsibilities
* Infrastructure ownership
* Technical support expectations

### Key Question

Will the client:

* Hire technical support personnel?
* Manage infrastructure internally?
* Use managed cloud services?

Understanding this will influence future design decisions.

---

# Action Items

## Xander

* Meet with Lewis
* Gather stakeholder feedback
* Discuss deployment strategy
* Clarify provider management requirements
* Clarify notification tracking requirements
* Report findings back to the team

## Joe

* Continue backend troubleshooting
* Resolve database connectivity issues
* Improve deployment workflow

## Josh

* Complete test plan
* Create installation guide
* Assist with unit testing

## Haeji

* Assist with database testing
* Help validate deployment and connectivity issues

---

# Key Takeaways

* Core RxNow functionality is operational and ready for stakeholder review.
* Deployment and database connectivity remain the largest technical challenges.
* The team has entered the Integration & Review phase.
* Formal testing and QA activities will begin next week.
* Installation documentation and reproducible setup procedures are current priorities.
* Several product scope and deployment questions need clarification from the stakeholder before additional development begins.
