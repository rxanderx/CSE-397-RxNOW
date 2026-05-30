# RxNow Team Meeting Summary
**Date:** May 27, 2026  
**Attendees:** Joe Tolley, Xander Weibel, Haeji Na, Josh Palmer

---

# Executive Summary

The team reviewed progress toward the RxNow MVP. The backend is largely functional and has been tested locally, but the primary remaining task is connecting the frontend to the real backend instead of the mock data source. Database schema work is mostly complete, and attention is shifting toward deployment, testing, and QA processes.

The team also discussed hosting options for the database and backend, with Supabase identified as a potential MVP solution pending feedback from Louis. Additional conversations covered future prescription refill functionality, QA planning, and upcoming course assignments.

---

# Key Discussion Points

## Backend Progress (Joe)

### Current Status
- Backend repository contains nearly everything needed to run the system.
- API endpoints are operational and can be tested using Thunder Client.
- Authentication and token generation are working.
- Medication retrieval and other backend functionality have been tested locally.
- Backend currently runs with a local database on Joe's machine.

### Main Challenge
- Frontend is still connected to mock data rather than the live backend.
- Joe is learning Flutter and considers frontend integration the primary bottleneck.

### Update at End of Meeting
- Joe successfully switched databases and confirmed the application works on his phone.
- The database migration turned out to be easier than expected.

---

## Frontend Integration

### Discussion
- Xander indicated there is a simple configuration change needed to connect the frontend to the live backend.
- He volunteered to work with Joe to complete the transition.

### Outcome
- Frontend-to-backend integration is now considered the final major hurdle before MVP readiness.

---

## Database Progress (Haeji)

### Completed
- MVP database schema is essentially complete.

### Remaining Work
- Test database connectivity.
- Validate seeded data.
- Continue investigating password hashing/storage implementation.
- Support creation of the data access layer as needed.

### Notes
- Joe explained that password hashes should be generated using the hashing algorithm before storage in the database.

---

## Hosting & Deployment Discussion

### Current Situation
- Database and backend are running locally.

### Proposed Solution
- Use Supabase as a temporary hosting solution for the MVP.
- Benefits:
  - Free hosting options.
  - Easier team-wide testing.
  - Removes dependency on local environments.

### Next Steps
- Xander will discuss hosting options with Louis before implementation.
- Team may compare Supabase with other alternatives before making a final decision.

---

## QA & Testing (Josh)

### Initiative
Josh proposed creating a formal QA test plan.

### Rationale
- Development progressed quickly.
- Need a structured way to verify:
  - Frontend functionality
  - API integrations
  - Backend requests
  - Database operations
  - AI-generated code reliability

### Team Response
- Positive reception from the group.
- Viewed as an important step before broader testing.

---

## Future Product Vision

### Prescription Refill Feature
Xander raised the possibility of implementing prescription refill requests directly through the app.

### Goal
- Determine requirements for supporting prescription refill workflows.
- Understand technical and business constraints.
- Evaluate feasibility after MVP completion.

### Action
- Xander will discuss the feature with Louis and gather requirements.

---

## Academic / Administrative Discussion

The team briefly discussed:
- Gold certification progress.
- Informational interviews.
- A possible research paper assignment.

### Outcome
- No one could find the assignment in Canvas.
- Team agreed to monitor for further clarification.

---

# Action Items

| Owner | Action Item | Priority |
|---------|------------|----------|
| **Joe** | Complete frontend connection to the live backend | High |
| **Joe** | Continue backend testing after frontend integration | High |
| **Joe** | Explore deploying backend/database to hosted environment | Medium |
| **Xander** | Work with Joe on switching frontend from mock data to live backend | High |
| **Xander** | Discuss hosting/database options with Louis | High |
| **Xander** | Research requirements for prescription refill functionality | Medium |
| **Haeji** | Test database connectivity and seeded data | High |
| **Haeji** | Resolve password hashing implementation details | Medium |
| **Josh** | Create formal QA test plan and testing strategy | High |
| **Entire Team** | Continue monitoring course assignments and research paper requirements | Low |

---

# MVP Readiness Status

### Completed
- Backend API functionality
- Authentication/token generation
- Database schema design
- Local backend testing
- Database switching on mobile

### In Progress
- Frontend integration with live backend
- Database connectivity validation
- QA planning
- Hosting strategy

### Future Enhancements
- Cloud-hosted backend/database
- Prescription refill workflow
- Expanded testing suite

---

# Team Assessment

The team agreed that the project is very close to MVP readiness. The primary remaining technical milestone is connecting the frontend to the live backend and validating the full application workflow. Once that integration is complete and hosting decisions are finalized, the team can shift focus toward testing, deployment, and future feature development.
