# DEVHACK 3.0 — Complete Frontend Specification

> **Source**: https://dsudevhack3.tech/  
> **Analyzed**: CSS bundle (`index-DIvpg3BQ.css`) + JS bundle (`index-BchfoYSX.js`)  
> **Stack**: React 19 + Vite + TailwindCSS v4 + Framer Motion + GSAP (ScrollTrigger)

---

## 1. Design System

### 1.1 Color Palette

| Token | HEX | RGB | Usage |
|---|---|---|---|
| `--color-base` | `#1a1a1a` | rgb(26, 26, 26) | Page background, primary dark surface |
| `--color-cream` | `#f3ecd2` | rgb(243, 236, 210) | Body text, headings on dark bg, borders |
| `--color-orange` | `#f97028` | rgb(249, 112, 40) | Primary CTA buttons, accents, underlines, glows, UI primary |
| `--color-pink` | `#f489a3` | rgb(244, 137, 163) | Secondary accent, gradient ends, hover states |
| `--color-yellow` | `#f3a20f` | rgb(243, 162, 15) | Gradient via stops, hover text on some links |
| `--color-ui-primary` | `#f97028` | rgb(249, 112, 40) | Alias for orange — all interactive primary elements |
| `color-black` | `#000000` | rgb(0,0,0) | Hard outlines, neo-brutalist shadows |
| `color-white` | `#ffffff` | rgb(255,255,255) | Text on colored backgrounds, overlay text |
| Dark variant | `#0a0a0a` | rgb(10,10,10) | Slightly darker surface panels |
| Dark variant 2 | `#00040D` | rgb(0,4,13) | Deep radial gradient cores (space/void effect) |
| Mid dark | `#2b2a2a` | rgb(43,42,42) | Card surfaces, elevated panels |
| Cream light | `#f9f1df` | rgb(249,241,223) | Light-mode card bg / elevated cream |
| Cream mid | `#e8e2c8` | rgb(232,226,200) | Borders on cream surfaces |
| White warm | `#fff9f4` | rgb(255,249,244) | Lightest surface tone |
| Text muted | `#3a3a3a` | rgb(58,58,58) | Secondary text on light surfaces |
| Text muted 2 | `#333333` | rgb(51,51,51) | Dark body copy on cream |
| Hover orange-dark | `#e05a10` | rgb(224,90,16) | Orange hover darken |

#### Selection Colors
- `::selection` background: `#f97028`
- `::selection` color: `#f3ecd2`

---

### 1.2 Typography

#### Font Families

| Role | Family | Import |
|---|---|---|
| `--font-display` | `Caprasimo` | Google Fonts — display/decorative, used for ALL headings (h1–h6) |
| `--font-sans` | `Space Grotesk` (300–700) | Google Fonts — body text, navigation, labels, paragraphs |
| `--font-mono` | `ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas` | Code snippets (rare usage) |
| Serif accent | `Cormorant Garamond` (ital, wgt 300–700) | Occasional decorative italic accents |

```
@import url("https://fonts.googleapis.com/css2?family=Caprasimo&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,500;1,600;1,700&family=Space+Grotesk:wght@300..700&display=swap");
```

#### Type Scale

| Token | Size | Line Height | Usage |
|---|---|---|---|
| `text-xs` | 0.75rem (12px) | 1.333 | Fine print, badges |
| `text-sm` | 0.875rem (14px) | 1.428 | Captions, labels |
| `text-lg` | 1.125rem (18px) | 1.555 | Body large, nav links |
| `text-xl` | 1.25rem (20px) | 1.4 | Sub-headings, card titles |
| `text-2xl` | 1.5rem (24px) | 1.333 | Section sub-headings |
| `text-3xl` | 1.875rem (30px) | 1.2 | Secondary headings |
| `text-4xl` | 2.25rem (36px) | 1.111 | Tertiary section titles |
| `text-5xl` | 3rem (48px) | 1 | Section main headings |
| `text-6xl` | 3.75rem (60px) | 1 | Large decorative titles |
| `text-7xl` | 4.5rem (72px) | 1 | Hero sub-text |
| `text-8xl` | 6rem (96px) | 1 | Hero graphic text |
| Fluid hero | `clamp(3.5rem, 8.5vw, 6rem)` | 1 | Responsive hero heading |
| Fluid hero L | `clamp(3.8rem, 8.5vw, 6.5rem)` | 1 | Larger responsive heading |
| Fluid hero XL | `clamp(4.2rem, 10vw, 7.5rem)` | 1 | Largest responsive heading |

#### Font Weights

