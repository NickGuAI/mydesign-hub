## UI Design System: Classic Japanese Mythology Theme

### Core Design Philosophy

Create an interface embodying **Ukiyo-e aesthetics** and **spirit world elegance** through the lens of **Japanese mythology**---the realm where kami dwell, torii gates mark the threshold between worlds, and indigo waves crash beneath sacred peaks. Inspired by Utagawa Hiroshige's landscapes, Hokusai's Great Wave, and the vermillion architecture of Fushimi Inari, UI components should feel like woodblock prints pressed onto washi paper---bold outlines, flat color planes, and deliberate negative space. The design honors **yogen** (the awareness of the universe that triggers emotional responses too deep for words) as the guiding spiritual force behind every interaction.

**Guiding Principles:**
- **Shinpi** (神秘) --- Mystery, the unseen world behind the torii gate
- **Fukinsei** (不均整) --- Asymmetry, as found in the irregular placement of shrine stones
- **Iki** (粋) --- Refined sophistication, the Edo-period sense of understated coolness
- **Kurai** (暗い) --- Darkness with depth, the midnight pine forests where spirits gather
- **Rei** (霊) --- Spirit presence, ethereal luminosity breaking through shadow
- **Chikara** (力) --- Power and authority, the commanding presence of a vermillion torii

---

### Color Palette

**Spirit World Darks (Primary Palette):**
- **Midnight Pine**: `#0D1B1E` --- the deepest forest at midnight, primary background and anchor
- **Shadow Bamboo**: `#152A2E` --- elevated surfaces, card backgrounds within the forest
- **Shrine Stone**: `#2A3D42` --- tertiary surfaces, borders, and muted structural elements
- **Spirit Mist**: `#4A6670` --- secondary text, disabled states, distant mountainsides
- **Frozen Moss**: `#6A8A8F` --- placeholder text, subtle dividers, weathered surfaces

**Vermillion & Warmth (Action Palette):**
- **Vermillion Torii**: `#D43B2F` --- primary brand color, the sacred gate between worlds
- **Lantern Glow**: `#E85D3A` --- hover states, warm interactions, festival lantern light
- **Ember Ash**: `#9A2A20` --- pressed/active states, deepened vermillion
- **Shrine Candle**: `#F0A868` --- gentle warnings, warm highlights, candlelight flicker

**Deep Indigo (Interactive Palette):**
- **Deep Indigo Wave**: `#1B3A6B` --- primary action buttons, links, interactive elements
- **Aizome Blue**: `#2A5298` --- hover states on indigo, traditional dye-vat blue
- **Storm Indigo**: `#0F2847` --- pressed states, the deepest part of the wave
- **Pale Indigo**: `#3A6BC5` --- focus rings, active indicators

**Sacred Whites & Frost (Light Accents):**
- **Frosted Fuji**: `#C8D8E8` --- accent highlights, frost on the sacred peak
- **Cloud Paper**: `#E8ECF0` --- primary text color on dark backgrounds
- **Washi Cream**: `#F0EDE6` --- secondary text, softer reading tone
- **Moonlit Snow**: `rgba(200, 216, 232, 0.12)` --- atmospheric layering, spirit glow

**Material References:**
- Spirit barrier glow: `rgba(212, 59, 47, 0.15)`
- Indigo ink wash: `rgba(27, 58, 107, 0.6)`
- Moonlight on shrine wood: `rgba(200, 216, 232, 0.08)`
- Washi paper grain overlay: `rgba(240, 237, 230, 0.03)`

---

### Typography

**Font Philosophy:** Text should feel like characters carved by a master calligrapher---deliberate strokes, confident weight, and the authority of ancient scrolls. Headings carry the gravitas of shrine inscriptions; body text flows like a storyteller's narration of old legends.

