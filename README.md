# Curigrove — first website

A lightweight, responsive, accessible studio website. No dependencies, build tools, paid hosting, trackers, or external fonts required.

## Contents
- `index.html` — homepage / current projects / studio philosophy / journal teaser
- `journal/index.html` — starter journal with an editable introductory note
- `assets/styles.css` — design and responsive layout
- `assets/logo.svg` and `assets/favicon.svg` — editable vector identity
- `assets/hero-grove.svg` — original vector illustration
- `assets/site.js` — current copyright year
- `.nojekyll` — asks GitHub Pages to serve files directly

## Preview locally
Open `index.html` in a browser. The site also works through any local static file server.

## Deploy to GitHub Pages (branch deployment)
1. Create **a separate public** repository on GitHub, for example `curigrove-site`. (With GitHub Free, Pages requires a public repository.) Never include credentials or personal data.
2. Unzip this starter and upload **the files inside the `curigrove-site` folder**, not the ZIP itself. Ensure `index.html` is in the repository root, and commit to `main`.
3. Repository **Settings → Pages**: choose `Deploy from a branch`, `main`, `/ (root)`, then Save.
4. Confirm the temporary `https://USERNAME.github.io/curigrove-site/` website works.
5. GitHub **profile Settings → Pages → Add a domain**: verify `curigrove.com` by adding the TXT record GitHub gives you in Porkbun DNS. Keep that TXT record afterward.
6. In the **repository** Settings → Pages → Custom domain, enter `www.curigrove.com` and Save. Github may create a `CNAME` file automatically. Do this before pointing DNS to GitHub.
7. In Porkbun Domain Management → DNS, follow their official **Quick DNS Config → Github** guide, specifying host `www` and `USERNAME.github.io` as the target. This sets up the GitHub Pages DNS records, including the appropriate apex IPs.
8. Verify that `www` is a CNAME directly to `USERNAME.github.io`, not `curigrove.com` and not a path ending with `/curigrove-site`. Apex `@` should point to the current GitHub Pages A records, or be configured by Porkbun’s Quick DNS workflow. Remove incompatible default parking A/CNAME records but do not remove the GitHub verification TXT record.
9. Back in the repository Settings → Pages, confirm DNS is valid and check **Enforce HTTPS** when available. DNS / certificates can take up to 24 hours.

**Important:** The domain stays registered at Porkbun; it is not transferred to GitHub. Never set a wildcard `*` DNS record. No separate Porkbun hosting plan is necessary.

### Official references
- GitHub Pages: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- GitHub domain verification: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
- Porkbun DNS walkthrough: https://kb.porkbun.com/article/64-how-to-connect-your-domain-to-github-pages

## How to update the site
- Change all wording in `index.html` and `journal/index.html` directly. The supplied first journal entry is *draft starter copy*; revise it to reflect your own voice before publishing.
- Project cards are informational for now, deliberately not links to unpublished / unknown apps. When apps launch, add `<a>` links around the relevant card content.
- To publish additional journal posts without a framework, create files such as `journal/my-new-post.html` and add links in `journal/index.html`. If the journal grows, consider moving to Astro or Eleventy later, but do not add complexity before it is useful.
- Do not include private family details, names, credentials, API keys, or user records in this public repository.
