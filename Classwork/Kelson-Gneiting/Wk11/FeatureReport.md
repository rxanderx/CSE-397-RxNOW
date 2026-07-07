# Feature Planning Report - Detail Design
<!-- Instructions
Please fill this out during your planning meeting.
Each member of the group should complete a feature every two weeks. You are encharge of ensuring that your feature is complete.

You need to make a copy of this file.
Name it the <FeatureNumber>_<Feature title>.md and
Put it in the <artifacts/<team>/project/engineering/detaileddesign directory
    where <team>, will be replace with your team's name 
    i.e. artifacts/RecSrv/project/engineering/methodology/02_UserProfile.md
-->

### Reference Information (10 pts)
---
* **Feature Title**:
* **Feature Number**: 
* **Date**: 
* **Author**: 
* **Team Members**: 

| Role | Team member name|
-- | --
| Product Owner | |
| Scrum Master |  |
| Tech Lead (Front-End) |  |
| Tech Lead (Back-End) |  |
| Tech Lead (Database) |  |
| Quality Assurance |  | 
| CM/DM | Sean Reading | 
| |if more team members than roles | 
| Responsible Engineer | | 
| Responsible Engineer | | 


----
### Traceablility (10 pts)
* **Requirement Number** (SRS Ref #): <!-- https://mermaid.js.org/syntax/requirementDiagram.html -->
* **Design Number** (SDD Ref #): <!-- Suggestion: https://mermaid.js.org/syntax/c4.html -->
* **Test Plan** (TPD Ref #):
* **User Documnet** (Ref Section #):
* **Installation Document** (Ref #):
* **Software Developer Guide** (Ref #): 

----
### Agile Taksing Information (10 pts)
* **Epic Story**:
<!--Format:
As <<>>,
I want <<>>,
so that <<>> -->
* **Value**: 
* **Planned Delivery**: 
<!--Use https://mermaid.js.org/syntax/gitgraph.html -->
* **Schedule**:
<!-- Use https://mermaid.js.org/syntax/gantt.html -->
* **Known Dependancies/Obsticles**: 
* **GitHub**
    * **GitHub Issue Number**: 
    * **GitHub Branch**: 
    * **GitHub Project**: 


---
Detailed Design 
---
<!-- NOTE: Not all projects will follow the 3-Tier and MVC architecture, please find the corresponding functionality. You may use N/A for any of the them but you must provide a detailed reason. 
-->
### FrontEnd (20 pts)
**Workflow Description**: <!-- Use paragraph and https://mermaid.js.org/syntax/sequenceDiagram.html-->
- Agile Info:
    - Story: 
    - Est Story Points: 
    - Assigned Responsible Engineer:
    - GitHub Issue Number: 

<!-- See Role -->

**Classes**:
* **Model**:
    * **UML Class**:
        <!-- Use https://mermaid.js.org/syntax/classDiagram.html: --->
    * ***Code Location***: 
* **Control** 
    * **UML Class**:
        <!-- Use https://mermaid.js.org/syntax/classDiagram.html: --->
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***: 

* **View** (UML Class)
    <!--- Use https://mermaid.js.org/syntax/classDiagram.html: --->
    * **User Interface (Wireframe)**:
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***: 
    * **Back Interface** (UML Class):
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***: 

### Back-End (20 pts)
* **Business Logic**: 
<!-- Use https://mermaid.js.org/syntax/flowchart.html -->
- Agile Info:
    - Story: 
    - Est Story Points: 
    - Assigned Responsible Engineer:
    - GitHub Issue Number: 

**Classes**
* **Models**: 
    <!--Use UML and Sequence or ZenUML -->
    * **UML Class**:
        <!-- Use https://mermaid.js.org/syntax/classDiagram.html: --->
    * ***Code Location***:
* **Control**: 
    <!-- Use UML and https://mermaid.js.org/syntax/sequenceDiagram.html -->
    * **UML Class**:
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***: 
            <!-- Use https://mermaid.js.org/syntax/classDiagram.html: -->

* **View**(UML Class)
    <!--- Use https://mermaid.js.org/syntax/classDiagram.html: --->
    * **Front-End API** ():
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***: 
    * **Database Interface** (UML Class):
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***: 
    
### Database (20 pts)
* **Data Relationship Logic**: 
<!-- Use https://mermaid.js.org/syntax/entityRelationshipDiagram.html -->
- Agile Info:
    - Story: 
    - Est Story Points: 
    - Assigned Responsible Engineer:
    - GitHub Issue Number: 

**Classes**:
<!--Use https://mermaid.js.org/syntax/entityRelationshipDiagram.html -->
* **Models**: (Table/Doc Descriptions) 
    * ***Code Location***: 
* **Control**: DBMS
    * Setup, Maintenance, Trigger Scripts
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***: 
* **View** (UML Class)
    <!--- Use https://mermaid.js.org/syntax/classDiagram.html: --->
    * **Back-End API/Queries** ():
        * **Create** (Function name):
        * **Read** (Function name):
        * **Update** (Function name):
        * **Delete** (Function name):
        * ***Code Location***:

---
### Review (10 pts)
- [ ] All elements of the form are filled out
    - [ ] Reference 
    - [ ] Traceablity
    - [ ] Agile
    - [ ] Detailed Design 
- [ ] Epic Story is created in the project's repo Issue
    * Issue Number (Reference):
    <!-- Include a link to the Issue--> 
- [ ] Sub stories are created as the project's repo Issues
    * Issue Number 1 (i.e. Front-End): 
    * Issue Number 2 (i.e. Back-End):
    * Issue Number 3 (i.e. Database):
    <!-- Include a link to the Issues--> 
- [ ] All stories/issues project attributes are filled out
- [ ] Teammembers have reviewed the items
