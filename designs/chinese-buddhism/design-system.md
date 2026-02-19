## UI Design System: Chinese Buddhism Style Theme

### Core Design Philosophy

Create an interface embodying **Chinese Buddhist temple aesthetics** and **Chan (禅) meditation principles** through the lens of eternal balance and meditative void. Inspired by incense smoke curling through lacquered halls, cinnabar seals pressed on sutras, and the warm glow of sandalwood interiors, UI components should feel like offerings arranged on an altar—deliberate, symmetrical, and reverent. The design honors **Ma** (間)—the contemplative emptiness between all things—as the foundational canvas upon which meaning appears.

**Guiding Principles:**
- **Zhongyong** (中庸) — The Doctrine of the Mean; perfect balance and centered harmony in all layouts
- **Kong** (空) — Emptiness; generous negative space as spiritual breathing room
- **Jing** (静) — Stillness; calm, unhurried interfaces that invite contemplation
- **Li** (礼) — Ritual propriety; every element placed with ceremonial intention
- **Yuan** (缘) — Interconnectedness; components relate to each other as parts of a whole
- **Shan** (善) — Virtue; design that serves the user with humility and clarity

---

### Color Palette

**Temple Tones (Primary Palette):**
- **Sandalwood**: `#C4A882` — warm temple wood, primary background tone
- **Deep Sandalwood**: `#A68B6B` — aged wood grain, secondary backgrounds
- **Cinnabar**: `#C83C2D` — vermillion red of temple pillars and seal ink, primary accent
- **Cinnabar Dark**: `#9E2E22` — deep cinnabar for pressed/active states
- **Temple Gold**: `#D4A843` — burnished gold of Buddha statues and border accents
- **Dark Lacquer**: `#2B1810` — lacquered wood, for primary text and deep anchors

**Ground Tones (Backgrounds):**
- **Rice Paper**: `#F5EDE0` — warm off-white of handmade paper, lightest background
- **Aged Parchment**: `#EDE4D3` — yellowed sutra pages, secondary background
- **Incense Ash**: `#D9CFC0` — soft gray-warm, tertiary background and borders
- **Temple Shadow**: `rgba(43, 24, 16, 0.04)` — atmospheric layering for depth

**Accent (Used Sparingly):**
- **Silk White**: `#FAF6EF` — luminous white of ceremonial silk, text on dark surfaces
- **Lotus Pink**: `#D4867C` — gentle lotus blossom, for soft highlights
- **Pine Green**: `#4A7A5E` — temple garden pine, for success states
- **Amber Warning**: `#C9943A` — prayer bead amber, for gentle warnings

**Material References:**
- Incense smoke haze: `rgba(196, 168, 130, 0.15)`
- Polished lacquer surface: `#3A1F14`
- Weathered bronze: `#8A7A5A`
- Temple gold leaf: `rgba(212, 168, 67, 0.85)`

---

### Typography

**Font Philosophy:** Text should feel like brushwork on sutra scrolls—deliberate, upright, and balanced. Each character carries weight and meaning. Prioritize vertical rhythm and centered alignment to echo the symmetry of temple architecture.

**Font Stack:**
```css
--font-primary: 'Noto Serif SC', 'Playfair Display', 'Songti SC', 'SimSun', serif;
--font-body: 'Noto Sans SC', 'Source Sans 3', -apple-system, 'Microsoft YaHei', sans-serif;
--font-mono: 'JetBrains Mono', 'SF Mono', monospace;
--font-decorative: 'Ma Shan Zheng', 'ZCOOL XiaoWei', cursive; /* For titles and seals */
```

**Type Scale:**
- **Display**: 28-32px, weight 400 (steady, like carved temple inscriptions)
- **Heading**: 20-24px, weight 500
- **Section title**: 14-16px, weight 600, `letter-spacing: 0.10em` (uppercase or small-caps)
- **Body**: 15-16px, weight 400, line-height 1.75
- **Small/Caption**: 12-13px, weight 400
- **Sutra whisper**: 11px, `letter-spacing: 0.06em`, muted warm tone

