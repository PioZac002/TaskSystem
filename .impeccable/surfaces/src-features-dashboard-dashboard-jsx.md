---
version: 1
slug: "src-features-dashboard-dashboard-jsx"
primary_target: "src/features/dashboard/Dashboard.jsx"
related_targets: []
---

# Surface: Dashboard (/dashboard)

Mode: Operate.
Task: on open, see a general overview of issues and projects, weighted to what is assigned to or owned by the user (open, due, overdue, blocked, in review), then act (open an issue, create a project or issue).
Frequency: many times a day. Scanability and stable positions outrank expression.
Must keep: layouts Default / Custom (widget toggle, order, half/full width, persisted per user) / Jira-like side panel; charts (status, priority, trend, project progress) with project filter; quick preview modals; links to full pages; create project and issue; +P / +I labels.
Replaces: the Classic/Fluid interface-style toggle and its CSS.

## Direction contract

THESIS: the dashboard is the cabinet's HUD and level select: your run at a glance, never a game that hides the work. Refuses the stat-card row plus widget grid of every admin template.

OWN-WORLD: same world as the landing: phosphor-black / instruction-card-white grounds, 16-color sprite palette with one color and glyph per status, pixel caps for labels, numbers and controls, plain readable system text for issue titles, chamfered tile corners, segmented block progress bars. Scanlines off by default here.

STORY: the user reads their queue (P1 QUEST LOG), sees counts as HUD readouts, spots overdue items flashing red, and jumps into an issue or project.

FIRST VIEWPORT: a HUD bar (PLAYER, OPEN, DUE 7D, OVERDUE, DONE, CLEAR %) across the top; below, 8/12 quest log of the user's open issues with status glyph, key, title, due; 4/12 a stage meter of all issues by status and the user's projects as stage progress bars; recent projects as level cards under it. Actions NEW ISSUE / NEW PROJECT top right.

FORM: Arcade Cabinet (challenger, chosen after re-roll 1), seed key 53d47090.

SIGNATURE INTERACTION: mode select behaves like a cabinet menu (arrow keys move a pixel cursor between DEFAULT, CUSTOM, JIRA); status changes and new done items flash their sprite color once.

FINISH: unreviewed and undocumented is unfinished; this build ends with the finish review, the verdict, DESIGN.md, and every shipping raster carrying its provenance