**Font Stack:**
```css
--font-primary: 'Noto Serif JP', 'Hiragino Mincho Pro', 'Yu Mincho', serif;
--font-body: 'Noto Sans JP', 'Hiragino Kaku Gothic Pro', -apple-system, sans-serif;
--font-mono: 'JetBrains Mono', 'SF Mono', monospace;
--font-display: 'Shippori Mincho', 'Noto Serif JP', serif;
```

**Type Scale:**
- **Display**: 30-36px, weight 700 (bold, like shrine gate inscriptions)
- **Heading**: 22-26px, weight 600
- **Section title**: 13-15px, weight 600, `letter-spacing: 0.14em` (uppercase, carved stone feel)
- **Body**: 15-16px, weight 400, line-height 1.75
- **Small/Caption**: 12-13px, weight 400
- **Whisper**: 11px, `letter-spacing: 0.1em`, spirit-mist tone

**Text Styling:**
- Generous line-height (1.7-1.8) for scroll-like readability
- Use weight hierarchy deliberately: 700 for display, 600 for headings, 400 for body
- Vertical text option for decorative labels: `writing-mode: vertical-rl`
- Color depth creates emphasis: Cloud Paper for primary, Frosted Fuji for secondary, Spirit Mist for tertiary
- Occasional `text-shadow: 0 0 20px rgba(212, 59, 47, 0.3)` for sacred/important text

---

### Component Patterns

#### Cards & Containers --- *Washi Scrolls*

Inspired by washi paper screens, painted scrolls, and the layered architecture of shrine buildings:

```css
.card {
  background: #152A2E;
  border: 1px solid rgba(200, 216, 232, 0.06);
  border-radius: 2px;
  padding: 28px 32px;
  position: relative;
  box-shadow:
    0 2px 8px rgba(0, 0, 0, 0.3),
    0 12px 40px rgba(0, 0, 0, 0.15);
}

/* Washi paper grain texture overlay */
.card::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events: none;
  mix-blend-mode: overlay;
}

.card-shrine {
  border-left: 3px solid #D43B2F; /* Vermillion shrine pillar accent */
  background: linear-gradient(170deg, #152A2E 0%, #0D1B1E 100%);
}

.card-scroll {
  background: linear-gradient(180deg, #1A2F34 0%, #152A2E 50%, #0D1B1E 100%);
  border: 1px solid rgba(200, 216, 232, 0.04);
  border-top: 2px solid rgba(200, 216, 232, 0.1); /* Scroll rod top edge */
  border-bottom: 2px solid rgba(200, 216, 232, 0.1); /* Scroll rod bottom edge */
}

.card-spirit {
  background: #152A2E;
  box-shadow:
    0 0 30px rgba(27, 58, 107, 0.1),
    0 0 60px rgba(212, 59, 47, 0.04);
  /* Ethereal spirit world glow */
}
```

**Border Philosophy:**
- Sharp, deliberate corners (2-4px radius) reflecting woodblock precision
- Occasional shrine-pillar left border accent in vermillion
- Reference the clean geometry of torii gate construction

**Depth & Shadow:**
- Shadows are deep and atmospheric, like moonlight through pines
- Layered: `0 4px 16px rgba(0, 0, 0, 0.25), 0 1px 3px rgba(0, 0, 0, 0.15)`
- Spirit glow for highlighted cards: `0 0 40px rgba(27, 58, 107, 0.08)`

---

#### Buttons & Interactive Elements --- *Torii Gates*

