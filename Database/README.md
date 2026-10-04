Database

Overview

This folder contains the MySQL database scripts for the Student Lab Management App.

The database stores student, account, programme, laboratory group and synchronization information.

Database Technologies

- MySQL
- InnoDB
- SQL
- Foreign Keys
- Transactions

Main Tables

PROGRAMMES

Stores information about academic programmes.

STUDENTS

Stores student information including:

- Student ID
- Student number
- Full name
- Programme
- Group
- Record version
- Active/deleted status

ACCOUNTS

Stores account and authentication information for students and lecturers.

Passwords are stored as hashes on the server.

GROUPS

Stores laboratory group information.

Each group has a maximum of 15 active students.

PENDING_OPERATIONS

Stores operations waiting to be synchronized with the server.

Deletion Metadata

Stores information required to prevent deleted records from incorrectly returning during synchronization.

Setup

1. Install MySQL.
2. Open MySQL Workbench.
3. Run "database.sql".
4. Run "tables.sql".
5. Run "sample_data.sql".

Important Rules

- Student IDs are immutable.
- Student numbers are unique.
- A student can have one active group.
- A group cannot exceed 15 active students.
- Foreign keys maintain database relationships.
- Transactions are used where necessary for safe concurrent operations.

Data Safety

Only fictitious data should be used in this project.

Database passwords, credentials and other secrets must not be uploaded to GitHub.
