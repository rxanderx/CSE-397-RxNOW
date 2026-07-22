# Weekly 0x Tasking
<!--Use this template to create your weekly gitHub Project file.
. You will submit this every week.
Points: 100 pts
Instructions: 
* Copy this to a new gitHub File and put it in your artifacts//dossier directory.
* Fill in the Issue's attributes
* Submit a Link of the GitHub issue to the Canvas course's weekly status.
-->

<!-- 5 pts: Create of gitHub Issues-->
**Story**: As a CSE 397 Student, I want to complete the following tasks this week, so that I can return and report on my success as a valuable member of the team. 

See [Weekly Tasking](../management/scheduling/Readme.md) for each weeks tasking.

## Agile Issue (05 pts)
Update the GitHub issue attributes
* **Author**: Kelson Gneiting
* **Labels**: Feature Planning, Password Reset, Installation Guide, Week09
* **Type**: Feature
* **Milestone**: v3.0
* **Projects**: RXNow MVP
* **Development (Branch)**: feature/forgot-password
<!-- See project/enggering/processes/VersionControl.md,
This should also match tasking information your made at the beginning of the semseter.
/project/engineering/processes/StudentSetup.md
--->



<!-- 5 pts: Link to Personal Summary of Learning in artifacts
Instructions: Please link your meeting notes to this checklist
-->
## Training/Class Meeting [Minutes](../management/meetingminutes/Readme.md)(05 pts)
 - [x] [Training/Class Meeting - June 17 Notes](../../Class-Notes/June-17.md)


<!-- 20 pts: Links to Career Readiness activites 
Instructions: Please link your summaries to each of these activities for verification of completion. 
Then check the box as complete. 
-->
## Individual Work (10 pts - 5 for [Gold](../training/CC_CareerReadiness.md), 5 for [Training](../training/))
 - [x] Professional Networking Certification: [Career Services Gold Certificate Progress](../Gold/Gneiting_CertificationReport.md) (every week)
 - [x] Professional Training
    - The 2-Hour Job Search (Week 01-03)
    - Job Search (Week 04-05)
     - AWS Modules: Cloud Fundamentals (Week 06-11) - [AWS Progress](../AWS.md)
    - Ethics (Week 12-14)


<!----------------------------
Instructions: 
------------------------------->
## Project Teamwork Meeting [Minutes](../management/meetingminutes/Readme.md)(10 pts)
<!-- 10 pts: Link to meeting minutes from team meeting-->
 - [x] [Weekly Meeting with team - June 16 Summary](../../../Teamwork/Team-Notes/June-16.md)

<!----------------------------
------------------------------->
## Project Individual Work (10 pts)
In Agile Daily Scrum meetings each individual are asked three questions:
* What did I do yesterday to help meet the Sprint Goal?

    I started the progress on the password reset and am in the testing phase now to make sure it works

* What will I do today to help meet the Sprint Goal?

    Test and then help with the installation guide to get the app rolling

* Do I see any impediment that prevents me or the team from meeting the Sprint Goal.

No

Since this is a 3 credit class, and you are spending about 9 hours a week working on this class, it is equivalent to a normal business day. Your weekly status will be your Agile Daily Scrum report.

### What did you do yesterday to help meet the Sprint Goal?
<!-- 10 pts: Link to feature planning tasking-->
* ([Feature](../management/planning/featurePlanningReport.md) or [Role](../management/planning/rolePlanningReport.md)) and [Research](../engineering/practices/Research/Readme.md) Planning Tasking (10 pts)
    <!-- Feature Planning
        Create a link to your copy of the <project/management/planning/featureReport.md>, that you put in the artifacts/<team>/project/engineering/detaileddesign directory -->
    - [x] [Feature Planning Tasking (every odd week)](./featurePlanningReport.md)
    <!-- Role Planning
        Create a link to your copy of the <project/management/planning/rolePlanningReport.md>, that you put in the artifacts/<team>/project/engineering/methodology/ directory -->
    - [ ] Role Planning Tasking (every even eek)[project/management/planning]
    <!-- Research Tasking
        Create a link to your teams copy of the <project/engineering/practices/research>, that you put a copy of in the artifacts/engineering/research directory      --> 
   - [x] [Research Tasking (05 pts) (every other week)](./Whitepaper.md)

* Daily Scrum Notes:
    * What did I do yesterday to help meet the Sprint Goal?
        * I implemented core forgot-password functionality across UI, API service paths, and backend token lifecycle support while helping align installation guide updates.
    * What will I do today to help meet the Sprint Goal?
        * I will continue stabilization of forgot-password flow, test edge cases, and help close documentation gaps in install/setup guidance.
    * Do I see any impediment that prevents me or the team from meeting the Sprint Goal.
        * Production email provider wiring for reset delivery mode is not yet integrated, so current email mode falls back to dev logging.