```css
.button-primary {
  background: #1B3A6B;
  color: #E8ECF0;
  border: none;
  border-radius: 2px;
  padding: 12px 28px;
  font-weight: 500;
  letter-spacing: 0.05em;
  transition: all 0.35s cubic-bezier(0.23, 1, 0.32, 1);
  position: relative;
  overflow: hidden;
}

.button-primary::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 2px;
  background: #D43B2F;
  transform: scaleX(0);
  transition: transform 0.35s cubic-bezier(0.23, 1, 0.32, 1);
}

.button-primary:hover {
  background: #2A5298;
  transform: translateY(-1px);
  box-shadow: 0 4px 20px rgba(27, 58, 107, 0.3);
}

.button-primary:hover::after {
  transform: scaleX(1); /* Vermillion underline reveals on hover */
}

.button-primary:active {
  background: #0F2847;
  transform: translateY(0);
}

.button-vermillion {
  background: #D43B2F;
  color: #E8ECF0;
  border-radius: 2px;
}

.button-vermillion:hover {
  background: #E85D3A;
  box-shadow: 0 4px 24px rgba(212, 59, 47, 0.25);
}

.button-ghost {
  background: transparent;
  border: 1px solid rgba(200, 216, 232, 0.15);
  color: #C8D8E8;
}

.button-ghost:hover {
  background: rgba(200, 216, 232, 0.05);
  border-color: rgba(200, 216, 232, 0.25);
}

.button-seal { /* Mon-style circular action button */
  background: #D43B2F;
  border: 2px solid rgba(200, 216, 232, 0.1);
  border-radius: 50%;
  width: 52px;
  height: 52px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 0 20px rgba(212, 59, 47, 0.2);
}

.button-seal:hover {
  box-shadow: 0 0 30px rgba(212, 59, 47, 0.35);
  transform: scale(1.05);
}
```

**Icon Buttons:**
- Circular mon (emblem) style for icon-only actions
- Generous touch targets: 44px minimum
- Hover reveals spirit glow: `box-shadow: 0 0 16px rgba(27, 58, 107, 0.15)`

---

#### Form Elements --- *Ink Stone Inputs*

```css
.input {
  background: rgba(200, 216, 232, 0.04);
  border: 1px solid rgba(200, 216, 232, 0.1);
  border-radius: 2px;
  padding: 12px 16px;
  font-size: 15px;
  color: #E8ECF0;
  transition: all 0.3s cubic-bezier(0.23, 1, 0.32, 1);
}

.input::placeholder {
  color: #4A6670;
  font-style: italic;
}

.input:focus {
  outline: none;
  border-color: #1B3A6B;
  box-shadow: 0 0 0 3px rgba(27, 58, 107, 0.2);
  background: rgba(200, 216, 232, 0.06);
}

.input:focus.vermillion-accent {
  border-color: #D43B2F;
  box-shadow: 0 0 0 3px rgba(212, 59, 47, 0.12);
}

.input-underline {
  background: transparent;
  border: none;
  border-bottom: 1px solid rgba(200, 216, 232, 0.12);
  border-radius: 0;
  padding: 12px 0;
}

.input-underline:focus {
  border-bottom-color: #D43B2F;
  box-shadow: none;
}

.checkbox {
  width: 20px;
  height: 20px;
  border: 1.5px solid rgba(200, 216, 232, 0.2);
  border-radius: 2px;
  background: rgba(200, 216, 232, 0.04);
  /* Checked state uses vermillion fill with white check */
}

.checkbox:checked {
  background: #D43B2F;
  border-color: #D43B2F;
}

.select {
  background: rgba(200, 216, 232, 0.04);
  border: 1px solid rgba(200, 216, 232, 0.1);
  border-radius: 2px;
  color: #E8ECF0;
}
```

**Focus States --- Spirit Barrier:**
- Indigo glow ring: `box-shadow: 0 0 0 3px rgba(27, 58, 107, 0.2)`
- Vermillion variant for primary actions: `box-shadow: 0 0 0 3px rgba(212, 59, 47, 0.12)`
- Border transitions from shadow to illuminated

---

#### Status & Feedback --- *Mon Emblems*

