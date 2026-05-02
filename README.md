# retainr · website

Single-page site for retainr.co. Static HTML, CSS, JS. No build step.

## What's in the box

```
website/
├── index.html      # The whole site, self-contained
├── vercel.json     # Headers + clean URL config
└── README.md       # This file
```

That's it. No `node_modules`, no bundler, no framework. Open `index.html` in any browser to preview locally.

## Deploy to Vercel

### Option 1 · Drag & drop (fastest)

1. Go to [vercel.com/new](https://vercel.com/new)
2. Drag the `website` folder into the upload area
3. Click **Deploy**

Live in about 30 seconds.

### Option 2 · Vercel CLI

```bash
npm i -g vercel       # one time
cd website
vercel                # follow prompts; press Enter to accept defaults
vercel --prod         # publish to production
```

### Option 3 · Git-connected (recommended for ongoing edits)

1. Push the `website/` folder to a GitHub/GitLab/Bitbucket repo
2. On Vercel, click **Add New Project** → import the repo
3. Framework preset: **Other** (or leave as auto-detected)
4. Root directory: `website` (or wherever you placed it)
5. Click **Deploy**

Every push to `main` auto-deploys. Pull requests get preview URLs.

## Custom domain

Once deployed:

1. Vercel dashboard → your project → **Settings** → **Domains**
2. Add `retainr.co` (and `www.retainr.co`)
3. Point your DNS at Vercel:
   - `A` record → `76.76.21.21`
   - `CNAME` for `www` → `cname.vercel-dns.com`
4. SSL provisions automatically

## Editing content

All copy lives inline in `index.html`. Search for the section you want and edit. No CMS, no templates.

Common edits:

- **Hero copy** → search `<section class="hero">`
- **Stats numbers** → search `data-target` (the counter animation reads from these attributes)
- **Service descriptions** → search `class="services-list"`
- **Case studies** → search `class="cases-grid"` (each `<article class="case-card">` is one)
- **Testimonials** → search `id="testimonialsTrack"`
- **FAQ** → search `class="faq-list"`
- **Email contact** → search `mailto:hello@retainr.co` and `mailto:careers@retainr.co`

## Stack

- HTML5 + vanilla CSS (CSS custom properties for theming)
- Vanilla JS, no dependencies
- Google Fonts: Bricolage Grotesque, Fraunces, IBM Plex Mono
- Brand tokens pulled from retainr Brand Guidelines v1.0
- Mobile-first responsive (480 / 768 / 1024 / 1280 breakpoints)
- Honors `prefers-reduced-motion`
- WCAG 2.2 AA contrast throughout

## Performance notes

The site is intentionally dependency-free. Initial payload is one HTML file plus Google Fonts CSS. No JS bundle, no framework runtime.

Expected Lighthouse scores on mobile:

- Performance: 95+
- Accessibility: 100
- Best Practices: 100
- SEO: 100

## Brand reference

- Colors: Onyx `#0A0A0A`, Antique Gold `#D4B36A`, Bone `#F4F4ED`
- Type: Bricolage Grotesque (display + body), Fraunces Italic (accent), IBM Plex Mono (data)
- Mark: The Meander, sharp-cornered Greek key, rendered as inline SVG
- All tokens defined in CSS `:root`. Edit them once, they propagate everywhere.

---

**v1.0 · 2026**
