# Product Requirement Document (PRD) & Antigravity Agent Prompt

## Project Name: Myanmar Open Golf Official Website
## Tech Stack: Pure HTML5, CSS3 (Tailwind CSS CDN), Vanilla JavaScript (Single-file Ready)

---

### 1. Executive Summary
Build a single-page, responsive, and elegant website for the **Myanmar Open Golf Tournament** using standard HTML, Tailwind CSS via CDN, and Vanilla JavaScript. The site includes a luxury dark emerald and gold theme, high-resolution placeholder images for golf courses and players, an interactive image lightbox gallery, a live searchable leaderboard, and past champions profiles.

---

### 2. Design & Media Assets (Image Specifications)

* **Theme Colors:** Dark Emerald (`#064e3b`), Accent Gold (`#d97706`), Slate Background (`#f8fafc`).
* **CDN Dependencies:**
  * Tailwind CSS: `https://cdn.tailwindcss.com`
  * FontAwesome Icons: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css`
* **Image Sources (Unsplash CDN Placeholders):**
  * **Hero Background:** `https://images.unsplash.com/photo-1535131749006-b7f58c99034b?auto=format&fit=crop&w=1600&q=80`
  * **Pun Hlaing Golf Club:** `https://images.unsplash.com/photo-1587174486073-ae5e5cff23aa?auto=format&fit=crop&w=800&q=80`
  * **Yangon Golf Club:** `https://images.unsplash.com/photo-1592919505780-303950717480?auto=format&fit=crop&w=800&q=80`
  * **2018 Champion (Paul Peterson):** `https://images.unsplash.com/photo-1593111774240-d529f12cf4bb?auto=format&fit=crop&w=400&q=80`
  * **Gallery Images:** High-resolution shots of golf swings, trophies, and tournament greens.

---

### 3. Website Structure & Components

1. **Header & Navigation:**
   * Logo with golf icon, responsive nav links, and mobile hamburger menu handled via JS.
2. **Hero Banner:**
   * Full-screen background image overlay, title, subtitle, and CTA buttons.
3. **Interactive Leaderboard:**
   * Real-time JavaScript search filter for players and countries.
4. **Past Champions & Player Profiles:**
   * Cards with player photo thumbnails, scores, and country flags.
5. **Venue Spotlight & Photo Gallery:**
   * Responsive grid of golf course photos.
   * **JS Lightbox Modal:** Clicking any gallery image opens a full-screen preview popup with a close button.
6. **Registration / Contact Form:**
   * Form layout with simple JS validation and alert popup.
7. **Footer:**
   * Copyright, social icons, and venue location tags.

---

### 4. Antigravity AI Agent Prompt (Copy & Paste directly into Antigravity)

```
Please create a complete, single-file `index.html` web application for "Myanmar Open Golf" using ONLY standard HTML5, CSS3 (Tailwind CSS CDN), and Vanilla JavaScript.

Requirements:
1. Include Tailwind CSS CDN and FontAwesome Icon CDN in the `<head>`.
2. Apply a luxury golf design theme using deep emerald green (#064e3b) and gold accents (#d97706).
3. Include high-quality Unsplash image URLs for all sections:
   - Hero banner with a full golf course background image.
   - Host Venues (Pun Hlaing Golf Club & Yangon Golf Club) with venue card photos.
   - Past Champions section featuring player avatar thumbnails (e.g., 2018 Champion Paul Peterson).
   - Photo Gallery grid displaying 4-6 tournament action shots and trophy pictures.
4. Add interactive JavaScript features inside embedded `<script>` tags:
   - Mobile navigation toggle.
   - Live Search filter for the Leaderboard table.
   - Image Lightbox Modal: Clicking any photo in the gallery opens a full-screen image preview overlay.
   - Working contact/registration form submission alert.
5. All HTML, CSS, JavaScript, and image links must be contained in a single `index.html` file without external build tools.
```