```css
.badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 4px 14px;
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  border-radius: 100px; /* Circular mon shape */
  background: rgba(200, 216, 232, 0.08);
  color: #C8D8E8;
}

.badge-icon {
  width: 28px;
  height: 28px;
  border-radius: 50%;
  padding: 0;
  font-size: 14px;
  /* Pure mon emblem --- circular with centered icon */
}

.badge-critical {
  background: rgba(212, 59, 47, 0.12);
  color: #E85D3A;
  border: 1px solid rgba(212, 59, 47, 0.2);
}

.badge-success {
  background: rgba(76, 145, 100, 0.12);
  color: #5AB878;
  border: 1px solid rgba(76, 145, 100, 0.2);
}

.badge-warning {
  background: rgba(240, 168, 104, 0.12);
  color: #F0A868;
  border: 1px solid rgba(240, 168, 104, 0.2);
}

.badge-indigo {
  background: rgba(27, 58, 107, 0.15);
  color: #6A9ADB;
  border: 1px solid rgba(27, 58, 107, 0.25);
}

.progress-bar {
  height: 4px;
  background: rgba(200, 216, 232, 0.06);
  border-radius: 2px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #1B3A6B, #D43B2F);
  border-radius: 2px;
  transition: width 0.6s cubic-bezier(0.23, 1, 0.32, 1);
  /* Indigo to vermillion: crossing the torii threshold */
}

.toast {
  background: #1A2F34;
  border: 1px solid rgba(200, 216, 232, 0.08);
  border-left: 3px solid #1B3A6B;
  border-radius: 2px;
  color: #E8ECF0;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
}

.toast-error {
  border-left-color: #D43B2F;
}

.toast-success {
  border-left-color: #5AB878;
}
```

---

### Layout Principles --- *Shrine Architecture*

**Spacing Scale:**
`4, 8, 12, 16, 24, 32, 48, 64, 96, 128px`

Use deliberate, structured spacing. Elements should be placed with the intentionality of shrine architecture---every pillar, every beam has purpose and precise placement.

**Grid Philosophy:**
- Structured asymmetry: primary content offset, secondary content balances
- Reference the layered depth of shrine halls (foreground, middle, background)
- Torii gate framing: key content areas bracketed by strong vertical elements
- Maximum content width: 720px for reading, 1200px for applications

**Visual Weight Distribution:**
```
+------------------------------+
|                              |
|  [===]                       |  <- Torii gate header, strong horizontal bar
|    |            |            |
|    |   +------+ |            |  <- Content panels like shrine rooms
|    |   |      | |     .      |  <- Secondary element, floating lantern
|    |   +------+ |            |
|    |            |            |
|  __|____________|__________  |  <- Stone foundation base
+------------------------------+
```

**Dividers & Separators:**
- Thin structural lines: `1px solid rgba(200, 216, 232, 0.06)`
- Vermillion accent dividers for section breaks: `1px solid rgba(212, 59, 47, 0.2)`
- Torii-gate-inspired double-line separator using `border-top` + `border-bottom` with gap
- Generous spacing above/below (32-48px) to create breathing room

---

### Interaction Design --- *Spirits in Motion*

**Transition Timing:**
```css
--ease-spirit: cubic-bezier(0.23, 1, 0.32, 1);  /* Ethereal float */
--ease-power: cubic-bezier(0.19, 1, 0.22, 1);   /* Decisive, authoritative */
--ease-flicker: cubic-bezier(0.36, 0.66, 0.04, 1); /* Lantern flame */
--duration-slow: 0.5s;    /* Spirit manifestation */
--duration-medium: 0.35s;  /* Standard interaction */
--duration-fast: 0.2s;     /* Immediate response */
--duration-ritual: 0.8s;   /* Ceremonial transitions */
```

**Hover Philosophy:**
- Spirit glow appears: `box-shadow: 0 0 20px rgba(27, 58, 107, 0.1)`
- Gentle ascension: `transform: translateY(-2px)`
- Vermillion reveals itself on interaction (hidden accent lines, border colors shifting)
- Never sudden; always a gradual manifestation, like a kami making its presence known

**Loading States:**
- Torii gate materializing from mist (fade-in with vertical lines appearing)
- Lantern flame pulse: warm glow cycling at 2-3s interval
- Ink brush stroke drawing across the screen (progress indication)
- Spirit orb floating in a gentle figure-eight path

