# Kelson Gneiting Introspection Analysis

* Ponder what are the wants and needs of the user, customer, and stakeholders.


## List of customers, users, and stakeholders
* Customer/Product Stakeholder: Louis Ramos (expects a hardened, testable MVP)
* Course Stakeholder: Professor Clements (expects traceability, process, and quality artifacts)
* End User: Adult patient managing medications and refill timing
* Development Team: Front-End, Back-End, Database, and QA leads
* Future Student Teams: Need maintainable architecture and handoff-ready documentation
* Potential Future External Stakeholders: Pharmacies/providers if integration expands later

## Answer the following questions:

    * What are the pain points of the customer?
        * Existing refill workflows are often slow and fragmented.
        * Teams can over-scope features instead of completing a reliable core.
        * Integration points across front end, back end, and database are common failure points.
        * Requirement drift can occur if SRS, test plans, and implementation are not aligned.
    * What are the types of users that might use the product? How will they use it?
        * Primary patient users will add medications, monitor supply, and start refill requests.
        * Caregivers may help maintain medication schedules for another person.
        * Support/admin-type users may review account issues or system behavior in future versions.
        * Team testers will run flows for validation and defect triage.
    * What other stakeholders are needed?
        * Security/compliance advisors to reduce legal and privacy risk.
        * Product owner decision maker to keep scope focused on MVP delivery.
        * QA stakeholders to enforce release criteria and regression quality.
        * Future maintainers who need clear API and data model documentation.

## Knowns, unknowns, gaps, and risks
* Knowns:
    * MVP scope includes authentication, medication CRUD, supply calculation, dashboard, notifications, and refill workflow.
    * External pharmacy/EHR integration is out of scope for this phase.
    * The system must stay lightweight and responsive.
* Unknowns:
    * Exact legal/compliance depth expected in this semester's implementation.
    * How realistic refill simulation should be for MVP demos.
    * Priority details when feature tradeoffs are required late in sprint cycles.
* Gaps:
    * More detail is needed on cross-system integration boundaries and error handling.
    * Final resolution is needed for requirement mapping mismatches in refill-related traces.
* Risks:
    * Performance goals could slip if architecture decisions are delayed.
    * Security could be under-scoped if input validation and password handling are inconsistent.
    * Team bandwidth concentration can delay testing and integration milestones.

## Summary (100-200 words)
> What did you learn about the project from Introspection?
Introspection clarified that this project is less about building many features and more about building the right core features well. The user needs are straightforward: fast medication tracking, clear low-supply signals, and a simple refill initiation process. The customer priorities align with that view, especially the emphasis on a stable MVP over feature volume. I also learned that many project risks are not in complex algorithms, but in coordination across layers. If front end, back end, database, and testing are not tightly aligned, even simple logic can break at integration points. Another key insight is that unknowns around legal boundaries and future external integrations should be treated as scoped questions, not blockers for MVP delivery. Overall, the project appears achievable and well-structured, but success depends on disciplined scope control, clear requirement traceability, and consistent implementation of performance and security expectations.