| Token | Value | Usage |
|---|---|---|
| `font-normal` | 400 | Body text |
| `font-medium` | 500 | UI labels, nav |
| `font-semibold` | 600 | Card labels |
| `font-bold` | 700 | Buttons, emphasis |
| `font-extrabold` | 800 | Decorative text |
| `font-black` | 900 | Hero impact text |

#### Letter Spacing

| Token | Value | Usage |
|---|---|---|
| `tracking-tighter` | -0.05em | Large decorative headings |
| `tracking-tight` | -0.025em | Sub-headings |
| `tracking-wide` | 0.025em | Default body |
| `tracking-wider` | 0.05em | Labels |
| `tracking-widest` | 0.1em | Badge text, tags |
| Custom `0.2em` | 0.2em | Uppercase eyebrow labels |
| Custom `0.3em` | 0.3em | Very spaced labels |
| Custom `0.4em` | 0.4em | Decorative spaced caps |

---

### 1.3 Spacing System

Base unit: `--spacing: 0.25rem` (4px)

| Scale | px Value | Usage |
|---|---|---|
| 1 | 4px | Micro gaps |
| 2 | 8px | Inner padding small |
| 3 | 12px | Button padding block |
| 4 | 16px | Standard padding |
| 5 | 20px | Card inner padding |
| 6 | 24px | Section sub-gaps |
| 8 | 32px | Card padding |
| 10 | 40px | Medium vertical rhythm |
| 12 | 48px | Section padding y |
| 16 | 64px | Large vertical padding |
| 20 | 80px | Major section gaps |
| 24 | 96px | Page-level vertical |
| 32 | 128px | Hero padding top |
| 40 | 160px | Hero padding variants |

#### Container Widths

| Token | Value |
|---|---|
| `max-w-4xl` | 56rem (896px) |
| `max-w-6xl` | 72rem (1152px) |
| `max-w-7xl` | 80rem (1280px) |
| `max-w-[1200px]` | 1200px |
| `max-w-[1400px]` | 1400px |
| `max-w-[1440px]` | 1440px |
| `max-w-[1640px]` | 1640px |
| Page max | `mx-auto` centered |

---

### 1.4 Border System

| Property | Value | Usage |
|---|---|---|
| Border 1px | `border` (1px solid) | Subtle dividers |
| Border 2px | `border-2` / `border-[2px]` | Card outlines |
| Border 3px | `border-[3px]` | Prominent cards |
| Border 4px | `border-[4px]` / `border-b-4` | Hero elements |
| `rounded-lg` | 0.5rem (8px) | Small components |
| `rounded-xl` | 0.75rem (12px) | Cards |
| `rounded-2xl` | 1rem (16px) | Large cards |
| `rounded-[24px]` | 24px | Prominent cards |
| `rounded-[28px]` | 28px | Large rounded panels |
| `rounded-[2rem]` | 32px | Feature cards |
| `rounded-[2.5rem]` | 40px | Hero panels, modals |
| `rounded-full` | 9999px | Pills, badges, avatar |

**Border colors used:**
- `#1a1a1a` — dark borders on cream surfaces
- `#f3ecd2` — cream borders on dark surfaces  
- `#f97028` — orange accent borders, active states
- `#f97028/30` — 30% opacity orange (subtle)
- `black/10`, `black/15`, `black/20` — soft shadows on white

---

### 1.5 Shadow System

The site uses **neo-brutalist offset box-shadows** as a primary design motif.

| Shadow Class | Value | Usage |
|---|---|---|
| `shadow-[2px_2px_0px_#1a1a1a]` | Hard offset dark | Small card default |
| `shadow-[3px_3px_0px_#1a1a1a]` | Hard offset dark | Card default state |
| `shadow-[4px_4px_0px_#1a1a1a]` | Hard offset dark | Cards, buttons |
| `shadow-[5px_5px_0_#1a1a1a]` | Hard offset dark | Prominent cards |
| `shadow-[6px_6px_0px_#1a1a1a]` | Hard offset dark | Feature cards |
| `shadow-[3px_3px_0px_#f97028]` | Hard offset orange | Hover accent |
| `shadow-[4px_4px_0px_#f97028]` | Hard offset orange | CTA hover |
| `shadow-[8px_8px_0px_#f97028]` | Larger offset orange | Hero CTA hover |
| `shadow-[4px_4px_0px_0px_#1a1a1a]` | Hard 0-spread dark | Buttons |
| `shadow-[0_4px_0px_#f97028]` | Bottom orange underline shadow | Decorative |
| `shadow-[0px_-6px_0px_#f97028]` | Top orange shadow bar | Section decorations |
| `shadow-[0_0_15px_rgba(249,112,40,0.4)]` | Orange glow (40%) | Cards hover glow |
| `shadow-[0_0_15px_rgba(249,112,40,0.5)]` | Orange glow (50%) | Intense glow |
| `shadow-[20px_20px_100px_rgba(244,137,163,0.5)]` | Pink diffuse glow | Pink feature cards |
| `shadow-card` | `0 16px 36px #1e10082e` | Standard card elevation |
| `shadow-glass` | `0 8px 40px #0000002e` | Glassmorphism panel |
| `shadow-2xl` | `0 25px 50px -12px rgba(0,0,0,0.25)` | Modals, overlays |
| `shadow-lg` | Standard large shadow | Dropdowns, menus |

