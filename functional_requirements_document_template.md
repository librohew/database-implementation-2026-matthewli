**Functional Requirements Document (FRD)** 

**Database Implementation Project Template** 

A Functional Requirements Document (FRD) explains **what a system must do** from the perspective of its  users and the organization. For a database implementation project, it defines the business problem, users,  processes, data the system must maintain, business rules, and the reports or queries the database must  support. 

The FRD is written before the database is implemented. It becomes the blueprint for later project work,  including: 

• Entity-relationship diagram (ERD) 

• Relational schema and normalization 

• Table creation scripts 

• Primary and foreign keys 

• Data-validation constraints 

• Sample data 

• SQL queries, views, stored procedures, and reports 

An FRD does **not** primarily explain how to write SQL or what data types to select. Those are design and  implementation decisions. Instead, an FRD states the required system behavior. For example: 

• Functional requirement: “The system shall allow staff to register a member for a class.” • Implementation decision: “Create an Enrollment table with MemberID and ClassID foreign keys.” 

**Writing guidance** 

Use clear, testable statements. A good functional requirement usually follows this pattern: The system shall \[perform an action\] for \[a user or role\] when \[a condition applies\]. Examples: 

• The system shall store one record for each customer. 

• The system shall prevent a customer from registering for the same event more than once.  
• The system shall display all unpaid invoices for a selected customer. 

• The system shall calculate the total amount paid for each order. 

Avoid vague statements such as “The system should be easy to use” or “The system should manage  inventory well.” Replace them with measurable requirements, such as “The system shall show the  quantity on hand for every product.” 

**Required sections** 

**1\. Project identification** 

Provide basic information about the project. 

| Item  | Your information |
| ----- | ----- |
| Project title  | KOHA-Lite Inventory Management for Little Free Libraries |
| Prepared by  | Matthew Li & Yash Shashtri |
| Course/section  | 01:198:437:01 |
| Date  | October 19, 2026 |
| Version  | 1.0 |

**2\. Business problem and project purpose** 

Describe the real-world situation the database will address. Explain why the organization needs the  system and what is currently difficult, inefficient, inaccurate, or impossible to track. 

**Template** 

Little free libraries across New Jersey need a database system to manage books borrowed.  Currently, the system is based on an honor code and not a database. The purpose of this project is to create a database that will allow little free library directors to track the flow of books in-and-out. 

**Questions to consider** 

• What organization is being modeled? 

• What information must it track? 

• What process currently depends on paper, spreadsheets, memory, or disconnected files?  
• What decisions or operations will improve when the database is available? 

**3\. Scope** 

Define the boundaries of the project. State what the system will do and what it will not do. Scope prevents  the project from becoming too broad. 

**In scope** might include managing customers, products, appointments, employees, orders, memberships,  inventory, courses, or payments. 

**Out of scope** might include a web interface, mobile application, online payment processing, employee  payroll, shipping integration, or accounting integration, unless your project specifically includes them. 

**Template** 

| In scope  | Out of scope |
| ----- | ----- |
| Managing what books are currently in the little free library  | Tracking the conditions of certain books |
| Measuring which books are currently in high demand  | Providing waiting lists for certain books |
| Keeping track of which little free libraries a user has visited | Granting physical little free library cards for frequent users |

**4\. Stakeholders and user roles** 

Identify the people or groups that use, manage, or are affected by the system. A user role is a category of  user, not necessarily a specific person. 

**Template** 

| Stakeholder or role  | Responsibilities  | Database needs |
| ----- | ----- | ----- |
| Director | Manages upkeep of little free library and adds add-ons/repairs as needed | Check status of library without invasive/constant surveillance technologies like cameras or AI |
| Reader/Patron | Borrows, returns, and tracks books borrowed from little free libraries | Statistics on libraries visited, a way of tracking which books came from which library |
| Donor | Donates books without necessarily borrowing any books  | Which books are in high-demand and are need of having extras |

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

**Worked example: Martial Arts School Management  Database** 

The following example illustrates a complete FRD for a manageable college-level database project. It is  intended as a model; students should adapt the structure and level of detail to their own project topic  rather than copying it word for word. 

**1\. Project identification**

| Item  | Information |
| :---- | ----- |
| Project title  | Martial Arts School Management Database |

| Prepared by  | \[Student name\] |
| ----- | :---- |
| Course/section  | \[Course and section\] |
| Date  | \[Date\] |
| Version  | 1.0 |

**2\. Business problem and project purpose** 

A martial arts school needs a centralized system to manage students, instructors, classes, class enrollment,  attendance, and membership payments. The school currently relies on separate spreadsheets and paper  attendance sheets, making it difficult to determine which students are active, which classes have open  spaces, and which membership payments are overdue. 

The purpose of this project is to create a relational database that allows school staff to maintain accurate  student and class information, enroll students in classes, track attendance, record payments, and produce  operational reports. 

