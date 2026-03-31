# Boschetti Engineering – Website Project

## Overview
Personal/business website for **Giovane Boschetti**, railway engineer and entrepreneur based in Zürich, Switzerland.
- **Live domain**: https://boschetti-eng.ch
- **GitHub repo**: https://github.com/giboschetti/boschetti-eng.ch
- **Hosting**: GitHub Pages (static site, no backend)
- **Old WordPress**: https://boschetti-eng.ch/wp-admin (IONOS hosting, still running but domain now points to GitHub Pages)

## Owner
- **Name**: Giovane Boschetti
- **Role**: Projektleiter Gleisbau at Rhomberg Sersa Rail AG, Zürich
- **Business**: Boschetti Engineering (sole proprietorship) / Infranexus OU (Estonian company)
- **Email**: giovane@boschetti-eng.ch
- **Phone**: +41 76 480 80 47
- **LinkedIn**: https://www.linkedin.com/in/giovaneboschetti/
- **Languages**: German (C1), English (C1), Portuguese (native), Italian (basic)

## Tech Stack
- Pure static HTML/CSS/JS — no framework, no build step
- Fonts: Google Fonts — Barlow + Barlow Condensed
- Contact form: Web3Forms (https://web3forms.com), access key: `4aa45ea8-7a9c-4fac-8dd8-7057f3da4de3`
- Deployed via git push to `master` branch → GitHub Pages auto-publishes

## File Structure
```
site/
├── index.html               # Home page
├── ueber-mich/
│   └── index.html           # About / CV page
├── dienstleistungen/
│   └── index.html           # Services page
├── digitale-tools/
│   └── index.html           # Digital tools page
├── kontakt/
│   └── index.html           # Contact page (with working form)
├── assets/
│   ├── css/
│   │   └── style.css        # Single global stylesheet
│   └── img/
│       └── profil.jpg       # Profile photo (DSC_9032 original, cropped via CSS)
└── CNAME                    # boschetti-eng.ch
```

## How to Deploy Changes
```bash
cd "C:/Users/GiovaneBoschetti/IONOS HiDrive/Boschetti EC/site"
# Edit files, then:
git add -A
git commit -m "description of change"
git push
# GitHub Pages publishes automatically within ~60 seconds
```

## Design System

### Colors
| Name | Hex | Usage |
|------|-----|-------|
| Navy | `#0B1F3A` | Primary text, backgrounds, buttons |
| Gold | `#C8860A` | Accents, dividers, CTAs, borders |
| Off-white | `#F7F5F0` | Light backgrounds |
| Border | `#E2DDD5` | Dividers, card borders |
| Body text | `#5C6B7A` | Secondary text |
| Muted | `#8A96A4` | Labels, captions |

### Fonts
- **Barlow Condensed** — headings, labels, navigation (uppercase, tracked)
- **Barlow** — body text (300–600 weight)

### CSS Class Naming
All classes are prefixed `.be-` (Boschetti Engineering):

| Class | Purpose |
|-------|---------|
| `.be-wrap` | Max-width 960px centered container with 24px side padding |
| `.be-hero` | Page hero section (72px top padding, navy bottom border) |
| `.be-section` | Content section (64px padding, light bottom border) |
| `.be-h1/h2/h3` | Heading styles (Barlow Condensed, uppercase) |
| `.be-label` | Small all-caps label (11px, tracked, muted) |
| `.be-divider` | 60px gold horizontal rule |
| `.be-lead` | Large intro paragraph (17px, light weight) |
| `.be-body` | Standard body text (14px, muted) |
| `.be-cta` | Primary button (navy fill) |
| `.be-cta-ghost` | Ghost button (navy outline) |
| `.be-cta-amber` | Gold fill button |
| `.be-card` | Card with gold left border |
| `.be-card-dark` | Dark navy card |
| `.be-two-col` | 2-column grid (50/50) |
| `.be-grid-3` | Auto-fit 3-column grid |
| `.be-timeline` | Timeline with gold dots |
| `.be-skill` | Skill tag (gold left border) |
| `.be-tool` | Alternating 2-col tool showcase |
| `.be-service-grid` | Auto-fill service cards grid |
| `.be-banner` | Dark CTA banner (full width) |
| `.be-contact-block` | Dark contact info block |
| `.be-field` | Form field wrapper |
| `.be-submit` | Form submit button (gold) |

### Header
- Sticky, 68px height, white background
- Profile photo: 44×44px round, `object-fit:cover`, gold border, `object-position: center 20%`
- Site title: "Boschetti Engineering" — Barlow Condensed 18px uppercase
- Nav links: 12px uppercase tracked, muted color → navy on hover/active
- Active page: navy color + gold underline
- "Kontakt" link: navy pill `.nav-cta`
- On mobile (<680px): only "Kontakt" nav link shows

## Pages Summary

### Home (`/`)
Sections: Hero (name + tagline + CTAs) → Stats (6+ Jahre, 20+ Projekte, 3 Tools, 4 Sprachen) → 3 service cards → Experience (text + dark card) → Contact CTA banner

### Über mich (`/ueber-mich/`)
Sections: Hero (bio + LinkedIn CTA) → Career timeline (Rhomberg Sersa 2024–, SBB 2023–2024, Rhomberg Bahntechnik 2019–2023) → Education timeline (CAS Fribourg 2026–, BSc Brazil 2013–2018) → Skills grid + Languages + Reference block

### Dienstleistungen (`/dienstleistungen/`)
Sections: Hero → Arbeitsvorbereitung (12 service cards) → Abrechnung & Finanzen (5 service cards) → Dark CTA banner

### Digitale Tools (`/digitale-tools/`)
Sections: Hero → Tool 01: Raillog (raillog.app) → Tool 02: Digitale Tagesberichte (bautagesrapportesgs.onrender.com) → Tool 03: Schichtplanung (rsrg-schichtplanung.web.app) → "In Entwicklung" section (WhatsApp Media Capture, Lieferanten-Dashboard)

### Kontakt (`/kontakt/`)
Sections: Hero → 2-col (Form | Contact info block + availability)
Form fields: Name, E-Mail, Unternehmen (optional), Betreff (select), Nachricht
Form: AJAX POST to Web3Forms, inline success/error messages, no page reload

## Contact Form (Web3Forms)
- Service: https://web3forms.com
- Access key: `4aa45ea8-7a9c-4fac-8dd8-7057f3da4de3`
- Sends to: giovane@boschetti-eng.ch
- Implementation: JavaScript `fetch()` in `/kontakt/index.html` — `<script>` at bottom of page
- On success: form hides, `#form-success` div shows
- On error: `#form-error` div shows, button re-enables

## DNS Setup (IONOS)
For `boschetti-eng.ch` pointing to GitHub Pages:
```
A     @     185.199.108.153
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
CNAME www   giboschetti.github.io
```

## Old WordPress Site
- Still running at IONOS: https://boschetti-eng.ch/wp-admin
- MCP endpoint: https://boschetti-eng.ch/wp-json/mcp/v1/http
- Auth: Bearer S5eHNWalarodQbBlSYv1WmmFV9Pa16Tr
- Page IDs: Home=10, Über mich=8, Dienstleistungen=14, Digitale Tools=15, Kontakt=16
- Theme: GeneratePress, custom CSS post ID=29
- NOTE: WordPress `wp_kses_post` strips `<form>`, `<input>`, `<select>`, `<script>`, `<style>` from post content — reason we migrated to static site
- WordPress push scripts in: `C:/Users/GiovaneBoschetti/IONOS HiDrive/Boschetti EC/WordPress Website/wp-pages/`

## Assets
- Profile photo source: `C:/Users/GiovaneBoschetti/IONOS HiDrive/Boschetti EC/WordPress Website/DSC_9032_b_select-fotostudio.ch.jpg`
- CV PDF: `CV-Giovane_Apr26.pdf` (not yet linked on site)
- Project references PDF: `2. Project-References_GiBo_Jan26.pdf` (not yet linked on site)
