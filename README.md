# ring-ring-website

The public landing page for the **Ring Ring** project: one self-contained `index.html` plus `assets/`, no build step, no external dependencies. It is served by GitHub Pages at https://glogiotatidis.github.io/ring-ring-website/.

It deploys through `.github/workflows/pages.yml` — every push to `main` stages the site, uploads it with `actions/upload-pages-artifact` and publishes it with `actions/deploy-pages`.

The hero copy is in **Greek**: the product is for Greek-speaking parents and kids, matching the project's parent-facing convention.

## Waitlist

Ring Ring isn't for sale yet, so the hero CTA collects waitlist interest. The page is a static GitHub Pages site (no backend), so the destination is a third-party, no-infrastructure form service. **Chosen mechanism: a Google Form** — responses land in a Google Sheet that is already readable/exportable through the repo owner's existing Google OAuth (Drive + Sheets scopes), so no new account and no password to hand over.

Current state: the CTA ships in a non-clickable **"σύντομα"** (opening soon) state because the form destination is not wired yet. To make it live, pick one:

- **Google Form (recommended).** Create a one-question form (short-answer "email"), then replace the `<p class="cta-row">…</p>` block in `index.html` with a live button pointing at the form's public URL — the exact snippet is in an HTML comment right above that block. A Google Form / `forms.gle` URL is **not** a secret; committing it is fine.
  - Automation note: the owner's Google token already carries the `drive` scope, which authorises the Google Forms API to create and read forms — the only thing missing is enabling the **Forms API** once in the Cloud project (one click in the Google Cloud console). Once enabled, the form can be created, wired, and tested end-to-end with no manual form-building.
- **Formspree / Getform (alternative).** Add an on-page `<form action="https://formspree.io/f/<id>" method="POST">` with an `email` field. Needs a free account created once. A Formspree form id is not a secret.

**Never** put an API key or service-account credential in this page's client-side HTML/JS — if a mechanism would require one, pick the other.