**Text Styling:**
- Generous line-height (1.75-1.85) for meditative reading pace
- Center-align headings to honor symmetry; body text left-aligned for readability
- Use color warmth hierarchy: darker lacquer tones = more important
- Occasional vertical text for decorative labels: `writing-mode: vertical-rl`
- Text color on light backgrounds: `#2B1810` (Dark Lacquer)
- Text color on dark backgrounds: `#FAF6EF` (Silk White)

---

### Component Patterns

#### Cards & Containers — *Temple Panels*

Inspired by lacquered wooden panels and sutra scroll housings. Clean rectangles with subtle ornamentation at corners, evoking carved wood frames:

```css
.card {
  background: #F5EDE0;
  border: 1px solid rgba(43, 24, 16, 0.08);
  border-radius: 4px;
  padding: 28px 32px;
  position: relative;
  box-shadow:
    0 2px 4px rgba(43, 24, 16, 0.03),
    0 8px 32px rgba(43, 24, 16, 0.05);
}

/* Red seal accent in top-right corner */
.card::after {
  content: '';
  position: absolute;
  top: 12px;
  right: 12px;
  width: 20px;
  height: 20px;
  background: #C83C2D;
  border-radius: 2px;
  opacity: 0.7;
  box-shadow: inset 0 0 0 1.5px rgba(250, 246, 239, 0.3);
}

.card-temple {
  background: linear-gradient(175deg, #F5EDE0 0%, #EDE4D3 100%);
  border: 1px solid rgba(212, 168, 67, 0.2);
  border-top: 2px solid #D4A843;
}

.card-scroll {
  background: #FAF6EF;
  border: none;
  border-left: 3px solid #C83C2D;
  border-right: 3px solid #C83C2D;
  padding: 32px 40px;
  box-shadow: 0 4px 24px rgba(43, 24, 16, 0.06);
}

/* Cloud watermark pattern overlay */
.card-cloud-watermark {
  position: relative;
  overflow: hidden;
}

.card-cloud-watermark::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 100'%3E%3Cpath d='M30 70 Q50 40 80 55 Q95 30 120 50 Q140 25 170 45 Q180 55 170 65 Q160 80 130 70 Q110 85 80 72 Q55 85 30 70Z' fill='none' stroke='%23C83C2D' stroke-width='0.5' opacity='0.06'/%3E%3C/svg%3E");
  background-size: 200px 100px;
  background-repeat: repeat;
  pointer-events: none;
  z-index: 0;
}
```

**Border Philosophy:**
- Favor clean rectangles with minimal radius (`2px-4px`)
- Symmetry is paramount; equal radius on all corners
- Gold top borders on elevated cards suggest temple roof eaves
- Red seal marks in corners provide subtle identity

**Depth & Shadow:**
- Shadows should feel like candlelight in a dim temple hall
- Warm-toned, diffused: `0 8px 32px rgba(43, 24, 16, 0.06)`
- Inner shadows for recessed altar-niche effects: `inset 0 2px 8px rgba(43, 24, 16, 0.04)`

---

#### Buttons & Interactive Elements — *Temple Seals*

```css
.button-primary {
  background: transparent;
  color: #C83C2D;
  border: 1.5px solid #D4A843;
  border-radius: 3px;
  padding: 12px 28px;
  font-weight: 500;
  letter-spacing: 0.06em;
  transition: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
  position: relative;
}

.button-primary:hover {
  background: #FAF6EF;
  color: #C83C2D;
  border-color: #D4A843;
  box-shadow: 0 2px 16px rgba(212, 168, 67, 0.2);
}

.button-primary:active {
  background: #EDE4D3;
  transform: scale(0.98);
}

.button-secondary {
  background: #C83C2D;
  color: #FAF6EF;
  border: none;
  border-radius: 3px;
  padding: 12px 28px;
  font-weight: 500;
  letter-spacing: 0.06em;
  transition: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
}

.button-secondary:hover {
  background: #9E2E22;
  box-shadow: 0 4px 20px rgba(200, 60, 45, 0.15);
}

.button-ghost {
  background: transparent;
  border: 1px solid rgba(43, 24, 16, 0.15);
  color: #2B1810;
  border-radius: 3px;
}

.button-ghost:hover {
  background: rgba(43, 24, 16, 0.03);
  border-color: rgba(43, 24, 16, 0.25);
}

.button-seal { /* Circular seal button for primary actions */
  background: #C83C2D;
  color: #FAF6EF;
  border: 2px solid #D4A843;
  border-radius: 50%;
  width: 52px;
  height: 52px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 12px rgba(200, 60, 45, 0.2);
}

.button-seal:hover {
  transform: rotate(5deg) scale(1.05);
  box-shadow: 0 4px 20px rgba(200, 60, 45, 0.25);
}
```

