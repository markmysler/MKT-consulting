# MKT Consulting site

A single static page with no build step. Vercel serves the files exactly as they are.

## Before deploying

Open `index.html` and look for the `BOOKING SETUP` block near the start of the main `<script>`:

```js
const BOOKING_URL = "";   // your Calendly / Cal.com link, e.g. "https://calendly.com/mkt-consulting/30min"
const CONTACT_EMAIL = ""; // used only if BOOKING_URL is empty
```

If you set `BOOKING_URL`, "Choose a time" opens your scheduling page in a new tab. The chosen plan is added to the link as `utm_content` (for example `Standard + custom content`). Calendly and Cal.com save that value on each booking. If you leave `BOOKING_URL` empty, the button opens an email to `CONTACT_EMAIL` instead.

## Deploy on Vercel

**Option A: Vercel CLI (no Git)**
1. Install the CLI with `npm i -g vercel`, then run `vercel login`.
2. From this folder, run `vercel --prod`. Accept the defaults (no framework, no build command, output directory `.`).

**Option B: GitHub (redeploys on every push)**
1. Push this folder to a GitHub repository.
2. On vercel.com, choose Add New, then Project, and import the repository.
3. Set Framework Preset to "Other" and leave the build command empty. Then deploy.

**Custom domain:** in the Vercel project, open Settings, then Domains, and add your domain. Then add the DNS records Vercel shows you at your domain registrar.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The page (styles and scripts inline; fonts from Google Fonts, three.js from cdnjs) |
| `favicon.svg` | Browser tab icon |
| `vercel.json` | Clean URLs and security headers |
| `robots.txt` | Allows search engines to index the page |
