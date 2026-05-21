# 🎨 Universal Frontend Design Prompt — Neo-Brutalist Premium UI
# inspiration link - https://sowieso.wero-wallet.eu/nl-en/merchant

> **How to use this file**: Give this entire `.md` file to any AI (ChatGPT, Claude, Gemini, Copilot, Cursor, etc.) along with your project description. The AI will generate a complete, production-quality frontend matching this design system. Replace all `{{PLACEHOLDER}}` values with your project-specific details before handing it off.

---

## 0. Project Variables (Fill These In)

```yaml
PROJECT_NAME:        "{{Your Project Name}}"          # e.g. "BookSphere", "HealthTrack", "EduFlow"
PROJECT_TAGLINE:     "{{Short tagline}}"               # e.g. "College Library System"
PROJECT_DOMAIN:      "{{Domain/industry}}"             # e.g. "Education", "Healthcare", "E-commerce"
HERO_HEADLINE:       "{{Main hero text}}"              # e.g. "Find your next big idea."
HERO_SUBTEXT:        "{{Hero description}}"            # e.g. "Access our collection of resources."
PRIMARY_ENTITY:      "{{Main data object}}"            # e.g. "Book", "Product", "Course", "Patient"
USER_ROLE_1:         "{{Primary user role}}"           # e.g. "Student", "Customer", "Patient"
USER_ROLE_2:         "{{Admin/secondary role}}"        # e.g. "Admin", "Manager", "Doctor"
CATEGORIES:          ["{{Cat1}}", "{{Cat2}}", ...]     # e.g. ["Mathematics", "Science", "Arts"]
COLLEGE_OR_ORG:      "{{Organization name}}"           # e.g. "VVCE Mysuru", "Acme Corp"
TECH_STACK:          "Next.js / React / Vite / etc."   # Choose your framework
CSS_FRAMEWORK:       "Tailwind CSS 4"                  # Or vanilla CSS
BACKEND:             "Supabase / Firebase / Express"   # Your backend
```

---

## 1. Design Philosophy — Neo-Brutalism

### What Is Neo-Brutalism?

A modern web aesthetic inspired by brutalist architecture and 90s print design. It prioritizes **boldness, clarity, and personality** over minimalism. Key traits:

- **Thick black borders** on everything (cards, buttons, inputs, sections)
- **Hard-edge drop shadows** (no blur, no spread — just solid offset rectangles)
- **Flat vivid colors** — no gradients on components, only on hero backgrounds
- **Uppercase display typography** for all headings and UI labels
- **Zero border-radius** on interactive elements (buttons, inputs, badges)
- **Chunky, physical hover states** — elements shift position like pressing a real button
- **Raw geometric shapes** — squares, rectangles, thick dividers
- **Playful tilted labels** — decorative "sticker" elements at slight angles
- **High contrast** — black borders on white cards, white text on black sections

### Why Neo-Brutalism?

It creates an **instantly memorable, premium-feeling UI** that stands out from every generic Tailwind template. It feels intentional, crafted, and unapologetically bold.

---

## 2. Color System

### 2.1 The Vivid 5-Color Palette

Choose **5 vivid, saturated colors** that match your project's domain. Here are domain-specific palette suggestions:

#### 📚 Education / Library / Academic
| Role | Name | Hex | Tailwind |
|------|------|-----|----------|
| Primary | Salmon | `#FF8A7A` | `--color-primary` |
| Secondary | Electric Yellow | `#F9FF73` | `--color-secondary` |
| Accent | Mint Green | `#64E78E` | `--color-accent` |
| Tertiary | Magenta | `#F778FF` | `--color-tertiary` |
| Quaternary | Cornflower Blue | `#70A1FF` | `--color-quaternary` |

#### 🏥 Healthcare / Medical
| Role | Name | Hex |
|------|------|-----|
| Primary | Teal | `#2DD4BF` |
| Secondary | Soft Blue | `#93C5FD` |
| Accent | Coral | `#FB7185` |
| Tertiary | Lavender | `#C084FC` |
| Quaternary | Amber | `#FCD34D` |

#### 🛒 E-commerce / Marketplace
| Role | Name | Hex |
|------|------|-----|
| Primary | Electric Orange | `#FF6B35` |
| Secondary | Cyan | `#22D3EE` |
| Accent | Lime | `#A3E635` |
| Tertiary | Hot Pink | `#EC4899` |
| Quaternary | Gold | `#FBBF24` |

