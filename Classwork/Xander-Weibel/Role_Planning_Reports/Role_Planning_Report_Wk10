# Role Planning Report - Detail Design

### Reference Information

---

* **Role**: Tech Lead (Front-End) / Product Owner / Scrum Master (Adapted)
* **Date**: 2026-06-25
* **Author**: Xander Weibel

* **Team Members**:

| Role | Team member name |
-- | --
| Product Owner | Xander Weibel |
| Scrum Master | Xander Weibel (adapted — structured check-ins in place of formal sprint scrums) |
| Tech Lead (Front-End) | Xander Weibel |
| Tech Lead (Back-End) | Joseph Tolley |
| Tech Lead (Database) | Haejin Na |
| Quality Assurance | Joshua Palmer |
| CM/DM | Joshua Palmer |
| Responsible Engineer | Kelson Gneiting |

---

### Agile Tasking Information

* **Epic Story**:
  As Tech Lead (Front-End) and Product Owner,
  I want to plan and execute the tasks associated with my roles for the v2.0 stabilization period,
  so that the locally-persistent MVP is hardened end-to-end — full screen coverage, safe data parsing, and a clean refill/notification flow — ahead of the next milestone review.

* **Story Point/Value**: 5

* **Planned Delivery**: v2.0 stabilization — Week 09 (Deployment & Installation) — June 16–25, 2026

* **Schedule**:

```mermaid
gantt
    title V2.0 Stabilization Role Planning — Xander Weibel
    dateFormat  YYYY-MM-DD
    section Planning
    Blocker Closeout Review (Haeji/Joe)         :done, 2026-06-16, 1d
    Team Check-In                               :done, 2026-06-17, 1d
    section Design
    Provider Dropdown / Optional-Field UX Pass  :done, 2026-06-17, 2d
    Refill Request Flow Review                  :done, 2026-06-18, 2d
    section Development
    Hive Adapter Finalization (Haeji)            :done, 2026-06-16, 3d
    Auth Endpoint Expansion (Joe)                :done, 2026-06-17, 3d
    Aiven User Table Migration (Haeji)           :done, 2026-06-18, 2d
    Safe-Int Parsing Hardening (all screens)     :done, 2026-06-19, 3d
    Refill Request Screen Rebuild                :done, 2026-06-20, 2d
    Password Reset Flow (Forgot/Confirm)          :done, 2026-06-21, 2d
    section Coordination
    Team Check-In Meeting (June 23)               :done, 2026-06-23, 1d
    Kelson Local Build Verification               :done, 2026-06-23, 1d
    section Delivery
    Repo Restructure Execution                    :done, 2026-06-24, 1d
    V2.0 Stabilization Delivery                   :milestone, 2026-06-25, 0d
```

* **Known Dependencies/Obstacles**:
  - ~~Hive local storage scaffolded but requires Haeji to finalize adapter/model pattern before data fully persists~~ — **Resolved.** Haeji finalized the box/key pattern in `local_storage_service.dart`; medications, providers, refills, and notifications all persist correctly across app restarts.
  - ~~Backend auth endpoints need Joe to add `username`, `first_name`, `last_name` fields and update login to accept email or username~~ — **Resolved**, but see new item below — this work is now slated for deprecation.
  - ~~Aiven DB migration (user table expansion, provider table cleanup) blocked on Haeji~~ — **Resolved**, but see new item below — Aiven's role is shrinking to zero under the new direction.
  - Render deployment pipeline remains unstable — updates still require manual steps; this is a v3.0 (Deployment & Installation) carryover, not closed yet.
  - Repo restructure (flattening Flutter app to root) is now executed, not just planned — confirm with Josh that the Installation Guide reflects new paths.
  - **NEW — Auth architecture pivoting to fully local.** Per Louis's direction (confirmed via Joe Tolley card), authentication is moving off Aiven entirely — email/password storage and verification will live in Hive alongside patient data, same as the v2.0 pivot already did for medications/providers/refills. This deprecates Joe's `/auth/*` endpoint work and the JWT-based session model in `secure_storage_service.dart`. SRS DB1/SA3 (User entity, one-way password hash) still apply as requirements; only the SDD's storage tier changes. **This is the largest open item this iteration** — needs an architecture decision doc before implementation starts, not just a code change.
  - **NEW — Pharmacy is a distinct entity from Provider**, not a Provider field. Haeji has a High-priority card to create `Pharmacy` + `PharmacyRepository`. ClassDiagram, ERD, and SRS currently have no Pharmacy entity at all — this is new scope, not a refinement of existing scope.
  - **NEW — Refill send mechanism changing from simulated send to real `mailto:` integration** (Xander). This is actually a closer match to SRS IR5 than the current simulated-send logic in `local_storage_service.dart`/`RefillService.sendRefillRequest()` — flagging as a net positive alignment, but it changes the FR20/FR21 implementation path.
  - **NEW — Provider fax field moving from optional to required** (gneitblood/Kelson), ahead of/in support of the mailto integration above.
  - Two divergent data models for `Provider` exist right now: the rich local schema in `mock_service.dart`/`provider_screen.dart` (clinic_name, phone, fax, address, email, npi, specialty, notes) vs. the thin ERD/openapi.yaml schema (name only). Now compounded by the Pharmacy split above — reconciliation needs to cover both entities together.

