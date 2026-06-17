# MKE Mental Health — community resource site

A free Greater-Milwaukee mental-health resource — practical help for the time **between deciding to get help and getting to a therapist** — **brought to you by Ellie Mental Health**.

- **Live (draft preview):** https://jjones447.github.io/mkementalhealth/
- **Status:** PUBLISHED as a **`noindex` DRAFT** — content is placeholder, pending clinical review. A real launch (custom domain + lift `noindex`/banners) is gated on the checklist below.
- **Future domain:** `mkementalhealth.com` (not yet registered).
- **Project tracker / full spec:** PIP repo → `04-ventures/mke-mental-health-site/README.md`.

## How to make changes (and deploy)
Plain static HTML/CSS — **no build step**. To change the site:
1. Edit the relevant `.html` file (or `styles.css`).
2. Commit + push to **`main`**.
3. GitHub Pages **auto-rebuilds**; the change is live in ~1–2 min (hard-refresh to bypass cache).

Today, edits come from **Kelly's informal change requests** ("change this on that page, this color, add X") → relayed → applied + pushed. The eventual self-serve path is a direct chat-to-edit interface (the platform **chat-service** component). Preview locally by opening `index.html` in a browser.

## Pages
| File | Page |
|---|---|
| `index.html` | Homepage |
| `get-help.html` | Get Help Now — 988/911, NAMI HelpLine, free screening |
| `while-you-wait.html` | "While You Wait" — the signature bridge page |
| `learn.html` | Education topic library |
| `find-care.html` | How to access therapy in MKE |
| `resources.html` | Milwaukee resource directory |
| `about.html` | Mission, clinician/Ellie framing, disclaimers, + Workplaces |
| `styles.css` | Shared design system (`.nojekyll` lets Pages serve raw HTML) |

## Brand (keep edits on-brand)
Echoes Ellie Mental Health — its **own mark, no Ellie logo**:
- Deep teal-blue `#245970` (primary) · turquoise `#0fe0d9` · pale mint `#a9fff8` / `#e8fffd` · coral `#ff6352` (accent) · ink `#364952`
- Headings **Poppins** (700/800); body system sans. Friendly, rounded, generous whitespace.
- Framing: **"Brought to you by Ellie Mental Health"** + a discreet Ellie link in the footer; content is **created and owned by licensed clinicians**.
- 🐘 TODO: add the **Ellie elephant logo/mascot** when supplied.

## Content & safety rules (this is YMYL health content)
- **Clinician-reviewed.** Don't publish health guidance a licensed clinician hasn't reviewed; placeholders are clearly marked.
- **Crisis numbers: verified only.** Use **988** (call/text) and **911** — never a placeholder or made-up number. The local Milwaukee County crisis line goes in only once verified.
- **No PHI.** The site collects no personal health information (a newsletter signup at most); it is not patient intake.
- **Don't copy** MHA / NAMI / other content — write original, or feature with permission.
- **`noindex` + draft banner** stay on every page until launch.

## Launch checklist (before lifting draft status)
- [ ] Clinician review of all content.
- [ ] Verify + add the Milwaukee County crisis line (and confirm NAMI HelpLine hours).
- [ ] Add the Ellie elephant logo / finalize branding.
- [ ] Register `mkementalhealth.com`; add it as the Pages custom domain + DNS.
- [ ] Decide static vs. a Kelly-editable CMS (low-friction monthly updates).
- [ ] Add privacy-respecting analytics (Plausible / Fathom).
- [ ] Replace placeholders; remove `noindex` + draft banners.