---

### 1.6 Gradients

| Usage | Gradient |
|---|---|
| Hero radial (space) | `radial-gradient(ellipse at center, #00040D 30%, transparent 70%)` |
| Hero radial alt | `radial-gradient(ellipse at center, #00040D 40%, transparent 75%)` |
| CTA button gradient | `linear-gradient(to right, #f97028 → via #f3a20f → #f489a3)` |
| Subtle overlay | `from-white/6 via-white/2 to-transparent` |
| Glass shimmer | `from-white/3 via-white/1 to-transparent` |

---

## 2. Layout Architecture

### Page Structure

```
<body> bg-[#1a1a1a]
  <Navbar>                        fixed top, z-[9999], backdrop-blur
  <main>
    §1  Hero / Landing            min-h-screen, pt-32–40
    §2  About                     py-16–24
    §3  Themes / Tracks           py-16–24
    §4  Timeline                  py-16–24
    §5  Prizes                    py-16–24
    §6  Sponsors                  py-16–24
    §7  FAQ                       py-16–24
    §8  Team                      py-16–24
  <Footer>                        py-8–16
```

### Grid System

- **1 column** → mobile default
- **2 columns** → `sm:grid-cols-2` (640px+), `grid-cols-2` (some sections)
- **Flex wrap** — used extensively for team cards, sponsor logos, FAQ items
- **Flexbox** — primary layout tool for all rows

### Breakpoints (Tailwind v4)

| Name | Min Width | Behavior |
|---|---|---|
| Default | 0px | Mobile single-column stacked |
| `sm` | 640px (40rem) | 2-col grids appear, larger sizes |
| `md` | 768px (48rem) | Mid layout adjustments |
| `lg` | 1024px (64rem) | Desktop multi-column full layout |
| `xl` | 1280px (80rem) | Wide desktop |
| `2xl` | 1536px (96rem) | Ultra-wide |

---

## 3. Component Library

### 3.1 Navigation Bar

**Purpose:** Fixed header providing quick section access and primary CTA.

**Structure:**
```
<nav> fixed top-0 inset-x-0 z-[9999] backdrop-blur-md
  <div> max-w-[1440px] mx-auto px-4–6 py-2–3
    ├── Logo (image)  h-8–12 object-contain
    ├── Desktop Nav Links (hidden on mobile)
    │   └── [Section anchors]
    │       — text-sm/lg, font-medium, text-cream
    │       — hover: text-[#f97028], transition-colors duration-300
    ├── Primary CTA Button (desktop)
    └── Hamburger Menu Button (mobile, z-60)
```

**Background states:**
- Default: `bg-[#1a1a1a]/40 backdrop-blur-md` (transparent with blur)
- Scrolled: `bg-[#1a1a1a]` fully opaque

**Mobile Menu (full-screen overlay):**
- `fixed inset-0 z-[200] bg-black/60 backdrop-blur-xl`
- Slides in from top or fades in
- Links stacked vertically, large tap targets
- `aria-expanded` toggle on hamburger button
- Close button top-right

**Hamburger icon:**  
3 bars (`h-[3px] w-6 bg-cream rounded-full`), animates to X on open via rotate/translate transforms

**Nav Link States:**
| State | Style |
|---|---|
| Default | `text-cream opacity-80` |
| Hover | `text-[#f97028] opacity-100` |
| Active section | `text-[#f97028]` with underline decoration |

---

### 3.2 Primary CTA Button

**Variants:**

**A) Primary / Filled**
- Background: `linear-gradient(to right, #f97028, #f3a20f, #f489a3)`  
  or solid `bg-[#f97028]`
- Text: `text-[#1a1a1a]` or `text-white`, `font-bold`, `uppercase`, `tracking-wider`
- Border: `border-2 border-[#1a1a1a]`
- Shadow: `shadow-[4px_4px_0px_#1a1a1a]` (neo-brutalist offset)
- Padding: `px-6 py-3` or `px-5 py-2.5`
- Border radius: `rounded-lg` or `rounded-xl`
- Hover: `translate-x-0.5 translate-y-0.5 shadow-none` (shifts into shadow)
- Transition: `transition-all duration-300`

