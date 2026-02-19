# UI Design System: Manhattan Brownstone — Old Money Off-Broadway Theme

## Core Design Philosophy

Create an interface embodying the quiet confidence of Upper West Side brownstones, the velvet-curtained intimacy of off-Broadway theaters, and the understated elegance of old Manhattan money. Inspired by herringbone parquet floors, brass door knockers tarnished just so, playbills tucked into coat pockets, and the amber glow of a library lamp at dusk. UI components should feel like the contents of a mahogany credenza—curated, inherited, and never trying too hard. The design honors **Restraint**—the principle that true wealth whispers—as the foundational ethos upon which every decision rests.

### Guiding Principles:

- **Provenance** — Every element should feel like it has a history; nothing looks brand new
- **Discretion** — Understated over ostentatious; the interface never raises its voice
- **Patina** — Warmth that comes from age and use, not artifice
- **Composure** — Layouts maintain their dignity; nothing is hurried or crowded
- **Cadence** — Rhythm borrowed from theater: entrance, pause, delivery
- **Stewardship** — Design that respects the user's intelligence and taste

---

## Color Palette

### Brownstone Tones (Primary Palette):

| Name | Hex | Description |
|------|-----|-------------|
| **Brownstone** | `#8B7355` | Warm sandstone façade, primary warm neutral |
| **Dark Brownstone** | `#6B5842` | Weathered stone in shadow, secondary anchor |
| **Oxblood** | `#6B2D3E` | Leather club chair, worn bookbinding, primary accent |
| **Oxblood Deep** | `#4E1F2D` | Pressed/active states, theater curtain shadow |
| **Brass** | `#B8956A` | Tarnished door hardware, warm metallic accent |
| **Charcoal Wool** | `#2C2C2E` | Cashmere overcoat, primary text and deep anchors |

### Interior Tones (Backgrounds):

| Name | Hex | Description |
|------|-----|-------------|
| **Linen** | `#F4F0EA` | Pressed table linen, lightest background |
| **Parchment** | `#EBE5DA` | Old program notes, secondary background |
| **Dove** | `#DDD7CC` | Plaster crown molding, tertiary background and borders |
| **Brownstone Shadow** | `rgba(44, 44, 46, 0.04)` | Atmospheric layering for depth |

### Accent (Used Sparingly):

| Name | Hex | Description |
|------|-----|-------------|
| **Ivory** | `#FAF8F4` | Piano keys, text on dark surfaces |
| **Curtain Red** | `#8C3A3A` | Velvet theater curtain, warm highlight |
| **Verdigris** | `#5A7A6B` | Copper roof patina, success states |
| **Playbill Gold** | `#C4A24E` | Embossed program lettering, gentle warnings |

### Material References:

| Material | Value |
|----------|-------|
| Theater smoke haze | `rgba(44, 44, 46, 0.08)` |
| Mahogany surface | `#3E2723` |
| Tarnished silver | `#9A9A8E` |
| Brass patina | `rgba(184, 149, 106, 0.7)` |

---

## Typography

### Font Philosophy:
Text should feel like it was typeset for a limited-run literary journal or embossed on a private invitation—measured, classical, and confident without being stiff. Prioritize readability and quiet authority. The typeface choices evoke midcentury Manhattan publishing, brownstone library shelves, and theater marquee elegance.

### Font Stack:

```css
--font-primary: 'Playfair Display', 'Georgia', 'Times New Roman', serif;
--font-body: 'Source Sans 3', 'Inter', -apple-system, 'Segoe UI', sans-serif;
--font-mono: 'JetBrains Mono', 'SF Mono', 'Consolas', monospace;
--font-display: 'Cormorant Garamond', 'Playfair Display SC', serif; /* For marquee titles and monograms */
```

### Type Scale:

| Level | Size | Weight | Notes |
|-------|------|--------|-------|
| Display | 32–40px | 400 | Elegant, like a theater marquee |
| Heading | 22–26px | 500 | Steady, like a chapter title |
| Section title | 13–15px | 600 | letter-spacing: 0.12em, uppercase, spaced like engraved stationery |
| Body | 15–16px | 400 | line-height: 1.7 |
| Small/Caption | 12–13px | 400 | |
| Whisper | 11px | 400 | letter-spacing: 0.05em, muted brownstone tone |

