## UI Design System: Apocalypse / Fallout Theme

### Core Design Philosophy

Create an interface embodying **industrial decay** and **survival utility** through the lens of a **post-nuclear wasteland**---celebrating the grit of improvised technology and the defiance of life persisting amid ruin. Inspired by Cold War-era civil defense equipment, Pip-Boy terminals, and bunker control panels, UI components should feel like scavenged hardware patched together with solder and duct tape, still flickering to life behind cracked CRT glass. The design honors **function over form**---every pixel earns its place by serving a survival purpose.

**Guiding Principles:**
- **Salvage** --- Nothing is wasted. Every component looks reclaimed, repurposed, still functional.
- **Legibility Under Duress** --- Information must be readable in low-light, at a glance, under stress.
- **Terminal Authority** --- The CRT is the last trusted source of truth. Honor it.
- **Hazard Awareness** --- Danger is always present. Visual hierarchy screams what matters most.
- **Analog Warmth** --- Digital precision softened by phosphor bloom, scan drift, and tube hum.
- **Endurance** --- The interface has survived the blast. It shows the scars but still boots up.

---

### Color Palette

**Charred Earth Tones (Background Palette):**
- **Bunker Black**: `#0D0D0D` --- deepest shelter interior, primary canvas
- **Charred Concrete**: `#1A1A17` --- scorched walls of a fallout shelter
- **Ash Layer**: `#2A2A24` --- settled fallout dust on surfaces
- **Rubble Gray**: `#3D3D35` --- exposed foundation, elevated surfaces
- **Dust Haze**: `#4A4A40` --- atmospheric particulate, tertiary backgrounds

**Rusting Steel Tones (Primary Palette):**
- **Corroded Iron**: `#8B4513` --- deep rust, primary structural color
- **Oxidized Copper**: `#6B3A2A` --- secondary structural accent
- **Bare Steel**: `#6E6E64` --- unpainted metal, neutral element
- **Patina Edge**: `#5C5C50` --- border and divider tone
- **Welding Scar**: `#7A6A55` --- subtle highlight on metal surfaces

**Hazard Yellow (Action Palette):**
- **Hazard Primary**: `#E5A100` --- caution tape, primary action buttons
- **Hazard Bright**: `#F5B800` --- hover state, emphasized warnings
- **Hazard Dim**: `#B8860B` --- pressed state, subdued caution
- **Hazard Stripe Dark**: `#1A1A17` --- alternating stripe in hazard patterns

**Nuclear Glow (Accent Palette):**
- **Reactor Core**: `#39FF14` --- maximum intensity, critical alerts
- **Isotope Green**: `#32CD32` --- active elements, success states
- **Fallout Teal**: `#20B2AA` --- secondary accent, linked elements
- **Radiation Amber**: `#FF8C00` --- radiation warnings, elevated danger

**Terminal Green (Text Palette):**
- **Phosphor Bright**: `#33FF33` --- primary text, active terminal output
- **Phosphor Standard**: `#20C020` --- body text, standard readability
- **Phosphor Dim**: `#0F8F0F` --- secondary text, labels, timestamps
- **Phosphor Ghost**: `#0A5A0A` --- disabled text, background data
- **Phosphor Burn**: `rgba(51, 255, 51, 0.08)` --- text glow bloom on dark surfaces

**Material References:**
- CRT phosphor bloom: `rgba(51, 255, 51, 0.15)`
- Scorched metal: `#3A3530`
- Irradiated water: `rgba(57, 255, 20, 0.06)`
- Bunker warning light: `rgba(229, 161, 0, 0.25)`

---

### Typography

**Font Philosophy:** Text must feel like output from a monochrome CRT terminal---fixed-width characters burning into a phosphor screen. Every letterform is utilitarian, designed for rapid parsing in hazardous conditions. Proportional fonts are a pre-war luxury.

**Font Stack:**
```css
--font-primary: 'Share Tech Mono', 'VT323', 'Courier New', monospace;
--font-body: 'Share Tech Mono', 'IBM Plex Mono', 'Fira Mono', monospace;
--font-display: 'VT323', 'Press Start 2P', 'Share Tech Mono', monospace;
--font-system: 'JetBrains Mono', 'SF Mono', 'Cascadia Mono', monospace;
```