**3\. Scope** 

| In scope  | Out of scope |
| ----- | ----- |
| Student contact and membership information  | Public website development |
| Instructor and class scheduling information  | Online class registration portal |
| Student enrollment in classes  | Credit-card payment processing |
| Attendance recording  | Payroll for instructors |
| Membership payment records  | Tournament registration and scoring |
| Operational reports and SQL queries  | Mobile application development |

**4\. Stakeholders and user roles**

| Stakeholder or   role | Responsibilities  | Database needs |
| ----- | :---- | :---- |
| School manager  | Oversees memberships, classes, and  payments | View active students, payment status, class capacity, and  operational reports |

| Front-desk staff  | Maintains student records and records  payments | Add and update students, enroll students, record attendance,  and enter payments |
| ----- | :---- | :---- |
| Instructor  | Teaches assigned classes  | View class rosters and attendance information |
| Student  | Enrolls in classes and maintains   membership | Is represented in the database; does not directly use the  database in this project |

**5\. Functional requirements**

| ID  | Functional requirement  | Priority  | Related data/entities |
| ----- | :---- | ----- | :---- |
| FR  01 | The system shall store one record for each martial arts student, including  name, date of birth, contact information, join date, belt rank, and  membership status. | High  | Student, BeltRank |
| FR  02 | The system shall store instructor information, including name, contact  information, rank, and active status. | High  | Instructor |
| FR  03 | The system shall store scheduled class information, including class name,  martial arts style, meeting day, start time, end time, room, capacity, and  assigned instructor. | High  | Class, Instructor |
| FR  04 | The system shall allow staff to enroll an active student in a scheduled class.  | High  | Enrollment, Student,  Class |
| FR  05 | The system shall prevent the same student from being enrolled in the same  class more than once. | High  | Enrollment |
| FR  06 | The system shall prevent enrollment when a class has reached its maximum  capacity. | High  | Enrollment, Class |
| FR  07 | The system shall record a student’s attendance for a specific class meeting  date. | Medium  | Attendance,   Enrollment, Class |
| FR  08 | The system shall record membership payments, including payment date,  amount, payment method, and applicable membership period. | High  | Payment, Student |
| FR  09 | The system shall allow staff to update a student’s membership status to  active, inactive, suspended, or expired. | High  | Student,   MembershipStatus |
| FR  10 | The system shall display the roster of students enrolled in a selected class.  | Medium  | Enrollment, Student,  Class |
| FR  11 | The system shall display students whose memberships are expired or whose  payments are overdue. | High  | Student, Payment |

| FR  12 | The system shall produce a report showing attendance totals by student for  a selected date range. | Medium  | Attendance, Student,  Class |
| ----- | :---- | :---: | :---- |
| FR  13 | The system shall produce a report showing enrollment count and remaining  capacity for each class. | Medium  | Class, Enrollment |
| FR  14 | The system shall produce a report showing total membership payments  received by month. | Medium  | Payment |

**6\. Data requirements** 

| Data   subject | Information to store  | Example identifiers |
| ----- | ----- | :---- |
| Student  | Student name, date of birth, phone, email, address, join date, belt rank,  membership status, membership expiration date | StudentID |
| Instructor  | Instructor name, phone, email, belt rank, hire date, active status  | InstructorID |
| Class  | Class name, style, day of week, start time, end time, room, capacity,  instructor | ClassID |
| Enrollment  | Student, class, enrollment date, enrollment status  | EnrollmentID or composite   StudentID/ClassID |
| Attendance  | Enrollment or student/class reference, meeting date, attendance status  | AttendanceID |
| Payment  | Student, payment date, amount, payment method, membership period  start and end dates | PaymentID |
| Belt rank  | Rank name, rank order, color  | BeltRankID |

**7\. Business rules and validation rules**

| ID  | Business rule  | Possible database enforcement |
| :---- | :---- | :---- |
| BR  01 | Every student must have a unique student ID.  | Primary key on Student |
| BR  02 | Each class must be assigned to one instructor. One instructor  may teach many classes. | Foreign key from Class to Instructor |
| BR  03 | A student may enroll in many classes, and a class may contain  many students. | Enrollment junction table |

| BR  04 | A student may be enrolled in a specific class no more than  once. | UNIQUE constraint on Enrollment(StudentID,  ClassID) |
| :---- | :---- | :---- |
| BR  05 | Only students with an active membership may be enrolled in a  class. | Application logic, trigger, or controlled   enrollment procedure |
| BR  06 | Enrollment count for a class may not exceed the class  capacity. | Query/procedure/trigger logic before insert |
| BR  07 | Attendance may be recorded only for a student who is  enrolled in that class. | Foreign key to Enrollment or controlled insert  logic |
| BR  08 | A payment amount must be greater than zero.  | CHECK constraint |
| BR  09 | Membership status must be one of Active, Inactive,  Suspended, or Expired. | CHECK constraint or lookup table |
| BR  10 | A class start time must occur before its end time.  | CHECK constraint or validation logic |

