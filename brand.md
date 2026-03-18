# Camino Tenerife — Brand Kit

---

## 1. BRAND IDENTITY

**Business name:** Camino Tenerife
**Tagline:** "Walk the Island. Find Your Way."
**Owner:** Andreas Höfelmeyer — experienced hiker, Camino Francés veteran (twice completed), local guide on Tenerife

**What this business is:**
Guided walking experiences on Tenerife's Caminos — routes inspired by the Camino de Santiago tradition. Andreas walks with you, not ahead of you. Every package includes professional photos and videos of your journey as a lasting memory.

**What makes it different:**
- Andreas has walked the Camino Francés twice — he is not a tourism operator, he is a fellow pilgrim who happens to live on Tenerife
- Small groups or solo — never a tourist bus
- The Camino de Santiago spirit: simplicity, presence, human connection
- Tenerife's volcanic landscape as a backdrop unlike anything on the original Camino

---

## 2. COLORS

The palette is drawn from the Tenerife landscape and the Camino Santiago tradition — earthy, warm, alive.

| Role | Hex | Usage |
|---|---|---|
| Background | `#FAF7F2` | Warm off-white — like sunlit stone |
| Primary text | `#1A1208` | Deep warm black — not cold |
| Secondary text | `#6B5B45` | Warm brown — captions, labels |
| Brand terracotta | `#C4622D` | Primary accent — CTAs, buttons, highlights |
| Brand gold | `#D4A035` | Secondary accent — icons, badges, decorative |
| Stone grey | `#8C7E6E` | Borders, dividers, muted UI |
| Forest green | `#3D5A3E` | Nature accent — trail markers, tags |
| Sky blue | `#7BA7BC` | Horizon accent — subtle backgrounds |
| Warm card | `rgba(250,247,242,0.85)` | Card fills |
| Card border | `rgba(196,98,45,0.15)` | Card borders |

### Primary Gradient
The warmth of the Camino — sunrise over volcanic rock:
```
linear-gradient(135deg, #C4622D 0%, #D4A035 100%)
```
Use on: primary buttons, decorative lines, section accents, badge backgrounds.

### Atmospheric Gradient (backgrounds)
```
linear-gradient(160deg, #FAF7F2 0%, #F5EFE4 50%, #EDE4D6 100%)
```

---

## 3. TYPOGRAPHY

Warm, readable, with a human touch. Inspired by trail signage and travel journals.

| Role | Font | Weight | Notes |
|---|---|---|---|
| H1 — Page title | Playfair Display | 700 | Serif — warmth, heritage, depth |
| H2 — Section title | Playfair Display | 600 | With terracotta line underneath |
| H3 — Subsection | Lato | 700 | Clean, grounded |
| H4 — Label/tag | Lato | 700 | Uppercase, letter-spacing: 2px |
| Body / paragraph | Lato | 400 | Line-height: 1.8 — easy to read on trail/mobile |
| Emphasis | Lato | 700 | Inline bold — never italic |
| Caption / meta | Lato | 400 | 13px, color: `#6B5B45` |
| Pull quote / accent | Playfair Display | 400 italic | For Camino quotes or testimonials |

Google Fonts import:
```
https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,600;0,700;1,400&family=Lato:wght@400;700&display=swap
```

**Language rule:** Write in English by default. German or Dutch only if explicitly requested.

---

## 4. VISUAL STYLE

**Aesthetic:** "The Trail Journal" — warm, textured, human. Like a well-worn guidebook combined with a photographer's travel diary. Organic, not corporate. Earthy, not luxury.

**Do:**
- Full-bleed landscape photography (volcanic paths, coastal trails, forest floors, Teide in the background)
- Warm overlay washes on hero images (terracotta or gold at 15–25% opacity)
- Organic shapes — no sharp grid-locked layouts
- Parallax scrolling — sky moves slower than the trail
- Hand-drawn style route maps or illustrated trail overviews
- Texture overlays — subtle grain, canvas-like backgrounds
- Generous white (warm off-white) space between sections
- Scroll-triggered reveals — content appears as you walk into it

**Do not:**
- No glassmorphism — that is AI-fy.me's signature, not Camino Tenerife
- No blue/purple gradients — those belong to AI-fy.me
- No corporate stock photos
- No dark mode — this brand lives in daylight
- No cold, technical aesthetics
- No cluttered layouts

### CSS Variables
```css
:root {
  --bg: #FAF7F2;
  --bg-warm: #F5EFE4;
  --bg-deep: #EDE4D6;
  --text: #1A1208;
  --text-muted: #6B5B45;
  --terracotta: #C4622D;
  --gold: #D4A035;
  --stone: #8C7E6E;
  --forest: #3D5A3E;
  --sky: #7BA7BC;
  --gradient: linear-gradient(135deg, #C4622D 0%, #D4A035 100%);
  --card-bg: rgba(250, 247, 242, 0.85);
  --card-border: rgba(196, 98, 45, 0.15);
  --radius: 12px;
  --radius-sm: 6px;
}
```

### Card Style
```css
.trail-card {
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: var(--radius);
  box-shadow: 0 4px 24px rgba(26, 18, 8, 0.08);
  padding: 32px;
}
```

