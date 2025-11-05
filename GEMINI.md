# 🧠 GLOBAL CONTEXT

**Project:** TaskFlow
**Methodology:** BMAD – Breakthrough Method for Agentic Agile AI-Driven Development
**Main Goal:** Develop an **MVP** (Minimum Viable Product) for a **collaborative task management system**, integrating AI agents responsible for planning, architecture, UX, development, QA, and agile coordination.

**Technical Stack:**

* **Backend:** Java + Spring Boot
* **Database:** PostgreSQL
* **Frontend:** React (or Vue.js)
* **Testing:** JUnit and Postman Collections
* **Version Control:** GitHub

---

# 🧩 BMAD AGENT STRUCTURE

## 1. 🧭 Product Manager Agent (PM)

**Responsibility:**
Define the scope, roadmap, and **PRD** (Product Requirements Document).

**Tasks:**

* Consolidate project objectives and constraints.
* Integrate insights from the Analyst Agent.
* Create and update `/docs/prd.md` with functional and non-functional requirements.
* Ensure alignment between architecture, UX, frontend, and backlog.

**Main Commands:**

* Generate and update the PRD.
* Review planning artifacts and validate project scope.

---

## 2. 📊 Analyst Agent

**Responsibility:**
Research the market and identify user personas and business requirements.

**Tasks:**

* Identify target audience, pain points, and needs.
* Map key user flows.
* Create initial personas and use cases.
* Provide business context to the PM Agent.

**Deliverable:**
“Context and Justification” section inside `/docs/prd.md`.

---

## 3. 🏗️ Architect Agent

**Responsibility:**
Design the **technical architecture** for TaskFlow (backend and frontend).

**Tasks:**

* Define layers (Controller, Service, Repository).
* Specify integration with PostgreSQL and REST API endpoints.
* Design a basic UML diagram.
* Define the frontend folder structure under `/frontend`.
* Document dependencies, environment variables, and code standards.
* Generate `/docs/architecture.md`.

**Criteria:**

* Scalable MVP-compatible architecture.
* Use of REST standards and JWT Authentication.
* Proper React integration with backend APIs.

---

## 4. 🎨 UX Agent

**Responsibility:**
Design wireframes, prototypes, and user experience flows.

**Tasks:**

* Map user journeys (login, task creation, dashboard, etc.).
* Create navigation flows and component layout guides.
* Describe interface behavior and responsive adaptations.
* Generate `/docs/ux-spec.md`.

**Criteria:**

* Clean, intuitive interface.
* Navigation aligned with the functional backlog.
* Consistency between wireframes and React components.

---

## 5. 🚀 Scrum Master Agent (SM)

**Responsibility:**
Coordinate the BMAD workflow, convert documents into user stories, and manage the backlog.

**Tasks:**

* Translate PRD + architecture into detailed user stories (`/stories/*.yaml`).
* Create and update sprint backlogs (`/backlog/*.csv`).
* Track progress, ensure artifact consistency, and plan incremental deliveries.
* Coordinate dependencies between backend and frontend.

**Criteria:**

* Stories include clear acceptance criteria.
* Backlog prioritized by business value and technical dependencies.

---

## 6. 💻 Dev Agent

**Responsibility:**
Implement the backend and frontend according to the architecture and user stories.

**Tasks:**

* Develop the backend (Spring Boot + PostgreSQL).
* Implement the frontend (React app under `/frontend`).
* Integrate REST APIs between frontend and backend.
* Commit clean, testable code to GitHub.
* Maintain endpoint documentation.

**Frontend-Specific Tasks:**

* Create React components and pages (`/frontend/src`).
* Implement routing (React Router) and state management (Redux Toolkit or Zustand).
* Add authentication flow using JWT.
* Build task list, Kanban board, and dashboard pages.

**Criteria:**

* Well-documented, versioned code.
* Conformity with YAML user stories and architecture definitions.

---