### Text Styling:

- Generous line-height (1.7–1.8) for unhurried reading
- Headings may be center-aligned for formal contexts; body text always left-aligned
- Color warmth hierarchy: darker wool tones = more important
- Occasional use of small-caps and wide letter-spacing for labels, like engraved brass nameplates
- Text color on light backgrounds: `#2C2C2E` (Charcoal Wool)
- Text color on dark backgrounds: `#FAF8F4` (Ivory)

---

## Component Patterns

### Cards & Containers — Brownstone Panels

Inspired by wainscoting, framed gallery walls, and the built-in bookshelves of a parlor-floor study. Clean proportions with quiet border details suggesting millwork and molding:

```css
.card {
  background: #F4F0EA;
  border: 1px solid rgba(44, 44, 46, 0.07);
  border-radius: 3px;
  padding: 28px 32px;
  position: relative;
  box-shadow:
    0 1px 3px rgba(44, 44, 46, 0.04),
    0 6px 24px rgba(44, 44, 46, 0.05);
}

/* Brass accent line — like a picture rail */
.card::after {
  content: '';
  position: absolute;
  top: 0;
  left: 24px;
  right: 24px;
  height: 1px;
  background: linear-gradient(90deg,
    transparent 0%,
    rgba(184, 149, 106, 0.4) 20%,
    rgba(184, 149, 106, 0.4) 80%,
    transparent 100%);
}

.card-parlor {
  background: linear-gradient(178deg, #F4F0EA 0%, #EBE5DA 100%);
  border: 1px solid rgba(184, 149, 106, 0.15);
  border-top: 2px solid #B8956A;
}

.card-playbill {
  background: #FAF8F4;
  border: none;
  border-left: 3px solid #6B2D3E;
  padding: 32px 40px;
  box-shadow: 0 4px 20px rgba(44, 44, 46, 0.06);
}

.card-gallery {
  background: #F4F0EA;
  border: 1px solid rgba(44, 44, 46, 0.06);
  box-shadow:
    inset 0 0 0 4px #F4F0EA,
    inset 0 0 0 5px rgba(184, 149, 106, 0.2);
  /* Double-frame effect like a matted picture */
}

/* Herringbone texture overlay */
.card-herringbone {
  position: relative;
  overflow: hidden;
}

.card-herringbone::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='40' height='40'%3E%3Cpath d='M0 20 L10 0 L20 20 L10 40Z' fill='none' stroke='%232C2C2E' stroke-width='0.3' opacity='0.03'/%3E%3Cpath d='M20 20 L30 0 L40 20 L30 40Z' fill='none' stroke='%232C2C2E' stroke-width='0.3' opacity='0.03'/%3E%3C/svg%3E");
  background-size: 40px 40px;
  pointer-events: none;
  z-index: 0;
}
```

### Border Philosophy:

- Clean rectangles with minimal radius (2px–4px)
- Subtle asymmetry is acceptable — a left border accent suggests a book spine
- Brass top borders on elevated cards suggest crown molding
- Oxblood left borders reference theater curtain edges and bookbinding

### Depth & Shadow:

- Shadows suggest afternoon light through tall parlor windows
- Warm-toned, soft: `0 6px 24px rgba(44, 44, 46, 0.06)`
- Inner shadows for recessed panel effects: `inset 0 2px 6px rgba(44, 44, 46, 0.03)`

---

### Buttons & Interactive Elements — Brass & Leather