#### 💻 Developer Tools / SaaS
| Role | Name | Hex |
|------|------|-----|
| Primary | Indigo | `#818CF8` |
| Secondary | Emerald | `#34D399` |
| Accent | Amber | `#F59E0B` |
| Tertiary | Rose | `#FB7185` |
| Quaternary | Sky | `#38BDF8` |

#### 🎵 Creative / Music / Art
| Role | Name | Hex |
|------|------|-----|
| Primary | Neon Pink | `#FF1493` |
| Secondary | Electric Violet | `#8B5CF6` |
| Accent | Chartreuse | `#DFFF00` |
| Tertiary | Cyan | `#00FFFF` |
| Quaternary | Tangerine | `#FF9F43` |

#### 🍔 Food / Restaurant
| Role | Name | Hex |
|------|------|-----|
| Primary | Tomato Red | `#FF6347` |
| Secondary | Mustard | `#FFD93D` |
| Accent | Avocado | `#6BCB77` |
| Tertiary | Eggplant | `#9B59B6` |
| Quaternary | Cream | `#FFF5E1` |

### 2.2 Universal Semantic Tokens

These map your chosen palette to CSS custom properties:

```css
:root {
  /* Surface */
  --background: #FAFAFA;
  --foreground: #0A0A0A;
  --card: #FFFFFF;
  --card-foreground: #0A0A0A;

  /* Brand (map to your chosen palette) */
  --primary: {{YOUR_PRIMARY_HEX}};
  --primary-foreground: #000000;
  --secondary: {{YOUR_SECONDARY_HEX}};
  --secondary-foreground: #000000;
  --accent: {{YOUR_ACCENT_HEX}};
  --accent-foreground: #000000;

  /* Neutral */
  --muted: #E5E5E5;
  --muted-foreground: #52525B;

  /* Functional */
  --destructive: #EF4444;

  /* Neo-Brutalism Core — DO NOT CHANGE */
  --border: #000000;
  --input: #000000;
  --ring: #000000;
  --radius: 0.5rem;
}
```

**Dark mode** variant (optional):
```css
.dark {
  --background: #121212;
  --foreground: #F5F5F5;
  --card: #1E1E1E;
  --card-foreground: #F5F5F5;
  --primary: {{YOUR_TERTIARY_HEX}};       /* Swap for dark mode contrast */
  --secondary: {{YOUR_QUATERNARY_HEX}};
  --accent: {{YOUR_SECONDARY_HEX}};
  --muted: #27272A;
  --muted-foreground: #A1A1AA;
  --border: #F5F5F5;                       /* Borders flip to white */
  --input: #F5F5F5;
  --ring: #F5F5F5;
}
```

### 2.3 The Hero Gradient

Every project gets **one diagonal gradient** used only on the hero section:

```css
.bg-gradient-hero {
  background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
}
```

---

## 3. Typography

### 3.1 Font Stack

Load exactly **3 Google Fonts**:

| Font | Role | CSS Variable | Where Used |
|------|------|-------------|-----------|
| **Inter** | Body | `--font-sans` | All body text, paragraphs, descriptions, form fields |
| **Archivo Black** | Display/Heading | `--font-heading` | Every heading, button label, nav link, badge, stat value |
| **JetBrains Mono** | Monospace | `--font-mono` | Code blocks, IDs, technical data (optional) |

> **Alternative heading fonts** if Archivo Black doesn't fit your vibe: `Space Grotesk`, `Bebas Neue`, `Oswald`, `Rubik Mono One`, `Anton`

### 3.2 Global Heading Rules

```css
h1, h2, h3, h4, h5, h6 {
  font-family: var(--font-heading);
  text-transform: uppercase;
  letter-spacing: -0.05em;  /* tight tracking */
}
```

### 3.3 Type Scale

| Element | Size | Weight | Extras |
|---------|------|--------|--------|
| Hero `<h1>` | `text-6xl md:text-8xl` | `font-black` (900) | `tracking-tighter leading-[0.9]` |
| Section `<h2>` | `text-4xl md:text-5xl` | `font-black` | `tracking-tighter` |
| Card/Sub `<h3>` | `text-xl md:text-2xl` | `font-black` | `leading-tight` |
| Stat number | `text-3xl md:text-4xl` | `font-black` | — |
| Stat label | `text-xs` | `font-bold` | `text-muted-foreground` |
| Navbar link | `text-sm` | `font-heading` | `tracking-wide uppercase` |
| Button label | `text-lg` or `text-xl` | `font-heading` | `uppercase tracking-wider` |
| Badge | `text-[10px]` or `text-xs` | `font-heading` | `uppercase` |
| Body text | `text-lg` | `font-medium` (500) | `text-muted-foreground` |
| Small/meta | `text-xs` or `text-sm` | `font-bold` | — |

