# CAIRN_QA.md — Phloe Marketing Site Final QA

**Date**: 2026-03-30
**Commit**: f7542c8 (feat(site): complete Phloe marketing site rebuild)

---

## Branding

| Check | Status |
|-------|--------|
| "Floe" replaced with "Phloe" everywhere | PASS |
| Nav logo says "Phloe" | PASS |
| Footer logo says "Phloe" | PASS |
| Footer copyright: "Phloe by NBNE" | PASS |
| Title tag references Phloe and phloe.co.uk | PASS |
| Meta description references Phloe | PASS |
| No remaining "Floe" or "floe" references | PASS |
| No remaining "NBNE" as primary brand (NBNE preserved in contact address and copyright only) | PASS |

## Beta Content Removal

| Check | Status |
|-------|--------|
| Beta signup form removed | PASS |
| Beta statement section removed | PASS |
| Beta badges removed | PASS |
| "Join the Free Beta" CTA removed | PASS |
| "Free for 3 months" trust bar item removed | PASS |
| "£30/month for life" references removed | PASS |
| Beta-specific nav links removed | PASS |
| Railway backend URL removed | PASS |

## Pricing

| Check | Status |
|-------|--------|
| £40/month displayed prominently | PASS |
| £200 setup fee displayed | PASS |
| Setup fee explanation included | PASS |
| Pricing includes list present (7 items) | PASS |
| No per-seat or tier language | PASS |
| CTA links to contact form | PASS |

## Design

| Check | Status |
|-------|--------|
| Dark background (#0a0a0b) | PASS |
| Light text on dark | PASS |
| Purple accent (#6c5ce7) | PASS |
| Green for checkmarks (#00b894) | PASS |
| Inter font loaded | PASS |
| Subtle gradient on hero (purple glow) | PASS |
| Module grid uses 1px gap borders | PASS |
| Cards have hover states | PASS |
| Consistent border-radius (10px) | PASS |
| Mobile responsive breakpoints (768px, 900px, 700px, 600px, 500px) | PASS |
| Fixed nav with scroll blur effect | PASS |
| No Unsplash hero background (removed) | PASS |

## Page Structure

| # | Section | Present | Notes |
|---|---------|---------|-------|
| 1 | Nav | PASS | Phloe logo, Platform/Demos/Pricing/How/Get Started |
| 2 | Hero | PASS | "Your entire business. One platform. One price." |
| 3 | Modules | PASS | 8-card grid, dark cards |
| 4 | Explainer | PASS | "One platform. Zero duct tape." + comparison table |
| 5 | Demos | PASS | 3 demo cards (Salon X, FitHub, Tavola) |
| 6 | Pricing | PASS | Single card, £40/mo + £200 setup |
| 7 | How It Works | PASS | 3-step numbered flow |
| 8 | Contact | PASS | 2-column: details + form |
| 9 | CTA | PASS | "Ready to simplify your business?" |
| 10 | Footer | PASS | Phloe logo, nav links, copyright |

## SEO / Meta

| Check | Status |
|-------|--------|
| `<title>` tag set | PASS |
| `<meta name="description">` set | PASS |
| `og:title` set | PASS |
| `og:description` set | PASS |
| `og:type` = website | PASS |
| `og:url` = https://phloe.co.uk | PASS |
| `og:image` referenced (placeholder path) | PASS — needs actual image created |
| `twitter:card` = summary_large_image | PASS |
| `<link rel="canonical">` set | PASS |
| Google Analytics preserved (G-GY4TF6F33C) | PASS |

## Technical

| Check | Status |
|-------|--------|
| Valid HTML5 structure | PASS |
| All CSS inline in `<style>` | PASS |
| All JS inline in `<script>` | PASS |
| Contact form POST to /api/contact/ (relative) | PASS |
| Mobile menu toggle works (JS) | PASS |
| Scroll-based nav blur (JS) | PASS |
| No external JS dependencies | PASS |
| No Vercel references | PASS |
| No Railway references | PASS |

## Outstanding Items

| Item | Action Required |
|------|----------------|
| OG image (`og-image.png`) | Create and upload a 1200x630 social sharing image |
| Contact form backend | Needs `/api/contact/` endpoint on Hetzner (or redirect to existing backend) |
| Favicon | Not yet added — create and reference |
| platform.html | Legacy page still exists — decide: update, redirect, or remove |
| Domain setup | Cloudflare + IONOS nameserver delegation (see go-live guide) |
| Demo site availability | Verify salon-x, fithub, tavola are still live |
| Demo credentials | Admin login (owner/admin123) displayed publicly — intentional for demos |
