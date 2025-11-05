# Test Plan: Project and Task Management

This document outlines test cases for core project and task management features.

**Feature:** Projects and Tasks
**User Stories:** PROJ-001, TASK-001, TASK-004

| Test Case ID | Description                               | Steps                                                                 | Expected Result                                                              |
|--------------|-------------------------------------------|-----------------------------------------------------------------------|------------------------------------------------------------------------------|
| PROJ-TC-01   | Verify successful project creation.       | 1. Log in. 2. Navigate to create project. 3. Enter valid data. 4. Submit. | A new project is created and linked to the user.                             |
| TASK-TC-01   | Verify successful task creation.          | 1. Log in. 2. Open a project. 3. Click "New Task". 4. Enter valid data. | A new task is created in the "To Do" column.                                 |
| TASK-TC-02   | Verify task status update.                | 1. Log in. 2. Open a project. 3. Drag a task to "In Progress".        | The task's status is updated in the backend and reflected on the UI.         |
| TASK-TC-03   | Verify that tasks are scoped to a project.| 1. Create tasks in Project A. 2. Open Project B.                      | Tasks from Project A should not be visible in Project B.                     |