```css
.button-primary {
  background: transparent;
  color: #6B2D3E;
  border: 1.5px solid #B8956A;
  border-radius: 3px;
  padding: 11px 28px;
  font-weight: 500;
  letter-spacing: 0.05em;
  transition: all 0.35s cubic-bezier(0.23, 1, 0.32, 1);
}

.button-primary:hover {
  background: #FAF8F4;
  color: #6B2D3E;
  border-color: #B8956A;
  box-shadow: 0 2px 14px rgba(184, 149, 106, 0.18);
}

.button-primary:active {
  background: #EBE5DA;
  transform: scale(0.98);
}

.button-secondary {
  background: #6B2D3E;
  color: #FAF8F4;
  border: none;
  border-radius: 3px;
  padding: 11px 28px;
  font-weight: 500;
  letter-spacing: 0.05em;
  transition: all 0.35s cubic-bezier(0.23, 1, 0.32, 1);
}

.button-secondary:hover {
  background: #4E1F2D;
  box-shadow: 0 4px 18px rgba(107, 45, 62, 0.15);
}

.button-ghost {
  background: transparent;
  border: 1px solid rgba(44, 44, 46, 0.12);
  color: #2C2C2E;
  border-radius: 3px;
}

.button-ghost:hover {
  background: rgba(44, 44, 46, 0.03);
  border-color: rgba(44, 44, 46, 0.2);
}

.button-brass { /* Circular brass button for key actions */
  background: linear-gradient(135deg, #B8956A 0%, #9A7B52 100%);
  color: #FAF8F4;
  border: 1.5px solid rgba(184, 149, 106, 0.6);
  border-radius: 50%;
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 10px rgba(107, 88, 66, 0.2);
}

.button-brass:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 16px rgba(107, 88, 66, 0.25);
}
```

### Icon Buttons:

- Circular brass forms or minimal rectangles
- Generous touch targets: 44px minimum
- Hover reveals warm brass glow: `background: rgba(184, 149, 106, 0.07)`

---

### Form Elements — Correspondence Inputs

```css
.input {
  background: rgba(250, 248, 244, 0.6);
  border: none;
  border-bottom: 1.5px solid rgba(44, 44, 46, 0.1);
  padding: 12px 4px;
  font-size: 16px;
  color: #2C2C2E;
  transition: border-color 0.3s ease;
}

.input:focus {
  outline: none;
  border-bottom-color: #B8956A;
  box-shadow: 0 1px 0 0 #B8956A;
}

.input-enclosed {
  background: rgba(250, 248, 244, 0.8);
  border: 1px solid rgba(44, 44, 46, 0.07);
  border-radius: 3px;
  padding: 14px 20px;
}

.input-enclosed:focus {
  border-color: #B8956A;
  box-shadow: 0 0 0 3px rgba(184, 149, 106, 0.1);
}

.label {
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #8B7355;
  margin-bottom: 6px;
}

.checkbox {
  width: 20px;
  height: 20px;
  border: 1.5px solid rgba(44, 44, 46, 0.18);
  border-radius: 2px;
  accent-color: #6B2D3E;
}

.checkbox:checked {
  background: #6B2D3E;
  border-color: #6B2D3E;
}

.select {
  background: rgba(250, 248, 244, 0.8);
  border: 1px solid rgba(44, 44, 46, 0.08);
  border-radius: 3px;
  padding: 12px 16px;
  color: #2C2C2E;
}
```

### Focus States — Brass Gleam:

- No harsh outlines
- Warm brass glow on focus: `box-shadow: 0 0 0 3px rgba(184, 149, 106, 0.12)`
- Border transitions from dove gray to tarnished brass

---

### Status & Feedback — Marquee Indicators

```css
.badge {
  display: inline-flex;
  padding: 4px 12px;
  font-size: 11px;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  border-radius: 2px;
  background: rgba(44, 44, 46, 0.04);
  color: #2C2C2E;
}

.badge-critical {
  background: rgba(107, 45, 62, 0.07);
  color: #6B2D3E;
  border-left: 2px solid #6B2D3E;
}

.badge-success {
  background: rgba(90, 122, 107, 0.07);
  color: #5A7A6B;
  border-left: 2px solid #5A7A6B;
}

.badge-warning {
  background: rgba(196, 162, 78, 0.07);
  color: #C4A24E;
  border-left: 2px solid #C4A24E;
}

.badge-info {
  background: rgba(184, 149, 106, 0.07);
  color: #8B7355;
  border-left: 2px solid #B8956A;
}

.progress-bar {
  height: 3px;
  background: rgba(44, 44, 46, 0.05);
  border-radius: 1.5px;
}

.progress-fill {
  background: linear-gradient(90deg, #B8956A, #6B2D3E);
  border-radius: 1.5px;
  /* Brass to oxblood: warming with progress */
}

.toast {
  background: #2C2C2E;
  color: #FAF8F4;
  border-left: 3px solid #B8956A;
  border-radius: 3px;
  padding: 16px 24px;
  box-shadow: 0 8px 28px rgba(44, 44, 46, 0.2);
}
```

