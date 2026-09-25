# King Technology Solutions website

The King Technology Solutions LLC website.

| | |
| --- | --- |
| **Live site** | https://www.kingtechsolutionsgroup.com/ |
| **Cloudflare Pages URL** | https://kts-website-7xz.pages.dev |
| **Plain domain** | https://kingtechsolutionsgroup.com forwards (301) to the www address |

## How it works

- **Static site.** The whole site is one hand-written `index.html` (inline CSS and JavaScript), plus `robots.txt` and `sitemap.xml`. There is no framework and no dependencies.
- **No build step.** Files are served exactly as they are in the repository. The output directory is the repository root (`/`).
- **Contact form.** The form posts to Formspree (`https://formspree.io/f/xljdlwzr`). Don't change that endpoint without updating the Formspree account.
- **Canonical address.** The canonical link in `index.html`, `sitemap.xml` and `robots.txt` all use `https://www.kingtechsolutionsgroup.com/`. Keep them that way.

## Hosting

**Cloudflare Pages** (project `kts-website`) is connected to this repository.

| Setting | Value |
| --- | --- |
| Production branch | `main` |
| Framework preset | None |
| Build command | *(empty)* |
| Build output directory | `/` |
| Custom domain | `www.kingtechsolutionsgroup.com` |

Every merge to `main` deploys to production. Every pull request gets its own preview URL.

## DNS (GoDaddy)

DNS stays at GoDaddy. The website uses only two things there:

- a `www` CNAME record pointing to `kts-website-7xz.pages.dev`
- GoDaddy domain forwarding, which sends `kingtechsolutionsgroup.com` to `https://www.kingtechsolutionsgroup.com` with a 301 redirect

**Never change the Microsoft 365 email records** (MX, SPF, DKIM, DMARC, autodiscover). Website work never needs them.

## Updating the site

`main` is protected. Nothing is pushed to it directly; every change goes through a pull request that John reviews and merges.

1. **Branch.** Make the change on a new branch from `main`, usually by editing `index.html`.
2. **Pull request.** Open a pull request into `main`.
3. **Preview.** Cloudflare Pages builds the branch and posts a preview link on the pull request. Check the change there.
4. **Review and merge.** John reviews the pull request and merges it.
5. **Live.** Cloudflare deploys `main` to https://www.kingtechsolutionsgroup.com in about a minute.

To preview locally, open `index.html` in a browser, or run `python3 -m http.server` in the repository root and visit http://localhost:8000.
