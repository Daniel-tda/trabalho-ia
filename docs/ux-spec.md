# TaskFlow UX Specification (MVP)

## 1. Design Philosophy

The user experience (UX) for TaskFlow will be clean, intuitive, and minimalist. The goal is to reduce cognitive load and allow users to manage their tasks with minimal friction. The interface will be straightforward, prioritizing core functionality over complex features for the MVP.

## 2. User Journeys

### 2.1. New User Onboarding
1.  **Landing Page:** A simple page with a call-to-action to "Sign Up".
2.  **Registration:** The user clicks "Sign Up", fills out a simple form (Name, Email, Password), and is redirected to the login page.
3.  **Login:** The user logs in with their new credentials.
4.  **Dashboard:** The user lands on the main dashboard, which is initially empty, with a prompt to "Create your first project".

### 2.2. Project & Task Creation
1.  **Create Project:** From the dashboard, the user clicks "Create Project", enters a project name and description in a modal or form.
2.  **Project View:** The user is taken to the project view, which displays a Kanban-style board.
3.  **Create Task:** The user clicks a "New Task" button, fills in a title and description, and the task appears in the "To Do" column.

### 2.3. Daily Task Management
1.  **Login:** The user logs in and sees their list of projects on the dashboard.
2.  **Select Project:** The user clicks on a project to view its task board.
3.  **Update Task Status:** The user drags a task card from the "To Do" column to the "In Progress" column.
4.  **Complete Task:** The user drags the task card to the "Done" column.

## 3. Wireframes (Text-based Description)

### 3.1. Login / Register Screen
*   **Layout:** Centered form on a clean background.
*   **Components:**
    *   App Logo (TaskFlow)
    *   "Login" or "Register" Title
    *   Input field: Name (Register only)
    *   Input field: Email
    *   Input field: Password
    *   Button: "Login" or "Create Account"
    *   Link: "Don't have an account? Register" or "Already have an account? Login"

### 3.2. Dashboard (Projects List)
*   **Layout:** Top navigation bar with user profile/logout; main content area with a list of projects.
*   **Components:**
    *   **Header:** "My Projects"
    *   **Button:** "+ New Project"
    *   **Project List:** A grid or list of cards, where each card shows:
        *   Project Name
        *   A snippet of the description
        *   (Optional) Number of tasks

### 3.3. Task Board Screen (Project View)
*   **Layout:** Top navigation bar; project title as a header; main area with three columns.
*   **Components:**
    *   **Header:** Project Name
    *   **Columns:**
        *   **To Do:** Contains task cards. A "+" button at the top to add a new task to this column.
        *   **In Progress:** Contains task cards.
        *   **Done:** Contains task cards.
    *   **Task Card:** A draggable card that displays:
        *   Task Title
        *   (Optional) Assignee avatar/initials

## 4. Key Interactions
*   **Drag-and-Drop:** Users will move tasks between columns to update their status.
*   **Modals:** Forms for creating new projects and tasks will appear in modals to keep the user in the same context.
*   **Feedback:** Clear visual feedback for actions (e.g., a success message after creating a task).