* **GitHub**
    * **GitHub Issue Number**: #156
    * **GitHub Branch**: `RXnow` / `Frontend`
    * **GitHub Project**: RXNow MVP — Iteration 2

---

### Implementation

- [x] **(1) Plan Tasking:** [#157 — Review closed blockers and re-scope remaining v2.0 stabilization work](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Confirmed with Haeji and Joe that the three wk08 blockers (Hive adapter, auth endpoint expansion, Aiven migration) are closed. Re-scoped remaining work toward hardening the existing screens rather than new architecture — defensive parsing, refill flow correctness, and password reset completion.
    * Story Points: 3

- [x] **(2) Code Tasking:** [#158 — Harden data parsing and complete password reset flow](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Added shared `_safeInt` parsing helpers across `medication_view_screen.dart`, `notifications_screen.dart`, and `add_edit_medication_screen.dart` to prevent cast crashes on Hive-returned values. Built out `forgot_password_screen.dart` end-to-end — request, token confirmation, and success screens — satisfying FR5. Fixed provider dropdown crash in `add_edit_medication_screen.dart` when a medication referenced a deleted provider.
    * Story Points: 8

- [x] **(3) Build Tasking:** [#159 — Rebuild refill request screen against LocalStorageService](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Rebuilt `refill_request_screen.dart` to load-or-create a pending refill request per selected medication via `RefillService`, display the generated message (FR19), and simulate send (FR20/FR21) with status display (FR22/FR23). Wired dashboard and medication view "Request Refill" entry points to pass preselected medications through.
    * Story Points: 5

- [x] **(4) Test Tasking:** [#160 — Manual review of hardened screens and password reset flow](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Verified safe-int parsing prevents crashes when Hive returns string-typed IDs. Walked through full password reset flow (request → token confirm → success → re-login). Confirmed refill request screen correctly transitions Pending → Sent and persists across navigation. Flagged the Provider schema divergence (local vs. ERD/openapi) as a non-blocking but unresolved item for QA tracking.
    * Story Points: 3

- [x] **(5) Release Tasking:** [#161 — Prepare stabilization release notes and update SDD references](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Documented closure of all three wk08 blockers for the team record. Flagged to Josh that SDD Section 6 (Database Design) and the ERD still reference the thin `Provider` model and need reconciliation against the richer local schema now in use.
    * Story Points: 2

- [x] **(6) Deploy Tasking:** [#162 — Execute repo restructure and rename frontend branch](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Executed the previously-planned repo restructure — flattened Flutter app files (`lib/`, `android/`, `ios/`, `pubspec.yaml`) to root, moved `delv/` to `docs/`. Renamed the working branch from `feature/02-provider-expansion` to `RXnow` / `Frontend` to align with the team's updated branch naming convention. Render deployment remains a known instability, still deferred to major milestones only.
    * Story Points: 3

- [x] **(7) Operate Tasking:** [#163 — Facilitate team check-in and verify Kelson's local build](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Ran June 23 team check-in. Confirmed Kelson has Flutter running locally against the restructured repo. Briefed team on blocker closeout and the Provider schema divergence flag. Continued coordination of the Scrum Master / Front-End Lead handoff to Kelson.
    * Story Points: 2

- [x] **(8) Monitor Tasking:** [#164 — Monitor Render stability and track remaining open items](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Continued monitoring Render deployment reliability — no change, still requires manual steps. Tracked remaining open items: Provider schema reconciliation, Installation Guide path updates post-restructure, and Kelson's transition into a formal role.
    * Story Points: 2

- [ ] **(9) Plan Tasking — NEW:** [#165 — Scope full-local auth architecture pivot](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Louis has directed that authentication move fully local (Hive), retiring Aiven/cloud auth entirely. Need an architecture decision doc covering: password hashing on-device (replacing JWT/session model in `secure_storage_service.dart`), migration path for any existing Aiven accounts, and SRS/SDD updates (Joe's card: "Update SRS per Louis' direction so that auth will be local now"). Not yet started — flagged here for next iteration's Code Tasking.
    * Story Points: 5
    * Owner: Joe Tolley (SRS/SDD), Xander (front-end session handling)

- [ ] **(10) Code Tasking — NEW:** [#166 — Create Pharmacy entity and PharmacyRepository](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: New entity distinct from Provider — High priority, owned by Haeji. Needs ClassDiagram, ERD, and SRS/openapi additions before implementation (Haeji's own follow-up card). Will affect `local_storage_service.dart` box structure and the refill `generated_message` content once Pharmacy data (fax, etc.) needs to be included alongside Provider data.
    * Story Points: 8
    * Owner: Haejin Na

- [ ] **(11) Code Tasking — NEW:** [#167 — Make Provider fax number required; implement mailto: refill send](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Promote `provider_screen.dart` fax field from optional to required (Kelson). Implement real `mailto:` launch for refill send in place of the current simulated send in `RefillService`/`local_storage_service.dart` — this satisfies SRS IR5 more directly than the prior approach. Update `generated_message` content to include provider fax and pharmacy info (Kelson's card + Joe's SRS FR17-23 update).
    * Story Points: 5
    * Owner: Kelson Gneiting (UI/logic), Xander (mailto integration)

- [ ] **(12) Release Tasking — NEW:** [#168 — Reconcile SRS/ERD/openapi for Provider and Pharmacy](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Description: Two outstanding doc-sync cards (Xander: "update the SRS and ERD openapi update for Provider fields"; Haeji: "update the SRS/ERD/openapi additions for Pharmacy"). These should land together since Pharmacy and Provider are being introduced/changed in the same pass — sequencing both in one PR avoids two ERD revisions in one week.
    * Story Points: 3
    * Owner: Xander (Provider), Haeji (Pharmacy)

---

---

### Reference
---
* [Role Responsibility Breakdown](./rolePlanningReference.md)
* [Version Planning](./versionPlanning.md)
* [Software Lifecycle](../../engineering/practices/SWLifecycle/Readme.md)
* [DevOps](../../engineering/practices/Methodologies/Readme.md)

---

### Review
- [x] All elements of the form are filled out
    - [x] Reference
    - [x] Agile
    - [x] Implementation

- [x] Epic Story is created in the project's repo Issue
    * Issue Number (Reference): #156
- [x] Sub stories are created as the project's repo Issues
    * Issue Number1 (Plan): [#157](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number2 (Code): #[158](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number3 (Build): #[159](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number4 (Test): #[160](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number5 (Release): #[161](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number6 (Deploy): #[162](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number7 (Operate): #[163](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number8 (Monitor): #[164](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number9 (Plan — NEW, in progress): #[165](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number10 (Code — NEW, in progress): #[166](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number11 (Code — NEW, in progress): #[167](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
    * Issue Number12 (Release — NEW, in progress): #[168](https://miro.com/app/board/uXjVHW1B9x4=/?openSyncedCardPanel=uXjVHW1B9xo%3D:cf26a05f-e49d-4c03-a3d1-f642ac4f7ed8:3458764670953758822:details)
- [x] All stories/issues project attributes are filled out
- [ ] Team members have reviewed the items (items 9-12 are newly surfaced from board review — pending team review)
