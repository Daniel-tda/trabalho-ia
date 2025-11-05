# Frontend Test Plan: TaskFlow React App

This document outlines the test cases for the TaskFlow frontend application.

| Test Case ID | Module      | Description                                                  | Steps                                                              | Expected Result                                                      |
|--------------|-------------|--------------------------------------------------------------|--------------------------------------------------------------------|----------------------------------------------------------------------|
| FE-TC-01     | Auth        | Verify successful user registration via UI.                  | 1. Go to /register. 2. Fill form with valid data. 3. Submit.       | User is redirected to /login. A success notification appears.        |
| FE-TC-02     | Auth        | Verify successful user login via UI.                         | 1. Go to /login. 2. Enter valid credentials. 3. Submit.            | User is redirected to the dashboard ('/'). `localStorage` has a token. |
| FE-TC-03     | Auth        | Verify that protected routes redirect unauthenticated users. | 1. Log out. 2. Attempt to navigate directly to '/'.                | User is redirected to '/login'.                                      |
| FE-TC-04     | Projects    | Verify that the project list is displayed correctly.         | 1. Log in. 2. View the dashboard.                                  | An API call to `/api/projects` is made. Projects are listed.         |
| FE-TC-05     | Tasks       | Verify that the task board is displayed for a project.       | 1. Log in. 2. Click on a project from the dashboard.               | User is navigated to `/projects/{id}`. Tasks are shown in columns.   |
| FE-TC-06     | Tasks       | Verify that updating a task's status works via drag-and-drop.| 1. On the task board, drag a task to a new column.                 | An API call to `/api/tasks/{id}` is made. The UI reflects the change.|
