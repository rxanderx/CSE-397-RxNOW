CSE 397 Professional Career Project - May 19th, 2026 Class Overview

Comprehensive lecture covering software architecture, risk management, testing methodologies, and professional development guidance for computer science students working on team projects.

Three-Tier Architecture and System Design

The course emphasizes a three-tier architecture consisting of front-end, back-end, and database layers, equivalent to the Model View Controller (MVC) design pattern. Each tier communicates through APIs using protocols like HTTP (GET, POST, PUT, DELETE), SOAP, and REST calls. The front-end can be web, mobile, desktop, or smart devices. The back-end handles heavy processing through processes and threads orchestrated by the operating system. Communication between layers involves invisible infrastructure including Docker, virtual machines, and microservices that distribute resources efficiently.123

Risk Management and Mitigation Strategies

Risk consists of two factors: probability of occurrence and impact. The course teaches four risk mitigation strategies: (1) Accept the risk and proceed, (2) Avoid the risk by not performing the activity, (3) Transfer the risk to another party (like insurance), and (4) Mitigate through planning, training, and monitoring. Peer reviews remove approximately 80% of bugs, while testing removes another 19%, leaving only 1% for security concerns. Risk analysis uses a matrix plotting probability against impact to identify high-risk areas requiring attention.456

Test Planning and Test Case Development

A comprehensive test plan should include: test case identification, descriptions, prerequisites, component categories, author information, and requirement mappings. Each test case consists of action-result pairs leading to verification steps. Tests can intentionally cause system failures to verify durability and reliability rather than just the 'happy path.' The CANOTNOT mnemonic guides testing: test for Nothing (null/empty values), One item (happy path), Multiple items, Boundaries (less than/greater than), Powers of 2 (binary systems), Incorrect data, and Thresholds. This approach catches approximately 99% of problems.789

Weekly Project Workflow and Issue Management

Students work on 5-7 issues per week derived from role planning and feature planning conducted during team meetings. The return and report format requires links to completed issues and planned future issues. A backlog of issues should exist beyond what can be completed weekly. Large tasks can be broken into smaller steps to demonstrate weekly progression. DevOps phases rotate weekly: even weeks cover Monitoring, Planning, Development, and Build; odd weeks cover Test, Release, Deploy, and Operate. Currently on week 5, teams should be on version 2 of their software, incorporating the design document and beginning the test plan.101112

Database Concepts and ACID Properties

Databases use SQL for relational databases and NoSQL (MongoDB, Amazon DynamoDB) for document-based systems. CRUD operations (Create, Read, Update, Delete) form the foundation of data manipulation. ACID properties ensure data integrity: Atomicity (all-or-nothing transactions), Consistency (same state across transactions), Isolation (concurrent transactions don't interfere), and Durability (data persists after replication). Databases employ data structures like hash indexes and B-trees for efficient searching and updating. Entity relationship diagrams map data relationships, and understanding these principles helps developers appreciate system architecture from front-end to back-end.1314

Professional Resume Development and Career Preparation

A strong resume should include 10 key sections: (1) Skill Summary (matching job requirements), (2) Education (degree, certificates, class projects, senior projects), (3) Experience (internships and all jobs to demonstrate soft skills), (4) Projects (personal, hackathons, community work). Soft skills like communication, collaboration, problem-solving, and customer satisfaction are critical across all jobs. Early career resumes should include all relevant experience; after 5 years, remove unrelated positions; after 10 years, remove smaller jobs. The resume serves as an abstraction or avatar representing professional identity. Students should practice job applications even if already employed to develop professional skills.151617

Documentation Requirements and AI Integration

Four critical documents support software development: Test Document (current focus), Installation Guide (how to set up the system), User Guide (how end-users interact with the system), and Developer Guide (environment setup and code continuation). These documents save hours of troubleshooting and are essential for project handoffs. The instructor encourages using AI agents and AI orchestration to accelerate development, noting this is the future direction of software engineering. Students have permission to use AI tools to complete assignments faster and more efficiently, and should highlight AI proficiency on resumes.1819
