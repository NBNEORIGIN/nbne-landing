# CAIRN_AUDIT.md — Phloe Marketing Site (nbne-landing)

**Audited**: 2026-03-30
**Repo**: NBNEORIGIN/nbne-landing (master branch)
**Hosted**: Vercel (vercel.json SPA rewrite)
**Domain**: Currently floe.nbne.uk — target: phloe.co.uk

---

## File Inventory

| File | Purpose | Lines |
|------|---------|-------|
| `index.html` | Main landing page — all HTML, CSS, JS inline | 1126 |
| `platform.html` | "Every Module Explained" detail page | ~1200 |
| `vercel.json` | SPA rewrite rule (`/(.*) → /index.html`) | 5 |

No external CSS or JS files. Everything is inline in `<style>` and `<script>` tags within each HTML file.

---

## Current Branding

- **Name used**: "Floe" (not Phloe) — appears ~15 times in index.html
- **Logo text**: "NBNE" (nav and footer)
- **Title tag**: `Floe — Complete Business Management for Small Service Businesses | NBNE`
- **Domain references**: `floe.nbne.uk` (not yet phloe.co.uk)
- **Google Analytics**: G-GY4TF6F33C

---

## Page Sections (index.html)

| # | Section | Class/ID | Content Summary |
|---|---------|----------|-----------------|
| 1 | Navigation | `.nav` | Fixed nav — NBNE logo, links: Demos, Platform, See All Modules, Contact, Beta, Pricing. Mobile hamburger. |
| 2 | Hero | `.hero` | Full-viewport Unsplash background with dark overlay. "Your entire business. One login. One price." Two CTAs: Explore Live Demos, Join the Free Beta. Trust bar: UK-built, no hidden fees, unlimited staff, cancel anytime, free for 3 months (beta). |
| 3 | Module Grid | `.module-grid-section` | Dark navy (#0f172a) section. 4-column grid of 8 module cards (Booking, Payments, Staff, CRM, Compliance, Comms, Documents, Shop). |
| 4 | Explainer | `.explainer` | "One platform. Zero duct tape." — comparison table (patchwork tools → Floe includes). White background. |
| 5 | Demo Sites | `#demos` | 3 demo cards: Salon X, FitHub, Tavola. Unsplash images, live demo links. Admin login + test card displayed. |
| 6 | Platform Features | `#platform` | 6 feature cards (same as module grid but different layout). White/grey background. |
| 7 | Beta Statement | `.beta-statement` | "Currently in beta — used by real businesses in the UK." 3-5 businesses, £30/month lifetime rate. |
| 8 | Beta Signup Form | `#beta` | Full form: business name, contact name, email, phone, business type dropdown (19 options), message. Posts to Railway backend. |
| 9 | Contact | `#contact` | 2-column: company details (address, phone, email, Google Maps link) + contact form. Posts to Railway backend. |
| 10 | CTA | `#pricing` | Dark gradient. "Ready to transform your business?" Demo login + test card repeated. |
| 11 | Footer | `.footer` | NBNE logo, demo links, copyright 2026. |

---

## Design Tokens (Current)

```css
--sans: 'Inter', -apple-system, sans-serif;
--dark: #0f0f0f;
--muted: #6b6b6b;
--accent: #2563eb;        /* Blue */
--accent-dark: #1d4ed8;   /* Darker blue */
```

- **Font**: Inter (Google Fonts), weights 300-800
- **Background**: Predominantly white (#fff) with light grey (#fafafa, #f8fafc) alternating sections
- **Dark section**: Module grid uses #0f172a (navy)
- **Hero**: Unsplash stock photo with dark gradient overlay
- **Colour scheme**: Light theme — white backgrounds, dark text, blue accent

---

## JavaScript (Inline)

1. **Scroll-based nav**: Adds `.scrolled` class on scroll > 60px (changes nav from transparent to white)
2. **Mobile menu**: Toggle hamburger/close icon, `closeMobile()` function
3. **Beta signup form**: `fetch()` POST to `https://nbneplatform-production.up.railway.app/api/beta-signup/`
4. **Contact form**: `fetch()` POST to `https://nbneplatform-production.up.railway.app/api/contact/`

---

## Issues to Address

### Branding
- [ ] "Floe" → "Phloe" everywhere (~15 instances)
- [ ] "NBNE" logo → "Phloe" (nav + footer)
- [ ] floe.nbne.uk → phloe.co.uk
- [ ] Title tag, meta description still reference "Floe"
- [ ] No OG/social meta tags exist

### Beta Content (to remove)
- [ ] Hero trust bar: "Free for 3 months (beta)"
- [ ] Hero CTA: "Join the Free Beta"
- [ ] Nav links: "Beta"
- [ ] Beta statement section (entire `.beta-statement`)
- [ ] Beta signup form (entire `#beta` section)
- [ ] Beta badge, beta-specific copy throughout

### Pricing
- [ ] "£30/month for life" → £200 setup + £40/month
- [ ] No pricing section exists — need dedicated pricing display
- [ ] "Free 3-month beta" references scattered throughout

### Design
- [ ] Light theme — needs dark theme rebuild (Linear/Stripe aesthetic)
- [ ] Unsplash stock hero photo — needs replacing or removing
- [ ] Blue accent (#2563eb) — review for new brand palette
- [ ] Module grid already dark (#0f172a) — could extend this as base
- [ ] No favicon referenced
- [ ] No smooth scroll-linked animations

### Content
- [ ] Demo login credentials displayed publicly (owner/admin123, test card)
- [ ] Railway backend URL hardcoded — may need updating
- [ ] platform.html exists but not integrated into redesign scope
- [ ] Demo sites (salon-x, fithub, tavola) — verify still live
- [ ] Contact details (NBNE Business, Alnwick) — confirm still correct

### Technical
- [ ] All CSS inline (~528 lines) — fine for single-page but large
- [ ] All JS inline — fine for this scope
- [ ] vercel.json SPA rewrite sends everything to index.html
- [ ] No service worker, no manifest.json
- [ ] Google Analytics tag present (G-GY4TF6F33C) — keep
