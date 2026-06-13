# Mini CRM Backend

Author: krutika goharkar

A role-based Mini CRM backend built with **NestJS**, **PostgreSQL**, and **Prisma**.
The system supports **Admin** and **Employee** roles with secure JWT authentication.

---

## 🚀 Tech Stack

- Node.js + TypeScript
- NestJS
- PostgreSQL (Docker)
- Prisma ORM
- JWT Authentication
- Swagger API Documentation
- Postman Collections

---

## ✨ Features

### Authentication
- User registration and login
- JWT-based authentication
- Role-based access control (ADMIN, EMPLOYEE)
- Secure password hashing with bcrypt

### Users (ADMIN Only)
- View all users
- View user by ID
- Update user role

### Customers
- Create, read, update, delete customers
- Pagination support
- Unique email and phone validation
- ADMIN: full access
- EMPLOYEE: read-only access

### Tasks
- ADMIN can create and assign tasks to employees
- Tasks linked to customers
- ADMIN sees all tasks
- EMPLOYEE sees only assigned tasks
- Task status updates with ownership checks

---

## 🛠️ Setup Instructions

### Clone repository

```bash
git clone <repository-url>
cd <project-folder>
```

### Install dependencies

```bash
npm install
```

### Environment
Create a `.env` file with these values (update as needed):

```env
DATABASE_URL=postgresql://postgres:postgres@localhost:5432/mini_crm
JWT_SECRET=supersecretkey
JWT_EXPIRES_IN=1d
```

### Start PostgreSQL (Docker)

```bash
docker-compose up -d
```

### Prisma setup

```bash
npx prisma migrate dev
npx prisma db seed
```

This creates the initial ADMIN user.

### Run the server (development)

```bash
npm run start:dev
```

Server runs at: http://localhost:3000

### API docs

Swagger UI: http://localhost:3000/api/docs

JWT Bearer authentication is supported.

### API testing

Postman collections are available in the `postman/` folder:

- Auth-Customers.postman_collection.json
- Tasks.postman_collection.json

See [docs/TESTING.md](docs/TESTING.md) for details.

### Default admin

- Email: admin@test.com
- Password: admin123

### Project structure (simplified)

src/
 ├── auth
 ├── users
 ├── customers
 ├── tasks
 ├── prisma
 └── common