**Type Scale:**
- **Display**: 28-36px, weight 400, `letter-spacing: 0.15em`, uppercase
- **Heading**: 20-24px, weight 700, `letter-spacing: 0.10em`, uppercase
- **Section title**: 14-16px, weight 700, `letter-spacing: 0.20em`, uppercase, with `>` prefix
- **Body**: 14-16px, weight 400, line-height 1.6
- **Data readout**: 13-14px, weight 400, `letter-spacing: 0.05em`
- **Small/Caption**: 11-12px, weight 400, `letter-spacing: 0.08em`, uppercase
- **Terminal prompt**: 14px, weight 400, preceded by blinking `_` cursor

**Text Styling:**
- Force `font-family: monospace` on ALL elements---no exceptions
- Uppercase for headings, labels, navigation; mixed case for body content
- Text-shadow for phosphor glow: `0 0 8px rgba(51, 255, 51, 0.4)`
- Generous `letter-spacing` (0.05em-0.15em) for terminal authenticity
- Line-height 1.5-1.6 for body text, tighter (1.2) for data readouts
- Prefix section headers with `> ` or `// ` for command-line aesthetics

---

### Component Patterns

#### Cards & Containers --- *Salvaged Panels*

Inspired by ripped-open control panels and bolted-together scrap metal:

```css
.card {
  background: #1A1A17;
  border: 1px solid #4A4A40;
  border-radius: 0; /* Sharp corners only. No luxury. */
  padding: 20px 24px;
  position: relative;
  font-family: 'Share Tech Mono', monospace;
  box-shadow:
    inset 0 1px 0 rgba(255, 255, 255, 0.03),
    0 2px 8px rgba(0, 0, 0, 0.6);
}

/* Scanline overlay for all cards */
.card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(0, 0, 0, 0.15) 2px,
    rgba(0, 0, 0, 0.15) 4px
  );
  pointer-events: none;
  z-index: 1;
}

/* Corner bolt rivets */
.card::after {
  content: '';
  position: absolute;
  top: 6px;
  left: 6px;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: #5C5C50;
  box-shadow:
    calc(100% - 18px) 0 0 0 #5C5C50,
    0 calc(100% - 18px) 0 0 #5C5C50,
    calc(100% - 18px) calc(100% - 18px) 0 0 #5C5C50;
  z-index: 2;
}

.card-terminal {
  border-color: #0F8F0F;
  box-shadow:
    inset 0 0 30px rgba(51, 255, 51, 0.03),
    0 0 1px rgba(51, 255, 51, 0.3);
}

.card-hazard {
  border-left: 4px solid #E5A100;
  background: linear-gradient(
    135deg,
    #1A1A17 0%,
    rgba(229, 161, 0, 0.03) 100%
  );
}

.card-damaged {
  border: 1px solid #4A4A40;
  border-top-width: 2px;
  border-right-width: 1px;
  border-bottom-width: 1px;
  border-left-width: 3px; /* Uneven, as if warped by heat */
  clip-path: polygon(0% 0%, 97% 0%, 100% 3%, 100% 100%, 3% 100%, 0% 97%);
}
```

**Border Philosophy:**
- `border-radius: 0` on everything. Sharp corners are mandatory.
- Uneven border widths simulate heat-warped metal
- Double-border effects for reinforced-panel appearance
- Corner accents via `::after` pseudo-elements (bolts, rivets, welds)

**Depth & Shadow:**
- Hard, dark shadows: `0 4px 12px rgba(0, 0, 0, 0.7)`
- Inner glow for terminal panels: `inset 0 0 20px rgba(51, 255, 51, 0.04)`
- No soft, diffused shadows---everything is harsh and industrial

---

#### Buttons & Interactive Elements --- *Bunker Controls*

```css
.button-primary {
  background: #E5A100;
  color: #0D0D0D;
  border: none;
  border-radius: 0;
  padding: 12px 28px;
  font-family: 'Share Tech Mono', monospace;
  font-weight: 700;
  font-size: 13px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  cursor: pointer;
  position: relative;
  overflow: hidden;
  transition: all 0.15s linear;
}

/* Hazard stripe hover effect using CSS background */
.button-primary:hover {
  background: repeating-linear-gradient(
    -45deg,
    #E5A100,
    #E5A100 8px,
    #1A1A17 8px,
    #1A1A17 16px
  );
  color: #E5A100;
  box-shadow: 0 0 12px rgba(229, 161, 0, 0.3);
}

.button-primary:active {
  background: #B8860B;
  color: #0D0D0D;
  transform: translateY(1px);
  box-shadow: none;
}

.button-terminal {
  background: transparent;
  color: #33FF33;
  border: 1px solid #20C020;
  text-shadow: 0 0 6px rgba(51, 255, 51, 0.4);
}

.button-terminal:hover {
  background: rgba(51, 255, 51, 0.08);
  border-color: #33FF33;
  box-shadow: 0 0 10px rgba(51, 255, 51, 0.15);
}

.button-danger {
  background: transparent;
  color: #FF4444;
  border: 2px solid #FF4444;
  position: relative;
}

.button-danger::before {
  content: '! ';
  font-weight: 700;
}

.button-danger:hover {
  background: rgba(255, 68, 68, 0.12);
  box-shadow: 0 0 15px rgba(255, 68, 68, 0.2);
}

.button-ghost {
  background: transparent;
  color: #6E6E64;
  border: 1px solid #3D3D35;
}

.button-ghost:hover {
  color: #E5A100;
  border-color: #E5A100;
}
```

