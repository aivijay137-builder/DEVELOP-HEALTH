1. WHAT WE ARE BUILDING
   A single-file HTML prototype of the PA Confidence Score Triage Queue
   for Develop Health. This is a leadership demo, not a production app.
   It must open in a browser with no server. All data hardcoded from pa_data.json.

2. THE USER
   A PA coordinator reviewing 30 prior authorization submissions per day.
   She needs to know at a glance which PAs she can approve in 30 seconds
   and which need her full attention.

3. WHAT SUCCESS LOOKS LIKE
   - Green-tier PAs: reviewed and bulk-approved in under 30 seconds total
   - Red-tier PAs: coordinator knows exactly what is wrong and what to fix
   - Leadership demo: 15 minutes, no confusion, one aha-moment per Red case

4. FILES WE WILL CREATE
   pa-triage-ui/
   ├── index.html       (single deliverable — CSS and JS inline)
   └── pa_data.json     (Week 1 sheet data — already prepared)

5. NON-NEGOTIABLES
   - No frameworks (no React, no Vue). Vanilla HTML/CSS/JS only.
   - No external CDN dependencies — must work offline for the demo
   - Every piece of text content comes from pa_data.json — no hardcoding in HTML
   - Three tiers: Green ≥75, Yellow 40–74, Red <40
   - Colour system: Green #15803D / #DCFCE7, Amber #B45309 / #FEF3C7, Red #991B1B / #FEE2E2