### 3.4 Text Selection

```css
body {
  selection: bg-primary text-primary-foreground;
}
```
Users see your brand primary color when selecting text.

---

## 4. Shadow & Interaction System

### 4.1 Hard Shadows (The Soul of Neo-Brutalism)

```css
/* Three tiers — never use blur or spread */
--shadow-brutal:    4px 4px 0px 0px rgba(0, 0, 0, 1);
--shadow-brutal-sm: 2px 2px 0px 0px rgba(0, 0, 0, 1);
--shadow-brutal-lg: 8px 8px 0px 0px rgba(0, 0, 0, 1);
```

Usage classes:
- `.brutal-shadow` → Cards, modals, hero search bar
- `.brutal-shadow-sm` → Buttons, badges, nav active states, inputs
- `.brutal-shadow-lg` → Featured/highlighted cards

### 4.2 Hover Animation (Lift + Shadow Grow)

```css
.brutal-transition {
  transition: transform 0.2s cubic-bezier(0.34, 1.56, 0.64, 1),
              box-shadow 0.2s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.brutal-hover:hover {
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0px 0px var(--border);
}
```

The `cubic-bezier(0.34, 1.56, 0.64, 1)` gives a **bouncy overshoot** — the element feels like it springs up.

### 4.3 Active/Press Animation (Push Down)

```css
.brutal-active:active {
  transform: translate(2px, 2px);
  box-shadow: 0px 0px 0px 0px var(--border);
}
```

Element pushes into the surface. Shadow disappears = feels "pressed in".

### 4.4 Additional Micro-Interactions

| Element | Effect |
|---------|--------|
| Card image | `group-hover:scale-105 transition-transform duration-300` |
| Category tiles | Inner text `group-hover:scale-110 transition-transform` |
| Social/icon buttons | `hover:-translate-y-1 hover:shadow-[4px_4px_0px_0px_{{PRIMARY_HEX}}]` |
| Loading states | Lucide `Loader2` icon + `animate-spin` |
| Mobile menu | Framer Motion `AnimatePresence` height 0→auto, opacity 0→1 |
| Nav links (active) | Colored background + `brutal-shadow-sm` appears |

---

## 5. Component Library

### 5.1 Button

```
┌──────────────────┐
│   BUTTON LABEL   │  ← font-heading, uppercase, tracking-wider
└──────────────────┘
  ████ ← brutal-shadow-sm (2px offset, black)
```

| Variant | Classes |
|---------|---------|
| **Primary** | `bg-primary text-black border-2 border-black rounded-none brutal-shadow-sm brutal-hover font-heading uppercase` |
| **Outline** | `bg-white text-black border-4 border-black rounded-none brutal-shadow-sm brutal-hover font-heading uppercase` |
| **Accent** | `bg-accent text-black border-2 border-black rounded-none brutal-shadow-sm brutal-hover font-heading uppercase` |
| **Destructive** | `bg-destructive/10 text-destructive font-heading uppercase` |
| **Ghost** | `hover:bg-muted font-heading uppercase` |
| **Icon** | `size-8 border-2 border-black brutal-shadow-sm brutal-hover rounded-none` |

Sizes:
- Standard: `h-8` (compact), `h-12` (form submit)
- Large/CTA: `h-14` to `h-16`, `px-8` to `px-10`, `text-lg` to `text-xl`

### 5.2 Input / Text Field

```
┌────────────────────────────────┐
│  Placeholder text...           │  ← h-12, text-lg, border-2 border-black
└────────────────────────────────┘     rounded-none, focus:border-primary
```

- `border-2 border-black rounded-none`
- `focus-visible:ring-0 focus-visible:border-primary` (border turns primary on focus, no ring)
- `h-12 text-lg` for form fields, `h-16 text-lg` for hero search
- **Dark variant** (admin forms): `bg-gray-900 border-2 border-white text-white placeholder:text-gray-600`

### 5.3 Badge / Tag

```
┌──────────┐
│ LABEL    │  ← font-heading, uppercase, text-[10px], border-2 border-black
└──────────┘     rounded-none, brutal-shadow-sm, colored bg
```

Status color map (universal):
| Status | Background | Text |
|--------|-----------|------|
| Success/Available/Active | `bg-accent` | `text-black` |
| Warning/Pending | `bg-yellow-400` | `text-black` |
| Error/Unavailable | `bg-destructive` | `text-white` |
| Completed/Returned | `bg-secondary` | `text-black` |
| Neutral/Outline | `border-2 border-black bg-transparent` | `text-foreground` |

