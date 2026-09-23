# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Primary: small software teams (a handful to a dozen-plus people) who track day-to-day development work: issues moving through triage, implementation, cross-team waits and code review.

Secondary: people evaluating the author's work (recruiters, engineers) who open the public demo to judge the product and its craft. The product must work as a real team tool and read well as a portfolio piece at the same time.

## Product Purpose

TaskSystem is an issue tracker and project board. Teams create projects, file issues under project keys, move them through a status workflow on a Kanban board, discuss them in comments, and see what is assigned to them. Success means a team can run its development workflow in it without reaching for another tool, and an evaluator can understand the product and its quality within minutes.

## Positioning

A self-hosted issue tracker the team owns end to end: its own Java/Spring backend and its own React frontend, deployable on the team's infrastructure, with a Jira-style workflow (Triage, Waiting for team, Code Review) rather than a hosted SaaS the team rents.

## Operating Context

- Daily use on desktop browsers; installable as a PWA and usable on phones (the board switches to a carousel on mobile).
- Work is organized as projects with short keys; issues are addressed by key (e.g. `TS-13`).
- Teams are assigned to projects and issues; admins manage users and labels.
- A public demo exists at http://komuna.site/.
- Backend: Java/Spring Boot API (`/api/v1/**`), currently running locally on port 6901 with a temporary H2 database.

## Capabilities and Constraints

- **Auth:** registration and login with JWT; roles include admin (user management, label management).
- **Projects:** create, view details, progress (done vs. total issues), owner, team assignment.
- **Issues:** title, description, project key, 8 statuses (New, Triage, To Do, In Progress, Waiting for Team, Code Review, Done, Canceled), 4 priorities (Low, Normal, High, Critical), assignee, team, due date, labels, watchers/preview, full page and quick-preview modal.
- **Board:** Kanban with drag and drop; Basic mode (3 grouped columns) and Detailed mode (8 status columns); carousel navigation on mobile.
- **Collaboration:** comments with @mentions and pasted images; per-issue activity log (created, status, priority, assignee, team, due date, title, description changes); notifications (e.g. assignment).
- **Dashboard:** issues assigned to the user, owned and recent projects, workspace totals, charts (status, priority, trend, project progress), user-selectable layouts (default, custom widgets, Jira-like side panel) persisted per user.
- **Search:** global search across projects and issues.
- **Theme:** light and dark mode with a user toggle (required).
- **Language:** the entire UI, including the landing page, is in English (required).
- **Name:** the product is called TaskSystem (required). The current checkbox mark is not binding and may be redesigned.
- **Stack:** React 19, Vite, Tailwind CSS v4, Radix UI, Zustand, GSAP, Recharts, vite-plugin-pwa.
- **Planned, not built yet:** Docker deployment with a PostgreSQL database that seeds demo accounts on build, so anyone can run the stack locally or try a ready-made demo account. Do not present this as available until it ships.
- **Open decisions:** pricing and licensing are undecided; real-time push (SignalR hub) is not implemented in the new backend.

## Brand Commitments

- Name: TaskSystem.
- English-language product and marketing copy.
- Light and dark themes both first-class.

## Evidence on Hand

- Real app screenshots: `src/assets/tsimg1.png` (dashboard), `src/assets/tsimg2.png` (projects), `src/assets/tsimg3.png` (board), dark mode, with some content blurred.
- Public demo URL: http://komuna.site/.
- Source repository: https://github.com/PioZac002/TaskSystemFront (public visibility unconfirmed).
- No customers, testimonials, usage metrics, benchmarks, or pricing exist. Future work must not fabricate them.

## Product Principles

1. The team owns it: self-hosted, no dependency on a vendor's cloud.
2. Show real workflow states, not just "in progress": blockers and reviews must be visible.
3. Everything is addressable by key and traceable in the activity log.
4. It must hold up to scrutiny as engineering craft, since evaluators judge it as a portfolio piece.
