# Akin Projects website: rules for agents

Public website for **Akin Projects**, the independent client-side project management arm of Guy Gleeson Building Pty Ltd, Wollongong / Illawarra NSW. Clients: strata, aged care, commercial / asset owners, community and non-profit.
Its sister business **Akin Building Co.** (residential building) has its own separate website and repository. Independence is Akin Projects' key selling point: never add content that links to, recommends or implies engaging Akin Building Co. on managed projects.

## How it is built and deployed
- Plain static HTML, CSS and JS in one page. No framework and no build step.
- Everything that is published lives in `site/`. Files at the repo root (this file, `netlify.toml`) are **not** published.
- `site/index.html` is a single page with sections `#about`, `#clients`, `#services`, `#process`, `#experience`, `#why` and `#contact`. The menu collapses to a hamburger below 860px.
- Design (chosen by the owner 2026-10-20, based on the Oct "v2/v3 visual concept" draft): full-width dark glass-tower hero, "Building expertise. Project confidence." headline, letter-spaced uppercase labels, light large headings, bronze `#b59a7a` buttons, cream `#f6f4ef` background, dark `#252927` contact section. Keep this look unless the owner asks to change it.
- Photos live in `site/images/`. Current ones are Unsplash stock images (free licence) and must stay labelled as illustrative. Never present them as Akin projects; replace with real project photos when the owner supplies them.
- Netlify deploys automatically from GitHub: a push to `main` updates the **live site**; other branches and pull requests get a **deploy preview** URL.
- The enquiry form uses Netlify Forms (`data-netlify="true"`, form name `projects-enquiry`). Don't rename it without telling the owner, as submissions are grouped by name.

## Rules for every change
1. **Never push untested changes straight to `main`.** Work on a branch, open a pull request, and check the Netlify deploy preview.
2. **Check every change at phone and desktop sizes:** at least 375px (phone), 768px (tablet) and 1280px (desktop). There must be no horizontal scrolling (`document.documentElement.scrollWidth` equals the viewport width), text must not overlap or be clipped, and the mobile menu must open, close and navigate.
3. The enquiry form must still validate and submit.
4. Contact details are set once in the `CONTACT` object near the bottom of `site/index.html`. Do not hard-code them elsewhere.
5. The footer must always show the ABN and the NSW contractor licence number.
6. Never publish placeholder text (`04XX XXX XXX`, `yourdomain`, `[ABN]`, `[LICENCE NO.]`) as if it were real. Ask the owner for the real values.
7. Don't add claims about past projects, clients or roles unless the owner has confirmed them. Projects from the director's previous roles (e.g. at Ventia, JLL) must be labelled as such.
8. Voice: warm but straight, plain language, confident not boastful. The logo (copper serif "akin" over a black circle, "PROJECTS" beneath) is `site/images/akin-projects-logo.png` (background removed, 520px wide), used small in the header (56px tall) and footer (84px). Original file is in `logo-source/` (not published). Don't enlarge it into the hero or distort it. In running text write "Akin Projects". Brand accent is bronze `#b59a7a`; headline "Building expertise. Project confidence." (secondary strapline "Plan. Manage. Deliver.")

## Domain
- Live domain: https://akinprojects.com.au/ (email: hello@akinprojects.com.au). Canonical URL, og:url, JSON-LD and sitemap.xml all use this domain; update them together if it ever changes.

## PRINCE2
- Guy holds PRINCE2 Foundation (owner confirmed 2026-10-20). Describe it as "PRINCE2® Foundation" / "Foundation certified"; never "Practitioner".
- The services section presents five delivery phases based on PRINCE2 processes (owner asked for the process names NOT to be shown on the cards): 01 Start up (Starting up a Project), 02 Initiate & plan (Initiating a Project), 03 Deliver & control (Controlling a Stage / Managing Product Delivery), 04 Commission & hand over (final delivery stage), 05 Close & review (Closing a Project). Directing a Project and Managing a Stage Boundary are shown as running throughout. Keep this mapping accurate if editing.
- Always write PRINCE2 with the ® on first use in a section, and keep the footer line "PRINCE2® is a registered trademark of the PeopleCert group." Don't add "used under licence" (that wording is for accredited training organisations).

## Netlify publish budget (important)
- The Netlify team is on the PERSONAL plan (US$9/month, upgraded 2026-10-21): 1,000 credits/month; every production deploy (every push to `main`) costs 15 credits — about 65 publishes per month SHARED across both akin sites. Check remaining credits on the team Billing page before publishing and warn the owner if under ~150.
- OWNER RULE (2026-10-21): NEVER push to `main` (= publish) unless the owner explicitly says "publish" in that session. Make all edits locally, commit locally, and show them in the local preview (see `.claude/launch.json` in the parent folder: akin-projects-site on :8766, akin-building-site on :8767). Batch everything into one publish per site.
- If deploys show "Skipped due to account credit usage exceeded", don't keep pushing; commit locally and tell the owner (options: wait for the cycle reset, or the owner upgrades the plan).