**Icon Buttons:**
- Square, rigid touch targets: 44px x 44px minimum
- No border-radius whatsoever
- Hover reveals hazard stripe flash or phosphor glow
- Active states depress with `translateY(1px)` and dimmed color

---

#### Form Elements --- *Terminal Inputs*

```css
.input {
  background: transparent;
  border: none;
  border-bottom: 2px solid #3D3D35;
  padding: 10px 0;
  font-family: 'Share Tech Mono', monospace;
  font-size: 14px;
  color: #33FF33;
  caret-color: #33FF33;
  letter-spacing: 0.05em;
  transition: border-color 0.15s linear;
}

.input::placeholder {
  color: #0A5A0A;
  font-style: normal;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.input:focus {
  outline: none;
  border-bottom-color: #33FF33;
  text-shadow: 0 0 4px rgba(51, 255, 51, 0.3);
}

/* Flickering cursor effect */
.input:focus {
  animation: cursor-flicker 0.08s infinite alternate;
}

@keyframes cursor-flicker {
  0% { caret-color: #33FF33; }
  100% { caret-color: transparent; }
}

.input-enclosed {
  background: rgba(13, 13, 13, 0.8);
  border: 1px solid #3D3D35;
  border-bottom: 2px solid #4A4A40;
  border-radius: 0;
  padding: 12px 16px;
}

.input-enclosed:focus {
  border-color: #20C020;
  box-shadow: inset 0 0 10px rgba(51, 255, 51, 0.05);
}

.label {
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #0F8F0F;
  margin-bottom: 6px;
}

.checkbox {
  width: 20px;
  height: 20px;
  border: 2px solid #4A4A40;
  border-radius: 0;
  background: transparent;
  appearance: none;
}

.checkbox:checked {
  background: #33FF33;
  border-color: #33FF33;
  box-shadow: 0 0 6px rgba(51, 255, 51, 0.4);
  /* Checkmark is a simple square fill --- no curves */
}

.select {
  background: #1A1A17;
  border: 1px solid #3D3D35;
  border-radius: 0;
  color: #20C020;
  font-family: 'Share Tech Mono', monospace;
  padding: 10px 32px 10px 12px;
}
```

**Focus States:**
- Terminal glow outline: `box-shadow: 0 0 0 2px rgba(51, 255, 51, 0.2)`
- Bottom border transitions from gray to phosphor green
- Text acquires subtle glow on focus
- No smooth curves in focus indicators---hard geometric outlines only

---

#### Status & Feedback --- *Radiation Gauges*

```css
.badge {
  display: inline-flex;
  align-items: center;
  padding: 4px 10px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  border-radius: 0;
  border: 1px solid currentColor;
  background: transparent;
}

.badge-default {
  color: #20C020;
  border-color: #0F8F0F;
  background: rgba(51, 255, 51, 0.05);
}

.badge-warning {
  color: #E5A100;
  border-color: #B8860B;
  background: rgba(229, 161, 0, 0.08);
}

.badge-critical {
  color: #FF4444;
  border-color: #CC0000;
  background: rgba(255, 68, 68, 0.08);
  animation: badge-pulse 1.5s ease-in-out infinite;
}

.badge-info {
  color: #20B2AA;
  border-color: #178A83;
  background: rgba(32, 178, 170, 0.06);
}

@keyframes badge-pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.6; }
}

.progress-bar {
  height: 8px;
  background: #2A2A24;
  border: 1px solid #3D3D35;
  border-radius: 0;
  position: relative;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: #20C020;
  box-shadow: 0 0 8px rgba(51, 255, 51, 0.3);
  position: relative;
}

/* Segmented progress --- like a Geiger counter bar */
.progress-fill::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: repeating-linear-gradient(
    90deg,
    transparent,
    transparent 6px,
    #1A1A17 6px,
    #1A1A17 8px
  );
}

/* Radiation level colors */
.progress-low .progress-fill { background: #20C020; }
.progress-medium .progress-fill { background: #E5A100; }
.progress-high .progress-fill { background: #FF8C00; }
.progress-critical .progress-fill { background: #FF4444; }

.alert {
  background: #1A1A17;
  border-left: 4px solid #E5A100;
  padding: 16px 20px;
  font-family: 'Share Tech Mono', monospace;
  color: #20C020;
  position: relative;
}

.alert::before {
  content: '[!] ';
  color: #E5A100;
  font-weight: 700;
}

.alert-critical {
  border-left-color: #FF4444;
  background: rgba(255, 68, 68, 0.04);
}

.alert-critical::before {
  content: '[CRITICAL] ';
  color: #FF4444;
}
```

