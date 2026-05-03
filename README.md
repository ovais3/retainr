# retainr · website

Single-page site for retainr.co. Static HTML + CSS + JS. Plus optimized image assets in /img.

## What's in the box

```
website/
├── index.html      # The whole site, self-contained
├── vercel.json     # Headers + clean URL config
├── img/            # 12 email mockup images (~880KB total)
└── README.md       # This file
```

No node_modules, no bundler, no framework. Open index.html in any browser to preview locally.

## Deploy to Vercel

### Path 1 :: Drag & drop (fastest)

1. Go to vercel.com/new
2. Click "Create empty project" or "Import Git Repository"
3. Drag the entire `website` folder onto the page
4. Click Deploy

Live in 30 seconds.

### Path 2 :: Git-connected (recommended for ongoing edits)

1. Push the `website/` folder to a GitHub repo
2. On Vercel, click Add New Project, import the repo
3. Framework preset: Other
4. Click Deploy

Every push to `main` auto-deploys.

## Custom domain

Vercel dashboard → Settings → Domains → add `retainr.co` and `www.retainr.co`.
DNS records:
- A record for `@` → 76.76.21.21
- CNAME for `www` → cname.vercel-dns.com

SSL provisions automatically.

## Editing content

All copy lives inline in `index.html`. Search for the section, edit, save.

- Hero copy: search `<section class="hero">`
- Stats numbers: search `data-target` (counter reads from these)
- Service descriptions: search `class="services-list"`
- Case studies: search `class="cases-grid"`
- Testimonials: search `id="testimonialsTrack"`
- FAQ: search `class="faq-list"`
- Email contacts: search `mailto:hello@retainr.co` and `mailto:careers@retainr.co`

## Replacing email mockup images

The work showcase pulls from `img/email-*.jpg`. To swap any:
1. Drop a new image (480x1080px ideal, JPEG quality 80) into `img/`
2. Update the `emailImages` array in the `<script>` block at the bottom of index.html

## Stack

- HTML5 + vanilla CSS (CSS custom properties for theming)
- Vanilla JS, no dependencies
- Google Fonts: Bricolage Grotesque + Fraunces
- Mobile-first responsive (480 / 768 / 1024 / 1280 breakpoints)
- Honors `prefers-reduced-motion`
- WCAG 2.2 AA contrast

## Performance notes

Initial payload: one HTML file + Google Fonts CSS + 12 lazy-loaded JPEGs.
Expected Lighthouse mobile scores:
- Performance: 90+
- Accessibility: 100
- Best Practices: 100
- SEO: 100

## Brand reference

- Colors: Onyx `#0A0A0A`, Antique Gold `#D4B36A`, Bone `#F4F4ED`
- Type: Bricolage Grotesque (display + body), Fraunces Italic (accent)
- Mark: The Meander, sharp-cornered Greek key, inline SVG
- All tokens defined in CSS `:root`. Edit once, propagates everywhere.

***

v3.0 · 2026
