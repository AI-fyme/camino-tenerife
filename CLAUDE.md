# CLAUDE.md — Camino Tenerife

This file is the project memory for Claude Code. Read it completely at the start of every session before writing a single line of code or copy.

---

## What This Project Is

**Camino Tenerife** is a static website for a guided walking business on Tenerife, owned and operated by Andreas Höfelmeyer. Andreas guides people on Camino-inspired routes across the island — volcanic paths, coastal trails, forest walks — and delivers professional photos and videos of each walk as part of the service.

This is not a corporate tourism site. It is a personal, warm, human website. The brand voice is Andreas speaking directly to fellow walkers and pilgrims, not a company selling packages.

**Live site:** Hosted on Netlify, deployed automatically from GitHub on every push.

---

## Critical Rules — Read Before Every Output

### 1. Brand rules are in `.claude/references/brand.md`
Read it before writing any copy, choosing any color, or designing any component. No exceptions.

### 2. HTML and frontend rules are in `.claude/references/html.md`
Read it before writing any HTML, CSS, or JavaScript.

### 3. This brand is completely separate from AI-fy.me
- Do NOT use glassmorphism — that is AI-fy.me's signature
- Do NOT use blue (#5170FF) or purple (#CB6CE6) — those are AI-fy.me colors
- Do NOT use Montserrat or Open Sans — those are AI-fy.me fonts
- Do NOT reference LLMO, AI visibility, or anything AI-fy.me related
- Do NOT apply any AI-fy.me marketing frameworks or patterns

### 4. No backend, no database, no login
This is a pure static HTML/CSS/JS site. If a feature requires server-side logic, do not build it. Use Netlify Forms for contact, Stripe Payment Links for bookings.

### 5. Voice rules (summary)
- Write as Andreas, not as a company
- Warm, direct, personal — like a message from a friend
- No hard sell — "Walk with me" not "Buy now"
- Sensory and specific — describe the path, the light, the feeling
- No dashes as separators. Use a new line or a period.
- Never: "unforgettable", "world-class", "luxury", "seamless", "package"

---

## Tech Stack

| Tool | Role |
|---|---|
| HTML / CSS / JavaScript | All frontend — no frameworks |
| Netlify | Hosting + form handling |
| GitHub | Version control (`main` branch → auto-deploy) |
| GoHighLevel | CRM post-inquiry (not part of this codebase) |
| Stripe Payment Links | Booking payments (external links, not embedded) |

---

## Project File Structure

```
camino-tenerife/
├── index.html
├── routes.html
├── routes/
│   ├── half-day.html
│   ├── full-day.html
│   └── sunrise.html
├── about.html
├── gallery.html
├── contact.html
├── styles.css
├── scripts.js
├── images/
└── .claude/
    ├── CLAUDE.md         ← this file
    └── references/
        ├── brand.md      ← colors, fonts, voice, audience
        └── html.md       ← HTML patterns, animations, components
```

---

## Design Decisions (do not change without asking)

- **Fonts:** Playfair Display (headings) + Lato (body) — warm, readable, human
- **Colors:** Terracotta (#C4622D) + Gold (#D4A035) on warm off-white (#FAF7F2)
- **Animation style:** Scroll-triggered reveals — slow, organic, like walking into a scene
- **Hero:** Full-bleed photo with warm overlay + parallax scroll
- **No dark mode** — this brand lives in daylight
- **Mobile first** — all layouts start at 375px and scale up

---

## How to Work on This Project

1. Open terminal inside the `camino-tenerife` folder
2. Run `claude` to start Claude Code
3. Claude Code reads this CLAUDE.md automatically
4. Make changes, then push to GitHub:
   ```bash
   git add .
   git commit -m "describe what changed"
   git push origin main
   ```
5. Netlify detects the push and deploys automatically — live within 30 seconds

---

## Current Status

- [ ] Homepage (index.html)
- [ ] Routes overview page
- [ ] Individual route pages (half-day, full-day, sunrise)
- [ ] About Andreas page
- [ ] Gallery page
- [ ] Contact / inquiry form
- [ ] Global styles (styles.css)
- [ ] Scroll animations (scripts.js)
- [ ] Netlify form connected to GHL webhook
- [ ] Custom domain configured on Netlify
