
Overview

This folder contains the Node.js and Express backend for the Student Lab Management App.

The backend provides a REST API that allows the Android application to communicate with the MySQL database.

Responsibilities

The backend handles:

- User registration.
- Authentication.
- Lecturer authentication.
- Student CRUD operations.
- Group assignment.
- Student search.
- Student filtering.
- Synchronization.
- Conflict handling.
- Server-side validation.
- Role and ownership checks.

Technologies

- Node.js
- Express.js
- MySQL
- REST API

Project Structure

Backend/
├── server.js
├── package.json
├── package-lock.json
├── routes/
├── controllers/
├── db/
└── README.md

Installation

Open a terminal inside this folder:

npm install

Starting the Server

Run:

node server.js

The server will then provide the REST API used by the Android application.

Database Connection

The backend connects to the MySQL database.

Database credentials should be stored securely using environment variables and must not be committed to GitHub.

Security

The backend uses:

- Authentication.
- Authorization.
- Role checks.
- Ownership checks.
- Server-side validation.
- Parameterized SQL queries.
- Password hashing.

Android communicates with the backend through the API and does not connect directly to MySQL.
