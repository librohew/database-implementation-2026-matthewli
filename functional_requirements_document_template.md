**Functional Requirements Document (FRD)** 

**1\. Project identification** 

| Item  | Your information |
| ----- | ----- |
| Project title  | KOHA-Lite Inventory Management for Little Free Libraries |
| Prepared by  | Matthew Li & Yash Shashtri |
| Course/section  | 01:198:437:01 |
| Date  | October 17, 2026 |
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

**5\. Functional requirements** 


| ID  | Functional requirement  | Priority  | Related data/entities |
| ----- | ----- | ----- | ----- |
| FR-01  | The system shall be able to securely track books.  | High  | Reader, Books |
| FR-02  | The system shall map which libraries have which books.  |  High | Libraries, Books |
| FR-03  | The system shall return a list of books in the library.  | High  | Libraries, Books, Reader |

**6\. Data requirements** 

| Data subject  | Information to store  | Example identifiers |
| ----- | ----- | ----- |
| Reader | Name, contact information, books out  | Reader ID |
| Book  | Name, price, category, quantity  | Book ID |
| Library  | Location, status, readers, books | Library ID |

**7\. Business rules and validation rules** 

| ID  | Business rule  | Possible database enforcement |
| ----- | ----- | ----- |
| BR-01  | Each book must have a unique Book ID.  | Primary key, UNIQUE |
| BR-02  | A reader can only check out books that are available in the library.  | Primary key, foreign key |
| BR-03  | The quantity of books cannot be negative.  | Query Logic |

**8\. Reports and queries** 


| ID  | Report/query name  | Purpose  | Required result |
| ----- | ----- | ----- | ----- |
| RQ-01  | BooksAvailable  | How many total books are in the library?  | Totals |
| RQ-02  | BooksCheckedOut  | How many of the books that are checked out belong to the reader?  | Filters |
| RQ-03  | BookTrend  | How many times has this specific book been checked out?  |  Sorting |

**9\. Assumptions and constraints** 


• Assumption: Each product is supplied by one primary supplier. 

• Assumption: A customer may check out many books.

• Constraint: The project will use MySQL.

• Constraint: The project will not use real-world personal identifying details such as phone numbers. 

**10\. Acceptance criteria** 

**Template** 

| Requirement  | Acceptance criterion |
| ----- | ----- |
| FR-01  | Using dataflow analysis/cryptographic techniques to demonstrate that no data is revealed that isn't meant to be revealed. |
| FR-02  | Rendering a map that shows which books belong to which libraries. |
| FR-03  | Returning arbitrary little free libraries' catalog lists and ensuring ACID properties are not violated. |