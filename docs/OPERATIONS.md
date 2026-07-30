# Site operations (for maintainers)

Plain static HTML/CSS, no build step. Two hosting surfaces — **do not confuse them**:

| Surface | Host | Serves from | Audience |
|---|---|---|---|
| **Live** — mkementalhealth.com | GitHub Pages | branch `coming-soon` | public (placeholder until launch) |
| **Draft/preview** — main.mkementalhealth.pages.dev | Cloudflare Pages (project `mkementalhealth`) | manual deploys of `main` | site owner review |

## Making a content change
1. Edit the `.html` / `styles.css` on `main`, commit + push.
2. Deploy the preview: `npx wrangler pages deploy . --project-name=mkementalhealth --branch=main`
   (auth via the fleet credential store — resolve at runtime, never commit or echo tokens).
3. Verify the change on `https://main.mkementalhealth.pages.dev/<page>` (curl or browser) **before** telling anyone it's ready.

**Pushing to `main` never changes the live site** — GitHub Pages serves `coming-soon`. Go-live is a
deliberate one-line switch of the Pages source branch (owner's call only).

## Content rules (standing)
- Owner-provided facts go in as given; anything unverified gets the `ph-inline` "confirm" placeholder pattern — never invent specifics.
- **Hard floor:** crisis-critical details (988, 911, county crisis lines) must be real and correct; never placeholder or fabricate those.
- Draft banner + "pending clinical review" footer stay until launch.
- Content requests arrive informally from the site owner; build and iterate — don't gate on perfection.