---

### Layout Principles --- *Bunker Architecture*

**Spacing Scale:**
`4, 8, 12, 16, 24, 32, 48, 64px`

Keep spacing tight and efficient. Screen real estate is a scarce resource in a bunker.

**Grid Philosophy:**
- Rigid, mechanical grid layouts---CSS Grid over Flexbox where possible
- Even, symmetrical columns: information must be scanned quickly
- Dense information display: minimize wasted space
- Maximum content width: 960px for terminals, 1200px for dashboards
- Sidebar-heavy layouts for navigation (bunker control panel aesthetic)

**Visual Weight Distribution:**
```
┌──────────────────────────────────┐
│ [STATUS BAR]   ████████████████ │  <- Top: system status, always visible
├──────┬───────────────────────────┤
│ NAV  │  > MAIN TERMINAL OUTPUT  │  <- Left: navigation panel
│      │                          │
│ [01] │  DATA READOUT AREA       │  <- Dense data display
│ [02] │  ________________________│
│ [03] │  SECONDARY PANEL         │
│      │                          │
├──────┴───────────────────────────┤
│ [COMMAND INPUT]              [>]│  <- Bottom: command/action bar
└──────────────────────────────────┘
```

**Dividers & Separators:**
- Solid 1px lines: `border-bottom: 1px solid #3D3D35`
- Double-line separators for major sections: `border: 2px double #4A4A40`
- Dashed lines for data grouping: `border-bottom: 1px dashed #3D3D35`
- ASCII-style separators in text: `// -------- SECTION -------- //`

---

### Interaction Design --- *Flickering Systems*

**Transition Timing:**
```css
--ease-mechanical: cubic-bezier(0.25, 0.1, 0.25, 1); /* Stiff, industrial */
--ease-snap: cubic-bezier(0, 0, 0.2, 1); /* Quick mechanical snap */
--ease-boot: cubic-bezier(0.22, 0.61, 0.36, 1); /* System powering up */
--duration-instant: 0.1s;
--duration-fast: 0.15s;
--duration-standard: 0.25s;
--duration-boot: 0.6s;
```

**Hover Philosophy:**
- Immediate response---no languorous transitions
- Hazard stripe patterns appear via `background` changes
- Phosphor glow intensifies: `text-shadow` and `box-shadow` brighten
- Color shifts from dim to bright green/yellow
- Elements feel like switches being toggled, not waves rolling

**Loading States:**
- CRT boot-up sequence: text appearing line-by-line
- Geiger counter tick animation
- Spinning radiation trefoil symbol
- Progress bar filling in segments

```css
@keyframes crt-boot {
  0% { opacity: 0; filter: brightness(3) blur(2px); }
  10% { opacity: 1; filter: brightness(2) blur(1px); }
  20% { opacity: 0.3; filter: brightness(0.5) blur(0px); }
  30% { opacity: 1; filter: brightness(1.2) blur(0px); }
  100% { opacity: 1; filter: brightness(1) blur(0px); }
}

@keyframes scanline-drift {
  0% { transform: translateY(-100%); }
  100% { transform: translateY(100vh); }
}

@keyframes phosphor-pulse {
  0%, 100% {
    text-shadow: 0 0 4px rgba(51, 255, 51, 0.3);
  }
  50% {
    text-shadow: 0 0 12px rgba(51, 255, 51, 0.6);
  }
}

@keyframes flicker {
  0%, 97%, 100% { opacity: 1; }
  98% { opacity: 0.85; }
  99% { opacity: 0.92; }
}

@keyframes geiger-tick {
  0%, 90%, 100% { transform: scaleY(0.3); background: #0F8F0F; }
  95% { transform: scaleY(1); background: #33FF33; }
}

@keyframes hazard-scroll {
  0% { background-position: 0 0; }
  100% { background-position: 22.63px 0; }
}
```

