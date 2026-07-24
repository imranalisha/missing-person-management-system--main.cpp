# missing-person-management-system--main.cpp
First-semester C++ project at UNIVERSITY: A console-based system using file handling and basic authentication to securely manage missing person records.

# Missing Person Management System

This repository contains my first-ever semester project for my Software Engineering degree. At the end of our first semester, our instructor tasked us with designing a general project that addresses a real-world societal problem. I chose to build a system that helps manage and track missing persons during crises.

## About the Project

The **Missing Person Management System** is a C++ console-based application designed to track and manage reports of missing individuals, particularly during critical situations like natural disasters or wars. 

This system aims to assist individuals, NGOs, and local authorities in maintaining organized data to facilitate family reunification efforts and preserve essential digital backups of missing person reports.

### Key Features
* **Secure Access:** Basic username and password authentication.
* **Add Records:** Log new missing person reports (includes personal details, last seen location, contact info, and current status).
* **View Records:** Display all stored missing person records in the system.
* **Search Functionality:** Quickly search for a specific person by their name.
* **Data Persistence:** All records are saved locally to a text file for future reference and backup.

## Repository Contents

* `main.cpp` (or whatever your file is named): The C++ source code containing the complete logic of the application.
* `Project_Report.pdf`: A detailed document outlining the project requirements, design, and execution.

## Technical Concepts Applied

Built entirely in C++, this project demonstrates foundational programming concepts learned during my first semester:
* **Data Structures:** Structure (`struct`), Array of Structures
* **File Handling:** Reading and writing to text files (`ifstream`, `ofstream`)
* **Control Flow:** Conditional statements (`if`, `switch`) and Loops (`for`, `do-while`)
* **Core Logic:** Functions, Constants (`const`), String Handling (`string`)
* **I/O:** User Input processing (`cin`, `getline`)

## How to Run
1. Clone the repository to your local machine.
2. Compile the `.cpp` file using any standard C++ compiler (e.g., GCC, MinGW, or through an IDE like Dev-C++ or Visual Studio).
3. Run the compiled executable to interact with the console interface.
