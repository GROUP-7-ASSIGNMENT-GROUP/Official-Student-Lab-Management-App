Android Application

Overview

This folder contains the Android application for the Student Lab Management App.

The application provides separate functionality for students and lecturers.

Student Features

Students can:

- Register an account.
- Log in.
- View their dashboard.
- View and edit permitted profile information.
- View their student number and programme.
- View their laboratory group.
- View group occupancy.
- Request laboratory group placement.
- Work with locally cached data when offline.
- Synchronize pending operations when connectivity is restored.

Lecturer Features

Lecturers can:

- Log in.
- View students.
- Add students.
- Edit student records.
- Delete student records.
- Search students.
- Filter students by programme and group.
- View unassigned students.
- Assign students to laboratory groups.
- Manage laboratory groups.

Android Technologies

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

Architecture

UI
 ↓
ViewModel
 ↓
Repository
 ↓
Room / Retrofit
 ↓
WorkManager
 ↓
Node.js REST API

How to Run

1. Open the "AndroidApp" folder in Android Studio.
2. Allow Gradle to synchronize.
3. Connect an Android device or start an emulator.
4. Build the project.
5. Run the application.

Configuration

The Android application communicates with the Node.js backend through the REST API.

Update the API base URL when configuring the application for a local or deployed server.