**CRT Screen Effect (applied to main container):**
```css
.crt-screen {
  position: relative;
  overflow: hidden;
}

/* Scanline overlay */
.crt-screen::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(0, 0, 0, 0.1) 2px,
    rgba(0, 0, 0, 0.1) 4px
  );
  pointer-events: none;
  z-index: 10;
}

/* Subtle screen flicker */
.crt-screen::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(51, 255, 51, 0.01);
  animation: flicker 4s infinite;
  pointer-events: none;
  z-index: 11;
}

/* Vignette effect on CRT edges */
.crt-vignette {
  box-shadow:
    inset 0 0 80px rgba(0, 0, 0, 0.4),
    inset 0 0 200px rgba(0, 0, 0, 0.2);
}
```

---

### Texture & Material References

**Industrial Textures:**
- Scanline overlay on all panels: `repeating-linear-gradient` at 2-4px intervals
- Noise/grain filter for scorched metal surfaces: fine SVG noise at `opacity: 0.04`
- Rust-stain gradients on structural borders
- Concrete dust: scattered micro-dot patterns at near-invisible opacity

**Wasteland-Inspired Patterns:**
- Hazard stripe backgrounds for warning areas
- CRT phosphor bloom around bright text elements
- Bunker wall texture: dark, barely-visible crosshatch grain
- Radiation symbol watermarks on critical sections

```css
.scanline-overlay {
  background: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(0, 0, 0, 0.12) 2px,
    rgba(0, 0, 0, 0.12) 4px
  );
}

.hazard-stripes {
  background: repeating-linear-gradient(
    -45deg,
    #E5A100,
    #E5A100 10px,
    #1A1A17 10px,
    #1A1A17 20px
  );
}

.hazard-stripes-subtle {
  background: repeating-linear-gradient(
    -45deg,
    rgba(229, 161, 0, 0.06),
    rgba(229, 161, 0, 0.06) 10px,
    transparent 10px,
    transparent 20px
  );
}

.rust-gradient {
  background: linear-gradient(
    180deg,
    #1A1A17 0%,
    rgba(139, 69, 19, 0.08) 60%,
    rgba(139, 69, 19, 0.15) 100%
  );
}

.phosphor-bloom {
  text-shadow:
    0 0 4px rgba(51, 255, 51, 0.4),
    0 0 12px rgba(51, 255, 51, 0.2),
    0 0 24px rgba(51, 255, 51, 0.1);
}

.concrete-texture {
  background-image: url("data:image/svg+xml,%3Csvg width='4' height='4' viewBox='0 0 4 4' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1 3h1v1H1V3zm2-2h1v1H3V1z' fill='%23ffffff' fill-opacity='0.02'/%3E%3C/svg%3E");
}
```

---

### Iconography --- *Stencil Marks*

- Monoline stroke icons, weight 2px---bold and legible
- Hard geometric forms: squares, triangles, straight lines
- No curves unless functionally necessary (circular gauges, radiation symbols)
- Icon size: 16-20px inline, 24-32px standalone
- Icons should feel spray-painted through a military stencil

**Style Reference:**
```
Standard:  [ ] ( ) < >
Fallout:   [X] /!\ >>> |||  (blocky, stenciled, utilitarian)
```

Consider icons that feel stamped or stenciled:
- Uniform stroke weight---no taper, no flourish
- Hard terminal ends, never rounded caps
- Angular construction: 90-degree and 45-degree angles preferred
- Enclosed in square brackets or framing marks for emphasis: `[ICON]`

**Recommended Icon Sets:**
- Lucide Icons (with `stroke-linecap: square; stroke-linejoin: miter`)
- Phosphor Icons (Bold weight, with forced square caps)
- Custom SVG stencils for key navigation elements

---

### Decay & Character Details

1. **Uneven borders**: `border-width: 1px 2px 1px 3px` --- heat-warped metal panels
2. **CRT scanlines**: Repeating 2-4px horizontal line overlay on all content areas
3. **Phosphor text glow**: All terminal text emits `text-shadow` bloom in green
4. **Screen flicker**: Subtle global `opacity` animation at irregular intervals (4-8s cycle)
5. **Noise grain**: SVG noise texture at 2-4% opacity over dark surfaces
6. **Hazard stripe accents**: Diagonal yellow-black stripes on hover states and warning borders
7. **Bolt/rivet details**: `::after` pseudo-element circles in card corners
8. **Vignette darkening**: `box-shadow: inset 0 0 80px rgba(0,0,0,0.3)` on main viewport
9. **Clipped corners**: `clip-path` polygons that suggest blast-damaged edges
10. **ASCII prefixes**: Section headers prefixed with `> `, `// `, or `[!]` for terminal character

