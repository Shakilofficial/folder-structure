#  Scalable Frontend Folder Structure

```markdown
project-name/
│
├── app/                           # Next.js App Router
│   │
│   ├── (public)/
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   ├── about/
│   │   ├── blog/
│   │   └── contact/
│   │
│   ├── (auth)/
│   │   ├── layout.tsx
│   │   ├── login/
│   │   ├── register/
│   │   ├── forgot-password/
│   │   └── reset-password/
│   │
│   ├── dashboard/
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   ├── analytics/
│   │   ├── profile/
│   │   └── settings/
│   │
│   ├── admin/
│   │   ├── layout.tsx
│   │   ├── users/
│   │   ├── content/
│   │   └── system/
│   │
│   ├── api/                       # Optional API routes
│   │
│   ├── layout.tsx
│   ├── page.tsx
│   ├── error.tsx
│   ├── loading.tsx
│   └── not-found.tsx
│
├── features/                      # Feature-based architecture
│   │
│   ├── auth/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── auth.store.ts
│   │   ├── auth.schema.ts
│   │   └── auth.types.ts
│   │
│   ├── blog/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── queries/
│   │   ├── services/
│   │   ├── blog.schema.ts
│   │   └── blog.types.ts
│   │
│   ├── dashboard/
│   │   ├── components/
│   │   ├── queries/
│   │   ├── services/
│   │   └── dashboard.types.ts
│   │
│   └── admin/
│       ├── users/
│       ├── analytics/
│       └── audit/
│
├── components/                    # Shared UI components
│   │
│   ├── ui/                        # UI primitives
│   │   ├── button.tsx
│   │   ├── input.tsx
│   │   ├── modal.tsx
│   │   ├── dropdown.tsx
│   │   └── table.tsx
│   │
│   ├── core/                      # Higher level reusable components
│   │   ├── form/
│   │   ├── table/
│   │   ├── modal/
│   │   └── layout/
│   │
│   └── shared/                    # Global components
│       ├── Navbar.tsx
│       ├── Footer.tsx
│       ├── Logo.tsx
│       ├── PageHeader.tsx
│       └── Loader.tsx
│
├── server-actions/                # Server Actions (Next.js)
│   │
│   ├── auth.actions.ts
│   ├── blog.actions.ts
│   ├── user.actions.ts
│   └── upload.actions.ts
│
├── queries/                       # TanStack Query hooks
│   │
│   ├── auth.query.ts
│   ├── blog.query.ts
│   ├── user.query.ts
│   └── dashboard.query.ts
│
├── stores/                        # Global state (Zustand)
│   │
│   ├── auth.store.ts
│   ├── theme.store.ts
│   ├── modal.store.ts
│   └── ui.store.ts
│
├── schema/                        # Validation schemas (Zod)
│   │
│   ├── auth.schema.ts
│   ├── user.schema.ts
│   ├── blog.schema.ts
│   └── common.schema.ts
│
├── services/                      # API communication
│   │
│   ├── api.ts
│   │
│   ├── auth/
│   │   └── auth.service.ts
│   │
│   ├── user/
│   │   └── user.service.ts
│   │
│   ├── blog/
│   │   └── blog.service.ts
│   │
│   └── admin/
│       └── admin.service.ts
│
├── hooks/                         # Global custom hooks
│   ├── use-auth.ts
│   ├── use-pagination.ts
│   ├── use-debounce.ts
│   └── use-media-query.ts
│
├── types/                         # TypeScript types
│   │
│   ├── api.ts
│   ├── common.ts
│   │
│   ├── auth/
│   │   └── auth.types.ts
│   │
│   ├── user/
│   │   └── user.types.ts
│   │
│   └── blog/
│       └── blog.types.ts
│
├── lib/                           # Utilities & helpers
│   ├── fetcher.ts
│   ├── token.ts
│   ├── utils.ts
│   ├── validators.ts
│   ├── date-utils.ts
│   └── file-utils.ts
│
├── config/                        # App configuration
│   ├── site.config.ts
│   ├── api.config.ts
│   ├── navigation.ts
│   └── constants.ts
│
├── providers/                     # Global providers
│   ├── index.tsx
│   ├── AuthProvider.tsx
│   ├── ThemeProvider.tsx
│   └── QueryProvider.tsx
│
├── styles/
│   ├── globals.css
│   ├── variables.css
│   └── animations.css
│
├── public/
│   ├── images/
│   ├── icons/
│   ├── fonts/
│   └── illustrations/
│
├── middleware.ts
│
├── next.config.ts
├── tailwind.config.ts
├── tsconfig.json
├── package.json
└── README.md
```

