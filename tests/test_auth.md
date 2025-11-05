# Test Plan: Authentication

This document outlines the test cases for the user authentication functionality.

**Feature:** User Registration and Login
**User Stories:** USER-001, USER-002

| Test Case ID | Description                                               | Steps                                                              | Expected Result                                             |
|--------------|-----------------------------------------------------------|--------------------------------------------------------------------|-------------------------------------------------------------|
| AUTH-TC-01   | Verify successful user registration.                      | 1. Navigate to registration page. 2. Fill in valid data. 3. Submit. | User is created. Success message is shown.                  |
| AUTH-TC-02   | Verify registration with an existing email.               | 1. Attempt to register with an email that is already in use.       | Registration fails. Error message is shown.                 |
| AUTH-TC-03   | Verify successful user login.                             | 1. Navigate to login page. 2. Enter valid credentials. 3. Submit.  | User is logged in. A JWT is returned.                       |
| AUTH-TC-04   | Verify login with invalid password.                       | 1. Navigate to login page. 2. Enter correct email, wrong password. | Login fails. Appropriate error message is displayed.        |
| AUTH-TC-05   | Verify that protected endpoints require authentication.   | 1. Attempt to access `/api/projects` without a valid JWT.          | Access is denied with a 401 Unauthorized status.            |
