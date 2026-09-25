# King Technology Solutions website

Source for **https://www.kingtechsolutionsgroup.com/**, the King Technology Solutions LLC site.

## How it works

- **Static site.** The whole site is one hand-written `index.html` (inline CSS and JavaScript), plus `robots.txt` and `sitemap.xml`. There is no framework and no dependencies.
- **No build step.** Files are served exactly as they are in the repository. The output directory is the repository root (`/`).
- **Hosted on Cloudflare Pages.** Cloudflare Pages is connected to this repository and deploys `main` to production automatically. Every pull request gets its own preview URL, so changes can be checked before they go live.
- **Contact form.** The form posts to Formspree (`https://formspree.io/f/xljdlwzr`). Don't change that endpoint without updating the Formspree account.

## Making changes

All changes go through pull requests. `main` is protected: nothing is pushed to it directly, and every pull request needs **John's approval** before it can be merged.

1. Create a branch from `main`.
2. Edit the files (usually `index.html`) and open a pull request.
3. Check the Cloudflare Pages preview link posted on the pull request.
4. John reviews and approves; then merge. Cloudflare deploys `main` within a minute or two.

To preview locally, open `index.html` in a browser, or run `python3 -m http.server` in the repository root and visit http://localhost:8000.

## Cloudflare Pages settings

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Framework preset | None |
| Build command | *(empty)* |
| Build output directory | `/` |
| Custom domain | `www.kingtechsolutionsgroup.com` |

## DNS

The domain's DNS is hosted at GoDaddy. The website needs only a `www` CNAME pointing to the Cloudflare Pages project. The existing Microsoft 365 email records (MX, SPF, DKIM, DMARC, autodiscover) must not be changed.