```css
@keyframes lantern-pulse {
  0%, 100% {
    opacity: 0.5;
    box-shadow: 0 0 15px rgba(212, 59, 47, 0.15);
  }
  50% {
    opacity: 1;
    box-shadow: 0 0 30px rgba(212, 59, 47, 0.3);
  }
}

@keyframes spirit-manifest {
  0% {
    opacity: 0;
    transform: translateY(8px) scale(0.98);
    filter: blur(4px);
  }
  100% {
    opacity: 1;
    transform: translateY(0) scale(1);
    filter: blur(0);
  }
}

@keyframes torii-reveal {
  0% {
    clip-path: inset(0 50% 0 50%);
    opacity: 0;
  }
  60% {
    clip-path: inset(0 5% 0 5%);
    opacity: 0.7;
  }
  100% {
    clip-path: inset(0 0 0 0);
    opacity: 1;
  }
}

@keyframes ink-stroke {
  0% {
    stroke-dashoffset: 100%;
    opacity: 0.4;
  }
  100% {
    stroke-dashoffset: 0%;
    opacity: 1;
  }
}

@keyframes spirit-orb {
  0%, 100% {
    transform: translate(0, 0);
    opacity: 0.6;
  }
  25% {
    transform: translate(6px, -8px);
    opacity: 1;
  }
  50% {
    transform: translate(0, -4px);
    opacity: 0.8;
  }
  75% {
    transform: translate(-6px, -8px);
    opacity: 1;
  }
}
```

---

### Texture & Material References

**Washi Paper Texture:**
- Subtle grain overlay on all cards and containers: `opacity: 0.03`
- Cool, dark undertone paper feel on backgrounds
- Use CSS noise filters or SVG `feTurbulence` for organic grain

**Spirit World Atmospheric Effects:**
- Shrine lantern glow: warm radial gradients for modals and overlays
- Pine forest depth: layered dark gradients creating dimensional backgrounds
- Mist/fog: soft horizontal gradients at container edges
- Moonlight through clouds: subtle light patches on elevated surfaces

```css
.spirit-glow {
  background: radial-gradient(ellipse at 30% 40%,
    rgba(212, 59, 47, 0.06) 0%,
    rgba(27, 58, 107, 0.04) 40%,
    transparent 70%);
}

.moonlight-patch {
  background: radial-gradient(ellipse at center,
    rgba(200, 216, 232, 0.06) 0%,
    transparent 60%);
}

.pine-forest-depth {
  background:
    linear-gradient(180deg,
      rgba(13, 27, 30, 0) 0%,
      rgba(13, 27, 30, 0.8) 100%),
    linear-gradient(90deg,
      rgba(21, 42, 46, 0.5) 0%,
      rgba(13, 27, 30, 0.3) 50%,
      rgba(21, 42, 46, 0.5) 100%);
}

.washi-grain {
  position: relative;
}

.washi-grain::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='grain'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23grain)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events: none;
  mix-blend-mode: overlay;
  border-radius: inherit;
}

.mist-edge {
  mask-image: linear-gradient(
    to bottom,
    black 0%,
    black 85%,
    transparent 100%
  );
}
```

---

### Iconography --- *Mon Crests & Brush Marks*

- Stroke-based icons, weight 1.5-2px
- Clean geometric forms inspired by family crests (kamon)
- Circular framing for standalone icons (mon-style)
- Icon size: 18-24px inline, 28-36px standalone, 48px for primary actions

**Style Reference:**
```
Standard:  [ ] ( ) < >
Mythology: [鳥] (月) <波>  (torii, moon, wave --- bold, emblematic)
```

