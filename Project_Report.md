Missing Persons Management System

1. Introduction

The Missing Persons Management System is a console-based application developed using C++.

The purpose of the project is to provide a simple method of recording and managing information about missing persons. Instead of relying completely on handwritten records, the application demonstrates how basic computer programming concepts can be used to store, retrieve, and organize information digitally.

The project was developed as a first-semester academic project.
 moreover it's a very basic project for learners.
---

2. Problem Statement

During emergencies and critical situations, information about missing people can become difficult to organize.

Traditional paper-based records can be difficult to search, update, preserve, and manage when the number of records increases.

There is therefore a need for a simple system that can:

1. Store information about missing persons.
2. Organize the collected information.
3. Retrieve records when required.
4. Search for a specific person.
5. Preserve records after the application closes.

This project demonstrates a basic solution to this problem using C++ and file handling.

---

3. Project Objectives

The main objectives of the project are:

- To develop a basic missing-person record management system.
- To practice structured programming in C++.
- To understand the use of structures.
- To understand arrays for storing multiple records.
- To implement functions for different operations.
- To learn file input and output.
- To implement a simple login system.
- To implement record searching.
- To maintain persistent records using a text file.

---

4. Scope

The current system focuses on basic record management.

The system supports:

- User authentication
- Adding records
- Viewing records
- Searching records
- Saving records to a file
- Loading previously saved records
- Tracking a person's status

The system does not currently provide professional investigation, identity verification, location tracking, communication with authorities, or automatic matching of people.

---

5. Target Users

The prototype is designed for an authorized person responsible for maintaining missing-person information.

Examples could include:

- A project administrator
- A responsible volunteer
- An organization maintaining records
- An academic demonstration user

The system should not be considered an official emergency or law-enforcement system.

---

6. Functional Requirements

FR-01: User Login

The system shall allow a user to enter a username and password.

FR-02: Authentication

The system shall allow access only when the entered credentials match the configured credentials.

FR-03: Add Record

The system shall allow the user to add a missing-person record.

FR-04: Store Personal Information

The system shall store:

- Name
- Age
- Gender
- Location
- Date missing
- Guardian contact
- Physical description
- Status

FR-05: Save Record

The system shall save newly added records to a text file.

FR-06: Load Records

The system shall load previously saved records when the application starts.

FR-07: Display Records

The system shall display all records currently available.

FR-08: Search Records

The system shall allow the user to search for a person by name.

FR-09: Record Limit

The system shall limit the number of records to 100 in the current implementation.

FR-10: Exit

The system shall allow the user to safely exit the application.

---

7. Non-Functional Requirements

Usability

The system should be simple enough for a user with basic computer knowledge to operate.

Reliability

The application should save records correctly and load previously stored records when possible.

Performance

The application should respond quickly because the current system operates on a small number of records.

Maintainability

The program is divided into separate functions so individual operations can be understood and modified more easily.

Security

The current prototype provides only basic authentication. It does not implement professional security mechanisms such as password hashing or encryption.

Portability

The application uses standard C++ libraries and can be compiled on systems with a compatible C++ compiler.

---

8. System Modules

The system consists of the following major modules.

8.1 Login Module

Responsible for displaying the login interface and checking credentials.

Main function:

bool login()

8.2 Record Management Module

Responsible for creating new missing-person records.

Main function:

void addRecord(...)

8.3 Display Module

Responsible for displaying stored records.

Main function:

void displayRecords(...)

8.4 Search Module

Responsible for finding a person by name.

Main function:

void searchByName(...)

8.5 File Management Module

Responsible for reading and writing records.

Main functions:

void loadRecords(...)

and file operations inside:

addRecord(...)

---

9. Data Model

The application uses a C++ structure named "MissingPerson".

The structure contains:

Field| Data Type| Description
name| string| Name of the person
age| int| Age of the person
gender| string| Gender
location| string| Last known location
dateMissing| string| Date the person went missing
guardianContact| string| Guardian/family contact
physicalDescription| string| Physical characteristics
status| string| Current status

The structure allows related information to be grouped into a single record.

---

10. Data Storage

The project uses a text file called:

missing_persons.txt

The program uses:

ofstream

to save records and:

ifstream

to load records.

Records are stored in a pipe-separated format.

Example structure:

Name | Age | Gender | Location | Date | Contact | Description | Status

This provides basic persistent storage without requiring a database.

---

11. Program Flow

The application follows this general sequence:

Start
  ↓
Login
  ↓
Credentials Correct?
  ↓
Yes
  ↓
Load Existing Records
  ↓
Display Main Menu
  ↓
┌───────────────┬──────────────────┬─────────────────┐
│ Add Record    │ Display Records  │ Search by Name  │
└───────────────┴──────────────────┴─────────────────┘
  ↓
Return to Main Menu
  ↓
Exit
  ↓
End

If authentication fails:

Start
  ↓
Login
  ↓
Credentials Incorrect
  ↓
Access Denied
  ↓
End

---

12. Testing

The following basic test cases can be used with the current application.

Test Case| Input/Action| Expected Result
TC-01| Correct username/password| Login successful
TC-02| Incorrect credentials| Access denied
TC-03| Add valid record| Record saved
TC-04| Display records| Records displayed
TC-05| Search existing name| Matching record displayed
TC-06| Search unknown name| No matching record message
TC-07| Add more than 100 records| Record limit message
TC-08| Restart application| Previously saved records loaded
TC-09| Select invalid menu option| Invalid choice message
TC-10| Select Exit| Application closes

---

13. Limitations

The current version has several technical limitations.

Fixed Record Capacity

The application can store only 100 records in memory.

Simple Authentication

The username and password are directly included in the source code.

Plain-Text Storage

Sensitive information is stored in a normal text file without encryption.

Exact Name Search

The search function requires the entered name to match the stored name.

No Editing

Existing records cannot currently be edited.

No Deletion

The application does not provide record deletion.

Console Interface

The system does not have a graphical user interface.

No Database

A text file is used instead of a relational database.

---

14. Ethical and Privacy Considerations

Missing-person information may contain sensitive personal information, including contact details and physical descriptions.

Therefore, a real-world implementation would require strong privacy and security controls.

The current project should only be used with appropriate test or authorized data.

The prototype should not be used as an official source for identifying missing people.

---

15. Future Development

The project can be expanded significantly.

Version 2

Possible improvements include:

- Unique record IDs
- Edit records
- Delete records
- Better searching
- Search by location
- Search by status
- Input validation
- Improved menu system

Version 3

Possible technical improvements:

- MySQL/PostgreSQL database
- Secure authentication
- Password hashing
- Role-based access
- Graphical interface
- Backup and restore
- Audit logs

Advanced Version

A future implementation could potentially become:

- Web-based
- Mobile-based
- Cloud-connected
- Multilingual
- Database-driven
- Integrated with authorized organizations

Such a version would require careful security, privacy, legal, and ethical considerations.

---

16. Learning Outcomes

Through this project, the following concepts were practiced:

- C++ syntax
- Variables
- Data types
- Structures
- Arrays
- Functions
- Loops
- Conditional statements
- Strings
- File handling
- Basic authentication
- Searching algorithms
- Modular programming
- Basic software design

---

17. Conclusion

The Missing Persons Management System successfully demonstrates how fundamental C++ programming concepts can be combined to create a functional information-management application.

Although the current implementation is simple and has several limitations, it provides a strong foundation for understanding how software can be designed to solve a real-world problem.

The project also provides a foundation for future development using databases, graphical interfaces, secure authentication, and modern software engineering practices.