<!----------------------------
------------------------------->
 - [ ] Issue Tasking (every week) [See Kanban Board](https://miro.com/app/board/uXjVHW1B9x4=/?share_link_id=2185336987) (50 pts - 5 per week @ 10 pts each)
- Note: Derived from meeting and discussing Planning Tasking and Research Tasking - expect 1 task from each teammember and role every two weeks].
<!-- List all the issues that you completed this week and what you plan on working next week.

Replace each of the Feature and Research Stories with the actual stories assigned to you. -->

<!-- 50 pts: Links to Product tasking issues -->
* [Scheduled](../management/scheduling/Readme.md) Tasking completed This week (50 pts - 10 pts per completed task)
    <!-- Completed Feture Stories
    During your team meeting you share your stories that you created doing the Feature Planning
    Copy the stories/issue information that were assigned to you through your team meeting.
    Replace each item below with the following information and format, seperated by :
                        Format
        * Issue Number  Normal
        * Issue name    **Bold**
        * Issue author  *Italics* 
        i.e. #1: **Master Issue**: *Clements*
    Expectations that you complete at least 5 tasks, list more if applicable.
    See /project/management/scheduling/Readme.md
    --> 
    - [Role](../management/planning/rolePlanningReport.md)/[Feature](../management/planning/featurePlanningReport.md)/[Research](../engineering/practices/Research/Readme.md) Stories
        - [x] 9.1. **Forgot Password UI flow and confirm reset screen**: *Kelson Gneiting* - [Feature Planning Report](./featurePlanningReport.md)
        - [x] 9.2. **Secure backend reset token lifecycle (request/confirm, hashing, expiry, invalidation)**: *Kelson Gneiting* - [RxNOW Kanban Board - Miro](https://miro.com/app/board/uXjVHW1B9x4=/?share_link_id=2185336987)
        - [x] 9.3. **Schema and runtime DB support for password_reset_tokens**: *Kelson Gneiting* - [RxNOW Kanban Board - Miro](https://miro.com/app/board/uXjVHW1B9x4=/?share_link_id=2185336987)
        - [x] 9.4. **API/service integration updates for forgot password (api_service.dart and mock compatibility)**: *Kelson Gneiting* - [RxNOW Kanban Board - Miro](https://miro.com/app/board/uXjVHW1B9x4=/?share_link_id=2185336987)
        - [x] 9.5. **Installation guide support and onboarding validation feedback**: *Kelson Gneiting* - [RxNOW Kanban Board - Miro](https://miro.com/app/board/uXjVHW1B9x4=/?share_link_id=2185336987)

    Where x is the week tasking.

<!-- 5 pts: Links to Product tasking issues -->
* [Role](../management/planning/rolePlanningReport.md)/[Feature](../management/planning/featurePlanningReport.md)/[Research](../engineering/practices/Research/Readme.md) Planned Next Week stories (5 pts - list of 5+)
    - Future [Role](../management/planning/rolePlanningReport.md)/[Feature](../management/planning/featurePlanningReport.md)/[Research](../engineering/practices/Research/Readme.md)
        - [ ] 10.1. Wire real email provider for reset delivery mode (replace dev-log fallback)
        - [ ] 10.2. Add backend integration tests for token reset flows (valid, expired, reused, unknown email)
        - [ ] 10.3. Add deep-link token auto-fill into confirm reset screen
        - [ ] 10.4. Continue installation guide hardening with setup troubleshooting notes
        - [ ] 10.5. Verify parity between live and mock reset behavior across all supported paths

## Weekly Evidence Links
* [Class Meeting - June 17](../../Class-Notes/June-17.md)
* [Team Meeting - June 16](../../../Teamwork/Team-Notes/June-16.md)
* [Gold Certification Progress](../Gold/Gneiting_CertificationReport.md)
* [AWS Certification Progress](../AWS.md)
* [Week 9 Feature Planning Report](./featurePlanningReport.md)
* [RxNOW Kanban Board - Miro](https://miro.com/app/board/uXjVHW1B9x4=/?share_link_id=2185336987)

        Where x is the week tasking.


### Rubric
*	05 pts – Agile Information
*	05 pts – Class/Training Meeting Notes
*	10 pts – Individual Work (CC-Gold, Training)
*	10 pts – Team planning meeting
*	10 pts – Planning Tasking (Feature or Role)
*	05 pts – Research Tasking
*	50 pts	- Issue Tasking (8 listed)
*	05 pts – Next Weeks Planning (5 listed)