**Icon Buttons:**
- Circular seal forms or minimal rectangles
- Generous touch targets: 44px minimum
- Hover reveals incense-glow warmth: `background: rgba(212, 168, 67, 0.08)`

---

#### Form Elements — *Offering Inputs*

```css
.input {
  background: rgba(250, 246, 239, 0.6);
  border: none;
  border-bottom: 1.5px solid rgba(43, 24, 16, 0.12);
  padding: 12px 4px;
  font-size: 16px;
  color: #2B1810;
  transition: border-color 0.3s ease;
}

.input:focus {
  outline: none;
  border-bottom-color: #D4A843;
  box-shadow: 0 1px 0 0 #D4A843;
}

.input-enclosed {
  background: rgba(250, 246, 239, 0.8);
  border: 1px solid rgba(43, 24, 16, 0.08);
  border-radius: 3px;
  padding: 14px 20px;
}

.input-enclosed:focus {
  border-color: #D4A843;
  box-shadow: 0 0 0 3px rgba(212, 168, 67, 0.1);
}

.label {
  font-size: 12px;
  font-weight: 500;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #A68B6B;
  margin-bottom: 6px;
}

.checkbox {
  width: 22px;
  height: 22px;
  border: 1.5px solid rgba(43, 24, 16, 0.2);
  border-radius: 2px;
  accent-color: #C83C2D;
  /* Checkmark styled as a seal impression */
}

.checkbox:checked {
  background: #C83C2D;
  border-color: #C83C2D;
}

.select {
  background: rgba(250, 246, 239, 0.8);
  border: 1px solid rgba(43, 24, 16, 0.1);
  border-radius: 3px;
  padding: 12px 16px;
  color: #2B1810;
}
```

**Focus States — Incense Glow:**
- No harsh outlines
- Gold glow on focus: `box-shadow: 0 0 0 3px rgba(212, 168, 67, 0.12)`
- Border transitions from incense ash to temple gold

---

#### Status & Feedback — *Dharma Indicators*

```css
.badge {
  display: inline-flex;
  padding: 4px 14px;
  font-size: 11px;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  border-radius: 2px;
  background: rgba(43, 24, 16, 0.05);
  color: #2B1810;
}

.badge-critical {
  background: rgba(200, 60, 45, 0.08);
  color: #C83C2D;
  border-left: 2px solid #C83C2D;
}

.badge-success {
  background: rgba(74, 122, 94, 0.08);
  color: #4A7A5E;
  border-left: 2px solid #4A7A5E;
}

.badge-warning {
  background: rgba(201, 148, 58, 0.08);
  color: #C9943A;
  border-left: 2px solid #C9943A;
}

.badge-info {
  background: rgba(212, 168, 67, 0.08);
  color: #A68B6B;
  border-left: 2px solid #D4A843;
}

.progress-bar {
  height: 3px;
  background: rgba(43, 24, 16, 0.06);
  border-radius: 1.5px;
}

.progress-fill {
  background: linear-gradient(90deg, #D4A843, #C83C2D);
  border-radius: 1.5px;
  /* Gold to cinnabar: increasing devotion with progress */
}

.toast {
  background: #2B1810;
  color: #FAF6EF;
  border-left: 3px solid #D4A843;
  border-radius: 3px;
  padding: 16px 24px;
  box-shadow: 0 8px 32px rgba(43, 24, 16, 0.2);
}
```

---

### Layout Principles — *Ma (間) as Meditative Void*

**Spacing Scale:**
`4, 8, 16, 24, 32, 48, 64, 96, 128px`

Prefer larger spacings. Let elements breathe as if separated by the silence between temple bell strikes.

**Grid Philosophy:**
- **Centered, symmetrical** layouts over asymmetric arrangements
- Bilateral symmetry reflecting temple architecture
- Centered focal points — like a Buddha statue on the central axis
- Maximum content width: 720px for reading, 1120px for applications
- Significant side margins: minimum 64px on desktop

