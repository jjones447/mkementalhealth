# MKE Mental Health — community resource site

A free **Greater Milwaukee Area** mental-health resource — practical help for the time **between
deciding to get help and getting to a therapist** — **brought to you by Ellie Mental Health, Greater
Milwaukee Area**.

- **Domain:** `mkementalhealth.com` (registered; DNS → GitHub Pages).
- **Status:** **DRAFT** — every page is `noindex` with a draft banner; all content is **pending
  clinician review**. `robots.txt` also disallows crawling while in draft.
- **Live Pages source:** the **`coming-soon`** branch (a holding page) is currently served at the
  domain. **`main`** holds this full draft. Launch = flip the Pages source `coming-soon` → `main`
  once the checklist below is cleared.
- **Project tracker / full spec:** PIP repo → `04-ventures/mke-mental-health-site/README.md`.

## How to make changes (and deploy)
Plain static HTML/CSS — **no build step**. Edit the `.html`/`styles.css`, commit + push to `main`,
GitHub Pages auto-rebuilds in ~1–2 min. Today edits come from **Kelly's informal change requests**
(relayed → applied → pushed). Preview locally by opening `index.html`.

## Pages
| File | Page |
|---|---|
| `index.html` | Homepage (incl. therapist spotlight, psychoeducation corner) |
| `get-help.html` | Get Help Now — 988/911, Milwaukee County crisis services, free screening |
| `while-you-wait.html` | "While You Wait" — the signature bridge page (coping support) |
| `learn.html` | Topic overviews + therapy-modality basics (CBT/DBT/…) |
| `find-care.html` | What to expect from therapy + insurance basics + provider finders |
| `resources.html` | Milwaukee resource directory |
| `about.html` | Mission, clinician/Ellie framing, disclaimers, Workplaces, contact |
| `references.html` | Source list (supports clinical review) |
| `404.html` | Friendly not-found page |
| `styles.css` | Shared design system · `assets/` logos · `robots.txt` · `.nojekyll` |

## Brand
- **Colors** (`styles.css` `:root`): Ellie Navy `#245970` · Teal `#0fe0d9` · Mint `#a9fff8` ·
  Green `#ced92b` · Purple `#cc61c7` · Poppy `#ff6352`.
- **Logos** (`assets/`): `elephant-teal.png` (header mark + favicon), `elephant-navy.png`,
  `ellie-logo.png` (horizontal — used on About), `ellie-logo-stacked.png`.
- **Fonts — TODO:** target brand fonts are **Final Six Black** (headings), **Canban Bold Italic**
  (sub-headings), **Sophia Pro** (third). Pending the actual font files/licenses; **Poppins** is the
  interim stand-in (swap `--head` in `styles.css`).
- Framing: **"Brought to you by Ellie Mental Health, Greater Milwaukee Area"** + a discreet Ellie link;
  content is **created and owned by licensed clinicians**.

## Content & safety rules (this is YMYL health content)
- **Clinician-reviewed.** Don't lift the draft status until a licensed clinician has reviewed all content.
- **Crisis numbers: verified only.** 988 (call/text) and 911 always; local Milwaukee numbers are drawn
  from official sources but **must be re-confirmed before launch** (accuracy is safety-critical).
- **No PHI.** The site collects no personal health information; it is not patient intake.
- **Original content.** Summarized in plain language from cited authoritative sources (see
  `references.html`); don't copy MHA/NAMI/etc. — feature with permission only.
- **`noindex` + draft banner + `robots.txt` Disallow** stay on every page until launch.

## Launch checklist (before lifting draft status)
- [ ] Clinician review of all content; then remove draft banners + `noindex` + `robots.txt` Disallow.
- [ ] Re-confirm every crisis/local number &amp; address against official sources.
- [ ] Add the brand font files; swap `--head` off Poppins.
- [ ] Add the OLS online-scheduling URL/QR for "Book an appointment."
- [ ] Name the clinical lead (About); finalize the workplace one-pager (PDF).
- [ ] Add a real therapist spotlight, events, and printable tools (from Kelly).
- [ ] Add privacy-respecting analytics (Plausible/Fathom).
- [ ] Flip Pages source `coming-soon` → `main`; enable "Enforce HTTPS."