---

### Recommended shadcn/ui Components

**Base Theme:** `theme-zinc` (closest industrial neutral tone; override all border-radius to `0` and force monospace fonts globally)

**Global CSS Overrides (apply before individual components):**
```css
/* Force the Wasteland aesthetic across all shadcn components */
* {
  font-family: 'Share Tech Mono', 'IBM Plex Mono', monospace !important;
  border-radius: 0 !important;
}

:root {
  --radius: 0;
  --background: #0D0D0D;
  --foreground: #20C020;
  --card: #1A1A17;
  --card-foreground: #20C020;
  --popover: #1A1A17;
  --popover-foreground: #20C020;
  --primary: #E5A100;
  --primary-foreground: #0D0D0D;
  --secondary: #2A2A24;
  --secondary-foreground: #20C020;
  --muted: #2A2A24;
  --muted-foreground: #0F8F0F;
  --accent: #33FF33;
  --accent-foreground: #0D0D0D;
  --destructive: #FF4444;
  --destructive-foreground: #0D0D0D;
  --border: #3D3D35;
  --input: #3D3D35;
  --ring: rgba(51, 255, 51, 0.3);
}
```

#### 1. Button
**Purpose:** Primary interaction element---bunker control switches.
```
Override: Remove all border-radius. Uppercase text with letter-spacing: 0.12em.
Primary variant: background #E5A100, color #0D0D0D.
Hover: Apply hazard stripe repeating-linear-gradient(-45deg, ...).
Ghost variant: border 1px solid #3D3D35, color #6E6E64. Hover color #E5A100.
Destructive variant: border 2px solid #FF4444, transparent background.
Add font-weight: 700 and text-transform: uppercase to all variants.
```

#### 2. Card
**Purpose:** Information panels---salvaged steel enclosures.
```
Override: background #1A1A17, border 1px solid #4A4A40, border-radius 0.
Add scanline overlay via ::before pseudo-element.
Card header: border-bottom 1px solid #3D3D35, uppercase title, letter-spacing 0.10em.
Card footer: border-top 1px dashed #3D3D35, muted green text.
Consider corner bolt/rivet accents via ::after on card wrapper.
```

#### 3. Input
**Purpose:** Data entry terminals---underline-only with flickering cursor.
```
Override: background transparent, border none, border-bottom 2px solid #3D3D35.
Text color #33FF33 with caret-color #33FF33.
Focus: border-bottom-color #33FF33, add text-shadow glow.
Placeholder: color #0A5A0A, uppercase, letter-spacing 0.08em.
Force monospace font on all input elements.
```

#### 4. Badge
**Purpose:** Status classification---stenciled military tags.
```
Override: border-radius 0, border 1px solid currentColor, background transparent.
Font: 11px, weight 700, letter-spacing 0.15em, uppercase.
Default: color #20C020. Warning: color #E5A100. Critical: color #FF4444 with pulse animation.
Consider adding bracket characters: content '[' before, ']' after.
```

#### 5. Alert
**Purpose:** System warnings---fallout shelter announcements.
```
Override: background #1A1A17, border-left 4px solid #E5A100.
Prefix alert text with [!] or [WARNING] in hazard yellow.
Critical alerts: border-left-color #FF4444, prefix [CRITICAL].
Add subtle hazard stripe background at 3-5% opacity.
Title: uppercase, letter-spacing 0.10em.
```

#### 6. Dialog / Alert-Dialog
**Purpose:** Critical confirmations---blast door authorization panels.
```
Override: background #1A1A17, border 2px solid #4A4A40.
Overlay: background rgba(0, 0, 0, 0.85) with scanline pattern.
Title: uppercase, letter-spacing 0.12em, color #E5A100.
Apply CRT boot animation on open (flicker-in effect).
Footer buttons: full-width, stacked vertically for mobile.
```

#### 7. Tabs
**Purpose:** Section navigation---bunker department switches.
```
Override: border-radius 0 on all tab triggers.
Inactive: background transparent, color #0F8F0F, border-bottom 2px solid transparent.
Active: color #33FF33, border-bottom 2px solid #33FF33, text-shadow phosphor glow.
Tab content area: border 1px solid #3D3D35, background #1A1A17.
Tab labels: uppercase, letter-spacing 0.10em, font-size 12px.
```

