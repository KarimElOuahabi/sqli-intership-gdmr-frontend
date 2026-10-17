# GDMR Frontend

Web client for **GDMR**, an occupational health visit management platform. It has role-specific dashboards for admins, HR, doctors and employees, with live notifications.

Built during my internship at SQLI. The API lives in [gdmr-backend](https://github.com/KarimElOuahabi/gdmr-backend).

## Features

- **Role-based UI:** `ADMIN`, `HR`, `DOCTOR` and `EMPLOYEE` each get their own pages, sidebar and route guards. The rules mirror the backend's authorization.
- **Visit workflow:** request, propose, confirm or reject, schedule, run, and complete visits, with a full negotiation history.
- **Live notifications:** a bell with an unread count, updated through Server-Sent Events.
- **Medical records:** patient history and documents for doctors, and an upload page for employees.
- **Staff and user management:** list, search, filter, edit and delete, with data tables and tabbed detail views.
- **Auth:** access token kept in memory, with automatic refresh and retry on `401` through an httpOnly cookie.

## Tech stack

React 19 · TypeScript · Vite · Redux Toolkit (RTK Query) · React Router 7 · Tailwind CSS 4 · react-hook-form + Zod · TanStack Table · Base UI / shadcn-style components

## Structure

```
src/
├── app/          store, base query with reauth
├── features/     one folder per domain, each with its own RTK Query API
├── pages/        route components grouped by role
├── components/   ui primitives, shared composites, layouts
└── routes/       single source of truth for paths and role gating
```

## Running locally

Requirements: Node.js 20+ and the [backend](https://github.com/KarimElOuahabi/gdmr-backend) running on port 8080.

```bash
cp .env.example .env   # VITE_API_URL=http://localhost:8080/api
npm install
npm run dev            # http://localhost:5173
```

Other scripts: `npm run build`, `npm run lint`, `npm run preview`.

## Related

- Backend: [gdmr-backend](https://github.com/KarimElOuahabi/gdmr-backend)