---

# Folder Explanation

## app/

Contains all **routes, layouts, and pages** using the **App Router**.

Example:

* Public pages
* Authentication pages
* Admin dashboard
* User dashboard

This folder defines the **main routing structure of the application**.

---

## features/

The `features` folder organizes the application by **business domain or feature**.

Each feature contains its own:

* components
* hooks
* services
* schemas
* types

Example:

```
features/
  auth/
  blog/
  dashboard/
  admin/
```

This keeps related logic **grouped together and easier to maintain**.

---

## components/

Contains **shared reusable UI components** used across the entire application.

Example:

* Buttons
* Form inputs
* Modals
* Tables
* Layout components

The components are typically separated into:

* `ui` → low-level UI primitives
* `core` → reusable application components
* `shared` → global layout elements

---

## server-actions/

Contains **server actions** used in **Next.js**.

These handle **server-side mutations**, such as:

* form submissions
* authentication
* database updates
* file uploads

---

## queries/

This folder contains **data fetching logic** using **TanStack Query**.

Queries are used to:

* fetch API data
* manage caching
* handle background updates

Example:

```
queries/
  auth.query.ts
  user.query.ts
  blog.query.ts
```

---

## stores/

Contains global state management using **Zustand**.

Typical stores include:

* authentication state
* UI state
* theme state
* modal state

---

## schema/

Contains **validation schemas**, usually built with **Zod**.

Schemas are used to validate:

* forms
* API inputs
* request payloads

Example:

```
schema/
  auth.schema.ts
  blog.schema.ts
  user.schema.ts
```

---

## services/

Handles **API communication** with the backend.

This layer keeps all HTTP requests centralized.

Example:

```
services/
  auth/
  user/
  blog/
  admin/
```

---

## hooks/

Contains reusable **custom React hooks**.

Examples:

* authentication hooks
* pagination hooks
* responsive hooks
* debounce hooks

---

## types/

Defines **TypeScript types and interfaces** used throughout the application.

Example:

```
types/
  api.ts
  auth/
  user/
  blog/
```

---

## lib/

Utility and helper functions used across the project.

Examples:

* token handling
* date formatting
* string utilities
* API helpers

---

## config/

Contains **application configuration files** such as:

* navigation configuration
* API configuration
* global constants
* site metadata

---

## providers/

Contains **global React providers**.

Examples:

* authentication provider
* theme provider
* query provider

These wrap the root layout of the application.

---

## styles/

Global styling files for the application.

Example:

* global CSS
* CSS variables
* animation styles

---

## public/

Stores **static assets** served by the application.

Example:

* images
* icons
* fonts
* illustrations

---

## middleware.ts / proxy.ts

Next.js middleware / proxy used for:

* authentication checks
* route protection
* redirects

---

# Design Principles

This structure follows several important principles:

* **Modular architecture** — each feature is isolated
* **Reusable components** — shared UI across the application
* **Clean separation of logic** — UI, services, and state management are separated
* **Scalable structure** — easy to add new features without restructuring the project
* **Type safety** — strong TypeScript support across the project

---

&copy; 2026 Md.Shakil Hossain