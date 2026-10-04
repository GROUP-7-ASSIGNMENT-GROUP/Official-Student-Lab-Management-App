Testing

Overview

This folder contains the test cases and test results for the Student Lab Management App.

Testing is performed to verify that the application meets its functional, security, database, synchronization and usability requirements.

Test Areas

Testing includes:

- Student registration
- Student login
- Lecturer login
- Student CRUD operations
- Duplicate student numbers
- Invalid input
- Group assignment
- Group capacity
- Simultaneous group requests
- Offline operations
- Synchronization
- Conflict handling
- Remote deletion
- Authentication and authorization
- Search and filtering
- Accessibility

Test Cases

All planned test cases are documented in:

"test_cases.md"

Test Results

The results of performed tests are documented in:

"test_results.md"

Expected Group Capacity

A laboratory group must never contain more than 15 active students.

The concurrent group-request test must demonstrate that when two clients request the final available place, only one request succeeds.
