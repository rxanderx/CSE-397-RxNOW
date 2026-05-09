# RxNow Team Meeting Summary

**Date:** May 6, 2026  
**Duration:** 48 minutes  
**Attendees:** Parker Morgan, Haeji Na, Joe Tolley, Josh Palmer

---

## Main Discussion Topics

### Repository Organization
- Parker reorganized the repository structure to make weekly assignment instructions easier to access.
- Initial attempt used separate folders for weekly scheduling documents, but GitHub would not track empty folders.
- Blank `.txt` files were added temporarily so folders could be committed.
- Final solution:
  - Remove duplicate scheduling folders
  - Add markdown links in the main README pointing directly to assignment/readme folders
- Team agreed the new structure is easier to navigate than the original repository layout.

---

### Understanding Weekly Requirements
Team reviewed Week 3 deliverables:
- Feature Planning Report
- VDD (Version Description Document)
- SRS review/update requirements

The team expressed confusion around:
- Epic stories
- Sub-stories
- Story points
- GitHub issue tracking
- Traceability/agile tasking sections
- Multiple duplicated folders/documents in the course repository

---

### SRS (Software Requirements Specification)
- Team discussed whether the inherited SRS should actually be modified.
- Concern was raised that changing inherited requirements from a previous team may not make sense unless issues are found.
- Haeji shared feedback from other teams/class discussions indicating:
  - Team members may need assigned sections of the SRS
  - Epic stories may relate to updating/completing SRS sections

---

### Project State / Previous Team
The team observed the inherited project appears incomplete:
- Minimal documentation
- No source code
- Empty `src` folder

Discussion suggested the previous team may have stopped mid-semester.

---

### Technology Stack Questions
The team identified unresolved questions for the client (Louis):
- Mobile framework/language choice
- Kotlin vs Swift vs other options
- Front-end expectations

Xander had already contacted Louis via email and the team is awaiting a response.

---

### Feature Planning Interpretation
- Team concluded the Feature Planning Report likely corresponds to one feature at a time.
- Six MVP/core features were identified in the SRS.
- Authentication was selected as the first feature to plan around.

---

### GitHub Issues / Epic Stories
Haeji identified examples in the previous RxNow repository showing:
- Epic issues
- Sub-issues/task breakdowns

Team concluded they likely need to:
- Create a new epic issue per feature
- Create sub-issues/tasks underneath each epic
- Reference issue numbers inside planning documents

---

## Work Division

The team agreed each member would work independently on sections of the planning report and merge work together later.

### Assigned Responsibilities

#### Josh
- Traceability section
- Agile tasking information
- Known dependencies/obstacles

#### Parker
- Front-end planning section
- Wireframes
- Repository organization
- Compile final submission

#### Joe
- Added template files (`features.md` and empty planning template)
- Help interpret feature planning structure

#### Haeji
- Investigated prior repo issues/epics
- Clarified likely GitHub workflow expectations

---

## Decisions Made
- Use the simplified repository structure with README links.
- Focus current effort on:
  - Feature Planning Report
  - VDD
  - Epic/sub-issue creation
- Work asynchronously on assigned sections and merge later.
- Wait for clarification from Louis/Xander before beginning implementation decisions.

---

## Action Items

| Action Item | Owner |
|---|---|
| Finalize repository cleanup and README links | Parker |
| Work on traceability/agile tasking sections | Josh |
| Continue feature planning template setup | Joe |
| Investigate GitHub epic/sub-issue workflow | Haeji |
| Follow up with Louis/client communication | Xander |
| Complete individual report sections before Saturday | Entire Team |
| Merge all report sections into final submission | Parker |

---

## Overall Team Concerns
- Instructions and repository organization are highly confusing.
- Many required terms/processes were unfamiliar to the team.
- Team feels blocked waiting for client clarification.
- No actual coding has started yet due to planning/documentation requirements.
