# Design Document for Myanmar Open Golf Official Website

---

## 1. Overview
The Myanmar Open Golf website is a **single‑page, responsive web app** built with **pure HTML5, Tailwind CSS (via CDN), and vanilla JavaScript**. The design focuses on a **luxury dark‑emerald and gold theme** that conveys prestige while remaining performant on low‑bandwidth connections.

---

## 2. Visual Theme & Brand Identity
| Element | Specification |
|---------|----------------|
| **Primary Color** | Dark Emerald `#064e3b` |
| **Accent Color** | Gold `#d97706` |
| **Background** | Slate‑light `#f8fafc` (used for content areas) |
| **Typography** | System UI font stack (Tailwind defaults). Headings receive a **bold weight** to reinforce hierarchy. |
| **Iconography** | FontAwesome (v6) via CDN for social icons, navigation toggles, and UI cues. |

The color palette is applied consistently across the header, hero overlay, buttons, and highlights in tables.

---

## 3. Layout & Structure
The page is divided into the following vertical sections, each implemented as a Tailwind **container** with responsive padding:

1. **Header & Navigation** – Fixed top bar with logo, navigation links, and a mobile hamburger menu.
2. **Hero Banner** – Full‑screen background image with a dark overlay, title, subtitle, and two CTA buttons.
3. **Leaderboard** – Searchable table of players and scores.
4. **Past Champions** – Card grid showcasing champion photos, names, scores, and flags.
5. **Venue Spotlight & Gallery** – Two‑column venue cards followed by a responsive image grid with a lightbox modal.
6. **Registration / Contact Form** – Simple form with client‑side validation and a JavaScript alert on submit.
7. **Footer** – Minimal footer with copyright, social icons, and venue tags.

All sections stack vertically on mobile (`flex-col`) and switch to a multi‑column layout on `md:` breakpoints using Tailwind's responsive utilities.

---

## 4. Component Details
### 4.1 Header & Navigation
- **Logo** – Golf club icon + site name, colored with the accent gold.
- **Nav Links** – `Home`, `Leaderboard`, `Champions`, `Venue`, `Contact`. Hidden on mobile; revealed via a JavaScript‑controlled collapse.
- **Mobile Toggle** – SVG hamburger that toggles a hidden `<nav>` with a smooth `transition`.

### 4.2 Hero Banner
- **Background Image** – Unsplash placeholder (link in the spec). Applied with `bg-cover bg-center`.
- **Overlay** – `bg-black/50` to improve text contrast.
- **CTA Buttons** – Primary (Gold border, emerald fill on hover) and secondary (transparent, gold text).

### 4.3 Leaderboard
- **Table** – Tailwind‑styled rows with zebra striping. Column headers are sticky on scroll.
- **Live Search** – `<input>` bound to a JS `filterTable` function that hides non‑matching rows in real time.

### 4.4 Past Champions Cards
- **Card Layout** – Flexbox grid (`grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3`).
- **Content** – Champion photo (rounded), name, score, and country flag icon.

### 4.5 Venue Spotlight & Gallery
- **Venue Cards** – Two cards side‑by‑side on desktop, stacked on mobile, each with a photo, name, and short description.
- **Gallery Grid** – 4‑6 images, responsive `grid-cols-2 md:grid-cols-3`. Clicking opens a **lightbox modal** (full‑screen overlay with fade‑in animation).

### 4.6 Registration Form
- **Fields** – Name, Email, Phone, and a message textarea.
- **Validation** – Simple JS checks for non‑empty values and email pattern; on success, `alert('Thank you for registering!')`.

### 4.7 Footer
- **Elements** – © year, social media icons (FontAwesome), and venue location tags styled with the accent gold.

---

## 5. Interaction & JavaScript Features
| Feature | Description |
|---------|-------------|
| **Mobile Nav Toggle** | Adds/removes `hidden` class on the mobile nav list. |
| **Leaderboard Live Search** | Filters table rows based on case‑insensitive substring match across all columns. |
| **Image Lightbox Modal** | Captures click events on gallery images, shows the clicked image in a centered overlay with a close button (`Esc` key also closes). |
| **Form Submission Alert** | Validates inputs and displays a modal alert (via `window.alert`). |

All scripts are placed inside a single `<script>` block at the bottom of `index.html` to keep the page self‑contained.

---

## 6. Accessibility & Performance
- **Semantic HTML** – Use of `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>` for better screen‑reader navigation.
- **Alt Text** – All images receive descriptive `alt` attributes.
- **Color Contrast** – Gold on dark emerald meets WCAG AA contrast requirements.
- **Responsive Images** – Unsplash URLs include width (`w=800`/`w=1600`) to serve appropriately sized assets. The `loading="lazy"` attribute is added to gallery images.
- **Tailwind CDN** – Loads a minified stylesheet on demand; no build step needed.
- **JavaScript Size** – All interactivity is under 5 KB gzipped.

---

## 7. Asset References (CDNs)
- **Tailwind CSS** – `https://cdn.tailwindcss.com`
- **FontAwesome** – `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css`
- **Hero Background** – `https://images.unsplash.com/photo-1535131749006-b7f58c99034b?auto=format&fit=crop&w=1600&q=80`
- **Pun Hlaing Golf Club** – `https://images.unsplash.com/photo-1587174486073-ae5e5cff23aa?auto=format&fit=crop&w=800&q=80`
- **Yangon Golf Club** – `https://images.unsplash.com/photo-1592919505780-303950717480?auto=format&fit=crop&w=800&q=80`
- **2018 Champion (Paul Peterson)** – `https://images.unsplash.com/photo-1593111774240-d529f12cf4bb?auto=format&fit=crop&w=400&q=80`
- **Gallery Images** – Placeholder Unsplash URLs (any suitable golf‑related images, same `auto=format&fit=crop` pattern).

---

## 8. Development & Deployment
1. **Clone / Copy** – The entire site lives in a single `index.html` file; no bundlers or server‑side code required.
2. **Testing** – Open `index.html` in any modern browser. Verify responsive breakpoints using DevTools.
3. **Hosting** – Deploy to any static‑file host (GitHub Pages, Netlify, Vercel, or an S3 bucket with public read access).

---

## 9. Future Enhancements (Optional)
- **Dynamic Leaderboard** – Replace the static table with an API‑driven fetch on page load.
- **Progressive Web App** – Add a manifest and service worker for offline caching.
- **Internationalisation** – Provide language toggle for Burmese and English.
- **Analytics** – Integrate a lightweight analytics script (e.g., Plausible).

---

*Document generated from the original specification (`myanmar_open_golf_spec_html_css_js.md`).*