# Product Requirements Document (PRD) for TaskFlow MVP

## 1. Introduction

TaskFlow is a collaborative task management system designed to help individuals and small teams organize, track, and manage their work efficiently. This document outlines the requirements for the Minimum Viable Product (MVP), which focuses on core functionalities for user authentication, project creation, and task management.

## 2. Target Audience & Personas

*   **Persona 1: The Freelancer (Paulo)**
    *   **Needs:** A simple way to manage tasks for multiple clients/projects. Needs to track deadlines and task statuses.
    *   **Pain Points:** Juggling tasks in spreadsheets or notebooks is inefficient and error-prone.

*   **Persona 2: The Small Team Manager (Ana)**
    *   **Needs:** A centralized place to assign tasks to team members and monitor progress. Needs a clear overview of who is working on what.
    *   **Pain Points:** Lack of visibility into team workload and project status leads to delays and communication overhead.

## 3. Functional Requirements

### 3.1. User Authentication
*   **USER-001:** Users must be able to create a new account (register) with a name, email, and password.
*   **USER-002:** Users must be able to log in using their email and password.
*   **USER-003:** The system must provide a secure session management (e.g., using JWT).
*   **USER-004:** Users must be able to log out.

### 3.2. Project Management
*   **PROJ-001:** Authenticated users must be able to create a new project with a name and an optional description.
*   **PROJ-002:** Users must be able to view a list of all projects they have created or are a member of.

### 3.3. Task Management
*   **TASK-001:** Within a project, users must be able to create a new task with a title, description, and status.
*   **TASK-002:** Tasks should have a default status of "To Do" upon creation.
*   **TASK-003:** Users must be able to view all tasks within a project, organized by status (e.g., in a Kanban-style board).
*   **TASK-004:** Users must be able to update the status of a task (e.g., "To Do", "In Progress", "Done").
*   **TASK-005:** Users must be able to assign a task to another user within the same project (for MVP, we can simplify to assigning to any registered user).

## 4. Non-Functional Requirements

*   **NFR-001 (Security):** User passwords must be securely hashed and salted before being stored in the database.
*   **NFR-002 (Security):** All API endpoints (except for login/register) must be protected and require authentication.
*   **NFR-003 (Performance):** Core API responses (e.g., fetching tasks for a project) should complete in under 500ms under normal load.
*   **NFR-004 (Usability):** The user interface must be clean, intuitive, and easy to navigate.