**B) Secondary / Ghost Button**
- Background: `transparent`
- Border: `border-2 border-[#f3ecd2]`
- Text: `text-cream`
- Hover: `bg-[#f97028] border-[#f97028] text-[#1a1a1a]`

**C) Icon Button**
- Similar to A, often with `ArrowRight` icon inline

---

### 3.3 Hero Section

**Purpose:** Full-viewport landing with primary heading and call-to-action.

**Layout:**
```
<section> min-h-screen relative overflow-hidden
  ├── Background layers (absolute)
  │   ├── Radial gradient #00040D overlay
  │   ├── Grid/noise texture image
  │   └── Decorative blob shapes (blur-3xl, opacity-20–40)
  ├── Center content column
  │   ├── Eyebrow label — uppercase tracking-[0.4em] text-sm text-cream/60
  │   ├── Main heading — font-display, clamp(4.2rem,10vw,7.5rem)
  │   │   text-cream, tracking-tighter, leading-none
  │   ├── Subtitle — text-lg text-cream/70
  │   ├── Info pill badges
  │   ├── CTA buttons row (Primary + Secondary)
  │   └── Scroll indicator (animated bounce arrow)
  └── Hero Graphic (right side on desktop)
```

**Animations:**
- Title: fade-in + slide-up (Framer Motion, delay 0.2s, duration 0.8s)
- Subtitle: fade-in (delay 0.5s)
- CTAs: fade-in + scale-in (delay 0.8s)
- Background: GSAP parallax scroll

**Background effect:** Deep space radial gradient + blurred color blobs (orange/pink) at corners, absolute positioned, `blur-2xl` to `blur-3xl`, `opacity-10` to `opacity-40`, `z-[-1]`

---

### 3.4 Feature Cards (Themes / Tracks)

**Purpose:** Display content category cards (e.g. hackathon tracks, service categories, features).

**Card Structure:**
```
<div> group rounded-[2rem] border-2 border-[#1a1a1a] or border-[#f3ecd2]
  shadow-[4px_4px_0px_#1a1a1a] hover:shadow-[8px_8px_0px_#f97028]
  bg-[#f9f1df] or bg-[#1a1a1a] (alternates light/dark)
  p-5–6 transition-all duration-300
  hover:-translate-y-1.5
  ├── Icon (SVG, 48–64px)
  ├── Title — font-display text-2xl–3xl text-[#1a1a1a] or text-cream
  └── Description — text-sm–lg text-[#333] or text-cream/80 leading-relaxed
```

**Grid:** `flex flex-wrap gap-4–6` or `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4–6`

---

### 3.5 Timeline Component

**Purpose:** Chronological schedule or process steps.

**Layout:** Horizontal carousel timeline with a persistent central "track" line, a moving train icon, and landscape background elements.

**Visual Details:**
- **Section Title:** "TIMELINE" in a thick, bubbly display font with each letter in an alternating color (brown, orange, pink, yellow).
- **Background Environment:** Light cream background with faint geometric triangular trees and wavy hill silhouettes at the bottom.
- **Track Line:** Solid orange line with an outer glowing aura, overlaid on a dotted path.
- **Progress Train:** Black vector train icon sitting on the active orange track.

**Timeline Item Structure:**
```
<div> relative overflow-hidden (carousel container)
  ├── Track line (orange glow + dotted path)
  ├── Train Icon (positioned on the active track)
  ├── Carousel Track (flex row)
      └── Timeline Cards (alternating top/bottom)
          ├── Card Window Header — Colored strip (orange, pink, etc.) with 3 dots (mac-style)
          ├── Platform Tag — Floating dark label overlapping the top left (e.g., "PLATFORM 03")
          ├── Card Body — White/cream background, solid black border, neo-brutalist shadow
              ├── Date Block — [Day] [Month] [Year] in separate small boxes
              ├── Title — font-display text-xl–2xl text-[#1a1a1a]
              └── Description — text-sm text-gray-600
  └── Controls
      ├── Circular `<` `>` buttons with solid black offset shadows
      ├── Pagination dots (active dot is an orange pill)
      └── Station Counter — "4 / 8 STATIONS" label bottom right
```

**Animation:** GSAP / Carousel — horizontal scrolling with the train icon advancing along the track and the active line filling up.

---

### 3.6 Tier / Prize Cards

**Purpose:** Highlight ranked items (prizes, plans, tiers).