### 5.4 Card (Entity Card)

This is your main reusable card for displaying items (books, products, courses, etc.):

```
┌───────────────────────────────┐  ← border-4 border-black brutal-shadow
│  ┌─────────────────────────┐  │     brutal-transition brutal-hover
│  │                         │  │
│  │     IMAGE / MEDIA       │  │  ← aspect-[2/3] or aspect-[4/3]
│  │     (or icon placeholder)│  │     border-b-4 border-black
│  │                  [BADGE]│  │  ← Status badge, absolute top-right
│  └─────────────────────────┘  │
│                               │
│  [CATEGORY TAG]    Meta info  │  ← Outline badge + secondary info
│  ITEM TITLE                   │  ← font-heading text-xl uppercase
│  Subtitle / Author            │  ← text-muted-foreground font-medium
│                               │
│  ┌─────────────────────────┐  │
│  │    PRIMARY ACTION       │  │  ← Full-width primary button
│  └─────────────────────────┘  │
└───────────────────────────────┘
```

- Container: `bg-white border-4 border-black brutal-shadow brutal-transition brutal-hover rounded-lg overflow-hidden h-full`
- Image placeholder: colored bg (`bg-secondary`) with a relevant icon at low opacity
- Image hover: `group-hover:scale-105 transition-transform duration-300`

### 5.5 Stat Card

```
┌─────────────────────────────┐
│  ┌──────┐                   │  ← bg-white border-4 border-black
│  │ ICON │  LABEL            │     brutal-shadow brutal-hover
│  │ (bg) │  BIG NUMBER       │
│  └──────┘                   │     Icon container: p-3, border-4 border-black,
└─────────────────────────────┘     colored bg from your palette
```

- Value: `font-heading text-3xl md:text-4xl font-black uppercase`
- Label: `font-heading uppercase text-xs text-muted-foreground font-bold`
- Icon box: `p-3 border-4 border-black rounded-sm` with a palette color bg
- Grid: `grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6`

### 5.6 Tilted Sticker Label

A decorative element placed on hero sections and auth pages — looks like a hand-placed sticker:

```html
<div class="inline-block bg-white border-4 border-black px-6 py-2 brutal-shadow mb-4 rotate-[-2deg]">
  <span class="font-heading uppercase text-xl font-black">{{LABEL TEXT}}</span>
</div>
```

Variants:
- White on colored section: `bg-white border-4 border-black rotate-[-2deg]`
- Colored accent: `bg-accent text-black border-2 border-black rotate-[-2deg]`
- Dark theme: `bg-primary text-black border-2 border-white rotate-[2deg]`

Use small angles: `-2deg`, `2deg`, `-1deg`, `1deg` only.

### 5.7 Section Heading Underline

After every section `<h2>`, place a small colored bar:

```html
<h2 class="font-heading text-5xl font-black uppercase tracking-tighter mb-4">
  Section Title
</h2>
<div class="h-2 w-24 bg-primary border-2 border-black brutal-shadow-sm"></div>
```

Alternate colors across sections: primary → accent → secondary → primary.

---

## 6. Layout System

### 6.1 Public Page Shell

```
┌─────────────────────────────────────┐
│ NAVBAR (sticky, border-b-4)         │ ← h-20, bg-white, z-50
├─────────────────────────────────────┤
│ HERO SECTION                        │ ← Full-width, vivid bg, border-b-8
├─────────────────────────────────────┤
│ CONTENT SECTION 1                   │ ← py-20 to py-24
├─────────────────────────────────────┤
│ CONTENT SECTION 2                   │ ← Alternate bg colors
├─────────────────────────────────────┤
│ CTA SECTION                         │ ← Vivid bg, border-b-8
├─────────────────────────────────────┤
│ FOOTER                              │ ← bg-black, border-t-8 border-primary
└─────────────────────────────────────┘
```

### 6.2 Dashboard Page Shell

```
┌──────────────────────────────────────┐
│ NAVBAR (sticky top)                  │
├──────────┬───────────────────────────┤
│ SIDEBAR  │ MAIN CONTENT              │
│ (w-64)   │ (p-4 md:p-8)             │
│ sticky   │ max-w-6xl/7xl            │
│ top-20   │                           │
├──────────┴───────────────────────────┤
```

- Sidebar: `hidden lg:block` (hidden on mobile)
- Dashboard bg: `bg-muted/30`
- Max wrapper: `max-w-[1600px] mx-auto`

### 6.3 Auth Page Shell