### Buttons
```css
.btn-primary {
  background: linear-gradient(135deg, #C4622D 0%, #D4A035 100%);
  color: #ffffff;
  font-family: 'Lato', sans-serif;
  font-weight: 700;
  font-size: 15px;
  letter-spacing: 0.5px;
  border: none;
  border-radius: 6px;
  padding: 14px 32px;
  cursor: pointer;
  transition: opacity 0.2s, transform 0.15s, box-shadow 0.2s;
}
.btn-primary:hover {
  opacity: 0.92;
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(196, 98, 45, 0.3);
}

.btn-outline {
  background: transparent;
  color: var(--terracotta);
  border: 1.5px solid var(--terracotta);
  font-family: 'Lato', sans-serif;
  font-weight: 700;
  font-size: 15px;
  border-radius: 6px;
  padding: 13px 31px;
  cursor: pointer;
  transition: all 0.2s;
}
.btn-outline:hover { background: rgba(196, 98, 45, 0.06); }
```

### Decorative Lines
```css
.brand-line {
  height: 2px;
  background: linear-gradient(90deg, #C4622D 0%, #D4A035 60%, rgba(212,160,53,0) 100%);
  border: none;
  margin: 24px 0;
}

.trail-marker {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: var(--forest);
  font-family: 'Lato', sans-serif;
  font-weight: 700;
  font-size: 11px;
  letter-spacing: 2px;
  text-transform: uppercase;
}
.trail-marker::before {
  content: '';
  display: inline-block;
  width: 24px;
  height: 3px;
  background: var(--gradient);
  border-radius: 2px;
}
```

### Badge
```css
.badge {
  display: inline-block;
  background: linear-gradient(135deg, rgba(196,98,45,0.1), rgba(212,160,53,0.1));
  border: 1px solid rgba(196, 98, 45, 0.25);
  color: var(--terracotta);
  font-family: 'Lato', sans-serif;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 4px 12px;
  border-radius: 20px;
}
```

---

## 5. BRAND VOICE

### Who Andreas Is (on this brand)
A fellow walker. Someone who has walked the Camino Francés twice and moved to Tenerife — and now wants to share what this island offers to people who walk slowly, look around, and want to feel something real. Not a tour guide. A companion.

### Tone Rules
- **First person and warm** — speak as Andreas, not as a company
- **No distance** — the reader feels like they are already talking to a friend
- **Camino spirit** — simplicity, honesty, presence. What you need, nothing more
- **Specific and sensory** — describe what the path smells like, what the light does at 7am, how the volcanic rock feels underfoot
- **Gentle invitation, never hard sell** — the CTA is always "join me" not "buy now"
- **No corporate language** — no "packages", "solutions", "deliverables" — say "walk", "route", "what's included", "we carry"
- **European measured warmth** — genuine, never gushing
- **No dashes as separators** — use a new line or a period instead
- **Never:** "unforgettable experience", "world-class", "luxury", "seamless", "life-changing" (show it, don't claim it)

### Voice Examples

**Wrong:**
> "Book our premium guided walking package and unlock an unforgettable Tenerife experience."

**Right:**
> "We start before the heat. I know a path that follows the ridge — on a clear morning you can see the ocean on both sides. Bring good shoes and I'll bring the coffee."

---

## 6. TARGET AUDIENCE

### Primary: "The Pilgrim at Heart"
- **Who:** People who have walked the Camino de Santiago, or deeply want to. Age 30–65. Solo travelers, couples, small friend groups.
- **Why Tenerife:** They want the Camino spirit but cannot do the full Francés right now. Or they have done it and want more.
- **Core truth:** The Camino is not a place — it is a pace, a presence, a way of being. They are looking for that feeling again.
- **Primary pain:** Mass tourism. Crowded trails. Guided groups where the guide is 20 meters ahead with a flag. They want human connection, not herding.
- **What converts them:** Andreas's personal Camino history. Small group or solo. Real photos from real walks. A tone that feels like a message from a friend, not a brochure.

### Secondary: "The Nature Walker"
- **Who:** Visitors to Tenerife who love hiking, nature, and getting away from the resorts. Not necessarily Camino-aware.
- **What converts them:** The landscape. The exclusivity of a personal guide. The photo/video package as a tangible memory.

### Default assumption
Write for "The Pilgrim at Heart" — they know what the Camino feels like and are looking for that again on this island.

---

## 7. OFFERS & SERVICES

Keep language simple. Never use "package" — say "walk" or "what's included."

| Walk | What it is | What's included |
|---|---|---|
| Half-day walk | 3–4 hours on one route | Guide (Andreas), photos delivered digitally |
| Full-day walk | 6–8 hours, one full route | Guide, photos + short video highlight reel |
| Sunrise walk | Early start, magic light | Guide, professional sunrise photography |
| Custom walk | Choose your route and pace | Guide, full photo + video package, flexible duration |

**Booking CTA language:**
- "Walk with me" (primary)
- "Choose your route" (secondary)
- "Send me a message" (contact)

Never: "Book now", "Purchase", "Add to cart"

---

## 8. TECH STACK (context for Claude)

| Tool | Role |
|---|---|
| Netlify | Static site hosting |
| GitHub | Version control and deployment trigger |
| Claude Code | AI coding assistant — builds and edits the site |
| GoHighLevel | CRM, contact list, email follow-up after inquiry |
| Stripe Payment Links | Booking payments — linked from site CTAs |
| Netlify Forms | Contact / inquiry form — feeds into GHL via webhook |

**No backend. No database. No login.** This is a pure static site. All complexity lives in GHL post-click.
