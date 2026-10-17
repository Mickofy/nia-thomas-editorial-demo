# NIA THOMAS — Unofficial Editorial Redesign Concept

An independent, speculative storefront redesign created as a portfolio demonstration for a freelance project application. **Not affiliated with, endorsed by, or commissioned by NIA THOMAS.**

**Live concept:** https://nia-thomas-editorial-concept.pages.dev/

This static HTML/CSS/JavaScript prototype illustrates responsive homepage, collection, and product pages. Cart, pricing, filters, and newsletter interactions are demonstrations only; they are **not connected to Shopify**. Fashion imagery and the NIA THOMAS name are the respective owner's intellectual property. Images load from the publicly accessible storefront; media files are not redistributed in this repository.

## Project files

- `index.html` — standalone editorial mockup
- `_headers` and `robots.txt` — discourage indexing of the unofficial prototype
- `.github/workflows/deploy.yml` — publish updates to the **existing** Cloudflare Pages URL

Open `index.html` locally to preview; an internet connection is needed for externally hosted images and fonts.

## Cloudflare Pages deployment

The original Cloudflare Pages project `nia-thomas-editorial-concept` predates this dedicated GitHub repository. Cloudflare Pages does not support changing the Git repository linked to an existing Pages project. To **preserve the same already-shared pages.dev URL**, this repository uses the Wrangler GitHub Action to deploy directly to that existing project, rather than its built-in Git integration.

Automatic deployments from the old `mickofy-portfolio` repository have been disabled. The latest successful production deployment remains available while the new workflow is configured.

### One-time setup for the repository owner

1. In Cloudflare, create an API token with **Account → Cloudflare Pages → Edit** permissions, restricted to the account containing `nia-thomas-editorial-concept`.
2. In this repository, open **Settings → Secrets and variables → Actions → New repository secret**.
3. Name the secret `CLOUDFLARE_API_TOKEN` and paste the token value. **Never commit the token**.
4. Under **Actions → Deploy editorial concept**, choose **Run workflow** to trigger an initial deployment.
5. Confirm the deployment succeeded and the live URL still works. Further pushes to `main` will then deploy automatically.

The workflow publishes only `index.html`, `_headers`, and `robots.txt`. For compatibility with the existing Pages project's production branch, it explicitly sets `--branch=demo/nia-thomas-editorial` in the Wrangler command. This refers to a Cloudflare deployment designation, not the source branch in this repository.

**Do not delete/recreate the Cloudflare Pages project**: doing so could interrupt the URL already shared with a client.
