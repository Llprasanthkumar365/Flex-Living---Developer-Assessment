# Flex-Living---Developer-Assessment
# Expense Tracker Starter — README

This is a minimal **starter** full-stack project (frontend + backend) to track expenses.

---

## Stack (defaults)
- **Frontend:** React  
- **Backend:** Java Spring Boot  
- **Database:** MongoDB (can be switched to PostgreSQL)  
- **Auth:** JWT (notes included; full implementation optional)

---

## What is included
- `backend/` — Spring Boot application with Expense model, repository, and REST controller (CRUD + pagination stub).  
- `frontend/` — React app skeleton with pages to list and add expenses.  
- `README.md` — this file.  
- `backend/README-JWT.md` — notes & next steps for adding JWT auth.  
- `.gitignore`

---

## Quick start (local)

### Prerequisites
- Java 17+ and Maven  
- Node 18+  
- MongoDB running locally (default: `mongodb://localhost:27017/expensedb`)

### Backend
1. Open terminal:
```bash
cd backend
mvn spring-boot:run
2.Server will run on http://localhost:8080.
API endpoints:

GET /api/expenses — list (supports ?page= & ?size= query params; starter returns all)

POST /api/expenses — create

GET /api/expenses/{id} — read

PUT /api/expenses/{id} — update

DELETE /api/expenses/{id} — delete
Frontend:
Open separate terminal:
cd frontend
npm install
npm start

2.App runs on http://localhost:3000 and communicates with backend at http://localhost:8080 (CORS enabled).
Project structure (high level):
/backend
  ├─ pom.xml
  ├─ src/main/java/com/example/expensetracker
  │   ├─ ExpenseTrackerApplication.java
  │   ├─ model/Expense.java
  │   ├─ repository/ExpenseRepository.java
  │   └─ controller/ExpenseController.java
  └─ src/main/resources/application.properties

/frontend
  ├─ package.json
  ├─ public/index.html
  └─ src/
     ├─ index.js
     ├─ App.js
     └─ components/
        ├─ AddExpense.js
        └─ ExpenseList.js

Notes :
JWT / Auth

A simple JWT authentication flow is planned but not included in this starter. See backend/README-JWT.md for recommended steps:

Add User model + UserRepository.

Add AuthController with /api/auth/register and /api/auth/login.

Use a JWT library (e.g., io.jsonwebtoken:jjwt or com.auth0:java-jwt) to issue & validate tokens.

Implement a JwtFilter and SecurityFilterChain to protect /api/expenses/**.

Use HTTP-only cookies for access/refresh token handling (recommended).
Next steps / customization suggestions

Implement full JWT auth (register/login, refresh tokens, HTTP-only cookies).

Add charts & insights page (Chart.js / react-chartjs-2) with aggregation endpoints on backend.

Add pagination, filters (by date / category / amount), and backend aggregation endpoints for totals / percentages.

Add unit/integration tests (Spring Boot tests + React testing).

Dockerize backend + frontend + MongoDB and add docker-compose.yml for easy deployment.

Improve UI/UX, add login/register flows, and protect routes.[expense-tracker-starter.zip](https://github.com/user-attachments/files/22460532/expense-tracker-starter.zip)

This starter project is minimal and designed to be extended for assignments or demos.

JWT authentication, charts, and insights are not implemented yet; instructions are provided in backend/README-JWT.md.

You can switch the database from MongoDB to PostgreSQL if needed.

The frontend and backend run on different ports (3000 and 8080), so CORS is enabled in the backend by default.

Recommended next steps:

Add JWT auth, login/register, and refresh token handling.

Implement charts and spending insights with backend aggregation endpoints.

Add pagination and filtering for expenses.

Dockerize backend + frontend + database for one-command setup.