---

## Layout Principles — Parlor Proportions

### Spacing Scale: `4, 8, 16, 24, 32, 48, 64, 96, 128px`

Prefer generous spacings. Let elements breathe as if arranged across a wide parlor floor, each piece of furniture given its due.

### Grid Philosophy:

- Classical proportions favoring the golden ratio
- Bilateral symmetry for formal layouts; gentle asymmetry permitted for editorial layouts
- Strong central axis — like the hallway of a brownstone, front door to garden
- Maximum content width: 680px for reading, 1080px for applications
- Significant side margins: minimum 64px on desktop

### Visual Weight Distribution:

```
┌──────────────────────────────────┐
│                                  │
│            ◎                     │  ← Marquee element, like a mantelpiece focal point
│                                  │
│     ·              ·             │  ← Flanking elements, like matching sconces
│                                  │
│   ─────────────────────────      │  ← Horizontal divider, like a chair rail
│                                  │
│       ·      ◎      ·           │  ← Secondary grouping, curated triptych
│                                  │
└──────────────────────────────────┘
```

### Dividers & Separators:

- Hair-thin lines with brass warmth: `1px solid rgba(184, 149, 106, 0.15)`
- Or pure negative space — the pause between acts
- Occasional em-dash or bullet ornament as section breaks: `— ◆ —`
- Double-line separators for major sections: two 1px lines with 4px gap between

---

## Interaction Design — Curtain Call

### Transition Timing:

```css
--ease-curtain: cubic-bezier(0.23, 1, 0.32, 1);   /* Deliberate, theatrical reveal */
--ease-brass: cubic-bezier(0.36, 0.66, 0.04, 1);   /* Warm mechanical movement */
--ease-applause: cubic-bezier(0.19, 1, 0.22, 1);   /* Quick entrance, gentle settle */
--duration-slow: 0.5s;
--duration-medium: 0.35s;
--duration-fast: 0.2s;
```

### Hover Philosophy:

- Warm brass glow appears: `background: rgba(184, 149, 106, 0.05)`
- Gentle upward lift: `transform: translateY(-1px)` — like leaning in during conversation
- Never abrupt; always like a door being held open

### Loading States:

- Curtain draw — a subtle horizontal wipe reveal
- Pulse like a dimming house light (slow, 3–4s cycle)
- Ellipsis that types like a telegram: `. . .`

```css
@keyframes parlor-breathe {
  0%, 100% { opacity: 0.4; transform: scale(1); }
  50% { opacity: 0.85; transform: scale(1.005); }
}

@keyframes curtain-reveal {
  0% { clip-path: inset(0 100% 0 0); opacity: 0; }
  100% { clip-path: inset(0 0 0 0); opacity: 1; }
}

@keyframes house-lights {
  0%, 100% { opacity: 0.3; }
  50% { opacity: 0.7; }
}

@keyframes brass-gleam {
  0% { background-position: -200% center; }
  100% { background-position: 200% center; }
}

@keyframes entrance {
  0% { transform: translateY(8px); opacity: 0; }
  100% { transform: translateY(0); opacity: 1; }
}
```

---

## Texture & Material References

### Brownstone Textures:

- Subtle linen weave overlay: `opacity: 0.02`
- Warm plaster micro-variation on backgrounds
- Herringbone parquet pattern for decorative depth (very faint)

### Manhattan-Inspired Surfaces:

