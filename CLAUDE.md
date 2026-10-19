# Akin Projects website: rules for agents

Public website for **Akin Projects**, the independent client-side project management arm of Guy Gleeson Building Pty Ltd, Wollongong / Illawarra NSW. Clients: strata, aged care, commercial / asset owners, community and non-profit.
Its sister business **Akin Building Co.** (residential building) has its own separate website and repository. Independence is Akin Projects' key selling point: never add content that links to, recommends or implies engaging Akin Building Co. on managed projects.

## How it is built and deployed
- Plain static HTML, CSS and JS in one page. No framework and no build step.
- Everything that is published lives in `site/`. Files at the repo root (this file, `netlify.toml`) are **not** published.
- `site/index.html` is a single page with sections `#clients`, `#services`, `#process`, `#experience`, `#about` and `#contact`. The menu collapses to a hamburger below 860px.
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
8. Voice: warm but straight, plain language, confident not boastful. Always style the wordmark in lowercase: **akin**. Brand accent is bronze `#987c5b`; strapline "Plan. Manage. Deliver."
