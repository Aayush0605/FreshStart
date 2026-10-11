# NeighborLy — Master Frontend

This is the **main reusable React + Vite + TypeScript project** for NeighborLy. Keep adding future pages to this same project instead of creating a new Vite project for each page.

## Install once

From this folder, run this only the first time:

```bash
npm install
```

Then start the website:

```bash
npm run dev
```

Keep this project folder and its `node_modules` folder. For future pages, add/update source files and routes; **do not run `npm install` again** unless a new dependency is added to `package.json` or dependencies need to be restored.

## Current routes

- `/` — NeighborLy landing page
- `/explore` — placeholder route ready for the Explore page
- `/login` — placeholder route ready for Login
- `/signup` — placeholder route ready for Signup
- Any unknown route — 404 page

## Where to add future pages

1. Create a file in `src/pages/`, e.g. `ProfilePage.tsx`.
2. Import it in `src/App.tsx`.
3. Add a route inside `<Routes>`, e.g. `<Route path="/profile" element={<ProfilePage />} />`.
4. Use `Link` from `react-router-dom` for in-app navigation.
5. Keep shared styles in `src/styles.css` and shared components in `src/components/` (create that folder as needed).

When requesting future work, say: **“Add this page to my existing NeighborLy Master Frontend. Do not create a new project or replace existing pages. Keep the current dependencies and routes; only add what is needed.”**

## Build

```bash
npm run build
npm run preview
```

## Tech stack

- React 19 + TypeScript
- Vite
- React Router
- Framer Motion
- Lucide React

## Important

The current project is frontend-only. Authentication, provider verification, database, booking, escrow/payments, and server-side security are not implemented by these page placeholders. Do not treat client-side validation as security. Replace the example contact email and sample provider content before launch.


## Admin console preview

Open `http://localhost:5173/admin` to view the NeighborLy Admin Console. It includes a responsive sidebar, sample KPI cards, analytics chart, category mix, moderation queues, quick-action dialogs, a searchable/filterable listings table, platform-health placeholders, and an activity timeline. The listing approve/flag actions only change local React state. All numbers and events are illustrative; this page is not connected to a live database or backend.

Before production, secure `/admin` with server-enforced administrator authentication and role-based access control. Build protected API endpoints for analytics, user management, moderation, disputes, fees, categories, settings and audit logs. Never rely on frontend route hiding as authorization.

## Admin workspace functionality

Open `/admin`. Sidebar modules now include locally persisted management workspaces for users, listings, orders, moderation, reports/disputes, reviews, support, payment records, categories, content, audit records, analytics, and settings. The workspace supports search, status filters, adding records, changing statuses, deleting local records, CSV export, and JSON analytics export. Records persist in this browser through `localStorage`.

**Important limitation:** this is a frontend/local prototype. It does not authenticate administrators or change production users, Firestore data, orders, payments, escrow, public listings, or security policies. Do not treat local browser storage as secure or as a source of truth. Before deployment, connect these actions to authenticated server-side endpoints, enforce roles on the server, use Firestore rules, and add audit logging. The overview dashboard still contains illustrative demo metrics.