**Visual Weight Distribution:**
```
┌──────────────────────────────────┐
│                                  │
│            ◎                     │  <- Central element, like a main altar
│                                  │
│     ·              ·             │  <- Flanking elements, symmetrical like guardian lions
│                                  │
│   ─────────────────────────      │  <- Horizontal divider, like a temple threshold
│                                  │
│       ·      ◎      ·           │  <- Secondary grouping, balanced tripartite
│                                  │
└──────────────────────────────────┘
```

**Dividers & Separators:**
- Hair-thin lines with gold tint: `1px solid rgba(212, 168, 67, 0.15)`
- Or pure negative space — the void between breaths
- Occasional decorative cloud-motif SVG as section breaks
- Double-line separators for major sections: two `1px` lines with `4px` gap between

---

### Interaction Design — *Incense in Motion*

**Transition Timing:**
```css
--ease-temple: cubic-bezier(0.23, 1, 0.32, 1); /* Deliberate, balanced arrival */
--ease-incense: cubic-bezier(0.36, 0.66, 0.04, 1); /* Slow rise, gentle dissolve */
--ease-bell: cubic-bezier(0.19, 1, 0.22, 1); /* Strike and reverberate */
--duration-slow: 0.6s;
--duration-medium: 0.4s;
--duration-fast: 0.2s;
```

**Hover Philosophy:**
- Warm incense glow appears: `background: rgba(212, 168, 67, 0.05)`
- Gentle upward lift: `transform: translateY(-1px)` — offering rising like incense
- Never abrupt; always like smoke drifting upward

**Loading States:**
- Incense smoke curl — a single wisp spiraling upward
- Breath-like pulse synced to meditation rhythm (slow, 4-5s cycle)
- Prayer wheel rotation — subtle continuous spin

```css
@keyframes incense-breathe {
  0%, 100% { opacity: 0.4; transform: scale(1); }
  50% { opacity: 0.9; transform: scale(1.01); }
}

@keyframes incense-rise {
  0% { transform: translateY(0) scaleX(1); opacity: 0.6; }
  25% { transform: translateY(-8px) scaleX(0.95); opacity: 0.8; }
  50% { transform: translateY(-16px) scaleX(1.05); opacity: 0.5; }
  75% { transform: translateY(-24px) scaleX(0.9); opacity: 0.3; }
  100% { transform: translateY(-32px) scaleX(0.85); opacity: 0; }
}

@keyframes prayer-wheel {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

@keyframes bell-strike {
  0% { transform: scale(1); opacity: 1; }
  10% { transform: scale(1.03); }
  100% { transform: scale(1); opacity: 0.8; }
}

@keyframes seal-stamp {
  0% { transform: scale(1.2); opacity: 0; }
  50% { transform: scale(0.95); opacity: 1; }
  100% { transform: scale(1); opacity: 1; }
}
```

---

### Texture & Material References

**Temple Textures:**
- Subtle rice paper grain overlay: `opacity: 0.03`
- Warm sandalwood surface micro-variation on backgrounds
- Cloud-motif SVG watermarks for decorative depth (very faint)

**Buddhism-Inspired Patterns:**
- Incense haze: soft warm radial gradients for modals/overlays
- Polished lacquer surface: deep warm darks with slight reflection
- Carved wood grain: subtle linear texture on sidebars and navigation

```css
.incense-haze {
  background: radial-gradient(ellipse at center,
    rgba(250, 246, 239, 0.97) 0%,
    rgba(237, 228, 211, 0.90) 60%,
    rgba(217, 207, 192, 0.80) 100%);
}

.lacquer-surface {
  background: linear-gradient(180deg, #3A1F14 0%, #2B1810 100%);
  box-shadow: inset 0 1px 0 rgba(212, 168, 67, 0.1);
}

.rice-paper-texture {
  background-color: #F5EDE0;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='4' height='4'%3E%3Crect width='4' height='4' fill='%23F5EDE0'/%3E%3Crect width='1' height='1' x='1' y='1' fill='%23EDE4D3' opacity='0.3'/%3E%3C/svg%3E");
  background-size: 4px 4px;
}

.cloud-border {
  /* Decorative cloud motif bottom border */
  border-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 20'%3E%3Cpath d='M0 15 Q25 5 50 12 Q70 3 100 10 Q130 2 150 12 Q175 5 200 15' fill='none' stroke='%23D4A843' stroke-width='1' opacity='0.3'/%3E%3C/svg%3E") 0 0 10 0 / 0 0 10px 0 stretch;
}

.red-seal {
  /* Small square cinnabar seal decoration */
  display: inline-block;
  width: 24px;
  height: 24px;
  background: #C83C2D;
  border-radius: 2px;
  box-shadow:
    inset 0 0 0 2px rgba(250, 246, 239, 0.25),
    0 1px 4px rgba(200, 60, 45, 0.3);
  opacity: 0.8;
}
```