**8\. Reports and queries** 

| ID  | Report/query name  | Purpose  | Required result |
| ----- | :---- | :---- | :---- |
| RQ  01 | Active student directory  | Allow staff to contact currently  active students | Student ID, full name, phone, email, belt rank;  only active students; sort by last name |
| RQ  02 | Class roster  | Allow an instructor to see who is  enrolled in a chosen class | Class name, instructor, student ID, student name,  enrollment date; sort by student name |
| RQ  03 | Class capacity report  | Identify classes with available or  limited space | Class ID, class name, capacity, enrolled count,  remaining spaces |
| RQ  04 | Expired/overdue   membership report | Identify students who require  follow-up | Student name, phone, email, membership status,  expiration date, most recent payment date |
| RQ  05 | Student attendance   summary | Review participation during a  selected date range | Student name, class name, number of meetings  attended, number absent, attendance percentage |
| RQ  06 | Monthly payment   summary | Measure membership revenue  | Month and year, number of payments, total  amount received; grouped by month |
| RQ  07 | Instructor teaching   schedule | Show the classes taught by each  active instructor | Instructor name, class name, day, start time, end  time, room |

**9\. Assumptions and constraints**  
• Assumption: Each class meets on one recurring day and time. If the school later needs multiple  meeting times for one class, a separate ClassMeeting table could be added. 

• Assumption: Each class has one assigned primary instructor. 

• Assumption: Each payment applies to one student and one membership period. • Assumption: The school records only membership payments, not retail merchandise sales. • Constraint: The database will be implemented in MySQL. 

• Constraint: The project will use fictional sample data and will not store actual sensitive payment card information. 

• Constraint: Staff access and authentication are outside the scope of the initial database  implementation. 

**10\. Acceptance criteria**

| Requirement  | Acceptance criterion |
| :---- | ----- |
| FR-01  | Demonstrate inserting, viewing, and updating at least five student records with required attributes. |
| FR-03  | Demonstrate inserting at least three classes, each linked to a valid instructor. |
| FR-04 and FR  05 | Demonstrate enrolling students in classes and show that a duplicate student/class enrollment is rejected. |
| FR-06  | Demonstrate that the system identifies a class that has reached its capacity and does not allow an  additional enrollment. |
| FR-07  | Demonstrate recording attendance for enrolled students and retrieving attendance records for a selected  class date. |
| FR-08  | Demonstrate recording payment records with a positive amount and valid payment method. |
| FR-10  | Run the class-roster query for one class and show the enrolled students. |
| FR-11  | Run the expired/overdue membership report and show students needing follow-up. |
| FR-12  | Run the attendance-summary report for a selected date range. |
| FR-13  | Run the class-capacity report showing capacity, enrollment count, and remaining spaces. |
| FR-14  | Run the monthly-payment summary using grouping and aggregation. |

**Requirement-to-design traceability example** 

A strong database project demonstrates how requirements lead to the data model and SQL work. The  following traceability table is optional but recommended. 

| Requirement  | Likely tables  | Expected relationship or constraint  | Example implementation   evidence |
| :---- | ----- | :---- | :---- |
| FR-03: Store classes and  assigned instructor | Class, Instructor  | One instructor to many classes;   Class.InstructorID foreign key | ERD, CREATE TABLE  statements, sample class   records |
| FR-04: Enroll students in  classes | Student, Class,   Enrollment | Many-to-many relationship resolved  by Enrollment | Enrollment table and insert  statements |
| FR-05: No duplicate   enrollment | Enrollment  | Unique StudentID/ClassID   combination | UNIQUE constraint and failed  duplicate-insert test |
| FR-06: Do not exceed   capacity | Class,   Enrollment | Enrolled count must not exceed class  capacity | Stored procedure, trigger, or  validation query |
| FR-07: Record   attendance | Enrollment,   Attendance | Attendance belongs to an enrollment  or valid student/class relationship | Attendance table and date based attendance query |
| FR-14: Monthly payment  total | Payment,   Student | Payment belongs to one student  | Aggregate SQL query with   GROUP BY month |

**Final student checklist** 

Before submitting your own FRD, verify that it: 

• Clearly explains the business problem and purpose. 

• Defines a reasonable scope for one database implementation project. 

• Identifies the users and their needs. 

• Includes numbered, testable functional requirements. 

• Identifies the major data subjects that will become entities/tables. 

• Includes business rules that guide keys, relationships, and constraints. 

• Specifies useful reports or SQL queries. 

• Contains assumptions and project limitations. 

• Includes acceptance criteria that can be demonstrated with SQL and sample data.  
• Aligns with the ERD, normalized relational schema, table definitions, sample data, and queries  submitted later in the project.