Consider icons that feel woodblock-carved:
- Consistent stroke weight, deliberate and authoritative
- Geometric precision with occasional organic curves for natural forms
- Enclosed forms (circles, hexagons) preferred for badges and status
- Vermillion color reserved for active/important icon states
- Cloud Paper (`#E8ECF0`) for default icon color on dark backgrounds

**Recommended Icon Families:**
- Lucide icons (stroke-based, clean geometry) as primary set
- Custom SVG mon-style icons for brand-specific elements
- Tabler icons as fallback for broader coverage

---

### Spirit World Character Details

1. **Vermillion threshold accents**: Left borders, underlines, and hover reveals---the torii gate marking the sacred boundary, appearing when interaction crosses a threshold
2. **Washi grain texture**: Subtle noise overlay on all surfaces---the handmade paper that holds centuries of ink and prayer
3. **Deep atmospheric shadows**: Layered, dark, diffused---the pine forest at midnight where spirits dwell between the trees
4. **Mon-style badges**: Circular emblems with high-contrast centered icons---family crests declaring allegiance and status
5. **Indigo-to-vermillion gradients**: Progress and transformation use this spectrum---crossing from the mortal world (indigo calm) into the spirit realm (vermillion power)
6. **Moonlight illumination**: Elevated surfaces catch subtle light---the moon breaking through clouds to illuminate a shrine clearing
7. **Deliberate geometry with organic exceptions**: Sharp 2px corners as the rule, organic curves as the exception---the precision of shrine carpentry meeting the wildness of sacred forests
8. **Mist dissolution at edges**: Content fading at boundaries using mask gradients---the ever-present mist that blurs the line between worlds

---

### Recommended shadcn/ui Components

Map of the 22 most relevant shadcn/ui components for this theme, with specific styling overrides:

**Base Theme:** `theme-slate` (closest match; override with Midnight Pine dark palette)

---

**1. Card**
- Background: `#152A2E` with washi grain `::before` overlay
- Border: `1px solid rgba(200, 216, 232, 0.06)`
- Border-radius: `2px`
- Variant: `.card-shrine` with `border-left: 3px solid #D43B2F`
- Box-shadow: `0 2px 8px rgba(0, 0, 0, 0.3), 0 12px 40px rgba(0, 0, 0, 0.15)`

**2. Button**
- Primary: Indigo `#1B3A6B` background, `#E8ECF0` text, 2px radius
- Destructive: Vermillion `#D43B2F` background
- Ghost: transparent with `rgba(200, 216, 232, 0.15)` border
- All variants: `letter-spacing: 0.05em`, `font-weight: 500`
- Hover: vermillion underline `::after` pseudo-element reveals via `scaleX`
- Active: darker shade, no translateY

**3. Badge**
- Shape: `border-radius: 100px` (circular mon form)
- Default: `rgba(200, 216, 232, 0.08)` background, `#C8D8E8` text
- Destructive: `rgba(212, 59, 47, 0.12)` with `#E85D3A` text
- Weight: `font-weight: 600`, `letter-spacing: 0.1em`
- Add `1px solid` border in matching translucent color for each variant

**4. Input**
- Background: `rgba(200, 216, 232, 0.04)`
- Border: `1px solid rgba(200, 216, 232, 0.1)`, radius `2px`
- Focus: `border-color: #1B3A6B`, ring `0 0 0 3px rgba(27, 58, 107, 0.2)`
- Placeholder: `#4A6670` italic
- Text color: `#E8ECF0`

**5. Dialog**
- Overlay: `rgba(13, 27, 30, 0.85)` with `backdrop-filter: blur(8px)`
- Content: `#152A2E` background, washi grain texture
- Border: `1px solid rgba(200, 216, 232, 0.08)`
- Entry animation: `spirit-manifest` (fade + translateY + blur)
- Header area: optional vermillion top border accent

**6. Sidebar**
- Background: `#0D1B1E` (Midnight Pine, deepest layer)
- Border-right: `1px solid rgba(200, 216, 232, 0.06)`
- Active item: `rgba(27, 58, 107, 0.15)` background with `#C8D8E8` text
- Hover: `rgba(200, 216, 232, 0.04)` background
- Section headers: `letter-spacing: 0.12em`, uppercase, `#4A6670` color
- Logo area: vermillion accent element

