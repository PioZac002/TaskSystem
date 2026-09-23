---
version: 1
slug: "src-features-landing-landingpage-jsx"
primary_target: "src/features/landing/LandingPage.jsx"
related_targets: []
---

# Surface: Landing page (/)

Mode: Persuade.
Audience: small dev teams sizing up a self-hosted tracker, and evaluators opening the demo.
Action: try the product (sign up / borrow a demo account) while seeing it work on the page; self-hosting via the source repo is the second exit.
Proof on hand: the real workflow (8 statuses, 4 priorities, project keys, Basic/Detailed board, activity log), real screenshots, public demo, source repo. No customers, metrics, pricing. Docker + PostgreSQL demo seeding is planned, not shipped: never claim it.
Constraints: English copy, light and dark themes, name TaskSystem.

## Direction contract

THESIS: TaskSystem boots like an arcade cabinet: the issue lifecycle is a playable stage run, TS-12 fighting from NEW to DONE. Refuses the dark-SaaS gradient hero with a screenshot and three feature cards.

OWN-WORLD: phosphor-black screen (dark) and printed instruction-card white (light); a strict 16-color sprite palette where each status owns one color and one pixel glyph; power gold and flash white are reserved by law for completion. Pixel caps for every label, HUD and control; chamfered 8px-tile corners; scanlines and bloom as toggleable layers.

STORY: visitors see the workflow as stages, play one issue through them, understand Waiting and Review are first-class, then press START to sign in or PLAYER 2 to self-host from source.

FIRST VIEWPORT: HUD strip at top (1UP, PROJECT TS, STAGE); left 5/12 a huge pixel title "SHIP EVERY ISSUE" with one line of plain copy and START / PLAYER 2 buttons; right 7/12 a canvas stage map of the 8 status tiles with TS-12 as a sprite advancing on Space or tap.

FORM: Arcade Cabinet (challenger, chosen after re-roll 1), seed key 53d47090.

SIGNATURE INTERACTION: press Space/▶ to move TS-12 one stage; entering DONE triggers the gold power-up flash; CANCELED is a game-over tile. Motion is whole-pixel steps only.

FINISH: unreviewed and undocumented is unfinished; this build ends with the finish review, the verdict, DESIGN.md, and every shipping raster carrying its provenance
