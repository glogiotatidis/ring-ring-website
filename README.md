# ring-ring

The public landing page for the **ring ring** project: one self-contained `index.html` plus `assets/`, no build step, no external dependencies. It is served by GitHub Pages at https://glogiotatidis.github.io/ring-ring/.

It deploys through `.github/workflows/pages.yml` — every push to `main` stages the site, uploads it with `actions/upload-pages-artifact` and publishes it with `actions/deploy-pages`.

## Open items

- [ ] **Real copy.** The tagline, the one-paragraph description and the contact link (`href="#"`) on the call-to-action are placeholders, each marked with `<!-- TODO(Giorgos): real copy -->` in `index.html`. Nothing about the product is claimed anywhere on the page.