**7. Tabs**
- Inactive: `#4A6670` text, no background
- Active: `#E8ECF0` text with vermillion `border-bottom: 2px solid #D43B2F`
- Hover: `#C8D8E8` text
- Tab list border-bottom: `1px solid rgba(200, 216, 232, 0.06)`
- Transition: `0.35s` with `--ease-spirit`

**8. Table**
- Header: `#0D1B1E` background, `#4A6670` text, uppercase `letter-spacing: 0.1em`
- Rows: alternating `#152A2E` / `rgba(200, 216, 232, 0.02)`
- Borders: `1px solid rgba(200, 216, 232, 0.04)` horizontal only
- Hover row: `rgba(27, 58, 107, 0.08)` background
- Selected row: `rgba(27, 58, 107, 0.12)` with left vermillion accent

**9. Select**
- Trigger: same styling as Input
- Content dropdown: `#1A2F34` background, `1px solid rgba(200, 216, 232, 0.08)`
- Option hover: `rgba(27, 58, 107, 0.12)`
- Selected option: `#1B3A6B` background, `#E8ECF0` text
- Radius: `2px`

**10. Dropdown Menu**
- Background: `#1A2F34`
- Border: `1px solid rgba(200, 216, 232, 0.08)`
- Item hover: `rgba(27, 58, 107, 0.12)`
- Separator: `rgba(200, 216, 232, 0.06)`
- Destructive items: `#E85D3A` text
- Box-shadow: `0 8px 32px rgba(0, 0, 0, 0.4)`

**11. Alert / Alert Dialog**
- Default: `#152A2E` background, `border-left: 3px solid #1B3A6B`
- Destructive: `border-left: 3px solid #D43B2F`, icon in `#E85D3A`
- Warning: `border-left: 3px solid #F0A868`
- Radius: `2px`
- Icon: mon-style circular background with centered icon

**12. Sonner (Toast)**
- Background: `#1A2F34`
- Border: `1px solid rgba(200, 216, 232, 0.08)`
- Accent border-left: `3px solid` matching status color
- Entry animation: slide in from right with `spirit-manifest` easing
- Close on hover: ghost-style X button

**13. Progress**
- Track: `rgba(200, 216, 232, 0.06)`, height `4px`, radius `2px`
- Fill: `linear-gradient(90deg, #1B3A6B, #D43B2F)` (indigo to vermillion crossing)
- Indeterminate: `lantern-pulse` animation

**14. Accordion**
- Background: transparent
- Border-bottom per item: `1px solid rgba(200, 216, 232, 0.06)`
- Trigger text: `#C8D8E8`, hover `#E8ECF0`
- Chevron: `#4A6670`, rotates `180deg` on open
- Open content: subtle `spirit-manifest` entry animation
- Active trigger: optional vermillion left accent

**15. Switch**
- Track off: `rgba(200, 216, 232, 0.1)`
- Track on: `#1B3A6B`
- Thumb: `#E8ECF0`
- On-state glow: `box-shadow: 0 0 8px rgba(27, 58, 107, 0.3)`
- Transition: `0.35s --ease-spirit`

**16. Tooltip**
- Background: `#0D1B1E`
- Border: `1px solid rgba(200, 216, 232, 0.1)`
- Text: `#C8D8E8`, `font-size: 12px`
- Box-shadow: `0 4px 16px rgba(0, 0, 0, 0.4)`
- Entry: fade + slight translateY, `0.2s`

**17. Avatar**
- Border: `2px solid rgba(200, 216, 232, 0.1)`
- Border-radius: `50%` (mon-style circular)
- Fallback background: `#1B3A6B`
- Fallback text: `#C8D8E8`
- Active/online indicator: `#5AB878` dot with `box-shadow: 0 0 6px rgba(90, 184, 120, 0.4)`

