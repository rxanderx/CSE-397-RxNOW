# CSE 397 Professional Career Project – Meeting Minutes

**Project:** RxNow  
**Date:** July 7th 2026  
**Duration:** ~19 minutes  
**Facilitator:** Kelson Gneiting
**Attendees:**
- Xander Weibel
- Joe Tolley
- Kelson Gneiting
- Josh Palmer
- Haeji Na
---

# Meeting Summary

The team reviewed the project's final priorities and agreed to focus on polishing the application rather than implementing the production backend. The application will generate refill request PDFs locally, while backend implementation will be documented for future developers. The discussion also covered future hosting recommendations, presentation preparation, scheduling the next meeting, and identifying additional tasks for team members.

---

# Discussion Topics

## 1. Final Project Priorities

- The client is satisfied with the project's current direction.
- The remaining development effort will focus on:
  - Improving the user experience.
  - Fixing bugs.
  - Polishing the application's interface.
  - Preparing documentation for future backend implementation.
- Rather than building a production eFax server now, the team will provide a detailed implementation plan.

---

## 2. Refill PDF Generation

The agreed workflow is:

1. User enters patient, provider, pharmacy, and refill information.
2. The Flutter application generates a refill request PDF locally using Dart.
3. The generated PDF serves as the final application deliverable.
4. A future backend server will eventually receive and transmit the PDF via eFax.

For this semester, PDF generation is considered sufficient while backend implementation remains in the planning phase.

---

## 3. Backend Implementation Planning

The team discussed preparing documentation so a future development team can implement the secure backend.

Topics included:

- Server responsibilities
- Secure eFax integration
- Request processing workflow
- Deployment considerations

The consensus was that building a secure production backend requires significantly more work than can reasonably be completed during the remaining project timeline.

---

## 4. Backend Ownership Discussion

Joe explained that building a temporary backend now would provide little long-term value.

Instead:

- The client should ultimately own the backend infrastructure.
- A permanent deployment should use a more formal platform than the current Render prototype.
- Firebase was discussed as a possible long-term solution.

This approach would allow future maintenance without depending on the current student team.

---

## 5. Documentation Responsibilities

Xander volunteered to prepare the backend implementation documentation.

Joe agreed to assist by explaining:

- Backend architecture
- Server responsibilities
- Technical implementation details
- Deployment recommendations

The goal is to make the documentation straightforward for future developers.

---

## 6. Presentation Planning

The team agreed that next week's meeting will focus primarily on the final presentation.

Plans include:

- Dividing presentation sections among team members.
- Reviewing completed work.
- Organizing demonstrations.

---

## 7. Scheduling

Kelson will be unavailable Tuesday due to travel.

The team agreed to:

- Share availability for Monday and Wednesday.
- Schedule another meeting that accommodates everyone.
- Avoid meeting without the full team if possible.

---

## 8. Additional Project Contributions

Xander asked Josh for ideas on additional improvements that could enhance the application before submission.

Possible areas include:

- Additional testing
- UI improvements
- General polish
- Presentation assistance

Josh explained that personal circumstances had limited his recent participation but expressed willingness to help during the final project phase.

Xander offered to involve Josh in preparing the presentation.

---

# Decisions Made

- Final development will prioritize bug fixes and user experience improvements.
- The application will generate refill request PDFs locally.
- Production backend implementation will be documented rather than built.
- Backend documentation will be written for future developers.
- Joe will provide backend architecture guidance.
- The team will hold another meeting before the presentation.
- Presentation responsibilities will be divided during the next meeting.

---

# Key Takeaways

- The project is transitioning from feature development to refinement.
- Local PDF generation is the final implemented refill workflow.
- Secure backend implementation is intentionally deferred in favor of detailed documentation.
- The team is shifting its focus toward presentation preparation and ensuring a polished final deliverable.