```
┌─────────────────────────────────────┐
│   [decorative blob 1]               │ ← bg-muted, pattern overlay
│                                     │    3 large blurred circles
│        CENTERED LOGO                │
│                                     │
│   ┌──────────────────────┐          │
│   │    AUTH FORM CARD     │          │ ← max-w-md, centered
│   │    border-4, shadow   │          │    No navbar, no footer
│   └──────────────────────┘          │
│                                     │
│   [decorative blob 2]               │
│   [decorative blob 3]               │
└─────────────────────────────────────┘
```

Blob recipe:
```html
<div class="absolute top-[-10%] left-[-10%] w-96 h-96 bg-primary rounded-full mix-blend-multiply filter blur-3xl opacity-50"></div>
<div class="absolute bottom-[-10%] right-[-10%] w-96 h-96 bg-secondary rounded-full mix-blend-multiply filter blur-3xl opacity-50"></div>
<div class="absolute top-[20%] right-[20%] w-72 h-72 bg-accent rounded-full mix-blend-multiply filter blur-3xl opacity-50"></div>
```

### 6.4 Section Background Rhythm

Alternate backgrounds to create visual rhythm and prevent monotony:

| Section # | Background | Border |
|-----------|-----------|--------|
| 1 (Hero) | Gradient or vivid color | `border-b-8 border-black` |
| 2 | `bg-muted` (#E5E5E5) | `border-b-8 border-black` |
| 3 | `bg-white` | — |
| 4 | `bg-black text-white` | `border-y-8 border-primary` |
| 5 | `bg-secondary` or `bg-accent` | `border-b-8 border-black` |
| 6 | `bg-white` | — |

**Key rule**: Dark (black bg) sections always use `border-y-8 border-primary` to create a vivid accent line.

### 6.5 Container

```html
<div class="container mx-auto px-4">
  <!-- Content -->
</div>
```
For narrower content pages (about, rules, settings): add `max-w-5xl`

### 6.6 Grid Patterns

| Content Type | Grid Classes |
|-------------|-------------|
| Entity cards (4 col) | `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8` |
| Stat cards (4 col) | `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6` |
| Category tiles | `grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-6` |
| Content cards (2 col) | `grid grid-cols-1 md:grid-cols-2 gap-8` |
| Feature cards (3 col) | `grid grid-cols-1 md:grid-cols-3 gap-6` |
| Footer columns | `grid grid-cols-1 md:grid-cols-4 gap-12` |

---

## 7. Navbar Specification

```
┌──────────────────────────────────────────────────────────────┐
│ [ICON] PROJECT_NAME   Home  Catalog  About    [🔍] [Login] [CTA] │
└──────────────────────────────────────────────────────────────┘
  ▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀  ← border-b-4 border-black
```

- `sticky top-0 z-50 w-full border-b-4 border-black bg-white brutal-shadow-sm`
- Height: `h-20`
- **Logo**: Icon in colored box (`bg-primary p-2 border-2 border-black rounded-sm brutal-shadow-sm`) + brand name in `font-heading text-2xl uppercase tracking-tighter`, second word colored `text-primary`
- **Links**: `font-heading uppercase text-sm tracking-wide px-3 py-1 border-2`
  - Active: `border-black bg-secondary brutal-shadow-sm`
  - Inactive: `border-transparent hover:border-black hover:bg-muted`
- **Auth buttons**:
  - Login: outline style
  - CTA/Admin: primary filled
- **Mobile**: Hamburger menu icon (`Menu`/`X`), animated dropdown with Framer Motion

---

## 8. Footer Specification

```
┌──────────────────────────────────────────────────────────────┐
│ bg-black, text-white, border-t-8 border-primary              │
│                                                              │
│  [LOGO] Brand Name          Quick Links       Contact Us     │
│  Description text           - Link 1          - Address      │
│                             - Link 2          - Phone        │
│  [📧] [🌐] [📖]            - Link 3          - Email        │
│                             - Link 4          - Website ↗    │
│                                                              │
│  ─────────────── border-t-4 border-gray-800 ──────────────── │
│  © 2025 Project Name        Privacy Policy  Terms of Service │
└──────────────────────────────────────────────────────────────┘
```

- "Quick Links" heading: `text-secondary` (your yellow/secondary)
- "Contact Us" heading: `text-accent` (your green/accent)
- Social icons: white bg boxes, hover → `border-primary -translate-y-1 shadow-[4px_4px_0px_0px_{{PRIMARY}}]`
- Links: `text-gray-300 hover:text-primary hover:underline underline-offset-4 decoration-2`
- Copyright: `font-heading uppercase tracking-widest text-sm text-gray-400`

---

## 9. Sidebar Specification (Dashboard)

```
┌──────────────────┐
│ [Avatar] UserName │ ← border-b-4 border-black
│           Role    │
├──────────────────┤
│ 📊 Dashboard     │ ← Active: bg-accent + brutal-shadow-sm
│ 🔍 Search        │    Inactive: hover:border-black hover:bg-muted
│ 📦 Manage Items  │
│ 📋 Requests      │
├──────────────────┤
│ 🚪 Logout        │ ← text-destructive, border-t-4 border-black
└──────────────────┘
```

- Width: `w-64`, `sticky top-20`, `h-[calc(100vh-5rem)]`
- `border-r-4 border-black`
- User avatar: Square, `rounded-none w-12 h-12 border-2 border-black brutal-shadow-sm`
  - Role 1: `bg-primary` avatar bg
  - Role 2: `bg-secondary` avatar bg
- Active link color differs by role:
  - Role 1 (student): `bg-accent` (green)
  - Role 2 (admin): `bg-primary` (salmon)

---

## 10. Page Templates

### 10.1 Home / Landing Page

**Sections in order:**

1. **Hero** — gradient bg, `border-b-8 border-black`, texture overlay (20% opacity)
   - Tilted sticker label ("{{TAGLINE}}")
   - Giant `<h1>`: "{{HERO_HEADLINE}}" — second line in white with `drop-shadow-[4px_4px_0_rgba(0,0,0,1)]`
   - Description in white pill with `brutal-shadow-sm`
   - Search form: white container, `border-4 border-black brutal-shadow`, Input + accent-colored search button
   - `py-24 md:py-32`

2. **Stats Bar** — `bg-muted border-b-8 border-black`, `py-20`
   - 4 stat cards showing key numbers

3. **Featured Items** — `bg-white`, `py-24`
   - Section heading + colored underline bar
   - "View All →" outline button
   - Grid of 4 entity cards

4. **Categories** — `bg-black text-white border-y-8 border-primary`, `py-24`
   - Grid of category tiles: `border-4 border-white p-6 h-32`, hover → `bg-white text-black`

5. **CTA Section** — `bg-secondary border-b-8 border-black`, `py-32`
   - 2 decorative blurred circles (primary + accent)
   - Big heading: "Ready to get started?"
   - 2 buttons: Primary action + secondary outline action

### 10.2 Catalog / Search Page

- `bg-muted` overall
- Dynamic page title with search query
- Colored underline bar
- Error state: `bg-destructive text-white border-4 border-black brutal-shadow`
- Empty state: white card with centered text
- Entity cards in 4-column grid

### 10.3 About / Info Page

1. Hero — `bg-accent`, tilted sticker, giant heading
2. Description section — 2-column (text + 2×2 stat grid)
3. Features/Infrastructure — `bg-muted border-y-8 border-black`, 3-column cards
4. Services — `bg-white`, 2×4 grid of service tags in secondary color
5. Resources — `bg-black text-white border-y-8 border-primary`, link grid

### 10.4 Rules / Guidelines Page

1. Hero — `bg-black text-white border-b-8 border-secondary`
2. Rules grid — 2-column, cards with colored header strips
3. Warning/penalty notice — `bg-destructive/10 border-4 border-destructive`
4. Stats bar — `bg-black text-white border-4 border-primary`

### 10.5 Auth Pages (Login / Signup)

**Student Login:**
- White card: `bg-white border-4 border-black brutal-shadow p-8`
- Green tilted "{{ROLE_1}} Access" sticker
- "WELCOME BACK" heading
- Form fields with black borders, rounded-none
- Primary colored submit button, full-width `h-14`
- Footer links to signup + admin login

**Admin Login:**
- **Dark card**: `bg-black text-white border-4 border-primary brutal-shadow p-8`
- Shield icon badge (top-right corner)
- Primary tilted "Staff Only" sticker
- Dark inputs: `bg-gray-900 border-2 border-white text-white`
- Primary submit button with white border

### 10.6 User Dashboard

- Welcome banner: white card, `border-4 border-black brutal-shadow-sm`
  - Greeting + "Explore" action button
- 4 stat cards
- Recent activity / items section
- Empty state with icon + CTA button

### 10.7 Admin Dashboard

- **Dark header**: `bg-black text-white border-4 border-primary brutal-shadow-sm`
  - Status sticker + overview heading + action buttons
- 4 stat cards (one in destructive color for alerts)
- Activity list: white card, `border-4 border-black brutal-shadow`
  - Colored header strip (`bg-secondary border-b-4 border-black`)
  - Items separated by `divide-y-4 divide-black`
  - Action buttons per item (Approve/Reject)

---

## 11. Responsive Design Rules

| Breakpoint | Behavior |
|-----------|----------|
| **Mobile (< 768px)** | Single column, hamburger menu, sidebar hidden, full-width buttons, smaller headings |
| **Tablet (768–1024px)** | 2-column grids, partial nav |
| **Desktop (> 1024px)** | Full 4-column grids, sidebar visible, complete navbar |

Key responsive patterns:
```
hidden md:flex          → Desktop nav links
md:hidden               → Mobile menu button
hidden lg:block         → Sidebar
grid-cols-1 sm:grid-cols-2 lg:grid-cols-4  → Responsive card grid
text-6xl md:text-8xl    → Responsive heading
py-24 md:py-32          → Responsive section padding
flex-col sm:flex-row    → Stack → row
```

---

## 12. Decorative Texture Patterns

Add subtle texture overlays on hero sections for depth:

```html
<!-- Cubes pattern (geometric, good for tech/academic) -->
<div class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] opacity-20"></div>

<!-- Diamonds pattern (elegant, good for auth pages) -->
<div class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/diagmonds-light.png')] opacity-30"></div>
```

Alternative patterns from transparenttextures.com:
- `bright-squares.png` — tech/SaaS
- `food.png` — food/restaurant
- `geometry2.png` — education
- `medical.png` — healthcare
- `tiny-grid.png` — minimal/neutral

---

## 13. Icon Strategy

Use **Lucide React** (`lucide-react`) for all icons. Choose icons that match your domain:

### Universal Icons (every project needs these)
| Purpose | Icon |
|---------|------|
| Logo/Brand | Domain-relevant (e.g., `Library`, `Heart`, `ShoppingBag`, `Code`) |
| Search | `Search` |
| Menu/Close | `Menu` / `X` |
| Dashboard | `LayoutDashboard` |
| Settings | `Settings` |
| Logout | `LogOut` |
| Loading | `Loader2` + `animate-spin` |
| Success | `CheckCircle` |
| Error | `XCircle` |
| Warning | `AlertTriangle` |
| Arrow | `ArrowRight` |
| Eye toggle | `Eye` / `EyeOff` |
| Admin shield | `Shield` / `ShieldCheck` |

### Domain-Specific Icon Suggestions

| Domain | Icons to Use |
|--------|-------------|
| 📚 Education | `BookOpen`, `Library`, `GraduationCap`, `Users`, `Clock` |
| 🏥 Healthcare | `Heart`, `Stethoscope`, `Pill`, `Activity`, `Thermometer` |
| 🛒 E-commerce | `ShoppingBag`, `CreditCard`, `Package`, `Truck`, `Star` |
| 💻 SaaS/Dev | `Code`, `Terminal`, `Layers`, `Zap`, `GitBranch` |
| 🍔 Food | `UtensilsCrossed`, `ChefHat`, `Flame`, `Timer`, `Star` |

---

## 14. Do's and Don'ts — Quick Reference

### ✅ ALWAYS DO

1. Use `border-black` (light) or `border-white` (dark) — **never** gray borders on structural elements
2. Use `rounded-none` on buttons, inputs, badges, and interactive elements
3. Use `font-heading uppercase` on all headings, buttons, nav links, labels, badges
4. Add `brutal-shadow` or `brutal-shadow-sm` to cards and interactive elements
5. Add `brutal-hover` to all clickable cards and buttons
6. Separate major page sections with `border-b-8 border-black`
7. Use `font-medium` (500) or `font-bold` (700) on body text — never regular weight
8. Use your 5-color vivid palette — never raw/generic colors
9. Use `py-20` to `py-32` on full-width sections for breathing room
10. Place a colored underline bar (`h-2 w-24`) after section headings

### ❌ NEVER DO

1. Use soft/blurred shadows (`shadow-md`, `shadow-lg`, etc.)
2. Use lowercase for headings, buttons, or navigation
3. Use thin (1px) borders on cards, sections, or buttons
4. Use generic sans-serif — always Inter (body) + Archivo Black (display)
5. Use border-radius on buttons, inputs, or badges
6. Use gray borders on primary structural elements
7. Use font-weight below 500 on visible text
8. Use more than 1 gradient (hero only)
9. Use icons without purpose — every icon should have semantic meaning
10. Create generic/bland layouts — every section should feel bold and intentional

---

## 15. Boilerplate CSS (Copy-Paste Ready)

```css
/* === GLOBALS.CSS — Neo-Brutalist Design System === */

@import "tailwindcss";

:root {
  /* REPLACE THESE WITH YOUR PALETTE */
  --color-palette-1: #FF8A7A;    /* Primary */
  --color-palette-2: #F9FF73;    /* Secondary */
  --color-palette-3: #64E78E;    /* Accent */
  --color-palette-4: #F778FF;    /* Tertiary */
  --color-palette-5: #70A1FF;    /* Quaternary */

  --background: #FAFAFA;
  --foreground: #0A0A0A;
  --card: #FFFFFF;
  --card-foreground: #0A0A0A;
  --primary: var(--color-palette-1);
  --primary-foreground: #000000;
  --secondary: var(--color-palette-2);
  --secondary-foreground: #000000;
  --accent: var(--color-palette-3);
  --accent-foreground: #000000;
  --muted: #E5E5E5;
  --muted-foreground: #52525B;
  --destructive: #EF4444;
  --border: #000000;
  --input: #000000;
  --ring: #000000;
  --radius: 0.5rem;

  /* Neo-Brutalism Shadows */
  --shadow-brutal: 4px 4px 0px 0px rgba(0, 0, 0, 1);
  --shadow-brutal-sm: 2px 2px 0px 0px rgba(0, 0, 0, 1);
  --shadow-brutal-lg: 8px 8px 0px 0px rgba(0, 0, 0, 1);
}

.dark {
  --background: #121212;
  --foreground: #F5F5F5;
  --card: #1E1E1E;
  --card-foreground: #F5F5F5;
  --primary: var(--color-palette-4);
  --secondary: var(--color-palette-5);
  --accent: var(--color-palette-2);
  --muted: #27272A;
  --muted-foreground: #A1A1AA;
  --border: #F5F5F5;
  --input: #F5F5F5;
  --ring: #F5F5F5;
}

/* Base */
* { border-color: var(--border); }
body { font-family: var(--font-sans); background: var(--background); color: var(--foreground); }
h1, h2, h3, h4, h5, h6 {
  font-family: var(--font-heading);
  text-transform: uppercase;
  letter-spacing: -0.05em;
}

/* Brutal Utilities */
.brutal-shadow    { box-shadow: var(--shadow-brutal); }
.brutal-shadow-sm { box-shadow: var(--shadow-brutal-sm); }
.brutal-shadow-lg { box-shadow: var(--shadow-brutal-lg); }

.brutal-transition {
  transition: transform 0.2s cubic-bezier(0.34, 1.56, 0.64, 1),
              box-shadow 0.2s cubic-bezier(0.34, 1.56, 0.64, 1);
}
.brutal-hover:hover {
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0px 0px var(--border);
}
.brutal-active:active {
  transform: translate(2px, 2px);
  box-shadow: 0px 0px 0px 0px var(--border);
}

/* Hero Gradient */
.bg-gradient-hero {
  background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
}
```

---

## 16. Pre-Flight Checklist

Before shipping, verify every page against these criteria:

- [ ] **Bold first impression** — Does the hero section feel energetic and premium?
- [ ] **Thick borders everywhere** — Are all cards, buttons, and inputs using `border-2`+ `border-black`?
- [ ] **Hard shadows** — Are shadows solid black offsets (no blur)?
- [ ] **Uppercase headings** — Are all `h1`–`h6`, buttons, and nav links uppercase Archivo Black?
- [ ] **Vivid colors** — Are palette colors used consistently? No gray/generic buttons?
- [ ] **Hover states** — Do cards and buttons physically shift on hover?
- [ ] **Section rhythm** — Do page sections alternate between white, muted, and black backgrounds?
- [ ] **Thick dividers** — Are major sections separated by `border-b-8`?
- [ ] **Responsive** — Does the layout collapse gracefully (4→2→1 columns)?
- [ ] **No border-radius** — Are buttons, inputs, and badges all `rounded-none`?
- [ ] **Text weight** — Is all visible text at least `font-medium` (500)?
- [ ] **Sticker labels** — Are decorative tilted labels used on hero/auth sections?
- [ ] **Empty states** — Do empty lists show a styled card with icon + CTA?
- [ ] **Loading states** — Do async operations show a `Loader2 animate-spin`?
- [ ] **Mobile menu** — Does the hamburger menu animate smoothly?

---

> **TL;DR for any AI**: Build a **neo-brutalist** web frontend. Use thick black borders (`border-4 border-black`), hard shadows (`4px 4px 0 0 black`), flat vivid colors (5-color palette), uppercase Archivo Black headings, Inter body text, `rounded-none` on all interactive elements, bouncy hover animations that shift elements up-left, alternating section backgrounds (white → gray → black), and chunky `border-b-8` section dividers. Make it look bold, premium, and unapologetically loud.