**18. Separator**
- Default: `rgba(200, 216, 232, 0.06)`
- Vermillion accent variant: `rgba(212, 59, 47, 0.2)` for major section breaks
- Shrine gate double-line: two `1px` lines with `4px` gap between

**19. Skeleton**
- Base: `rgba(200, 216, 232, 0.04)`
- Shimmer: `linear-gradient(90deg, transparent, rgba(200, 216, 232, 0.06), transparent)`
- Animation: `lantern-pulse` at reduced intensity, `2s` cycle
- Border-radius: `2px` (matching card geometry)

**20. Scroll Area**
- Scrollbar track: transparent
- Scrollbar thumb: `rgba(200, 216, 232, 0.1)`, hover `rgba(200, 216, 232, 0.2)`
- Thumb radius: `100px`
- Width: `6px`

**21. Navigation Menu**
- Background: `#0D1B1E`
- Active link: `#E8ECF0` with vermillion bottom accent
- Inactive: `#4A6670`
- Hover: `#C8D8E8` with `rgba(200, 216, 232, 0.04)` background
- Dropdown: same as Dropdown Menu styling
- Letter-spacing: `0.04em`

**22. Form / Field / Label**
- Label: `#C8D8E8`, `font-size: 13px`, `font-weight: 500`, `letter-spacing: 0.06em`
- Description text: `#4A6670`, `font-size: 12px`
- Error text: `#E85D3A`, `font-size: 12px`
- Error input border: `1px solid rgba(212, 59, 47, 0.5)`
- Required indicator: vermillion `*` character

---

**Block Pattern Recommendations:**

- **dashboard-01**: Use as primary layout; restyle chart containers with `.card-shrine` pattern
- **sidebar-01 through sidebar-05**: Use sidebar-01 as default; apply Midnight Pine background with shrine-pillar vermillion active indicators
- **login-01**: Center form on dark `pine-forest-depth` background with spirit-glow radial gradient behind the form card

**Chart Theming:**
- Chart backgrounds: transparent over card backgrounds
- Grid lines: `rgba(200, 216, 232, 0.04)`
- Primary data: `#1B3A6B` (Deep Indigo Wave)
- Secondary data: `#D43B2F` (Vermillion Torii)
- Tertiary data: `#C8D8E8` (Frosted Fuji)
- Accent data: `#F0A868` (Shrine Candle)
- Tooltip: match theme Tooltip styling

---

### Key Design Principles Summary

1. **Shinpi (Mystery)** --- The spirit world exists beyond the visible; let shadows hold depth and suggestion, never reveal everything at once
2. **Torii Threshold** --- Vermillion marks the crossing point; reserve it for moments of action, transition, and significance
3. **Midnight Pine Foundation** --- Dark backgrounds are the forest floor; all elements emerge from and return to this primordial darkness
4. **Mon Precision** --- Badges and icons carry the authority of family crests; circular, centered, high-contrast, unmistakable
5. **Washi Materiality** --- Every surface carries the grain of handmade paper; texture is presence, not decoration
6. **Indigo Depth** --- Interactive elements live in the indigo spectrum; deeper blue means deeper engagement
7. **Spirit Manifestation** --- Elements do not merely appear; they manifest---fading through mist, resolving from blur, emerging from shadow
8. **Shrine Architecture** --- Layout follows the logic of sacred buildings; deliberate placement, structural hierarchy, intentional negative space
9. **Restraint of Power** --- Vermillion and indigo are potent; use them sparingly, and their impact compounds
10. **Yugen (Profound Grace)** --- The most powerful design decisions are felt, not seen; atmosphere over ornamentation, suggestion over declaration

---

*"The gods are present everywhere---in the rustle of pine, in the vermillion gate, in the ink that flows across paper like water finding its path."* --- Inspired by Shinto philosophy
