**Functional Requirements Document (FRD)** 

**1\. Project identification** 

| Item  | Your information |
| ----- | ----- |
| Project title  | KOHA-Lite Inventory Management for Little Free Libraries |
| Prepared by  | Matthew Li & Yash Shashtri |
| Course/section  | 01:198:437:01 |
| Date  | October 19, 2026 |
| Version  | 1.0 |

**2\. Business problem and project purpose** 

Little free libraries across New Jersey need a database system to manage books borrowed.  Currently, the system is based on an honor code and not a database. The purpose of this project is to create a database that will allow little free library directors to track the flow of books in-and-out. 

**3\. Scope** 

| In scope  | Out of scope |
| ----- | ----- |
| Managing what books are currently in the little free library  | Tracking the conditions of certain books |
| Measuring which books are currently in high demand  | Providing waiting lists for certain books |
| Keeping track of which little free libraries a user has visited | Granting physical little free library cards for frequent users |

**4\. Stakeholders and user roles** 

| Stakeholder or role  | Responsibilities  | Database needs |
| ----- | ----- | ----- |
| Director | Manages upkeep of little free library and adds add-ons/repairs as needed | Check status of library without invasive/constant surveillance technologies like cameras or AI |
| Reader/Patron | Borrows, returns, and tracks books borrowed from little free libraries | Statistics on libraries visited, a way of tracking which books came from which library |
| Donor | Donates books without necessarily borrowing any books  | Which books are in high-demand and are need of having extras |

TO-DO:

**5\. Functional requirements** 

List the actions the database system must support. Number every requirement so it can be referenced in  the ERD, schema, testing documentation, and final presentation.  
**Template** 

| ID  | Functional requirement  | Priority  | Related data/entities |
| ----- | ----- | ----- | ----- |
| FR-01  | The system shall \[action\].  | High/Medium/Low  | \[Entities likely needed\] |
| FR-02  | The system shall \[action\].  | High/Medium/Low  | \[Entities likely needed\] |
| FR-03  | The system shall \[action\].  | High/Medium/Low  | \[Entities likely needed\] |

A complete project should normally contain enough functional requirements to justify multiple related  tables. Aim for requirements that cover: 

• Adding and maintaining core records 

• Recording transactions or events 

• Searching or retrieving information 

• Reporting or summarizing data 

• Enforcing important business rules 

**6\. Data requirements** 

Identify the major information the system must store. At this stage, do not worry about every column or  data type. Focus on the important business objects and the facts stored about them. 

**Template** 

| Data subject  | Information to store  | Example identifiers |
| ----- | ----- | ----- |
| \[Entity, such as Customer\]  | \[Name, contact information, status, etc.\]  | \[Customer ID\] |
| \[Entity, such as Product\]  | \[Name, price, category, quantity, etc.\]  | \[Product ID\] |
| \[Entity, such as Order\]  | \[Date, status, customer, total, etc.\]  | \[Order ID\] |

**7\. Business rules and validation rules** 

Business rules describe policies or facts that must always be true in the modeled organization. Many  business rules become database constraints, keys, or validation logic. 

**Template**

| ID  | Business rule  | Possible database enforcement |
| ----- | ----- | ----- |
| BR-01  | \[Rule that must always be true\]  | \[Primary key, foreign key, UNIQUE, CHECK, trigger, query logic\] |
| BR-02  | \[Rule that must always be true\]  | \[Primary key, foreign key, UNIQUE, CHECK, trigger, query logic\] |
| BR-03  | \[Rule that must always be true\]  | \[Primary key, foreign key, UNIQUE, CHECK, trigger, query logic\] |

Examples: 

• Each customer must have a unique customer ID. 

• An order must belong to exactly one customer. 

• An order must contain at least one order line before it is marked complete. • A quantity on hand cannot be negative. 

• A student may enroll in the same section only once. 

**8\. Reports and queries** 

Describe the information users need to retrieve. Each report or query should be specific enough to later  implement in SQL. 

**Template** 

| ID  | Report/query name  | Purpose  | Required result |
| ----- | ----- | ----- | ----- |
| RQ-01  | \[Name\]  | \[Business question answered\]  | \[Columns, filters, totals, sorting\] |
| RQ-02  | \[Name\]  | \[Business question answered\]  | \[Columns, filters, totals, sorting\] |
| RQ-03  | \[Name\]  | \[Business question answered\]  | \[Columns, filters, totals, sorting\] |

Include a mix of basic and more advanced queries, such as: 

• A filtered list of records 

• A query joining multiple tables 

• An aggregate report using COUNT, SUM, AVG, MIN, or MAX 

• A grouped report 

• A query that identifies missing, overdue, low-stock, unpaid, or inactive records  
**9\. Assumptions and constraints** 

Document assumptions made because information was not available, along with project limits. **Template** 

• Assumption: \[Example: Each product is supplied by one primary supplier.\] 

• Assumption: \[Example: A customer may place many orders.\] 

• Constraint: \[Example: The project will use MySQL.\] 

• Constraint: \[Example: The project will not process real credit-card payments.\] 

**10\. Acceptance criteria** 

Acceptance criteria describe how you will know the database meets the requirements. Link each criterion  to a functional requirement. 

**Template** 

| Requirement  | Acceptance criterion |
| ----- | ----- |
| FR-01  | \[How the requirement will be demonstrated or tested\] |
| FR-02  | \[How the requirement will be demonstrated or tested\] |
| FR-03  | \[How the requirement will be demonstrated or tested\] |