```css
.theater-haze {
  background: radial-gradient(ellipse at center,
    rgba(250, 248, 244, 0.97) 0%,
    rgba(235, 229, 218, 0.92) 55%,
    rgba(221, 215, 204, 0.85) 100%);
}

.mahogany-surface {
  background: linear-gradient(180deg, #3E2723 0%, #2C2C2E 100%);
  box-shadow: inset 0 1px 0 rgba(184, 149, 106, 0.08);
}

.linen-texture {
  background-color: #F4F0EA;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='4' height='4'%3E%3Crect width='4' height='4' fill='%23F4F0EA'/%3E%3Crect width='1' height='1' x='2' y='0' fill='%23EBE5DA' opacity='0.25'/%3E%3Crect width='1' height='1' x='0' y='2' fill='%23EBE5DA' opacity='0.25'/%3E%3C/svg%3E");
  background-size: 4px 4px;
}

.wainscoting-border {
  border-bottom: 1px solid rgba(184, 149, 106, 0.12);
  box-shadow: 0 1px 0 rgba(250, 248, 244, 0.5);
  /* Double-line highlight effect like painted millwork */
}

.brass-nameplate {
  display: inline-block;
  padding: 4px 14px;
  background: linear-gradient(135deg, rgba(184, 149, 106, 0.15), rgba(184, 149, 106, 0.08));
  border: 1px solid rgba(184, 149, 106, 0.25);
  border-radius: 2px;
  font-size: 11px;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: #6B5842;
}
```

---

## Iconography — Engraved Strokes

- Stroke-based icons, weight 1.5–2px
- Clean, classical forms — reflecting architectural draftsmanship
- Balanced proportions, optically centered
- Icon size: 18–24px inline, 28–32px standalone

### Style Reference:

```
Standard:  ▢ ◯ △
Manhattan: ◆ ▬ ❧  (weighted, grounded, editorial)
```

Consider icons that feel engraved or embossed:

- Even stroke weight throughout, like a copperplate etching
- Clean terminals and joints, like ironwork detailing
- Weighted, grounded forms — nothing whimsical or playful
- Occasional use of em-dash ornaments `—` and bullet diamonds `◆` as decorative punctuation

---

## Signature Character Details

- **Brass picture rail**: Subtle horizontal gradient line across card tops — `linear-gradient(90deg, transparent, rgba(184,149,106,0.4), transparent)`
- **Wainscoting borders**: Double-line bottom borders suggesting chair rail millwork
- **Warm plaster textures**: Linen undertones in all white spaces — never clinical
- **Oxblood book spine**: Left-border accents on featured cards — like a leather-bound volume pulled from the shelf
- **Herringbone pattern**: Faint chevron SVG behind hero sections — parquet underfoot
- **Centered compositions**: Formal headings center-aligned — brownstone symmetry
- **Parlor shadow warmth**: Shadows tinted warm, never cool — `rgba(44, 44, 46, 0.05)` not blue-gray
- **Editorial rhythm**: Consistent vertical spacing creates the cadence of well-set type
- **Monogram moments**: Single decorative initials or `◆` marks as section punctuation

---

## Recommended shadcn/ui Components

### Base Theme: `theme-stone`
Override CSS variables to shift from neutral stone to warm brownstone Manhattan tones.

