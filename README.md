# Official-Student-Lab-Management-App
The main official student management lab management app
Student Lab Management App

Project Overview

The Student Lab Management App is a mobile-based student registration and laboratory group management system.

The system allows students to register, manage their profiles, view their laboratory group status, and make group requests. Lecturers can manage student records, search and filter students, assign students to laboratory groups, and manage group information.

The system is designed to support both online and offline operation, with local Android storage and synchronization with the central server.

Project Objectives

The main objectives of the system are to:

- Allow students to register and log in.
- Allow students to view and edit permitted profile information.
- Allow students to view their laboratory group and group occupancy.
- Allow students to request laboratory group placement.
- Allow lecturers to add, view, edit and delete student records.
- Allow lecturers to search and filter students.
- Allow lecturers to assign students to laboratory groups.
- Enforce a maximum of 15 active students per laboratory group.
- Support offline data storage and synchronization.
- Handle synchronization conflicts safely.
- Protect student data using authentication, authorization and server-side validation.

Technologies Used

Android Application

- Android Studio
- Java
- XML
- Material Components
- Room Database
- ViewModel
- Repository
- Retrofit
- OkHttp
- WorkManager

Backend

- Node.js
- Express.js
- REST API

Database

- MySQL
- InnoDB
- SQL

Development Tools

- Git
- GitHub
- Android Emulator / Android Device
- MySQL Workbench

System Architecture

The system follows a layered architecture:

Android Application
       |
       v
View / Activity / Fragment
       |
       v
ViewModel
       |
       v
Repository
      / \
     /   \
    v     v
 Room   Retrofit
  |        |
  |        v
  |     Node.js
  |     Express
  |        |
  |        v
  |      MySQL
  |
WorkManager
     |
Offline Synchronization

The Android application does not connect directly to MySQL. Communication with the server is performed through the Node.js/Express REST API.

Main Student Functions

Students can:

1. Register an account.
2. Log in.
3. View their dashboard.
4. View and edit permitted profile information.
5. View their student number and programme.
6. View their laboratory group.
7. View group occupancy.
8. Request group placement when unassigned.
9. Use the application while offline where supported.
10. Synchronize pending operations when connectivity is restored.

Main Lecturer Functions

Lecturers can:

1. Log in.
2. View the student roster.
3. Add students.
4. View student details.
5. Edit student information.
6. Delete students using the appropriate deletion mechanism.
7. Search by student name.
8. Search by student number.
9. Filter by programme.
10. Filter by laboratory group.
11. View unassigned students.
12. Assign students to groups.
13. Manage laboratory groups.
14. View group members and occupancy.

Group Capacity

Each laboratory group has a maximum capacity of:

15 active students

The server/database is responsible for enforcing this limit. The Android application must not rely only on a local count because two devices could request the final available place at the same time.

Database

The database contains the core entities required by the system, including:

- "PROGRAMMES"
- "STUDENTS"
- "ACCOUNTS"
- "GROUPS"
- "PENDING_OPERATIONS"
- Deletion metadata / deletion markers

Important database rules include:

- "student_id" is immutable.
- "student_number" is unique.
- Each student can have one active laboratory group.
- A group cannot contain more than 15 active students.
- Foreign keys maintain relationships between records.
- Record versions support conflict detection.
- Passwords are stored as hashes on the server rather than as plain text.

API

The Node.js/Express backend provides API functionality for:

- Student registration
- Login/authentication
- Student CRUD operations
- Group assignment
- Student search
- Student filtering
- Synchronization
- Conflict handling

Protected requests perform appropriate identity, role and ownership checks.

Offline Synchronization

The Android application uses Room for durable local storage and WorkManager for background synchronization.

A typical operation follows this process:

User Action
    ↓
Save Locally
    ↓
Pending
    ↓
WorkManager
    ↓
Send to Server
    ↓
Node.js / Express
    ↓
MySQL
    ↓
Server Response
    ↓
Synced / Conflict / Rejected

The system supports states such as:

- Saved locally
- Pending
- Syncing
- Synced
- Action required

Security

Security measures include:

- Server-side authentication
- Role-based authorization
- Ownership checks
- Password hashing
- Parameterized SQL queries
- Server-side validation
- No passwords stored on the Android phone
- No secrets committed to GitHub
- Appropriate session handling

Project Structure

Student-Lab-Management-App/
│
├── README.md
├── .gitignore
│
├── AndroidApp/
│   └── README.md
│
├── Backend/
│   └── README.md
│
├── Database/
│   └── README.md
│
├── Documentation/
│   └── README.md
│
└── Testing/
    └── README.md

As development continues, the folders will contain the actual Android source code, Node.js backend, database scripts, documentation and testing evidence.

Installation and Setup

1. Clone the Repository

git clone <repository-url>
cd Student-Lab-Management-App

2. Android Application

Open the "AndroidApp" project using Android Studio.

Allow Gradle to synchronize and download the required dependencies.

Then:

Build → Make Project

Connect an Android device or start an Android emulator and run the application.

3. Database Setup

Install MySQL and MySQL Workbench.

Create the project database:

CREATE DATABASE student_lab_management;

Then execute the SQL scripts located in:

Database/

The database scripts will create the required tables, relationships and sample/fictitious data.

Do not upload real student information or database credentials to GitHub.

4. Backend Setup

Open a terminal inside the "Backend" directory:

cd Backend

Install the Node.js dependencies:

npm install

Configure the database connection using environment variables.

Then start the server:

node server.js

The Android application communicates with the backend through the REST API.

Testing

Testing documentation and evidence will be stored in:

Testing/

Testing will cover:

- Student registration
- Lecturer CRUD operations
- Duplicate student numbers
- Invalid input
- Group capacity
- Simultaneous group requests
- Offline saving
- Interrupted synchronization
- Conflict handling
- Remote deletion
- Authentication and authorization
- Search and filtering
- Accessibility

Documentation

Project documentation, architecture diagrams and wireframes will be stored in:

Documentation/

Group Members

No.| Name| Student Number| Responsibility
1| [Name]| [Number]| [Role]
2| [Name]| [Number]| [Role]
3| [Name]| [Number]| [Role]
4| [Name]| [Number]| [Role]
5| [Name]| [Number]| [Role]

Add all project group members before submission.

Contribution Log

A contribution log will record each member's contribution to:

- Code
- Testing
- Documentation
- Database
- UI/UX
- Architecture
- Integration

AI / Source Log

Any AI assistance or external sources used during development will be recorded according to the course requirements.

Important Development Rules

- Do not commit passwords, API keys or database credentials.
- Do not commit "node_modules".
- Use fictitious student data.
- Record dependency versions.
- Use parameterized SQL queries.
- Keep the Android application separate from the backend.
- Do not connect Android directly to MySQL.

Submission Requirements

The final project package will contain:

- Android source
- Node.js source
- APK
- Database scripts
- Test evidence
- Architecture diagrams/wireframes
- Setup README
- Contribution log
- AI/source log
- Group demonstration

Project Status

Status: In Development

The system is currently being developed according to the ICT361 Final Prototype Specification.
