# MKE Mental Health — community resource site

Static scaffold for **mkementalhealth.com** — a free Greater-Milwaukee mental-health resource (bridge-the-wait, shareable, low-stigma), affiliated with **Ellie Mental Health – Greater Milwaukee**.

> **Status: DRAFT / private.** Content is placeholder and **pending clinical review**. Every page is `noindex,nofollow` and carries a draft banner. **Do not publish publicly** until the launch gates below are cleared. Full project spec lives in the PIP repo: `04-ventures/mke-mental-health-site/README.md`.

## What's here
Plain static HTML/CSS (no build step), modeled on mhanational.org / nami.org / namiwisconsin.org:

| File | Page |
|---|---|
| `index.html` | Homepage |
| `get-help.html` | Get Help Now — crisis (988/911/local), NAMI HelpLine, free screening |
| `while-you-wait.html` | The signature "bridge the wait" page |
| `learn.html` | Education topic library |
| `find-care.html` | How to access therapy in MKE |
| `resources.html` | Milwaukee resource directory |
| `about.html` | Mission, affiliation, disclaimers, + Workplaces section |
| `styles.css` | Shared design system · `.nojekyll` lets Pages serve raw HTML |

## Preview
Open `index.html` locally, or (once approved) enable GitHub Pages on `main` / root.

## Launch gates (clear before public publish)
- [ ] **Clinician review** of all health content (YMYL).
- [ ] **Verify every crisis number/hour** — esp. the **Milwaukee County Crisis Line** (currently a `[confirm]` placeholder; 988/911 are correct).
- [ ] **Ellie franchise brand-guideline approval** for a separately-branded affiliated site.
- [ ] **Branding** decision (own identity vs. Ellie's vs. light new mark).
- [ ] **Register the domain** + DNS to Pages; remove `noindex` + draft banners only at launch.
- [ ] Decide production path: keep static vs. **Kelly-editable CMS** (the spec's recommendation for low-friction monthly updates).
- [ ] Add **privacy-respecting analytics** (Plausible/Fathom).
- [ ] Replace placeholders; curate any partner content **with permission** (no copying).
