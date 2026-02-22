# Backend Project Folder Structure

This project follows a **modular and scalable backend architecture**. Each folder has a clear responsibility to keep the codebase organized, maintainable, and easy to scale as the application grows.

---

# Project Structure

```
backend-project/

├── src/
│
│   ├── app/
│   ├── configs/
│   ├── constants/
│   ├── database/
│   ├── errors/
│   ├── interfaces/
│   ├── middlewares/
│   ├── logs/
│   ├── modules/
│   ├── routes/
│   ├── services/
│   ├── utils/
│   ├── scripts/
│
├── tests/
├── .env
├── .env.example
├── .prettierrc.json
├── tsconfig.json
├── eslint.config.mts
├── package.json
├── pnpm-lock.yaml
└── README.md
```

---

# Folder Explanation

## src/app

This folder initializes the application.

* **app.ts** → Configures Express app, middleware, and routes.
* **server.ts** → Starts the HTTP server.

This separation allows the app to be reused for testing or other environments.

---

# configs

Stores configuration logic for environment variables and external services.

Examples:

* **env.config.ts** → Loads environment variables
* **database.config.ts** → Database connection setup
* **redis.config.ts** → Redis caching configuration
* **cloudinary.config.ts** → File upload service setup

Keeping configurations centralized makes the system easier to maintain.

---

# constants

Contains global constants used across the project.

Examples:

* **roles.ts** → User roles
* **permissions.ts** → System permissions
* **response.constant.ts** → Standard API responses

This prevents hardcoded values in business logic.

---

# database

Handles database setup and migrations.

* **Database.ts** → Database connection instance
* **migrations/** → Database schema migrations
* **seeds/** → Seed scripts for initial data

This helps manage database schema changes safely.

---

# errors

Defines custom error classes.

Examples:

* **AppError.ts** → Base application error
* **ValidationError.ts** → Validation-related errors

These errors are used by the global error handler to return consistent API responses.

---

# interfaces

Contains global TypeScript types and interfaces.

Examples:

* **request.ts** → Custom request types
* **response.ts** → API response structure
* **common.ts** → Shared interfaces

This ensures strong type safety across the application.

---

# middlewares

Stores Express middleware functions.

Examples:

* **Auth.ts** → Authentication middleware
* **RoleGuard.ts** → Role-based access control
* **ValidateRequest.ts** → Request validation
* **RateLimiter.ts** → API rate limiting
* **Upload.ts** → File upload handling
* **GlobalErrorHandler.ts** → Central error handling
* **NotFound.ts** → Handles unknown routes

Middleware helps control request flow and security.

---

# logs

Handles logging configuration.

* **logger.ts** → Logger setup (e.g., Winston or Pino)

Used for debugging, monitoring, and production logging.

---

# modules

Contains **feature-based modules**.
Each module represents a domain or business feature.

Example modules:

* **auth** → Authentication system
* **user** → User management
* **product** → Product management
* **order** → Order management

Each module usually contains:

* controller → handles HTTP requests
* service → business logic
* route → API route definitions
* validation → request validation schema
* interface → TypeScript types
* constant → module constants

This structure keeps features isolated and scalable.

---

# routes

Central place where all module routes are combined.

* **index.ts** imports routes from every module and registers them in the Express app.

---

# services

Contains **global services** used across modules.

Examples:

* **email.service.ts** → Email sending logic
* **sms.service.ts** → SMS notifications
* **storage.service.ts** → File storage handling

These services can be reused by different modules.

---

# utils

Reusable helper functions.

Examples:

* **catchAsync.ts** → Handles async errors in controllers
* **pagination.ts** → Pagination helper
* **jwt.ts** → JWT token utilities
* **response.ts** → Standard API response format
* **pick.ts** → Extract specific object fields
* **generateId.ts** → Unique ID generation
* **now.ts** → Timestamp utilities

Utilities keep the code DRY.

---

# scripts

Contains CLI scripts for development tasks.

Examples:

* **generate-module.ts** → Auto-generate new modules
* **seed-admin.ts** → Create initial admin user

These scripts improve developer productivity.

---

# tests

Contains automated tests.

* **unit/** → Unit tests for individual functions
* **integration/** → API and module integration tests

Testing ensures code reliability.

---

# Root Files

Important configuration files:

* **.env** → Environment variables
* **.env.example** → Example environment variables
* **tsconfig.json** → TypeScript configuration
* **eslint.config.mts** → Code linting rules
* **.prettierrc.json** → Prettier configuration
* **package.json** → Project dependencies and scripts
* **pnpm-lock.yaml** → Package lock file
* **README.md** → Project documentation

---

✅ This architecture provides:

* Clear separation of concerns
* Feature-based modular development
* Scalable backend structure
* Clean and maintainable codebase

---

&copy; 2026 Md.Shakil Hossain