**Card:**
```
<div> rounded-[2rem] border-[3px] border-[#f97028] or border-[#1a1a1a]
  shadow-[6px_6px_0px_#1a1a1a] p-6–8 bg-[#f9f1df] or bg-[#2b2a2a]
  ├── Icon (SVG, 48–80px)
  ├── Position/tier label — uppercase tracking-widest text-xs text-[#f97028]
  ├── Primary value — font-display text-5xl–6xl font-black text-cream or text-[#1a1a1a]
  └── Description — text-sm text-cream/70
```

---

### 3.7 Logo / Partner Cards

**Purpose:** Display partner or sponsor logos in a grid.

**Logo Card:**
```
<div> group rounded-xl border border-black/10 bg-white/50 p-4–6
  hover:bg-white/80 hover:shadow-lg transition-all duration-300
  ├── Logo image (object-contain, grayscale → hover:grayscale-0)
  └── Name (optional, text-sm)
```

---

### 3.8 FAQ Accordion

**Purpose:** Collapsible Q&A section.

**Accordion Item:**
```
<div> border-b border-[#f3ecd2]/20 group
  <button> flex justify-between items-center w-full py-4–5 px-4–6
    aria-expanded="false|true"
    ├── Question text — font-sans font-medium text-lg text-cream
    └── Chevron icon — rotate-0 → rotate-180 transition-transform duration-300
  <div> overflow-hidden h-0 → h-auto transition-all duration-500
    └── Answer text — text-sm–md text-cream/70 leading-relaxed pb-4–5 px-4–6
```

---

### 3.9 Team / Member Cards

**Purpose:** Display people organized by department/role.

**Member Card:**
```
<div> rounded-[24px] border-2 border-[#1a1a1a] shadow-[4px_4px_0px_#1a1a1a]
  bg-[#f9f1df] or bg-cream p-4–5 flex flex-col items-center text-center
  hover:-translate-y-1.5 hover:shadow-[6px_6px_0px_#f97028] transition-all
  ├── Avatar (rounded-full, w-20–24 h-20–24, border-2 border-[#1a1a1a])
  ├── Name — font-display text-xl text-[#1a1a1a]
  ├── Role — text-sm uppercase tracking-wider text-[#f97028]
  └── Social links row (optional)
```

**Grid:** `flex flex-wrap gap-4` or `grid grid-cols-2 sm:grid-cols-3 gap-4`

---

### 3.10 Step / Process Card

**Purpose:** Numbered steps with connecting line.

**Design:** Numbered step cards with connecting line, icon per step, neo-brutalist border styling.

**Steps typically include:**
1. Step 1 — account / setup action
2. Step 2 — profile / configuration
3. Step 3 — selection / mode choice
4. Step 4 — group / team creation
5. Step 5 — confirmation / join action
6. Step 6 — review and submit

---

### 3.11 Footer

**Structure:**
```
<footer> bg-[#0a0a0a] border-t border-[#f3ecd2]/10 py-8–16
  ├── Logo + tagline
  ├── Quick links (section anchors)
  ├── Contact info (mailto + phone)
  ├── Social links row
  │   └── Icons (Instagram, Twitter/X, LinkedIn, etc.)
  ├── Organizer / brand info
  └── Copyright line
```

---

## 4. Navigation System

### Desktop Navbar

```
Navbar (fixed, z-9999)
├── Logo (left)
├── Nav links (center) — section anchors
└── Primary CTA button (right)
```

**Scroll behavior:** Active section is detected via IntersectionObserver; corresponding nav link gets `text-[#f97028]` class.

### Mobile Navigation

- Hamburger icon (top-right, z-60)  
- Full-screen slide-in overlay (`fixed inset-0 bg-black/60 backdrop-blur-xl z-[200]`)
- Vertical list of all nav items
- Close button (`aria-label="Close menu"`)
- Primary CTA repeated

### Scroll to Section

All nav links use smooth scroll (`scroll-behavior: smooth` on `html`). Each section has `scroll-mt-20` to account for fixed header height.

### Section Aria Labels

- `"Main navigation header"` — navbar aria-label
- `"Go to [Section name] section"` — aria-label pattern for each nav link

---

## 5. Section-by-Section Analysis

### §1 Hero

