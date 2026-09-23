# Style lock: TaskSystem landing

## Direction contract
- Thesis: show the product's real mechanisms (board modes, activity log, real screenshots) instead of describing benefits.
- Mood: technical. Palette inherited from the app (src/index.css) plus the app's violet-600 accent. Not regenerated.
- First viewport: two-sentence statement headline, subhead + CTAs left, board screenshot bleeding off the right edge.
- Risk / rule-break: hero shot bleeds to the viewport edge; projects screenshot overlaps the dashboard with parallax.

## Color contract (tokens in src/features/landing/landing.css)
- Light: bg #f7f9fc, surface #fff, ink #111827, muted #5b6576 (5.58:1 on bg), line #d8dee8, accent-text #6d28d9, accent-fill #7c3aed, on-accent #fff (5.70:1)
- Dark: bg #0b1120, surface #111827, ink #f8fafc, muted #a3adbd (7.83:1 on surface), line #243044, accent-text #a78bfa (6.92:1 on bg), accent-fill #7c3aed, on-accent #fff (5.70:1)
- Text-safe: ink/bg, ink/surface, muted/bg, accent-text/bg, on-accent/accent-fill (both modes)
- Decorative only: line/bg, status dots (always paired with a text label)

## Type
- Archivo 600/700 (display), IBM Plex Sans (body), IBM Plex Mono (issue keys, timestamps only)

## Density & spacing
- Section padding: py-24 mobile, py-36 to py-40 desktop; one separation mechanism: hairline top border per section
- Radii: --lp-r-sm 6, --lp-r-md 8, --lp-r-lg 12, --lp-r-pill

## Structure
- Macrostructure: Product Demo / Workbench. Arc: hook (hero) > problem+solution (board modes) > how it works (TS-12 activity log) > proof (real screenshots + facts from code) > close.

## Assets
- Real app screenshots src/assets/tsimg1-3.png (dark mode). No photos or illustrations: the product UI is the visual. Icons: lucide-react only.
- Logo: existing app mark (CheckSquare tile from Sidebar) preserved.

## Do not
- No invented metrics, pricing claims ("free forever") or testimonials. No dead # links. No gradient text. No em dashes in copy.

## App UI (dashboard + shared primitives, 2026-09-16)
- Primary unified to violet #7c3aed (fill, white text 5.7:1); dark-mode text-primary #a78bfa.
- Buttons: solid fill or outline, press feedback `active:scale-[0.97]` 150ms ease-out. No hover scale/lift, no gradients, no expanding-circle buttons.
- Status badges: tinted 10% fill + tone text (getStatusBadgeClass). Labels: neutral outline chip with the label's color as a dot.
- Motion tokens in index.css @theme: --ease-out (0.23,1,0.32,1), --ease-in-out (0.77,0,0.175,1), --ease-drawer (0.32,0.72,0,1).
- Overlays via tw-animate-css: anchored surfaces scale from Radix transform-origin 150ms; modals fade+zoom 200ms; Jira drawer slides from the right 300ms.
- Dashboard motion: one-time data-ready stagger (8px, 300ms, 40ms), mode indicator transform 200ms, layout crossfade 200ms, FLIP on widget reorder 250ms. Charts do not animate.

## Interface style variants (2026-09-16)
- Toggle "Classic | Fluid" in the top bar (mobile: user menu), stored in localStorage `ui_style`, applied as `<html data-ui>` before first paint.
- Classic = everything above. Fluid = src/styles/fluid.css (all rules scoped to [data-ui="fluid"]) + DrawerDragHandle.
- Fluid springs: critically damped curve as CSS linear(); response 0.25 → 367ms, 0.40 → 587ms. JS spring (src/lib/spring.js) for gestures: dismiss ζ1.0/0.35, spring-back ζ0.8/0.3 (momentum earned by the drag).
- Fluid materials: thin (top bar, content scrolls under, scroll-edge fade), thick (sidebar), regular (popovers/menus/segmented controls). Modals dim + push app back (scale .985); Jira drawer is a parallel panel (light scrim, no push-back, drag to dismiss with momentum projection + rubber-band).
- Honors prefers-reduced-motion, prefers-reduced-transparency, prefers-contrast: more.