---

### Iconography — *Dharma Wheel Strokes*

- Stroke-based icons, weight 1.5-2px
- Clean, geometric forms preferred — reflecting Buddhist sacred geometry
- Balanced, symmetrical where possible — honoring the Middle Way
- Icon size: 18-24px inline, 28-32px standalone

**Style Reference:**
```
Standard:  ▢ ◯ △
Temple:    ◎ ☸ ◇  (centered, balanced, geometric)
```

Consider icons that feel carved or stamped:
- Even stroke weight throughout, like carved inscription
- Clean endpoints, like chiseled stone
- Symmetrical, centered forms echoing mandala geometry
- Occasional use of the endless knot motif for decorative moments

---

### Meditative Character Details

1. **Symmetrical borders**: Equal widths on all sides — balance above all
2. **Gold thread accents**: `border-top: 1px solid rgba(212, 168, 67, 0.3)` — gold leaf applied to surfaces
3. **Warm paper textures**: Sandalwood undertones in all white spaces — aged sutra warmth
4. **Seal stamp decorations**: Small cinnabar squares in card corners — artist's chop mark
5. **Cloud watermark patterns**: Faint repeating cloud SVG behind content — auspicious clouds
6. **Centered compositions**: Headings and hero elements always center-aligned — temple axis
7. **Incense shadow warmth**: Shadows tinted warm, never cool — `rgba(43, 24, 16, 0.05)` not blue-gray
8. **Deliberate rhythm**: Consistent vertical spacing creates a chanting cadence

---

### Recommended shadcn/ui Components

**Base Theme:** `theme-stone` — closest match for warm, earthy temple tones. Override CSS variables to shift from cool stone to warm sandalwood.

```css
/* theme-stone overrides for Chinese Buddhism palette */
:root {
  --background: 35 30% 92%;       /* #F5EDE0 Rice Paper */
  --foreground: 16 42% 13%;       /* #2B1810 Dark Lacquer */
  --card: 35 28% 88%;             /* #EDE4D3 Aged Parchment */
  --card-foreground: 16 42% 13%;  /* #2B1810 Dark Lacquer */
  --primary: 5 66% 48%;           /* #C83C2D Cinnabar */
  --primary-foreground: 36 52% 95%; /* #FAF6EF Silk White */
  --secondary: 35 24% 80%;        /* #D9CFC0 Incense Ash */
  --secondary-foreground: 16 42% 13%; /* #2B1810 Dark Lacquer */
  --accent: 40 55% 55%;           /* #D4A843 Temple Gold */
  --accent-foreground: 16 42% 13%; /* #2B1810 Dark Lacquer */
  --muted: 35 20% 82%;            /* Incense Ash lighter */
  --muted-foreground: 30 18% 53%; /* #A68B6B Deep Sandalwood */
  --destructive: 5 66% 48%;       /* #C83C2D Cinnabar */
  --destructive-foreground: 36 52% 95%;
  --border: 30 15% 80%;           /* Warm border tone */
  --input: 30 15% 80%;
  --ring: 40 55% 55%;             /* Temple Gold ring */
  --radius: 0.2rem;               /* Minimal radius: clean temple geometry */
}

.dark {
  --background: 16 42% 13%;       /* #2B1810 Dark Lacquer */
  --foreground: 36 52% 95%;       /* #FAF6EF Silk White */
  --card: 16 38% 16%;             /* Slightly lighter lacquer */
  --card-foreground: 36 52% 95%;
  --primary: 5 66% 48%;           /* #C83C2D Cinnabar */
  --primary-foreground: 36 52% 95%;
  --secondary: 16 30% 22%;        /* Dark temple wood */
  --secondary-foreground: 36 52% 95%;
  --accent: 40 55% 55%;           /* #D4A843 Temple Gold */
  --accent-foreground: 36 52% 95%;
  --muted: 16 25% 20%;
  --muted-foreground: 35 18% 65%;
  --border: 16 20% 25%;
  --input: 16 20% 25%;
  --ring: 40 55% 55%;
}
```

