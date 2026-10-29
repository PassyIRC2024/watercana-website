# Watercana website starter

A responsive six-page Astro website with a Pages CMS-managed conservation journal, prepared for **static Cloudflare Pages** deployment. No database, server adapter or paid plan required for the starter.

## Included pages
- `/` — Home
- `/our-water/` — Our Water
- `/our-story/` — Our Story
- `/conservation/` — Conservation
- `/journal/` — Journal, including article pages
- `/contact/` — Contact

## Run locally
Install Node.js 22, then in the project folder:

```bash
npm install
npm run dev
```
Open the local URL shown in the terminal (typically http://localhost:4321).

To check a production build:

```bash
npm run build
npm run preview
```

## Deploy to Cloudflare Pages (free-first)
1. Create a free GitHub account and repository called `watercana-website`.
2. Upload the **contents** of this folder to the repository root (including the hidden `.pages.yml` file). Git command alternative:
   ```bash
   git init
   git add .
   git commit -m "Initial Watercana website"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/watercana-website.git
   git push -u origin main
   ```
3. Create a free Cloudflare account at https://dash.cloudflare.com/.
4. Open **Workers & Pages → Create application → Pages → Import existing Git repository**. Connect the GitHub repository.
5. Select framework **Astro**, production branch `main`, build command **`npm run build`**, output directory **`dist`**. Use Node.js 22 if asked (the project includes `.nvmrc`).
6. Deploy. Cloudflare will give you an address similar to `https://watercana-website.pages.dev`. Actual address depends on availability and your chosen project name.
7. Optional: once your actual URL is known, update `astro.config.mjs` `site` value or set the build environment variable `SITE_URL` to your full deployed URL, then redeploy. This makes sitemap/canonical site configuration accurate.

## Enable the blog editor (Pages CMS)
1. Visit https://app.pagescms.org and sign in with GitHub.
2. Authorize/install Pages CMS GitHub App for the repository.
3. Select the Watercana repository and its `main` branch.
4. The `.pages.yml` configuration in the repository provides **Conservation journal** and **Website contact details** editors.
5. Choose **Conservation journal → New**, fill title, description, publication date, category, image and article content.
6. Set **Draft** to **false** when ready to publish, then save. Pages CMS commits changes to GitHub; Cloudflare builds and publishes them automatically. Publishing may take a minute or two.
7. To hide an article, edit it and set Draft to true. To edit contact details, open **Website contact details** and add your real email and WhatsApp number in international digits (e.g. Kenya number starts `254`, no plus sign).

**Media:** Images uploaded via Pages CMS go into `public/images` and become public at `/images/...`. Don't upload private or sensitive information. Optimize photos for the web before uploading.

## Before launch
- Replace the illustrative SVG and emoji with authentic Watercana photography (only photos you have rights to use).
- Review the two starter blog posts; they are editorial examples, not evidence of completed work.
- Confirm conservation pledge wording and all product/quality claims. Do not claim certifications or test results without documentation.
- Add verified public email and WhatsApp in the CMS.
- Review privacy obligations before adding forms, analytics or collecting personal data.
- Test navigation, mobile view, links, images, blog creation and unpublished draft behavior.
- The text-only brand is temporary until the official logo is supplied.

## Site structure
`src/pages` — six main pages and article route; `src/layouts` — shared header/footer; `src/styles` — visual design; `src/content/blog` — editable Markdown articles; `src/data/site.json` — editable contact details; `.pages.yml` — CMS configuration.

## Cost
Cloudflare Pages, GitHub and Pages CMS can be used with their free tiers for this starter, subject to provider limits and policies. A custom domain is optional and would cost extra. No payment processing or server-side form backend is included.
