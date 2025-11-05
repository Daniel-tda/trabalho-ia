# TaskFlow Technical Architecture

## 1. Overview

This document describes the technical architecture for the TaskFlow MVP. The architecture is designed to be scalable, maintainable, and secure, using a modern technology stack.

*   **Backend:** Java 17 with Spring Boot 3.x
*   **Database:** PostgreSQL
*   **Frontend:** React (or Vue.js)
*   **Authentication:** Spring Security with JSON Web Tokens (JWT)

## 2. Backend Architecture

The backend follows a classic three-layer architecture to separate concerns and promote modularity.

![Layered Architecture](https://i.imgur.com/8G4g4hK.png)

### 2.1. Controller Layer
*   **Framework:** Spring Web (MVC)
*   **Responsibility:** Exposes the RESTful API endpoints. Handles HTTP requests, deserializes request bodies into DTOs (Data Transfer Objects), and calls the appropriate service methods. It is responsible for input validation.

### 2.2. Service Layer
*   **Framework:** Spring Framework (@Service)
*   **Responsibility:** Contains the core business logic. It orchestrates calls to the repository layer and implements the application's use cases. Transactions are managed at this layer.

### 2.3. Repository Layer
*   **Framework:** Spring Data JPA
*   **Responsibility:** Handles all data persistence and retrieval operations. It defines interfaces that extend `JpaRepository`, allowing Spring to automatically implement basic CRUD operations.

### 2.4. Security
*   **Framework:** Spring Security
*   **Responsibility:** Manages authentication and authorization. A JWT-based filter chain will be implemented to secure API endpoints. A `UserDetailsService` will be used to load user-specific data.

## 3. Database Schema (High-Level)

The initial database schema for the MVP will consist of three main tables.

*   **`users`**
    *   `id` (PK, BIGINT, Auto-increment)
    *   `name` (VARCHAR)
    *   `email` (VARCHAR, Unique)
    *   `password` (VARCHAR)

*   **`projects`**
    *   `id` (PK, BIGINT, Auto-increment)
    *   `name` (VARCHAR)
    *   `description` (TEXT)
    *   `owner_id` (FK to `users.id`)

*   **`tasks`**
    *   `id` (PK, BIGINT, Auto-increment)
    *   `title` (VARCHAR)
    *   `description` (TEXT)
    *   `status` (VARCHAR)
    *   `project_id` (FK to `projects.id`)
    *   `assignee_id` (FK to `users.id`, Nullable)

## 4. API Design (RESTful)

The API will be designed following REST principles.

*   **Authentication:** `POST /api/auth/register`, `POST /api/auth/login`
*   **Projects:** `GET /api/projects`, `POST /api/projects`
*   **Tasks:** `GET /api/projects/{projectId}/tasks`, `POST /api/projects/{projectId}/tasks`, `PUT /api/tasks/{taskId}`

## 5. Frontend Architecture

The frontend is a **Single Page Application (SPA)** built using **React**.

### 5.1. Core Libraries
*   **Framework:** React 18
*   **Routing:** `react-router-dom` for declarative, client-side routing.
*   **API Communication:** `axios` for making HTTP requests to the backend REST API.
*   **Styling:** A simple CSS approach (e.g., CSS Modules or a lightweight library like Bootstrap) for the MVP.

### 5.2. Folder Structure
The `/src/frontend/src` directory will be organized as follows:
```
/src
   ├── components/      # Reusable UI components (Button, Input, etc.)
   ├── pages/           # Top-level page components (LoginPage, DashboardPage, etc.)
   ├── services/        # API communication logic (authService.js, projectService.js)
   ├── context/         # (Optional) React Context for global state management
   ├── App.js           # Main application component with routing setup
   └── index.js         # Application entry point
```

### 5.3. Component-Based Architecture
The UI will be broken down into a hierarchy of reusable components.
*   **Page Components:** Represent entire screens (e.g., `LoginPage`).
*   **Functional Components:** Represent specific pieces of the UI (e.g., `ProjectCard`, `TaskColumn`).
*   **Shared Components:** Generic, reusable elements (e.g., `Button`, `Modal`).

### 5.4. State Management
*   For the MVP, component-level state (`useState`) and prop drilling will be used for simplicity.
*   For global state like user authentication status, React's `Context API` will be used to avoid prop drilling.

### 5.5. API Integration
*   An `api.js` service will be created to configure the `axios` instance, setting the base URL (`http://localhost:8080`) and handling JWT tokens in Authorization headers.
*   Separate service files (`authService.js`, `projectService.js`) will encapsulate the logic for specific API endpoints.