#### 8. Table
**Purpose:** Data readouts---terminal log displays.
```
Override: border-collapse collapse, monospace font throughout.
Header row: background #2A2A24, color #E5A100, uppercase, letter-spacing 0.08em.
Body rows: border-bottom 1px solid #2A2A24, color #20C020.
Hover row: background rgba(51, 255, 51, 0.04).
Alternate rows: background rgba(42, 42, 36, 0.5) for readability.
Cell padding: 10px 16px for comfortable data scanning.
```

#### 9. Progress
**Purpose:** Resource gauges---reactor fuel level indicators.
```
Override: height 8px, background #2A2A24, border 1px solid #3D3D35, border-radius 0.
Fill: background #20C020 with segmented repeating-linear-gradient overlay.
Glow effect: box-shadow 0 0 8px rgba(51, 255, 51, 0.3) on fill.
Color stages: green (<50%), yellow (50-75%), orange (75-90%), red (>90%).
```

#### 10. Select
**Purpose:** Option selection---system configuration dropdown.
```
Override: background #1A1A17, border 1px solid #3D3D35, border-radius 0.
Text: color #20C020, monospace, letter-spacing 0.05em.
Dropdown menu: background #1A1A17, border 1px solid #4A4A40.
Item hover: background rgba(51, 255, 51, 0.06), color #33FF33.
Chevron icon: color #0F8F0F, square stroke caps.
```

#### 11. Sidebar
**Purpose:** Navigation panel---bunker section directory.
```
Override: background #0D0D0D, border-right 2px solid #3D3D35.
Nav items: uppercase, letter-spacing 0.08em, font-size 12px, color #0F8F0F.
Active item: color #33FF33, border-left 3px solid #33FF33, phosphor glow.
Section headers: color #E5A100, preceded by '>' character.
Collapse toggle: square icon button, hazard yellow on hover.
Width: 240px expanded, 56px collapsed.
```

#### 12. Tooltip
**Purpose:** Contextual data---field manual callouts.
```
Override: background #2A2A24, border 1px solid #4A4A40, border-radius 0.
Text: color #20C020, font-size 12px, letter-spacing 0.05em.
Arrow: match background #2A2A24 with matching border.
Box-shadow: 0 2px 8px rgba(0, 0, 0, 0.6).
Max-width: 280px. Delay: 200ms (snappy response).
```

#### 13. Switch / Toggle
**Purpose:** System toggles---circuit breaker switches.
```
Override: border-radius 0, background #2A2A24, border 2px solid #4A4A40.
Thumb: square (border-radius 0), background #6E6E64.
Checked: background #0F8F0F, border-color #20C020, thumb color #33FF33.
Checked thumb glow: box-shadow 0 0 6px rgba(51, 255, 51, 0.5).
Transition: 0.15s linear (mechanical snap, not smooth glide).
```

#### 14. Checkbox / Radio-Group
**Purpose:** Selection controls---checklist verification.
```
Override: border-radius 0 (square checkboxes, square radio buttons).
Border: 2px solid #4A4A40, background transparent.
Checked: fill #33FF33, border-color #33FF33, inner glow.
Checkmark: simple square fill or X mark, no curved checkmark.
Radio: smaller inner square instead of circle when selected.
```

#### 15. Separator
**Purpose:** Section dividers---bulkhead boundaries.
```
Override: background #3D3D35 (solid), height 1px.
Variant heavy: height 2px, double border style.
Variant dashed: border-style dashed for sub-section grouping.
Vertical separators: width 1px, background #3D3D35.
Add spacing of 24px above and below for section-level separation.
```

#### 16. Skeleton
**Purpose:** Loading placeholders---data stream buffering.
```
Override: background #2A2A24, border-radius 0.
Animation: phosphor pulse (green glow oscillation) instead of shimmer.
Alternate animation: horizontal scanline sweeping across placeholder.
Color: Use rgba(51, 255, 51, 0.05) to rgba(51, 255, 51, 0.10) for pulse range.
```

#### 17. Sonner (Toast)
**Purpose:** System notifications---bunker PA announcements.
```
Override: background #1A1A17, border 1px solid #4A4A40, border-radius 0.
Success: border-left 4px solid #32CD32, prefix [OK].
Error: border-left 4px solid #FF4444, prefix [ERROR].
Warning: border-left 4px solid #E5A100, prefix [WARN].
Info: border-left 4px solid #20B2AA, prefix [INFO].
Add brief CRT-flicker animation on appearance.
Text: monospace, color #20C020, uppercase for prefix.
```

