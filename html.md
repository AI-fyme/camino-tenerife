# Camino Tenerife — HTML & Frontend Reference

This module governs all HTML, CSS, and JavaScript output for the Camino Tenerife website.

---

## Core Principles

1. **Static only** — no backend, no login, no database
2. **Mobile first** — the audience books from their phone
3. **Performance first** — large images must be lazy-loaded and compressed
4. **Warm & organic** — never cold, never corporate, never glassmorphism
5. **One file per page** — all CSS and JS inline or in companion files in the same folder

---

## Page Structure

Every HTML page must include:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Page Title] | Camino Tenerife</title>
  <meta name="description" content="[Page description]">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,600;0,700;1,400&family=Lato:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="styles.css">
</head>
```

---

## Animation Rules

Animations must feel like nature — unhurried, smooth, purposeful.

```css
/* Scroll reveal — content walks into view */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Hero parallax */
.hero-bg {
  background-attachment: fixed;
  background-size: cover;
  background-position: center;
}

/* Staggered children */
.reveal:nth-child(1) { transition-delay: 0s; }
.reveal:nth-child(2) { transition-delay: 0.1s; }
.reveal:nth-child(3) { transition-delay: 0.2s; }
.reveal:nth-child(4) { transition-delay: 0.3s; }
```

JavaScript for scroll reveal:
```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) e.target.classList.add('visible');
  });
}, { threshold: 0.15 });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```

---

## Navigation

Simple, sticky, warm. No mega-menus.

```html
<nav class="nav">
  <a href="/" class="nav-logo">Camino Tenerife</a>
  <div class="nav-links">
    <a href="/routes">Routes</a>
    <a href="/about">About Andreas</a>
    <a href="/gallery">Gallery</a>
    <a href="/contact" class="btn-primary">Walk with me</a>
  </div>
</nav>
```

---

## Hero Section Pattern

Full-bleed image, warm overlay, Playfair Display headline, short human line, single CTA.

```html
<section class="hero">
  <div class="hero-overlay"></div>
  <div class="hero-content">
    <span class="trail-marker">Tenerife · Camino Routes</span>
    <h1>Walk the Island.<br>Find Your Way.</h1>
    <p>Guided walks on Tenerife's most beautiful paths — with someone who has walked the Camino twice and now calls this island home.</p>
    <a href="/routes" class="btn-primary">Choose your route</a>
  </div>
</section>
```

```css
.hero {
  position: relative;
  height: 100vh;
  min-height: 600px;
  background-image: url('images/hero.jpg');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  display: flex;
  align-items: center;
}
.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to bottom,
    rgba(26, 18, 8, 0.3) 0%,
    rgba(196, 98, 45, 0.15) 50%,
    rgba(26, 18, 8, 0.5) 100%
  );
}
.hero-content {
  position: relative;
  z-index: 2;
  color: #ffffff;
  max-width: 680px;
  padding: 0 48px;
}
.hero-content h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.5rem, 6vw, 4.5rem);
  font-weight: 700;
  line-height: 1.1;
  margin: 16px 0 20px;
}
```

---

## Route Cards Pattern

Each Camino route gets its own card. Photo, route name, distance, short description, CTA.

```html
<div class="trail-card reveal">
  <div class="card-image">
    <img src="images/route-1.jpg" alt="Route name" loading="lazy">
    <span class="badge">Half day · 3–4h</span>
  </div>
  <div class="card-body">
    <span class="trail-marker">Coastal route</span>
    <h3>Route Name</h3>
    <p>Short description of what the walker will experience — sensory, specific, honest.</p>
    <a href="/routes/route-name" class="btn-outline">See this walk</a>
  </div>
</div>
```

---

## Contact / Inquiry Form

Uses Netlify Forms. Feeds into GHL via webhook.

```html
<form name="contact" method="POST" data-netlify="true" netlify-honeypot="bot-field">
  <input type="hidden" name="form-name" value="contact">
  <p class="hidden"><label>Do not fill: <input name="bot-field"></label></p>

  <div class="form-group">
    <label for="name">Your name</label>
    <input type="text" id="name" name="name" required placeholder="First name is fine">
  </div>

  <div class="form-group">
    <label for="email">Email</label>
    <input type="email" id="email" name="email" required>
  </div>

  <div class="form-group">
    <label for="route">Which walk interests you?</label>
    <select id="route" name="route">
      <option value="">Tell me more first...</option>
      <option value="half-day">Half-day walk</option>
      <option value="full-day">Full-day walk</option>
      <option value="sunrise">Sunrise walk</option>
      <option value="custom">Custom walk</option>
    </select>
  </div>

  <div class="form-group">
    <label for="when">When are you visiting Tenerife?</label>
    <input type="text" id="when" name="when" placeholder="e.g. April 2026, not sure yet">
  </div>

  <div class="form-group">
    <label for="message">Anything else you want to tell me?</label>
    <textarea id="message" name="message" rows="4" placeholder="Solo, with a partner, group size — whatever helps me prepare"></textarea>
  </div>

  <button type="submit" class="btn-primary">Send me a message</button>
</form>
```

---

## Image Guidelines

- **Hero images:** Minimum 1920px wide. Landscape orientation. Volcanic paths, coastal trails, forest routes, Teide views.
- **Route cards:** 800×600px. Warm light preferred — golden hour, morning mist.
- **Gallery:** Consistent warm tone. Photos should show the path AND the person on it.
- **Format:** WebP with JPG fallback for maximum performance.
- **Alt text:** Always descriptive. "Rocky volcanic trail on the slopes of Teide, Tenerife" not "image1".

---

## File Structure

```
camino-tenerife/
├── index.html          ← Homepage
├── routes.html         ← All routes overview
├── routes/
│   ├── half-day.html
│   ├── full-day.html
│   └── sunrise.html
├── about.html          ← Andreas's story
├── gallery.html        ← Photo/video gallery
├── contact.html        ← Inquiry form
├── styles.css          ← Global styles
├── scripts.js          ← Scroll animations, nav behavior
├── images/             ← All images (WebP)
└── .claude/            ← Claude Code project memory
    ├── CLAUDE.md
    └── references/
        ├── brand.md
        └── html.md
```
