# Missing Persons Management System

A C++ console-based application developed as a first-semester software engineering project to help maintain organized records of missing persons during emergencies and critical situations.

## 📌 Project Overview

The **Missing Persons Management System** is designed to provide a simple digital alternative to maintaining missing-person records manually on paper.

The system allows an authorized user to:

* Log in to the system
* Add missing-person records
* Store records permanently in a text file
* Display all stored records
* Search for a person by name
* Track the current status of a person
* Maintain a digital backup of collected information

The project was developed as an educational project to practice fundamental C++ programming concepts and understand how a basic information management system works.

## 🎯 Motivation

During situations such as wars, floods, earthquakes, and other emergencies, families can become separated and information about missing people can become difficult to organize.

This project was inspired by the humanitarian need to maintain organized information about missing persons and provide a basic digital record that could potentially help responsible organizations organize information more effectively.

> **Important:** This project is an educational prototype and is not intended to replace professional missing-person databases, government systems, emergency services, or verified humanitarian organizations.

## ✨ Features

### 1. User Login

The system contains a basic login mechanism to prevent unauthorized access.

### 2. Add Missing Person

The user can enter information including:

* Name
* Age
* Gender
* Last known location
* Date missing
* Guardian contact
* Physical description
* Current status

### 3. Display All Records

The system displays all missing-person records currently loaded into memory.

### 4. Search by Name

Users can search for a missing person using their name.

### 5. File Storage

Records are saved to a text file named:

`missing_persons.txt`

This allows information to remain available after the program is closed.

### 6. Record Limit

The program uses a fixed-size array with a maximum capacity of 100 records.

### 7. Status Tracking

Each record can contain a status such as:

* Missing
* Found

## 🛠️ Technologies Used

| Technology | Purpose                        |
| ---------- | ------------------------------ |
| C++        | Main programming language      |
| iostream   | Console input/output           |
| fstream    | File reading and writing       |
| string     | Text-based information         |
| Structures | Organizing missing-person data |
| Arrays     | Storing multiple records       |
| Functions  | Modular program design         |
| Text File  | Persistent data storage        |

## 🏗️ Basic System Structure

```text
                    ┌──────────────────────┐
                    │       Login          │
                    └──────────┬───────────┘
                               │
                         Authentication
                               │
                               ▼
                    ┌──────────────────────┐
                    │     Main Menu        │
                    └──────────┬───────────┘
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
             ▼                 ▼                 ▼
       Add Record       Display Records    Search by Name
             │                 │                 │
             └─────────────────┼─────────────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Text File Storage  │
                    │ missing_persons.txt  │
                    └──────────────────────┘
```

## 📂 Project Structure

```text
Missing-Persons-Management-System/
│
├── README.md
├── PROJECT_REPORT.md
├── TECHNICAL_DOCUMENTATION.md
│
├── src/
│   └── main.cpp
│
├── data/
│   └── .gitkeep
│
└── .gitignore
```

## ▶️ How to Run

### Requirements

You need a C++ compiler such as:

* GCC / G++
* MinGW
* Visual Studio
* Code::Blocks
* Dev-C++
* Visual Studio Code with a C++ compiler

### Compile

Using G++:

```bash
g++ src/main.cpp -o missing_persons
```

### Run

Linux/macOS:

```bash
./missing_persons
```

Windows:

```bash
missing_persons.exe
```

## 🔐 Login

The current educational version uses a fixed username and password inside the source code.

This is intentionally simple because the project was created to demonstrate basic programming concepts.

For a real-world system, credentials should **never be hardcoded in source code**.

## 💾 Data Storage

The program stores records in:

```text
missing_persons.txt
```

Records are stored using a pipe-separated format:

```text
Name | Age | Gender | Location | Date | Contact | Description | Status
```

When the program starts, previously saved records are loaded into memory.

## ⚠️ Current Limitations

This is a first-semester educational project, so it has several limitations:

* Maximum of 100 records
* Console-based interface
* Single-user login
* Fixed credentials
* Plain-text data storage
* No database
* Exact-name searching
* No edit/delete functionality
* No advanced validation
* No encryption
* No role-based access control
* No network functionality
* No automated backup system
* No professional identity verification

These limitations provide opportunities for future development.

## 🚀 Future Improvements

Possible future versions could include:

* Graphical user interface
* Database integration
* Secure authentication
* Password hashing
* Multiple user accounts
* Admin and staff roles
* Edit and delete functionality
* Advanced search and filtering
* Unique record IDs
* Image/document support
* Automatic backups
* Cloud synchronization
* Mobile application
* Web application
* Secure communication with authorized organizations
* Better data validation
* Audit logs
* Multilingual support

## 📚 Learning Outcomes

This project helped demonstrate practical use of:

* Variables
* Data types
* Conditional statements
* Loops
* Functions
* Arrays
* Structures
* Strings
* Input/output
* File handling
* Basic authentication
* Searching
* Modular programming

## 👨‍💻 Project Type

**Academic / Educational Project**

**Semester:** First Semester

**Language:** C++

**Application Type:** Console Application

## 📄 License

This project is intended primarily for educational purposes.

You may modify and extend it for learning and academic use.

## ⭐ Project Status

**Status:** Completed — First Semester Academic Project

The current version represents the original educational implementation. Future versions can improve security, usability, scalability, and data management.
