# Technical Documentation

## Missing Persons Management System

## 1. Technical Overview

The Missing Persons Management System is a procedural C++ console application.

The application uses an array of structures to store records in memory and text-file input/output to provide persistent storage.

The main components are:

```text
Login
  │
  ▼
Record Array
  │
  ├── Add Record
  │
  ├── Display Records
  │
  ├── Search Records
  │
  └── Load Records
          │
          ▼
  missing_persons.txt
```

---

# 2. Technologies

## Programming Language

**C++**

The application uses standard C++ functionality rather than external libraries.

## Header Files

### `<iostream>`

Used for console input and output.

### `<fstream>`

Used for reading and writing the data file.

### `<string>`

Used for storing textual information.

---

# 3. Data Structure

The primary data structure is:

```cpp
struct MissingPerson
```

It contains eight fields:

```cpp
string name;
int age;
string gender;
string location;
string dateMissing;
string guardianContact;
string physicalDescription;
string status;
```

Each instance represents one missing-person record.

---

# 4. Record Storage

The program creates an array:

```cpp
MissingPerson records[MAX_RECORDS];
```

The maximum number of records is defined as:

```cpp
const int MAX_RECORDS = 100;
```

Therefore, the current application can hold up to 100 records in memory.

The variable:

```cpp
int count;
```

keeps track of the number of active records.

---

# 5. Login Function

The login system is implemented using:

```cpp
bool login()
```

The function:

1. Displays project information.
2. Requests a username.
3. Requests a password.
4. Compares them with the configured credentials.
5. Returns `true` for successful authentication.
6. Returns `false` otherwise.

The `main()` function uses the returned Boolean value to decide whether access should be granted.

### Security Note

The current implementation is educational only because the credentials are hardcoded.

A production system should use:

* Password hashing
* Secure credential storage
* Session management
* Account management
* Access control

---

# 6. Add Record Function

The function:

```cpp
void addRecord(MissingPerson records[], int &count)
```

is responsible for adding a new record.

The function first checks:

```cpp
if (count >= MAX_RECORDS)
```

If the maximum capacity has been reached, the function stops and displays an error.

Otherwise, it collects information from the user.

The function uses `getline()` for text fields so that values containing spaces can be entered.

After collecting the information, the record is written to:

```text
missing_persons.txt
```

using:

```cpp
ofstream
```

The file is opened using append mode:

```cpp
ios::app
```

This means new records are added to the existing file rather than replacing previous records.

---

# 7. Display Records Function

The function:

```cpp
void displayRecords(const MissingPerson records[], int count)
```

loops through the records from index `0` to `count - 1`.

For every record, it displays all stored fields.

If no records exist, the function displays:

```text
No records to display.
```

---

# 8. Search Function

The search operation is implemented by:

```cpp
void searchByName(const MissingPerson records[], int count)
```

The function:

1. Requests a name.
2. Loops through all records.
3. Compares the entered name with each stored name.
4. Displays the matching record.
5. Reports when no match is found.

The comparison currently uses:

```cpp
records[i].name == searchName
```

Therefore, the search is an exact string comparison.

---

# 9. File Loading

Previously saved records are loaded by:

```cpp
void loadRecords(MissingPerson records[], int &count)
```

The function opens:

```text
missing_persons.txt
```

using:

```cpp
ifstream
```

It then reads each stored field and places the information into the record array.

This allows records to remain available after the program has been closed and restarted.

---

# 10. Main Program

The `main()` function controls the overall application.

The basic sequence is:

```text
Start
 ↓
Login
 ↓
Load Records
 ↓
Main Menu
 ↓
User Selection
 ↓
Perform Operation
 ↓
Return to Menu
 ↓
Exit
```

The menu is implemented using a `do-while` loop and a `switch` statement.

Available options are:

```text
1. Add New Record
2. Display All Records
3. Search by Name
4. Exit
```

---

# 11. Function Dependency

```text
main()
 │
 ├── login()
 │
 ├── loadRecords()
 │
 ├── addRecord()
 │
 ├── displayRecords()
 │
 └── searchByName()
```

Each function has a specific responsibility.

This separation makes the program easier to understand and maintain.

---

# 12. File Format

The application stores records in the following format:

```text
name | age | gender | location | dateMissing | guardianContact | physicalDescription | status
```

The pipe character:

```text
|
```

is used as a separator between fields.

The application reads the fields in the same order in which they were written.

---

# 13. Memory and Storage

The application has two main forms of storage.

### Temporary Storage

Records currently being used by the program are stored in:

```cpp
MissingPerson records[100];
```

### Persistent Storage

Records are stored between program executions in:

```text
missing_persons.txt
```

Therefore:

```text
User Input
    ↓
Array in Memory
    ↓
Text File
```

When the application starts again:

```text
Text File
    ↓
Array in Memory
```

---

# 14. Complexity

The current implementation uses simple linear operations.

### Display

Displaying all records:

```text
O(n)
```

### Search

Searching by name:

```text
O(n)
```

where `n` is the number of records.

Because the current system supports only 100 records, this approach is sufficient for the educational prototype.

A larger system would require more efficient database indexing and querying.

---

# 15. Error Handling

The application contains basic error handling.

Examples include:

### Record Limit

```text
Record limit reached!
```

### File Error

```text
Error saving to file.
```

### Invalid Menu Choice

```text
Invalid choice.
```

### Empty Database

```text
No records to display.
```

### Search Failure

```text
No matching record found.
```

---

# 16. Known Technical Improvements

The current source code works as an educational prototype, but several areas can be improved.

## Input Validation

The program should validate:

* Age
* Date format
* Empty names
* Status values
* Menu input

## Authentication

Credentials should not be hardcoded.

## Data Storage

A database should replace the text file for a larger system.

## Search

Search could support:

* Partial names
* Case-insensitive matching
* Location
* Status
* Date

## Record Management

Future versions should support:

* Update
* Delete
* Unique IDs

## Security

Sensitive information should be protected through appropriate security mechanisms.

---

# 17. Development Lessons

This project demonstrates an important transition from basic programming concepts to software development.

The project started with a real-world problem and converted that problem into:

```text
Problem
  ↓
Requirements
  ↓
Data Structure
  ↓
Functions
  ↓
File Storage
  ↓
User Interface
  ↓
Working Program
```

This provides a foundation for developing larger systems in future semesters.

---

# 18. Future Architecture

A future version could move from the current architecture:

```text
C++ Console
     │
     ▼
Array
     │
     ▼
Text File
```

to a more scalable architecture:

```text
Mobile/Web Interface
        │
        ▼
    Backend API
        │
        ▼
     Database
        │
        ▼
 Secure Storage
```

This would make the system more suitable for larger numbers of records and multiple authorized users.

---

# 19. Conclusion

The current implementation is intentionally simple because it was developed as a first-semester academic project.

Its primary purpose was to demonstrate fundamental programming concepts while solving a meaningful record-management problem.

The system provides a foundation that can later be redesigned using modern software engineering principles, databases, secure authentication, APIs, and user-friendly interfaces.