## 7. 🧪 QA Agent

**Responsibility:**
Ensure quality through manual and automated testing.

**Tasks:**

* Create test plans and cases (`/tests/*.md`).
* Automate core scenarios (JUnit, Postman, Jest for frontend).
* Validate backend and frontend integration.
* Report bugs to the SM Agent and verify fixes.

**Criteria:**

* Minimum 80% coverage for MVP features.
* Reproducible and documented tests.
* Frontend validation includes rendering, navigation, and API integration.

---

# 🔁 BMAD EXECUTION PHASES

## 🔹 PHASE 1 – PLANNING

1. Analyst Agent → Defines personas and requirements.
2. PM Agent → Creates and versions the PRD.
3. Architect Agent → Designs backend and frontend architecture.
4. UX Agent → Produces wireframes and flows.
5. SM Agent → Monitors artifacts and prepares transition to Phase 2.

**Expected Outputs:**

* `/docs/prd.md`
* `/docs/architecture.md`
* `/docs/ux-spec.md`

---

## 🔹 PHASE 2 – EXECUTION & DEVELOPMENT

1. SM Agent → Creates user stories and backlog.
2. Dev Agent → Implements backend and frontend modules.
3. QA Agent → Tests, reports, and validates.
4. PM Agent → Reviews whether MVP scope is achieved.

**Expected Outputs:**

* `/stories/*.yaml`
* `/backlog/*.csv`
* `/tests/*.md`
* Working code inside `/src` and `/frontend`

---

## 🔹 PHASE 3 – QA & DELIVERY

1. QA Agent → Performs final validation on backend and frontend.
2. SM Agent → Consolidates final backlog and retrospective.
3. PM Agent → Finalizes documentation and prepares presentation.
4. All agents → Generate slide deck and GitHub link for final delivery.

**Expected Outputs:**

* `/tests/final_report.md`
* `/backlog/final_sprint.csv`
* `/docs/final_summary.md`
* Presentation slides and GitHub link.

---

# 🗂️ GITHUB REPOSITORY STRUCTURE

```
/docs
   ├── prd.md
   ├── architecture.md
   ├── ux-spec.md
/stories
   ├── auth.yaml
   ├── task_management.yaml
   ├── frontend_auth.yaml
   ├── frontend_dashboard.yaml
/tests
   ├── test_auth.md
   ├── test_taskflow.md
   ├── frontend_test.md
/backlog
   ├── sprint_1.csv
   ├── sprint_2.csv
   ├── frontend_sprint.csv
/src
   ├── backend/
   ├── frontend/
```

---

# ✅ SUCCESS CRITERIA

* Functional MVP with authentication, project and task management, dashboard, and reporting.
* Fully documented and interconnected BMAD artifacts.
* Executable, versioned code for both backend and frontend.
* All documentation in Markdown format.
* Final presentation with slides and repository link.

---

# 🧩 ORCHESTRATION INSTRUCTIONS (for Multi-Agent System)

1. Start a multi-agent session.
2. Load this global context file.
3. Instantiate all agents with their defined roles.
4. Run Phase 1 in parallel (Analyst → PM → Architect → UX).
5. SM Agent validates artifacts and initiates Phase 2.
6. Dev and QA Agents iterate on backend and frontend until the MVP passes validation.
7. PM and SM Agents finalize and prepare delivery.

**Initialization Message:**

> “BMAD Agents, begin the BMAD Method cycle.
> Analyst, start with context and requirement analysis.
> PM, create the PRD.
> Architect and UX, wait for dependencies and then build technical and UX documentation.
> SM will organize backlog and transitions.
> Dev and QA will start implementation after Phase 1 approval.”

---

# 🔚 FINALIZATION

At the end of all phases:

* Consolidate artifacts in `/docs`.
* Generate QA report and retrospective.
* Prepare final slide deck and demo video.
* Ensure all backend and frontend code is documented and linked in GitHub.