```css
/* theme-stone overrides for Manhattan Brownstone palette */
:root {
  --background: 36 22% 93%;       /* #F4F0EA Linen */
  --foreground: 240 3% 18%;       /* #2C2C2E Charcoal Wool */
  --card: 36 20% 89%;             /* #EBE5DA Parchment */
  --card-foreground: 240 3% 18%;  /* #2C2C2E Charcoal Wool */
  --primary: 340 38% 34%;         /* #6B2D3E Oxblood */
  --primary-foreground: 40 33% 97%; /* #FAF8F4 Ivory */
  --secondary: 36 14% 83%;        /* #DDD7CC Dove */
  --secondary-foreground: 240 3% 18%; /* #2C2C2E Charcoal Wool */
  --accent: 30 30% 55%;           /* #B8956A Brass */
  --accent-foreground: 240 3% 18%; /* #2C2C2E Charcoal Wool */
  --muted: 36 14% 85%;            /* Dove lighter */
  --muted-foreground: 30 18% 44%; /* #8B7355 Brownstone */
  --destructive: 340 38% 34%;     /* #6B2D3E Oxblood */
  --destructive-foreground: 40 33% 97%;
  --border: 36 10% 82%;           /* Warm border tone */
  --input: 36 10% 82%;
  --ring: 30 30% 55%;             /* Brass ring */
  --radius: 0.2rem;               /* Minimal radius: brownstone geometry */
}

.dark {
  --background: 240 3% 18%;       /* #2C2C2E Charcoal Wool */
  --foreground: 40 33% 97%;       /* #FAF8F4 Ivory */
  --card: 240 3% 21%;             /* Slightly lighter charcoal */
  --card-foreground: 40 33% 97%;
  --primary: 340 38% 34%;         /* #6B2D3E Oxblood */
  --primary-foreground: 40 33% 97%;
  --secondary: 240 3% 24%;        /* Dark wool */
  --secondary-foreground: 40 33% 97%;
  --accent: 30 30% 55%;           /* #B8956A Brass */
  --accent-foreground: 40 33% 97%;
  --muted: 240 3% 22%;
  --muted-foreground: 36 14% 65%;
  --border: 240 3% 26%;
  --input: 240 3% 26%;
  --ring: 30 30% 55%;
}
```

### Component Styling Guidance (22 Components):

**1. Button (@shadcn/button)**
The brass door handle of user intent. Brass borders with oxblood text; hover reveals ivory fill with a warm glow.

```css
.btn { border: 1.5px solid hsl(var(--accent)); color: hsl(var(--primary)); border-radius: 3px; }
.btn:hover { background: hsl(var(--primary-foreground)); box-shadow: 0 2px 14px rgba(184,149,106,0.18); }
/* Destructive uses deeper oxblood */
/* Ghost: transparent with warm hover glow */
```

**2. Card (@shadcn/card)**
Brownstone panel with brass picture-rail accent. Add `::after` for the horizontal brass gradient line at top. Use `border-top: 2px solid hsl(var(--accent))` for the molding line. Optional herringbone background pattern.

**3. Dialog (@shadcn/dialog)**
Theater curtain parting. Overlay uses `theater-haze` radial gradient. Content panel styled as a playbill: oxblood left border, linen background. Entry animation uses `curtain-reveal` keyframes.

**4. Navigation Menu (@shadcn/navigation-menu)**
Brownstone corridor wayfinding. Horizontal layout, considered spacing. Active item marked with a small brass underline (2px) rather than background change. Diamond `◆` separator between items. Dropdown panels use `card-parlor` style.

**5. Sidebar (@shadcn/sidebar)**
Mahogany library panel. Use `mahogany-surface` dark background. Menu items in Ivory, active item highlighted with a brass left border (`3px solid hsl(var(--accent))`). Section headers in small-caps with `letter-spacing: 0.12em`.

**6. Tabs (@shadcn/tabs)**
Playbill act dividers. Active tab receives an oxblood bottom border (`2px solid hsl(var(--primary))`). Inactive tabs in Brownstone tone. Tab content area uses linen background with subtle inner shadow.

**7. Accordion (@shadcn/accordion)**
Library catalog drawers. Trigger text in Charcoal Wool, chevron in Brass. Expanded content has a faint left border in oxblood. Smooth `--ease-curtain` transition on open/close.

**8. Input (@shadcn/input)**
Correspondence field. Bottom-border-only by default, like a signature line. Focus transitions border from Dove to Brass. Background on focus: faint linen warmth.

**9. Select (@shadcn/select)**
Catalog selector. Trigger styled with brass bottom border. Dropdown uses Parchment background. Selected item marked with a small oxblood diamond to the left.

**10. Badge (@shadcn/badge)**
Engraved classification. Minimal rectangle (`border-radius: 2px`). Left-border colored for variant distinction (oxblood for critical, verdigris for success, playbill gold for warning). Background at 0.07 opacity of accent color.

**11. Alert / Alert Dialog (@shadcn/alert, @shadcn/alert-dialog)**
Concierge notification. Left border in oxblood for errors, brass for info. Background warmer than default — use Parchment. Alert Dialog overlay uses `theater-haze` gradient.

