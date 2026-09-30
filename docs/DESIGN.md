# MKE Mental Health, version 2: design and plan

Status: DRAFT for review by Jacob, Lisa, Dawn and Meghan. Written 2026-09-30 after a comparison
with the Legacy Caregiver Hub, which Jacob built and which this plan borrows from freely.

This document is the plan of record for the site. It says what the site is for, what it will
contain, how it looks, how it is built, who owns what, and what is still undecided. Update it when
a decision changes; do not let the site drift away from it silently.

## 1. Purpose and audiences

A free, public mental-health resource site for the Milwaukee area, meant to be shared in the
moment ("go here right now") and to bridge the wait for care. Ellie Mental Health Greater
Milwaukee stands behind it and is named on every page, but the site is a neutral guide, not a
funnel to one clinic.

Audiences, in order:
1. People waiting for care, including the Ellie waitlist.
2. Executives, workplaces and groups looking for a credible, low-stigma answer.
3. Parents, teens and the general Milwaukee public.

Two jobs, in this order: get people to help, and promote mental health.

## 2. Principles

- **Crisis first, always.** A crisis bar with tap-to-call 988 and 911 sits at the top of every
  page. Crisis details are verified or absent, never placeholders.
- **Ellie visible, not dominant.** Ellie is listed first in Find Care and is labeled as ours. Then
  come many other clinics and resources we would recommend. LifeStance is never listed.
- **Pages, not one long scroll.** Each key area gets its own landing page of tiles. Panels within
  a page are fine; a single endless page is not.
- **Real people, no stock strangers.** Illustration, icon chips and the brand's organic shapes
  carry the design. Photos are of real Ellie people and places, supplied by the team.
- **Senior-friendly floor (from Legacy):** 18px base text, 44px tap targets, visible focus rings,
  reduced-motion fallbacks, AA contrast. Checked at 375px and 1366px wide.
- **Unfinished looks deliberate.** Stubs use the "Content coming" badge and the inline dashed
  "to confirm" tag. Nothing on the site is invented to fill space.
- **Edits by chat, reviewed by people.** Content owners change the site through the assistant
  with a preview and a confirm step, as on Legacy.

## 3. Platform decision

**Version 2 is built on the Legacy platform.** The Legacy codebase (`jjones447/legacy-hub-pilot`)
is forked as the base and re-skinned to the Ellie brand. This brings, ready-made:

- Cloudflare Pages Functions and a D1 database.
- Templated pages (`build.py`) with a byte-identical verification in CI.
- Page copy, form wording and option lists editable by chat, with draft, preview and confirm.
- The events system: listings, registration, capacity, follow-up queue.
- The member portal with email one-time-code sign-in.
- The staff console, behind Cloudflare Access.
- Nightly backups to private storage, with a tested restore.
- The enforced content security policy and the accessibility floor.

What changes from Legacy: the brand (section 7), the page map (section 4), "caregiver" becomes
"member", and the grant workflow is dropped.

Hosting stays on Jacob's Cloudflare account, project `mkementalhealth`, with its own D1 database
and its own Access application. The Zero Trust team domain (`legacy-hub.cloudflareaccess.com`) is
account-wide and shared; the sign-in page will need a neutral name before this site launches (open
decision 11.4).

## 4. Site map

Landing pages are tile grids in the Legacy style. Panels are stacked sections inside one page.

| Page | Type | Contents |
|---|---|---|
| **Home** | panels | Short hero; four tiles: Get Help Now, While You Wait, Find Care, Learn; Ellie spotlight; weekly quote and question; events teaser; About teaser |
| **Get Help Now** | page | 988 and 911, other national lines, Milwaukee County crisis services, walk-in and Access clinics, free screening. Unchanged in substance from v1. |
| **While You Wait** | panels | Right now / Today / This week; safety-plan note; the free screening |
| **Find Care** | landing | Tiles: **Ellie Mental Health** (first, labeled as ours); Outpatient clinics; Intensive and inpatient care; Low-cost and sliding-scale; What to expect and insurance terms |
| Find Care: Outpatient clinics | page | Curated directory (section 5) |
| Find Care: Intensive and inpatient | page | Rogers Behavioral Health and similar; when to consider this level of care |
| Find Care: Low-cost and sliding-scale | page | Community clinics, county services, training clinics |
| Find Care: What to expect | page | The v1 "what to expect in therapy" and the 10 insurance terms |
| **Learn** | landing | Tiles: Topics; Therapy approaches; Common questions; later, an article hub with search |
| **Community** (replaces "Milwaukee Resources") | landing | Tiles: Support groups; Community organizations; Media and podcasts; Workplaces; Events |
| **Events** | page | Legacy events system: listing, registration, capacity |
| **About** | panels | Mission; the Ellie relationship stated plainly; the team; sources and references; contact |
| **Member area** | portal | Section 6 |
| **Donate** | page, hidden | Section 8; built but not linked until decided |
| 404 | page | Kept from v1 |

Primary navigation: Get Help Now (coral pill, always visible), While You Wait, Find Care, Learn,
Community, About, and Sign in. Mobile gets the Legacy hamburger and accordion.

## 5. Directory model (Find Care and Community)

- **Curators:** Dawn, Meghan and Lisa. A listing appears only after one of them confirms it in the
  staff console. Clinical accuracy on crisis and care-level pages gets a clinician's eyes before
  launch.
- **Inclusion rule (draft, to be confirmed by the curators):** Milwaukee-area; licensed or
  accredited; accepting new patients or clearly stating a wait; a working phone number and address;
  no LifeStance.
