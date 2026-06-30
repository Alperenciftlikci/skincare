# GlowIQ — Marketing Website

The marketing website for **GlowIQ**, an AI skincare companion for iOS. Take a selfie, get an instant skin analysis with scores, a personalized phased routine, and a product/ingredient scanner — and track your skin over time.

## Contents

| File | Purpose |
| --- | --- |
| `index.html` | Landing page (hero, how it works, features, social proof, pricing, FAQ, footer). Single file — inline CSS + JS, no external dependencies. |
| `privacy-policy.html` | Privacy Policy (Firebase + RevenueCat data handling, photo privacy, GDPR/CCPA, deletion, children's privacy). |
| `CNAME` | Custom domain for GitHub Pages: `glowiq.app`. |
| `README.md` | This file. |

## Design

Matches the GlowIQ app design system: cream background (`#FAF6F1`), terracotta accent (`#C26B4E`), sage support (`#7E9B86`), rounded geometric system-ui type, rounded cards, soft shadows, pill buttons. Mobile-first and responsive, with automatic dark mode (`prefers-color-scheme`) and subtle scroll-reveal animations that respect `prefers-reduced-motion`.

## Before going live — replace placeholders

- `apple-itunes-app` meta tag in `index.html`: set the real `app-id` (currently `000000000`).
- App Store links (`https://apps.apple.com/app/id000000000`): set the real App Store URL.
- Open Graph / Twitter image: add an `og-image.png` (1200×630) in this folder.

## Deploy to GitHub Pages

1. **Create a repo** and push the contents of this `website/` folder to the repository root (so `index.html` sits at the root of the deployed site).

   ```bash
   git init
   git add .
   git commit -m "Add GlowIQ marketing site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```

2. **Enable Pages**: in the repo, go to **Settings → Pages**. Under *Build and deployment*, set **Source = Deploy from a branch**, **Branch = `main`**, folder **`/ (root)`**, then save.

3. **Custom domain**: the included `CNAME` file sets the domain to `glowiq.app`. At your DNS provider, point the domain to GitHub Pages:
   - **Apex domain (`glowiq.app`)** — add `A` records to GitHub's IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (and/or the equivalent `AAAA` records for IPv6).
   - **`www` subdomain** — add a `CNAME` record pointing to `<your-username>.github.io`.

4. In **Settings → Pages**, confirm the custom domain shows `glowiq.app` and enable **Enforce HTTPS** once the certificate is issued.

Your site will be live at **https://glowiq.app** within a few minutes.

> Note: if you serve from a project subpath instead of a custom domain, adjust internal links accordingly. With the `CNAME` domain at the root, the relative links between `index.html` and `privacy-policy.html` work as-is.