**12. Separator (@shadcn/separator)**
Chair rail molding. Default: `1px solid rgba(184, 149, 106, 0.15)` (brass-tinted). For major sections, double-line style. Optional `— ◆ —` ornament for editorial section breaks.

**13. Form / Field / Label (@shadcn/form, @shadcn/field, @shadcn/label)**
Formal correspondence layout. Labels in uppercase with Brownstone color and wide letter-spacing, like an engraved nameplate. Error messages in Oxblood. Success in Verdigris. Generous vertical spacing (24px minimum between fields).

**14. Avatar (@shadcn/avatar)**
Circular with a thin brass border (`1.5px solid hsl(var(--accent))`). Fallback background in Oxblood with Ivory initials. Suggests a framed portrait miniature.

**15. Tooltip (@shadcn/tooltip)**
Whispered aside. Charcoal Wool background, Ivory text. Minimal `border-radius: 3px`. Subtle warm shadow. Entry: fade in with slight upward drift.

**16. Progress (@shadcn/progress)**
Intermission countdown. Track in Dove (`rgba(44,44,46,0.05)`). Fill gradient from Brass to Oxblood. Height 3px.

**17. Switch (@shadcn/switch)**
Dimmer toggle. Unchecked track in Dove. Checked track in Oxblood. Thumb in Ivory with warm shadow. Transition uses `--ease-brass`.

**18. Table (@shadcn/table)**
Building registry. Header row in Parchment with uppercase small-caps. Row borders in faint brass (`rgba(184,149,106,0.1)`). Alternating rows: Linen and transparent. Hover with brass glow.

**19. Scroll Area (@shadcn/scroll-area)**
Scrollbar thumb in Brownstone, track invisible. Hover shifts to Oxblood. Thin 6px width. Smooth kinetic scrolling.

**20. Sonner / Toast (@shadcn/sonner)**
Stage whisper. Charcoal Wool background with brass left border. Text in Ivory. Entry slides up with `--ease-applause`. Auto-dismiss at 5s — unhurried.

**21. Skeleton (@shadcn/skeleton)**
House lights dimming. Pulse animation uses `parlor-breathe` keyframes. Color oscillates between Dove and Parchment — warm, never cool gray.

**22. Dropdown Menu / Context Menu (@shadcn/dropdown-menu, @shadcn/context-menu)**
Library card catalog. Background in Linen. Items on hover gain brass glow (`rgba(184,149,106,0.07)`). Separator lines in faint brass. Active items get a small oxblood left indicator.

---

### Block Pattern Recommendations:

| Pattern | Theme Application |
|---------|-------------------|
| `dashboard-01` | Parlor floor layout; brass-bordered stat cards; oxblood highlights for key metrics |
| `sidebar-01` | Mahogany panel sidebar with Ivory text on Charcoal Wool background |
| `sidebar-07` | Floating sidebar; warm shadow, brass header accent |
| `login-01` | Centered symmetrical login; `card-playbill` style with oxblood left border; monogram as logo |
| `login-03` | Split layout; left as mahogany surface with brass engraved typography; right as linen form |

---

## Key Design Principles Summary

1. **Restraint is refinement** — Every element earns its place; if it doesn't serve, it doesn't stay
2. **Warmth over cool** — Linen, brownstone, brass, and oxblood; never clinical white or blue-gray
3. **Patina over polish** — Surfaces suggest history: tarnished brass, aged linen, weathered stone
4. **Classical proportions** — Generous margins, golden ratios, the unhurried pace of well-set type
5. **Theater as metaphor** — Entrances and exits, dimming and revealing, the pause before the line
6. **Material honesty** — Surfaces reference leather, linen, brass, plaster, and parquet — never synthetic
7. **Oxblood restraint** — Reserve deep red for meaningful marks: featured content, errors, primary actions
8. **Stillness with presence** — Animations are slow, deliberate, like a door being opened by a doorman
9. **Brass as connective thread** — The warm metallic tone links elements like picture rail running through rooms
10. **Monogram as signature** — Small decorative moments — a diamond, an initial, a rule — mark quality without announcing it

> *"Money talks. Wealth whispers."* — Old New York proverb
