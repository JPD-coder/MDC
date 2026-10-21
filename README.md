# My Doctor's Choice — Marketing Website

A single-page marketing and lead-generation website for the **My Doctor's Choice** health & wellness clinic-partnership program.

---

## What this is

The entire website is **one self-contained file: `index.html`**. There is no separate codebase, build step, framework, or dependency to install.

- **HTML, CSS, and JavaScript** are all inline in `index.html`.
- The logo is **embedded directly** in the file (base64 data URI) — there are no external image files to keep track of.
- The only external resources are **Google Fonts** (loaded via `<link>`), which require an internet connection to render the intended typefaces; the page still works without them using fallback fonts.

Because it's self-contained, you can open it, email it, or host it anywhere as-is.

---

## How to view it

- **Locally:** double-click `index.html` to open it in any web browser.
- **To read/edit the code:** open `index.html` in a text editor or IDE (e.g., VS Code).

## How to host it

Drop `index.html` onto any static host. No server-side code is required.

- **GitHub Pages:** commit `index.html` to the repository root; the file must be named exactly `index.html` (lowercase) to serve as the homepage.
- **Netlify / Cloudflare Pages / Vercel:** drag-and-drop the file, or point the service at the repo.
- **Any web server:** place the file in the web root.

---

## Structure (sections, top to bottom)

1. Hero — headline, logo, primary call-to-action
2. What You Become
3. The Offering — service menu
4. Why My Doctor's Choice — comparison table
5. Your Team — support specialists
6. Leadership & Expertise — partner bios
7. The Challenge
8. The Process — 4-stage roadmap, plus:
   - **Interactive EBITDA estimator** (a draggable slider that maps EBITDA to an estimated multiple and implied value — pure client-side JavaScript)
   - Roll-up pooling diagram
9. Request an Invitation — lead form
10. Legal & Disclaimers — plus Privacy Policy, Terms of Use, and Accessibility modals

---

## Important notes for anyone taking this over

### 1. The lead form is front-end only
The "Request an Invitation" form currently shows a thank-you message but **does not send or store submissions anywhere.** To capture leads, wire the `<form id="leadForm">` handler to one of:
- a form service (Formspree, Netlify Forms, Basin, etc.), or
- a backend endpoint / CRM integration.
The `submitLead()` function near the bottom of the file is where to hook this up.

### 2. Legal/privacy text is template language — pending attorney review
The Privacy Policy, Terms of Use, and the medical and financial disclaimers contain **placeholder/template language that must be reviewed by qualified counsel** before the site is used publicly. The medical (FDA), corporate-practice-of-medicine, and any investment/securities language in particular should be confirmed by a healthcare-marketing attorney. The disclaimer modals are visibly flagged as drafts in the code.

### 3. Contact details
Some contact links in the footer (email/phone) are placeholders and should be updated to the correct destinations.

---

## Accessibility

The page targets **WCAG 2.1 Level AA** and includes: a skip-to-content link, a `<main>` landmark, ARIA labels on the interactive slider and mobile menu, keyboard focus styles, reduced-motion support, and color-contrast-checked text. A final manual screen-reader pass (VoiceOver / NVDA) and an automated scan (axe or WAVE) are recommended before launch.

---

## Tech summary (for developers)

| | |
|---|---|
| **Type** | Single-page static site |
| **Stack** | Vanilla HTML / CSS / JavaScript — no framework |
| **Build step** | None |
| **Dependencies** | None (Google Fonts via CDN, optional) |
| **Assets** | Logo embedded as base64 (no external files) |
| **Entry point** | `index.html` |

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The main marketing page (self-contained: inline CSS and JS) |
| `frontops.html` | One-page FrontOps ("Technology partner") section; self-contained, same design as `index.html`, legal links point back to `index.html#legal` |
| `frontops-logo.svg` | FrontOps logo, copied from frontops.io (used on `frontops.html`) |
| `mdc-logo.jpg` | My Doctor's Choice logo as a file (same image embedded in `index.html`; used on `frontops.html`) |
| `favicon-32.png` | 32×32 browser favicon |
| `apple-touch-icon.png` | 180×180 iOS home-screen icon |
| `og-image.png` | 1200×630 social share image (Open Graph / Twitter card) |