Below are the 22 most relevant components for this theme, with specific styling guidance:

---

#### 1. **Button** (`@shadcn/button`)
The seal-stamp of user intent. Gold borders with cinnabar text; hover reveals silk-white fill.
```css
/* Default variant */
.btn { border: 1.5px solid hsl(var(--accent)); color: hsl(var(--primary)); border-radius: 3px; }
.btn:hover { background: hsl(var(--primary-foreground)); box-shadow: 0 2px 16px rgba(212,168,67,0.2); }
/* Destructive variant uses deeper cinnabar */
/* Ghost variant: transparent with warm hover glow */
```

#### 2. **Card** (`@shadcn/card`)
Temple panel with red seal accent. Add `::after` pseudo-element for the cinnabar corner seal. Use `border-top: 2px solid hsl(var(--accent))` for the gold eave line. Cloud watermark as optional background pattern.

#### 3. **Dialog** (`@shadcn/dialog`)
Temple gate opening. Overlay uses `incense-haze` radial gradient instead of flat backdrop. Content panel styled as a scroll: cinnabar left/right borders, rice paper background. Entry animation uses `seal-stamp` keyframes.

#### 4. **Navigation Menu** (`@shadcn/navigation-menu`)
Temple corridor wayfinding. Horizontal layout, centered alignment. Active item marked with a small cinnabar dot below (like a seal) rather than underline. Gold separator dots between items. Dropdown panels use the `card-temple` style.

#### 5. **Sidebar** (`@shadcn/sidebar`)
Lacquered wooden panel. Use `lacquer-surface` dark background. Menu items in Silk White, active item highlighted with a subtle gold left border (`3px solid hsl(var(--accent))`). Section headers in small-caps with `letter-spacing: 0.10em`.

#### 6. **Tabs** (`@shadcn/tabs`)
Sutra scroll tabs. Active tab receives a cinnabar bottom border (`2px solid hsl(var(--primary))`). Inactive tabs in Deep Sandalwood tone. Tab content area uses rice paper background with subtle top shadow.

#### 7. **Accordion** (`@shadcn/accordion`)
Folding sutra panels. Trigger text in Dark Lacquer, chevron icon replaced conceptually with a lotus or simple plus in Temple Gold. Expanded content has a faint left border in cinnabar. Smooth `--ease-temple` transition on open/close.

#### 8. **Input** (`@shadcn/input`)
Offering field. Bottom-border-only style by default. Focus state transitions border from Incense Ash to Temple Gold. Background on focus: faint rice paper warmth `rgba(250,246,239,0.6)`.

#### 9. **Select** (`@shadcn/select`)
Dharma wheel selector. Trigger styled with gold bottom border. Dropdown content uses Aged Parchment background. Selected item marked with a small cinnabar dot to the left.

#### 10. **Badge** (`@shadcn/badge`)
Sutra classification tags. Minimal rectangular shape (`border-radius: 2px`). Left-border colored accent for variant distinction (cinnabar for critical, pine green for success, amber for warning). Background uses `0.08` opacity of the accent color.

#### 11. **Alert / Alert Dialog** (`@shadcn/alert`, `@shadcn/alert-dialog`)
Temple bell notification. Left border in cinnabar for errors, Temple Gold for info. Background warmer than default — use Aged Parchment. Alert Dialog overlay uses incense-haze gradient.

#### 12. **Separator** (`@shadcn/separator`)
Temple threshold. Default: `1px solid rgba(212,168,67,0.15)` (gold-tinted). For major sections, use double-line style (two parallel `1px` lines with `4px` gap). Optional cloud-border SVG for decorative section breaks.

#### 13. **Form / Field / Label** (`@shadcn/form`, `@shadcn/field`, `@shadcn/label`)
Ritual offering arrangement. Labels in uppercase small text with Deep Sandalwood color and wide letter-spacing. Error messages in Cinnabar. Success validation in Pine Green. Form groups maintain generous vertical spacing (`24px` minimum between fields).