**Layout:** Full viewport, centered content, absolute background layers  
**Visual hierarchy:** Main heading (largest) → Subtitle → Info badges → CTA buttons → Scroll arrow  
**Background:** Deep radial dark gradient (#00040D core) with orange/pink blurred blobs  
**Side element:** Hero graphic / illustration — `drop-shadow-[0_20px_50px_rgba(0,0,0,0.4)]`  
**Interactions:** Parallax on scroll, floating/pulsing graphic animation  
**Animations:** Sequential fade+slide-up on all text elements (Framer Motion stagger)

---

### §2 About

**Layout:** `max-w-4xl–6xl mx-auto`, flex or grid, centered text + stat blocks  
**Content:**
- Section heading
- Description paragraph
- Key stats (e.g. hours, participants, prizes): displayed as large bold numbers with labels
- Participation mode / rules callout
**Animations:** Stats count up on scroll entry (GSAP)

---

### §3 Themes / Tracks

**Layout:** `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6` or masonry-like flex-wrap  
**Section header:** Decorative section title  
**Card hover:** lift + shadow color shifts orange  
**Animations:** Staggered card reveal from bottom on scroll (Framer Motion)

---

### §4 Timeline

**Layout:** Horizontal train track carousel  
**Connector:** Horizontal track line with moving train icon indicating progress  
**Animations:** Train icon moves along the track, active line fills up synchronously with horizontal scroll (GSAP ScrollTrigger or Carousel interaction)

---

### §5 Prizes / Tiers

**Layout:** Flex-wrap, centered, 3–4 cards  
**Spotlight:** Top/winner card is larger, centered, distinct styling  
**Animations:** Scale-in + fade-in stagger

---

### §6 Sponsors / Partners

**Layout:** Flex-wrap, center-aligned, grouped by tier  
**Tiers labeled:** e.g. Gold Sponsors, Platform Partners  
**Animations:** Fade-in on scroll

---

### §7 FAQ

**Layout:** Single column, max-w-4xl, accordion  
**Section intro:** Brief intro text + contact prompt  
**Animations:** Accordion smooth height transition (CSS max-height or Framer Motion layout animation)

---

### §8 Team

**Layout:** Grouped by department, horizontal scrollable or wrapped grid  
**Chief / Senior members:** Prominent display, larger cards  
**Sub-team cards:** 2–3 per row on desktop  
**Animations:** Staggered card fade-in

---

## 6. Animations & Motion Design

### Libraries
- **Framer Motion** — component-level enter animations, hover states, layout animations
- **GSAP** + **ScrollTrigger** — scroll-based reveals, parallax, counters
- **GSAP ScrollSmoother** — smooth scroll inertia (if enabled)
- **CSS Transitions** — hover micro-interactions

### Animation Catalog

| Name | Trigger | Duration | Easing | Delay | Direction |
|---|---|---|---|---|---|
| Hero title reveal | Page load | 0.8s | ease-out | 0.2s | bottom → up |
| Hero subtitle reveal | Page load | 0.6s | ease-out | 0.5s | bottom → up, fade |
| Hero CTA reveal | Page load | 0.5s | ease-out | 0.8s | scale 0.9→1, fade |
| Section heading reveal | Scroll enter viewport | 0.6s | ease-out | 0s | bottom → up |
| Card stagger | Scroll enter viewport | 0.4s each | ease-out | 0.1s stagger | bottom → up |
| Stat counter | Scroll enter viewport | 1.5s | ease-in-out | 0.2s | count 0→value |
| Timeline train progress | Carousel scroll / Next | 0.5s | ease-out | 0s | left → right |
| FAQ open/close | Click | 0.3–0.5s | ease-in-out | 0s | height collapse |
| Card hover lift | Mouse enter | 0.3s | ease-out | 0s | translateY -6px |
| Card hover shadow | Mouse enter | 0.3s | ease-out | 0s | shadow color shift |
| Button press | Mouse down | 0.15s | ease-out | 0s | translate x+0.5 y+0.5 |
| Nav mobile open | Hamburger click | 0.3s | ease-out | 0s | fade in + backdrop |
| Graphic float | Continuous loop | 3s | ease-in-out | 0s | translateY ±10px |
| Background parallax | Scroll | continuous | linear | 0s | 0.3× scroll speed |
| Blob pulse | Continuous | 4–6s | ease-in-out | random | scale 0.95↔1.05, opacity |

### Hover Micro-interactions

```css
/* Standard card hover */
transition: transform 0.3s ease, box-shadow 0.3s ease;
hover: translateY(-6px), shadow shifts to orange

/* Button neo-brutalist press */
hover: translate(0.5px, 0.5px), shadow-none (shadow "disappears" as button "presses in")

/* Nav link */
transition: color 0.15s ease;
hover: color → #f97028

/* Logo / partner card */
filter: grayscale(100%) → grayscale(0%) on hover
opacity: 0.6 → 1
```

---

## 7. Responsive Design Specification

### 320px (Small mobile)
- Single column everything
- Fluid hero text: ~3.5rem
- Nav: hamburger only
- Cards: full-width, stacked
- Padding: px-4

### 375px (Standard mobile)
- Same as 320px but slightly larger font
- Hero text: ~4rem
- Button text fits comfortably

### 640px / sm breakpoint
- 2-column grid for feature cards, team members
- Timeline becomes scrollable horizontal track
- Partner logos wrap in 3-column
- Nav still hamburger

### 768px / md breakpoint
- Nav may partially show (depends on design)
- Timeline shows more cards horizontally

### 1024px / lg breakpoint
- Full desktop navbar visible (all links + CTA button)
- Hamburger hidden
- 3-column feature cards
- Hero: split layout (text left, graphic right) or centered
- Timeline: full horizontal train carousel
- Container: `max-w-6xl`

### 1280px / xl breakpoint
- Comfortable padding throughout
- Max container `max-w-7xl`
- Team grid: 3–4 per row

### 1440px
- Max container `max-w-[1440px]`
- Extra whitespace breathing room

### 1920px
- Content max-width capped at `max-w-[1640px]`
- Background decorations fill remaining space

### Element Responsive Changes

| Element | Mobile | Desktop |
|---|---|---|
| Hero heading | `clamp(3.5rem, 8.5vw, 6rem)` | Up to 6–7.5rem |
| Feature cards | 1 col, full width | 3 col grid |
| Timeline | Horizontal scroll | Horizontal carousel |
| Nav | Hamburger + overlay | Inline links |
| Team cards | 2 col grid | 3-4 col grid |
| Footer | Stacked | Multi-column |
| CTA buttons | Full width or stacked | Inline row |
| Hero graphic | Hidden or small | Large, prominent |

---

## 8. Accessibility Specification

| Feature | Implementation |
|---|---|
| Keyboard navigation | All interactive elements focusable, tab order logical |
| Focus states | `outline-none` with custom `:focus-visible` ring (implied) |
| Hamburger button | `aria-expanded="true|false"`, `aria-label` |
| Nav links | `aria-label="Go to [Section] section"` |
| Accordion | `aria-expanded`, `aria-controls` |
| Screen reader | `aria-hidden="true"` on decorative elements |
| Social links | `aria-label` on icon-only links, "Social links" label on container |
| Skip links | (recommended to add) |
| Color contrast | Cream (#f3ecd2) on dark (#1a1a1a): ~13.8:1 ✅ |
| Color contrast | Orange (#f97028) on dark (#1a1a1a): ~4.8:1 ✅ (AA) |
| Color contrast | Dark (#1a1a1a) on cream (#f3ecd2): ~13.8:1 ✅ |
| Reduced motion | (recommended: `@media (prefers-reduced-motion: reduce)` to disable GSAP/Framer) |
| Image alt text | All images should have descriptive alt attributes |
| Font size | Minimum 12px (0.75rem), comfortable body at 16–18px |

---

## 9. Frontend Technology Stack

| Layer | Technology | Version |
|---|---|---|
| Framework | React | 19 |
| Build tool | Vite | Latest |
| Styling | TailwindCSS v4 | 4.x |
| Animation | Framer Motion | Latest |
| Scroll animation | GSAP + ScrollTrigger | 3.x |
| Routing | React Router DOM (or none — SPA) | — |
| Icons | Lucide React or custom SVG | — |
| Fonts | Google Fonts (Caprasimo, Space Grotesk, Cormorant Garamond) | — |

### Folder Structure

```
src/
├── assets/
│   ├── logo.png
│   ├── hero-graphic.png / .svg
│   ├── hero-bg.png (grid/noise texture)
│   └── partner-logos/
├── components/
│   ├── layout/
│   │   ├── Navbar.jsx
│   │   ├── MobileMenu.jsx
│   │   └── Footer.jsx
│   ├── sections/
│   │   ├── Hero.jsx
│   │   ├── About.jsx
│   │   ├── Themes.jsx
│   │   ├── Timeline.jsx
│   │   ├── Prizes.jsx
│   │   ├── Sponsors.jsx
│   │   ├── FAQ.jsx
│   │   └── Team.jsx
│   ├── ui/
│   │   ├── Button.jsx
│   │   ├── Card.jsx
│   │   ├── AccordionItem.jsx
│   │   ├── TeamMemberCard.jsx
│   │   ├── FeatureCard.jsx
│   │   ├── TimelineItem.jsx
│   │   ├── PartnerLogo.jsx
│   │   └── SectionHeading.jsx
│   └── animations/
│       ├── FadeInView.jsx        (Framer Motion wrapper)
│       ├── StaggerChildren.jsx   (stagger container)
│       └── CountUp.jsx           (GSAP counter)
├── hooks/
│   ├── useActiveSection.js      (IntersectionObserver for nav)
│   ├── useScrollLock.js         (mobile menu body scroll lock)
│   └── useGSAP.js               (GSAP context cleanup hook)
├── data/
│   ├── themes.js
│   ├── timeline.js
│   ├── prizes.js
│   ├── sponsors.js
│   ├── faq.js
│   └── team.js
├── styles/
│   └── index.css                (TailwindCSS v4 entry + custom vars)
├── App.jsx
└── main.jsx
```

### TailwindCSS v4 Config (CSS-based)

```css
/* index.css */
@import "tailwindcss";

@layer theme {
  :root {
    --font-display: "Caprasimo", sans-serif;
    --font-sans: "Space Grotesk", sans-serif;
    --color-base: #1a1a1a;
    --color-cream: #f3ecd2;
    --color-orange: #f97028;
    --color-pink: #f489a3;
    --color-yellow: #f3a20f;
    --color-ui-primary: #f97028;
  }
}

@layer base {
  body {
    background-color: var(--color-base);
    color: var(--color-cream);
    font-family: var(--font-sans);
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
  }
  h1, h2, h3, h4, h5, h6 {
    font-family: var(--font-display);
    font-weight: 400;
  }
  html { scroll-behavior: smooth; }
}
```

---

## 10. Asset Inventory

| Asset | Type | Description | Suggested Replacement |
|---|---|---|---|
| Site logo | PNG | Brand logo | Custom logo |
| Hero Graphic | PNG/SVG | 3D isometric illustration | Generate with CSS 3D or Three.js |
| Hero Background | PNG | Grid/noise texture | CSS grid or SVG noise filter |
| Favicon | PNG | Same as logo | Same as logo |
| Partner logos | Various | Per partner | Grayscale + color versions |
| Team member photos | JPG/PNG | Per member | Placeholder avatars |
| Feature/track icons | SVG | Per card category | Lucide/Heroicons + custom |
| Tier/prize icons | SVG | Per tier | Emoji or custom SVG |
| Social media icons | SVG | Instagram, Twitter, LinkedIn | Lucide or Simple Icons |
| Arrow icon | SVG | `ArrowRight` inline in buttons | Lucide `ArrowRight` |

---

## 11. Build Instructions

### Phase 1: Foundation & Design System

1. `npm create vite@latest . -- --template react`
2. Install deps: `tailwindcss@4`, `framer-motion`, `gsap`
3. Set up `index.css` with full token system (colors, fonts, custom shadows)
4. Import Google Fonts (Caprasimo, Space Grotesk, Cormorant Garamond)
5. Set body background `#1a1a1a`, color `#f3ecd2`, font Space Grotesk
6. Set all headings to Caprasimo

### Phase 2: Layout Shell

1. Build `App.jsx` with `<Navbar>` + `<main>` + `<Footer>`
2. Build `Navbar.jsx`: fixed, backdrop-blur, logo + links + CTA
3. Build `MobileMenu.jsx`: full-screen overlay with stacked links
4. Build `Footer.jsx`: dark bg, links, contact, copyright
5. Add section anchors and scroll-mt-20 offsets

### Phase 3: Section Components

Build each section in order:
1. `Hero.jsx` — full viewport, gradient bg, fluid type, CTA buttons
2. `About.jsx` — stats, description, rules
3. `Themes.jsx` — card grid with hover effects
4. `Timeline.jsx` — horizontal carousel with train progress track
5. `Prizes.jsx` — tier cards with neo-brutalist styling
6. `Sponsors.jsx` — logo grid with grayscale hover
7. `FAQ.jsx` — accordion with smooth toggle
8. `Team.jsx` — member cards grouped by department

### Phase 4: Responsive Design

1. Test each breakpoint (320, 375, 640, 768, 1024, 1280, 1440, 1920px)
2. Apply sm: / md: / lg: / xl: overrides
3. Verify nav collapses correctly
4. Verify hero text scales with clamp()
5. Verify all grids reflow properly

### Phase 5: Animations

1. Wrap section headings in `<FadeInView>` Framer Motion components
2. Wrap card grids in `<StaggerChildren>` with 0.1s delays
3. Add GSAP `useGSAP` for horizontal carousel scroll and train progress animation
4. Add `<CountUp>` to stat numbers in About section
5. Add hero entrance sequence (staggered delays: 0.2, 0.5, 0.8s)
6. Add hero graphic floating loop animation
7. Add background parallax (GSAP ScrollTrigger)
8. Add accordion smooth height animation (Framer Motion `AnimatePresence`)
9. Test all animations, add `prefers-reduced-motion` fallbacks

### Phase 6: Optimization

1. Lazy-load below-fold images
2. Optimize fonts: `display=swap`, preconnect to Google Fonts
3. Code-split heavy GSAP imports
4. Compress all PNG/JPG assets (WebP preferred)
5. Add `<meta>` SEO tags (title, description, OG)
6. Lighthouse audit: target 90+ performance, 100 accessibility
