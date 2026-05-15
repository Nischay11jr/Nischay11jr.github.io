# Nischay Arora — Portfolio Deployment Guide

This guide gets your portfolio live and ranking on Google. Total time: **~30 minutes**, total cost: **€0** (or €10–15/year if you want a custom domain like `nischayarora.com`).

---

## Files included

| File | Purpose |
|---|---|
| `index.html` | The entire portfolio — fully self-contained |
| `robots.txt` | Tells Google it can crawl everything |
| `sitemap.xml` | Helps Google index faster |
| `README.md` | This guide |

> **Important — update URLs before deploying.** Every reference to `https://nischayarora.com/` in `index.html` and `sitemap.xml` is a placeholder. Once you know your final URL, do a find-and-replace on it across all three files.

---

## Part 1 — Get it online (pick one)

### Option A: GitHub Pages (recommended — free, you already have GitHub)

1. Go to [github.com](https://github.com) → **New repository**
2. Name it exactly: `Nischay11jr.github.io` (using your GitHub username makes it auto-host at that URL)
3. Upload `index.html`, `robots.txt`, and `sitemap.xml` to the repo (drag-and-drop in the web UI works)
4. Go to **Settings → Pages**. Source: `Deploy from a branch`. Branch: `main`, folder: `/ (root)`. Save.
5. Wait 2–3 minutes. Your site is live at **`https://nischay11jr.github.io`**

### Option B: Netlify (free, no GitHub needed)

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag the folder containing all three files onto the page
3. Done. You'll get a URL like `your-site-name.netlify.app`. You can rename it in the dashboard.

### Option C: Vercel (free)

1. Go to [vercel.com](https://vercel.com), sign in
2. **Add New → Project → Import** from GitHub (or upload)
3. Deploy. URL is `your-project.vercel.app`.

### Option D: Custom domain (highly recommended for SEO)

Once your site is live on any of the above, point a custom domain at it. A domain like `nischayarora.com` will rank dramatically better than a subdomain.

1. Buy `nischayarora.com` (or your preferred name) at [Namecheap](https://namecheap.com), [Cloudflare](https://cloudflare.com), or [Porkbun](https://porkbun.com). ~€10–15/year.
2. In your domain registrar's DNS settings, add a CNAME or A record pointing to your host:
   - **GitHub Pages**: A records → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`. Plus a CNAME `www` → `nischay11jr.github.io`.
   - **Netlify / Vercel**: each has a custom-domain UI that walks you through it.
3. **CRITICAL — update the URL inside your files.** Open `index.html` and `sitemap.xml`, find-and-replace every `https://nischayarora.com/` with your real domain. Re-upload.

---

## Part 2 — Get it on Google (the part that actually matters)

Hosting it isn't enough. Google needs to know your site exists.

### Step 1: Submit to Google Search Console

1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Click **Add property** → **URL prefix** → enter your full URL (`https://yourdomain.com/`)
3. **Verify ownership.** Easiest method: choose **HTML tag**. Copy the meta tag they give you, paste it inside the `<head>` of `index.html` (anywhere before `</head>`), re-upload, then click Verify.
4. Once verified, go to **Sitemaps** in the left menu → enter `sitemap.xml` → Submit.
5. Go to **URL Inspection** → paste your full URL → click **Request Indexing**.

That last step is the magic one — it tells Google: "index this now, don't wait."

### Step 2: Bing too (cheap insurance)

Same idea: [bing.com/webmasters](https://www.bing.com/webmasters). You can import directly from Search Console with one click.

### Step 3: Help Google understand who you are

The site already includes structured data (JSON-LD `Person` schema) that tells Google:
- Your name
- Your location
- Your role
- Your social profiles (LinkedIn, GitHub)

To strengthen this further, make sure your **LinkedIn profile** and **GitHub profile** both link to your portfolio URL. Google uses these cross-references heavily.

### Step 4: Build link signals

For unique names like yours, indexing alone usually gets you to #1 within 2–14 days. To accelerate:
- Add the portfolio URL to your **LinkedIn** (Contact info → Website)
- Add it to your **GitHub** profile (Edit profile → Website)
- Add it to your **email signature**
- Mention it on **any other profiles** you have (Twitter/X, Instagram bio, etc.)

Each link to your site from a high-trust domain (LinkedIn, GitHub) is a signal that helps you rank.

---

## Part 3 — Expected timeline

| Time | What happens |
|---|---|
| **Day 0** | Site goes live |
| **Day 1–2** | Google indexes it (after you request indexing in Search Console) |
| **Day 3–14** | You appear in search results for your name |
| **Week 2–4** | Ranking stabilises. For a unique name like "Nischay Arora", expect to hold **#1 or top 3** consistently. |

If after 14 days you're not ranking on the first page for your full name, search Google for `site:yourdomain.com` — if results appear, you're indexed; if not, re-check Search Console for crawl errors.

---

## Part 4 — Updating the site later

The whole site is **one file** (`index.html`). To update anything — add a project, change a job, swap a photo — just edit that file and re-upload it the same way you deployed it.

To add your **photo**: 
1. Save it as `me.jpg` (or `.png`) — square crop, 800×800px ideally
2. Upload alongside `index.html`
3. In `index.html`, find this line:
   ```html
   <meta property="og:image" content="https://nischayarora.com/og-image.jpg" />
   ```
   and change `og-image.jpg` to your filename. The Open Graph image is what shows up when someone shares your link on LinkedIn/Twitter/WhatsApp.
4. If you want the photo visible *on the page itself*, send me where you'd like it placed and I'll patch the layout.

---

## Part 5 — Things you should know

**The placeholder URL.** Right now `index.html` and `sitemap.xml` reference `https://nischayarora.com/`. If you use a different domain (e.g. `nischay11jr.github.io`), do a find-and-replace before deploying. It's about 8 references total.

**The `og-image.jpg` reference.** Until you upload a real OG image, link previews will be blank. Not urgent but nice to have. A 1200×630px image with your name + tagline works perfectly.

**Phone number on a public page.** Your phone number is currently listed in the contact section and in the structured data. Public phone numbers attract spam calls eventually. If you'd rather not have it public, just delete the `tel:` link and the `telephone` line from the JSON-LD block.

**Mobile.** The site is fully responsive. Test it on your phone before sharing.

**The custom cursor** is desktop-only and auto-disables on touch devices. The animations also auto-disable for users who have "reduced motion" set in their OS — that's an accessibility feature.

---

## Need to update something?

Send me what you want changed — new project, new role, photo position, tweak the copy, different colour scheme, new section. The whole thing is one file and easy to iterate on.