#### 14. **Avatar** (`@shadcn/avatar`)
Rounded with a thin gold border (`1.5px solid hsl(var(--accent))`). Fallback background in Cinnabar with Silk White initials. Suggest circular shape to echo dharma wheel.

#### 15. **Tooltip** (`@shadcn/tooltip`)
Whispered sutra guidance. Dark Lacquer background, Silk White text. Minimal `border-radius: 3px`. Small arrow. Subtle warm shadow. Entry animation: fade in with slight upward drift.

#### 16. **Progress** (`@shadcn/progress`)
Path to enlightenment. Track in Incense Ash (`rgba(43,24,16,0.06)`). Fill uses gradient from Temple Gold to Cinnabar (`linear-gradient(90deg, #D4A843, #C83C2D)`). Height `3px` — thin and deliberate.

#### 17. **Switch** (`@shadcn/switch`)
Yin-yang toggle. Unchecked track in Incense Ash. Checked track in Cinnabar. Thumb in Silk White with subtle warm shadow. Transition timing uses `--ease-temple`.

#### 18. **Table** (`@shadcn/table`)
Sutra registry. Header row uses Aged Parchment background with uppercase small-caps text. Row borders in faint gold (`rgba(212,168,67,0.1)`). Alternating row backgrounds: Rice Paper and transparent. Hover highlight with incense glow.

#### 19. **Scroll Area** (`@shadcn/scroll-area`)
Scrollbar thumb in Deep Sandalwood, track invisible. Thumb on hover shifts to Cinnabar. Thin scrollbar width (`6px`). Smooth kinetic scrolling.

#### 20. **Sonner / Toast** (`@shadcn/sonner`)
Temple bell echo. Dark Lacquer background with gold left border. Text in Silk White. Entry animation slides up with `--ease-bell`. Auto-dismiss timing generous (5s) — no rushing the bell's fade.

#### 21. **Skeleton** (`@shadcn/skeleton`)
Meditation waiting state. Pulse animation uses `incense-breathe` keyframes. Color oscillates between Incense Ash and Aged Parchment — warm, never cool gray.

#### 22. **Dropdown Menu / Context Menu** (`@shadcn/dropdown-menu`, `@shadcn/context-menu`)
Offering selection. Background in Rice Paper. Items on hover gain incense glow (`rgba(212,168,67,0.08)`). Separator lines in faint gold. Active/selected items get a small cinnabar left indicator.

---

**Block Pattern Recommendations:**

| Pattern | Theme Application |
|---------|-------------------|
| `dashboard-01` | Central altar layout; gold-bordered stat cards with seal accents; cinnabar highlight for key metrics |
| `sidebar-01` | Lacquered panel sidebar with Silk White menu text on Dark Lacquer background |
| `sidebar-07` | Floating sidebar variant; warm shadow, gold header accent |
| `login-01` | Centered, symmetrical login; card-scroll style with cinnabar borders; seal icon as logo mark |
| `login-03` | Split layout; left panel as lacquer surface with gold calligraphy; right panel as rice paper form |

---

### Key Design Principles Summary

1. **Ma (間) as Meditative Void** — Generous negative space is the silence between bell strikes; elements exist within emptiness
2. **Symmetry over asymmetry** — Centered compositions reflect temple architecture and the balanced Middle Way
3. **Warmth hierarchy** — Darker lacquer tones = more important; lighter parchment tones recede
4. **Temple geometry** — Clean rectangles and minimal radii; components feel carved from wood, not molded from plastic
5. **Material honesty** — Surfaces reference sandalwood, lacquer, rice paper, and bronze — never synthetic
6. **Cinnabar restraint** — Reserve red for meaningful marks: seals, alerts, primary actions. Overuse cheapens its power
7. **Stillness** — Animations are slow, incense-like, meditative. Never frantic or bouncy
8. **Gold as sacred thread** — Temple Gold connects elements like the golden thread in a sutra binding
9. **Seal as signature** — Small cinnabar squares in corners function as the artisan's identity mark on every component
10. **Incense softness** — Overlays and modals glow warmly like candlelight through incense smoke, never cold or harsh

---

*"In the midst of all things, find the stillness; in the stillness, find the way."* — Chan Buddhist proverb