#### 18. Dropdown-Menu / Context-Menu
**Purpose:** Action menus---system command palettes.
```
Override: background #1A1A17, border 1px solid #4A4A40, border-radius 0.
Item: color #20C020, padding 8px 16px, font-size 13px, monospace.
Item hover: background rgba(51, 255, 51, 0.06), color #33FF33.
Separator: 1px solid #2A2A24.
Keyboard shortcut text (kbd): color #0F8F0F, letter-spacing 0.08em.
Sub-menu indicator: > character instead of chevron arrow.
```

#### 19. Accordion / Collapsible
**Purpose:** Expandable sections---compartment access panels.
```
Override: border 1px solid #3D3D35, border-radius 0, background #1A1A17.
Trigger: uppercase, letter-spacing 0.08em, color #20C020.
Trigger prefix: [+] when collapsed, [-] when expanded, color #E5A100.
Content area: border-top 1px dashed #3D3D35, padding 16px.
Transition: 0.2s ease-out (quick mechanical deployment).
```

#### 20. Scroll-Area
**Purpose:** Scrollable regions---terminal log buffers.
```
Override: scrollbar-width thin.
Track: background #0D0D0D.
Thumb: background #3D3D35, border-radius 0.
Thumb hover: background #4A4A40.
Width: 6px vertical, 6px horizontal.
Maintain hard square edges on scrollbar thumb.
```

#### 21. Kbd
**Purpose:** Keyboard shortcut display---command reference tags.
```
Override: background #2A2A24, border 1px solid #4A4A40, border-radius 0.
Text: color #E5A100, font-size 11px, font-weight 700, monospace.
Padding: 2px 6px. Display: inline-block.
Add subtle inset shadow: inset 0 -1px 0 #3D3D35 (key depth effect).
```

#### 22. Slider
**Purpose:** Parameter adjustment---analog dial control.
```
Override: track background #2A2A24, height 6px, border-radius 0.
Fill: background #20C020, box-shadow 0 0 4px rgba(51, 255, 51, 0.3).
Thumb: width 16px, height 20px, background #E5A100, border-radius 0.
Thumb border: 2px solid #B8860B.
Active thumb: box-shadow 0 0 8px rgba(229, 161, 0, 0.4).
Step markers: small ticks below track in #3D3D35.
```

---

### Block Pattern Guidance

**Dashboard (dashboard-01):**
- Apply CRT screen effect to entire dashboard wrapper
- Use card grid with 1px gap borders (control panel aesthetic)
- Status bar across top: system health, radiation level, timestamp
- All charts use terminal green palette with phosphor glow

**Sidebar Variants (sidebar-01 through sidebar-16):**
- Dark background (#0D0D0D), phosphor green text
- Section dividers as dashed lines with ASCII markers
- Active states: left border accent + phosphor bloom on text
- Collapse to icon-only mode at 56px width

**Login Pages (login-01 through login-05):**
- Center terminal card on scorched background
- Title: "VAULT ACCESS TERMINAL" or similar thematic heading
- Input fields: underline-only, green text on dark
- Submit button: full-width hazard yellow
- Add CRT boot animation on page load
- Include scanline overlay and vignette on the login card

**Charts:**
- Use #33FF33 (phosphor bright) for primary data series
- Use #E5A100 (hazard) for secondary data series
- Use #20B2AA (fallout teal) for tertiary series
- Grid lines: #2A2A24, dashed
- Axis labels: #0F8F0F, uppercase, 10px monospace
- Tooltips: dark background with terminal green text

---

### Key Design Principles Summary

1. **Zero Radius** --- Every corner is sharp. Round edges are a pre-war indulgence.
2. **Terminal Green Authority** --- Phosphor green is the voice of the system. Trust the green text.
3. **Hazard Means Action** --- Yellow/black stripes signal "interact here." Use sparingly but decisively.
4. **Scanlines Are Texture** --- The CRT overlay is not decoration; it is atmosphere. Apply to all panels.
5. **Monospace Everything** --- Fixed-width fonts are not a choice; they are a survival requirement.
6. **Function Over Beauty** --- Every element earns its pixels. No ornamental flourishes.
7. **Glow Is Feedback** --- Phosphor bloom indicates life, focus, and activity. Dim means inactive.
8. **Hard Transitions** --- Animations are mechanical and snappy. Nothing glides; everything clicks.
9. **Noise and Wear** --- Grain, flicker, uneven borders---the interface has survived the apocalypse.
10. **Dense Information** --- Pack the screen. Operators need data, not whitespace. Ma is for peacetime.

---

*"War. War never changes."* --- Fallout