- **Order:** Ellie first in every care category where it applies, labeled "Ellie Mental Health
  (this site's sponsor)". Everything else alphabetical within the category.
- **Each listing:** name, what they do in one line, who they serve, insurance or cost note, phone,
  address, website, and a "last checked" date. Listings without a verified URL render as
  non-clickable cards, as on Legacy.
- **Categories:** outpatient clinics; intensive and inpatient; low-cost and sliding-scale; crisis
  and walk-in; support groups; community organizations; media and podcasts; workplaces.
- **Submissions (phase C):** partners can propose a listing through the member area; it sits in the
  review queue until a curator confirms it.

## 6. Member area

The Legacy portal (email one-time-code sign-in) with these capabilities, built in this order:

1. **Personal toolkit.** Save resources, a wellness check-in with a trend over time, private notes.
2. **Events and updates.** Register for events, see registrations, opt into a monthly update.
3. **Partner submissions.** Clinicians, organizations and workplace contacts propose resources or
   events for review.
4. **Volunteer coordination.** Volunteers see tasks, shifts and materials; staff assign them.

Data floor: the member record holds only what these features need. No clinical notes, no
diagnoses. The check-in is the member's own record and is never used for outreach without consent.

## 7. Visual system

- **Palette:** the Ellie brand palette already in `styles.css` (navy `#245970`, teal `#0fe0d9`,
  mint `#a9fff8`, coral `#ff6352`, plus the accents). Move the hard-coded colors (footer, placeholders,
  event card borders) into tokens.
- **Type:** Poppins for headings until the brand fonts (Final Six Black, Canban Bold Italic,
  Sophia Pro) are licensed. Body moves from 17px to 18px.
- **Tokens to add (from Legacy):** shadow and shadow-lg; button pressed and focus states; a
  section-head eyebrow and underline; the "Content coming" badge; the event date-block card; the
  quote card.
- **Components kept from v1:** the organic blob motif (brand manual p.46), inline SVG icon chips, the
  spotlight photo shape, the `.note` callout, the inline "to confirm" tag.
- **Components taken from Legacy:** tile grids with whole-tile click targets, the mobile menu,
  dropdowns with one level, the footer sitemap, the photo hero per area (only with real photos), the
  carousel and gallery if photos arrive.
- **Photos and video (the Legacy pattern):** one shared Google Drive folder per page area, under the
  Empyrean LLC Google account, shared with Dawn, Lisa and Meghan. Whatever they drop in becomes that
  area's hero image or video, through a manifest the site reads (Legacy's `area-media.json` and
  edge rewrite). The same photos go on the Empyrean Google Business profile so the two stay
  consistent. Pulling straight from the Business profile needs Google's Business Profile API, which
  requires an approved application; the Drive folder is the reliable path and needs no approval.
- **Marks:** the teal elephant as favicon and header mark. Share-image (1200x630) from the elephant
  on mint. Open decision 11.2 covers the Ellie logo.

## 8. Donations

Parked. The code path (donate page, GiveButter link, the "Support this work" band) is carried over
from Legacy and kept unlinked. `mkementalhealth.org` is registered (GoDaddy, through 2029, nothing
pointed at it) and is reserved for a nonprofit entity if one is formed; the donate page would live
there. Nothing about donations appears on the public site until that decision is made.

## 9. Content ownership and editing

| What | Owner | How it changes |
|---|---|---|
| Directory listings | Dawn, Meghan, Lisa | Staff console, or chat with preview and confirm |
| Page copy, forms | Lisa (with Dawn and Meghan) | Chat editing; break-glass direct edit with undo |
| Events | Whoever runs the event | Staff console or chat |
| Crisis numbers | Jacob, with clinician sign-off | Code change with review; never chat-edited |
| Code and infrastructure | Jacob and Lisa | Pull requests on `jjones447/mkementalhealth` |

Contact: the About page contact section and `hello@mkementalhealth.com` must point at a current
person (open decision 11.1).

## 10. Phases and launch gates

- **Phase A: platform port.** Fork Legacy, re-skin, build the page map with stubs, port the v1
  content, crisis bar on every page, staff login for the four of us. Gate: byte-identical build
  verification, accessibility floor checks at 375 and 1366, all v1 content present.
- **Phase B: directory and events.** Curators load and confirm the Find Care and Community
  listings; events live. Gate: every listing confirmed by a curator; crisis pages clinician-reviewed.
- **Phase C: member area.** Toolkit and events first, then submissions and volunteers.
- **Public launch.** Domain cutover to Cloudflare with `hello@` forwarding carried over and tested
  before and after; `noindex` lifted; draft banner removed. Gate: the launch checklist in README.md.
- **Phase D: donations.** Only after the entity decision.

## 11. Open decisions

1. **`hello@mkementalhealth.com` forwarding.** It currently forwards to Kelly's Ellie mailbox, and
   the About page contact section names it. Jacob has said to fix it; the new target is to be named
   (the forwarding lives in ImprovMX under Jacob's Gmail; it can forward to more than one address).
2. **The Ellie logo on the site.** The specification said "its own mark, no Ellie logo"; the built
   site uses Ellie logos on About. Pick one.
3. **Brand fonts.** Licenses for the three brand fonts, or stay on Poppins.
4. **Sign-in page name.** The account-wide Cloudflare Access team domain is `legacy-hub...`. Rename
   to something neutral (for example `empyrean-sites`) before this site's staff or members sign in.
5. **Who is on the staff login list.** Emails for Dawn and Meghan; Lisa's email of choice.
6. **Directory inclusion rule.** Curators confirm or amend the draft rule in section 5.
7. **Domain cutover timing** and whether `www` redirects to the apex.
