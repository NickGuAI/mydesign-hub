# UI Design System: Chinese New Year — Year of the Horse (馬年)
## 春节 · 马到成功

---

## Core Design Philosophy

Create an interface that captures the **blazing vitality of Chinese New Year**—the explosive crack of firecrackers at midnight, rivers of red lanterns swaying over crowded streets, gold characters gleaming on spring couplets pasted fresh on every door. This is the Year of the Horse (馬年): galloping energy, unstoppable momentum, and the fierce optimism of new beginnings.

Where temple aesthetics seek stillness, **New Year design seeks celebration**. Every element should feel like unwrapping a red envelope—vivid, auspicious, and charged with possibility. Interfaces should evoke the warmth of a family reunion dinner table: abundant, generous, layered with meaning, and glowing under strings of red lanterns.

### Guiding Principles:

- **福 (Fú) — Fortune** — Every design choice invites good luck; abundance over minimalism
- **喜 (Xǐ) — Joy** — Interfaces radiate warmth and festive energy; never cold or clinical
- **旺 (Wàng) — Prosperity** — Rich, layered, generous; gold flows freely like wealth pouring in
- **勇 (Yǒng) — Courage** — Bold reds, confident layouts; the horse charges forward without hesitation
- **合 (Hé) — Togetherness** — Components gather like family; groupings feel communal, not isolated
- **火 (Huǒ) — Fire** — Fiery gradients, ember glows, spark animations; the element of the horse

### Horse Spirit (馬精神):
The horse in Chinese culture represents speed, perseverance, elegance, and success. The proverb **马到成功** (mǎ dào chéng gōng — "success upon the horse's arrival") defines the interaction philosophy: every action should feel like it arrives with momentum and resolves with triumph.

---

## Color Palette

### Prosperity Reds (Primary Palette):

| Token | Hex | Description |
|---|---|---|
| **Lucky Red** | `#DE2910` | The red of spring couplets and national flags; primary brand color |
| **Firecracker Red** | `#C41E10` | Deep explosive red; hover/pressed states |
| **Lantern Red** | `#E8453A` | Warm lantern glow; lighter accent, notifications |
| **Ember Red** | `#8B1A10` | Smoldering coal; dark text on light, deep anchors |
| **Red Envelope** | `#F04B3E` | Hongbao red; call-to-action highlights |

### Fortune Gold (Secondary Palette):

| Token | Hex | Description |
|---|---|---|
| **Imperial Gold** | `#FFD700` | Pure gold of ingots (元宝); primary gold accent |
| **Coin Gold** | `#DAA520` | Ancient coin patina; secondary gold, borders |
| **Silk Gold** | `#F0C75E` | Embroidered silk thread; warm highlights |
| **Burnished Gold** | `#B8860B` | Aged temple gold; text on dark, muted gold |
| **Gold Leaf** | `rgba(255, 215, 0, 0.85)` | Translucent gold foil overlay |

### Ground Tones (Backgrounds):

| Token | Hex | Description |
|---|---|---|
| **Rice Paper White** | `#FFF8F0` | Warmest white; primary light background |
| **Dumpling Cream** | `#FEF0E0` | Warm cream of steamed buns; secondary background |
| **Smoke Blush** | `#F5E1D0` | Firecracker smoke at dawn; tertiary background |
| **Night Sky** | `#1A0A08` | Deep red-black of midnight sky; dark mode base |
| **Charcoal Ember** | `#2D1215` | Glowing coal pit; dark mode card surface |

### Accent Colors (Auspicious Touches):

| Token | Hex | Description |
|---|---|---|
| **Jade Green** | `#2E8B57` | Jade pendant; success, growth, health |
| **Mandarin Orange** | `#FF8C00` | Tangerine offerings; warm warnings, generosity |
| **Peach Blossom** | `#F4A6B0` | Spring blossoms; soft highlights, femininity |
| **Firecracker Spark** | `#FFE066` | Sparks in the night; micro-interactions, badges |
| **Ink Black** | `#1A0505` | Calligraphy ink; text on light surfaces |

### Material References:

| Material | Value | Use |
|---|---|---|
| Lantern glow | `rgba(222, 41, 16, 0.12)` | Hover states, warm overlays |
| Firecracker smoke | `rgba(26, 10, 8, 0.6)` | Modal overlays, depth |
| Gold dust | `rgba(255, 215, 0, 0.15)` | Decorative shimmer overlays |
| Red silk | `linear-gradient(135deg, #DE2910, #C41E10)` | Primary button fills |
| Ember gradient | `linear-gradient(180deg, #DE2910 0%, #8B1A10 100%)` | Hero sections, nav bars |

---

## Typography

### Font Philosophy:
Text should feel like **spring couplets brushed in bold ink**—confident, celebratory, and unapologetically ornamental for display, yet crisp and legible for body content. Headings carry the weight of blessings written on red paper; body text is the clear voice reading fortunes aloud.

### Font Stack:

```css
--font-display: 'ZCOOL XiaoWei', 'Ma Shan Zheng', 'Noto Serif SC', cursive;
/* For hero text, banners, and fortune phrases */

--font-primary: 'Noto Serif SC', 'Playfair Display', 'Songti SC', serif;
/* For headings and emphasis */

--font-body: 'Noto Sans SC', 'Source Sans 3', -apple-system, 'Microsoft YaHei', sans-serif;
/* For body text and UI elements */

--font-mono: 'JetBrains Mono', 'SF Mono', monospace;
/* For data, code, numeric displays */

--font-fortune: 'ZCOOL KuaiLe', 'Ma Shan Zheng', cursive;
/* For decorative fortune phrases and proverbs */
```

### Type Scale:

| Level | Size | Weight | Notes |
|---|---|---|---|
| **Fortune Banner** | 36-48px | 700 | `--font-display`; gold or white on red |
| **Display** | 28-32px | 600 | Bold as firecrackers; commanding |
| **Heading** | 20-24px | 600 | Strong, warm |
| **Section Title** | 14-16px | 700 | `letter-spacing: 0.08em`, uppercase |
| **Body** | 15-16px | 400 | `line-height: 1.7` |
| **Small/Caption** | 12-13px | 400 | Muted gold or ember tones |
| **Fortune Whisper** | 11px | 500 | `letter-spacing: 0.06em`, gold on dark |

### Text Styling:

- **Fortune phrases** centered in display font, often gold on red banners
- Headings center-aligned for celebratory sections; left-aligned for utilitarian content
- **Color warmth hierarchy**: Ember Red/Ink Black = most important → Coin Gold = secondary → muted tones recede
- Decorative vertical text for banners and side elements: `writing-mode: vertical-rl`
- Generous `line-height: 1.7` for body; tighter `1.3` for display/fortune text
- Text on red backgrounds: `#FFD700` (Imperial Gold) or `#FFF8F0` (Rice Paper White)
- Text on light backgrounds: `#1A0505` (Ink Black) or `#8B1A10` (Ember Red)
- Text on dark backgrounds: `#FFD700` (Imperial Gold) or `#FFF8F0` (Rice Paper White)

### Chinese Proverbs for UI Microcopy:
Use these as loading messages, empty states, success toasts, and decorative elements:

| Proverb | Pinyin | Meaning | UI Use |
|---|---|---|---|
| 马到成功 | mǎ dào chéng gōng | Success upon arrival | Success states, completion |
| 龙马精神 | lóng mǎ jīng shén | Vitality of dragon & horse | Loading, energy states |
| 万事如意 | wàn shì rú yì | May all go as you wish | Welcome, onboarding |
| 恭喜发财 | gōng xǐ fā cái | Wishing you prosperity | Payment success, rewards |
| 一马当先 | yī mǎ dāng xiān | Taking the lead | First-place, achievement |
| 金玉满堂 | jīn yù mǎn táng | Gold and jade fill the hall | Dashboard, abundance |
| 年年有余 | nián nián yǒu yú | Surplus year after year | Savings, growth metrics |
| 吉星高照 | jí xīng gāo zhào | Lucky stars shine bright | Feature spotlight |
| 心想事成 | xīn xiǎng shì chéng | Wishes come true | Form submission success |
| 福 | fú | Fortune/Blessing | Icon, seal decoration |

---

## Component Patterns

### Cards & Containers — Red Envelope Panels

Inspired by **红包 (hóngbāo)** red envelopes, lantern shapes, and spring couplet scrolls. Cards should feel generous and auspicious—something you *want* to open.

```css
.card {
  background: #FFF8F0;
  border: 1px solid rgba(222, 41, 16, 0.1);
  border-radius: 8px;
  padding: 28px 32px;
  position: relative;
  box-shadow:
    0 2px 8px rgba(222, 41, 16, 0.06),
    0 8px 32px rgba(26, 10, 8, 0.08);
  overflow: hidden;
}

/* Gold fortune corner — like the clasp of a red envelope */
.card::after {
  content: '福';
  position: absolute;
  top: -2px;
  right: -2px;
  width: 36px;
  height: 36px;
  background: linear-gradient(135deg, #FFD700 0%, #DAA520 100%);
  color: #DE2910;
  font-size: 14px;
  font-weight: 700;
  font-family: 'Noto Serif SC', serif;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 0 8px 0 8px;
  box-shadow: -2px 2px 8px rgba(218, 165, 32, 0.3);
}

.card-hongbao {
  background: linear-gradient(175deg, #DE2910 0%, #C41E10 100%);
  color: #FFF8F0;
  border: 2px solid rgba(255, 215, 0, 0.3);
  border-radius: 12px;
  padding: 32px;
}

.card-hongbao::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 72px;
  height: 72px;
  background: rgba(255, 215, 0, 0.15);
  border: 2px solid rgba(255, 215, 0, 0.3);
  border-radius: 50%;
  /* Gold coin seal in center, like a hongbao clasp */
}

.card-couplet {
  background: #DE2910;
  color: #FFD700;
  border: none;
  border-radius: 4px;
  padding: 24px 20px;
  text-align: center;
  font-family: var(--font-display);
  box-shadow:
    inset 0 0 0 3px rgba(255, 215, 0, 0.25),
    0 4px 24px rgba(222, 41, 16, 0.2);
  writing-mode: vertical-rl;
  /* Spring couplet scroll style */
}

.card-lantern {
  background: radial-gradient(ellipse at top, #E8453A 0%, #DE2910 50%, #C41E10 100%);
  color: #FFD700;
  border-radius: 50% / 60%;
  padding: 40px 32px;
  text-align: center;
  box-shadow: 0 8px 40px rgba(222, 41, 16, 0.25);
  /* Lantern-shaped card for hero stats or highlights */
}

/* Firecracker border pattern */
.card-firecracker-border {
  border-image: repeating-linear-gradient(
    0deg,
    #DE2910 0px, #DE2910 8px,
    #FFD700 8px, #FFD700 10px
  ) 10;
  border-width: 3px;
  border-style: solid;
}
```

### Border Philosophy:
- Rounded corners (`8px-12px`) — softer, more festive than sharp temple geometry
- **Gold borders on red surfaces**, **red borders on light surfaces**
- Double-happiness (囍) motifs as decorative corner elements on featured cards
- Coin-circle motifs (○) for highlight badges

### Depth & Shadow:
- Shadows tinted warm red: `rgba(222, 41, 16, 0.08)` — lantern glow on surfaces
- Elevated cards get a **gold rim glow**: `0 0 20px rgba(255, 215, 0, 0.15)`
- Inner shadows for recessed areas: `inset 0 2px 8px rgba(26, 10, 8, 0.06)`

---

### Buttons & Interactive Elements — Firecracker Triggers

Buttons should feel like lighting a firecracker: a confident action that produces a satisfying burst.

```css
.button-primary {
  background: linear-gradient(135deg, #DE2910 0%, #C41E10 100%);
  color: #FFD700;
  border: 2px solid rgba(255, 215, 0, 0.4);
  border-radius: 8px;
  padding: 12px 32px;
  font-weight: 600;
  letter-spacing: 0.04em;
  transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  position: relative;
  overflow: hidden;
}

.button-primary::before {
  /* Gold shimmer sweep on hover */
  content: '';
  position: absolute;
  top: 0; left: -100%;
  width: 100%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,215,0,0.2), transparent);
  transition: left 0.5s ease;
}

.button-primary:hover::before {
  left: 100%;
}

.button-primary:hover {
  transform: translateY(-2px);
  box-shadow:
    0 4px 20px rgba(222, 41, 16, 0.25),
    0 0 40px rgba(255, 215, 0, 0.1);
  border-color: #FFD700;
}

.button-primary:active {
  transform: scale(0.97);
  box-shadow: 0 2px 8px rgba(222, 41, 16, 0.3);
}

.button-gold {
  background: linear-gradient(135deg, #FFD700 0%, #DAA520 100%);
  color: #8B1A10;
  border: none;
  border-radius: 8px;
  padding: 12px 32px;
  font-weight: 600;
}

.button-gold:hover {
  background: linear-gradient(135deg, #FFE44D 0%, #FFD700 100%);
  box-shadow: 0 4px 24px rgba(255, 215, 0, 0.3);
  transform: translateY(-2px);
}

.button-ghost {
  background: transparent;
  border: 1.5px solid rgba(222, 41, 16, 0.3);
  color: #DE2910;
  border-radius: 8px;
}

.button-ghost:hover {
  background: rgba(222, 41, 16, 0.06);
  border-color: #DE2910;
}

.button-fortune { /* Circular fortune coin button */
  background: linear-gradient(135deg, #FFD700, #DAA520);
  color: #8B1A10;
  border: 3px solid #DE2910;
  border-radius: 50%;
  width: 56px;
  height: 56px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-display);
  font-size: 20px;
  box-shadow:
    0 4px 16px rgba(255, 215, 0, 0.3),
    inset 0 0 0 4px rgba(139, 26, 16, 0.15);
  /* Square hole in center via inner shadow mimics ancient coins */
}

.button-fortune:hover {
  transform: rotate(15deg) scale(1.1);
  box-shadow: 0 6px 24px rgba(255, 215, 0, 0.4);
}
```

### Icon Buttons:
- Coin-shaped (circular with implied square center) or rounded rectangles
- Touch targets: **48px minimum** — generous like a red envelope
- Hover produces warm lantern glow: `background: rgba(222, 41, 16, 0.08)`

---

### Form Elements — Wishing Well Inputs

Forms are where users make their wishes (万事如意). Each field should feel like writing a wish on a red ribbon to hang on a wishing tree.

```css
.input {
  background: rgba(255, 248, 240, 0.8);
  border: 1.5px solid rgba(222, 41, 16, 0.12);
  border-radius: 8px;
  padding: 14px 20px;
  font-size: 16px;
  color: #1A0505;
  transition: all 0.3s ease;
}

.input:focus {
  outline: none;
  border-color: #DE2910;
  box-shadow:
    0 0 0 3px rgba(222, 41, 16, 0.1),
    0 0 20px rgba(255, 215, 0, 0.08);
}

.input-festive {
  background: rgba(255, 248, 240, 0.9);
  border: 2px solid rgba(255, 215, 0, 0.3);
  border-radius: 8px;
  padding: 14px 20px;
}

.input-festive:focus {
  border-color: #FFD700;
  box-shadow: 0 0 0 3px rgba(255, 215, 0, 0.15);
}

.label {
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.06em;
  color: #8B1A10;
  margin-bottom: 6px;
}

.checkbox {
  width: 22px;
  height: 22px;
  border: 2px solid rgba(222, 41, 16, 0.25);
  border-radius: 4px;
  accent-color: #DE2910;
}

.checkbox:checked {
  background: #DE2910;
  border-color: #DE2910;
  /* Checkmark in gold */
}

.select {
  background: rgba(255, 248, 240, 0.9);
  border: 1.5px solid rgba(222, 41, 16, 0.15);
  border-radius: 8px;
  padding: 12px 16px;
  color: #1A0505;
}
```

### Focus States — Lantern Glow:
- Red glow ring: `box-shadow: 0 0 0 3px rgba(222, 41, 16, 0.12)`
- Gold shimmer variant for premium inputs: `box-shadow: 0 0 0 3px rgba(255, 215, 0, 0.15)`
- Border transitions from muted to vivid red/gold

---

### Status & Feedback — Fortune Indicators

```css
.badge {
  display: inline-flex;
  padding: 4px 14px;
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  border-radius: 20px; /* Pill shape like a lucky coin */
  background: rgba(222, 41, 16, 0.08);
  color: #DE2910;
}

.badge-fortune {
  background: linear-gradient(135deg, rgba(255,215,0,0.15), rgba(218,165,32,0.15));
  color: #B8860B;
  border: 1px solid rgba(255, 215, 0, 0.3);
}

.badge-critical {
  background: rgba(139, 26, 16, 0.1);
  color: #8B1A10;
  border-left: 3px solid #8B1A10;
  border-radius: 4px;
}

.badge-success {
  background: rgba(46, 139, 87, 0.1);
  color: #2E8B57;
  border-left: 3px solid #2E8B57;
  border-radius: 4px;
}

.badge-warning {
  background: rgba(255, 140, 0, 0.1);
  color: #FF8C00;
  border-left: 3px solid #FF8C00;
  border-radius: 4px;
}

.progress-bar {
  height: 6px;
  background: rgba(222, 41, 16, 0.08);
  border-radius: 3px;
  overflow: hidden;
}

.progress-fill {
  background: linear-gradient(90deg, #DE2910, #FFD700);
  border-radius: 3px;
  position: relative;
}

/* Galloping sparkle effect on progress */
.progress-fill::after {
  content: '';
  position: absolute;
  right: 0; top: 0;
  width: 20px; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4));
  animation: gallop-shimmer 1.5s infinite;
}

.toast-fortune {
  background: linear-gradient(135deg, #DE2910, #C41E10);
  color: #FFD700;
  border: 1px solid rgba(255, 215, 0, 0.3);
  border-radius: 12px;
  padding: 16px 24px;
  box-shadow: 0 8px 40px rgba(222, 41, 16, 0.25);
}

.toast-dark {
  background: #1A0A08;
  color: #FFF8F0;
  border-left: 4px solid #FFD700;
  border-radius: 8px;
  padding: 16px 24px;
  box-shadow: 0 8px 32px rgba(26, 10, 8, 0.4);
}
```

---

## Layout Principles — 团圆 (Tuányuán) — Reunion Gathering

### Spacing Scale:
`4, 8, 12, 16, 24, 32, 48, 64, 80, 96px`

More compact than meditative layouts—New Year is about **abundance and gathering**. Elements cluster together like family around a round table, but still breathe.

### Grid Philosophy:
- **Round table layouts** — centered groupings, radial arrangements for dashboards
- **Bilateral symmetry** for hero sections and banners (like spring couplets flanking a door)
- **Dense but organized** — like a feast table: many dishes, all arranged with care
- Maximum content width: **1200px** for applications, **800px** for reading
- Embrace fullwidth red/gold banner sections that span edge-to-edge

### Visual Weight Distribution:

```
┌──────────────────────────────────────┐
│ ████████████████████████████████████ │  ← Full-width red banner with gold text (春联)
│                                      │
│        🏮  Fortune Card  🏮         │  ← Central hero, flanked by lantern accents
│                                      │
│   ┌──────┐  ┌──────┐  ┌──────┐     │  ← Triple-card grid (福禄寿 — fortune, status, longevity)
│   │  福  │  │  禄  │  │  寿  │     │
│   └──────┘  └──────┘  └──────┘     │
│                                      │
│ ═══════════ 金 ═══════════          │  ← Gold divider with character
│                                      │
│       ┌──────────────────┐          │  ← Content area, generous but warm
│       │                  │          │
│       └──────────────────┘          │
└──────────────────────────────────────┘
```

### Dividers & Separators:
- Gold line: `1px solid rgba(255, 215, 0, 0.3)` — the primary divider
- Red dashed: `1px dashed rgba(222, 41, 16, 0.2)` — secondary, playful
- **Decorative divider**: A small centered character (福, ◇, or ⬥) flanked by gold lines
- Firecracker string pattern for festive section breaks

---

## Interaction Design — Galloping Fire (飞马奔腾)

### Transition Timing:

```css
--ease-gallop: cubic-bezier(0.34, 1.56, 0.64, 1);    /* Bouncy, energetic, horse-like */
--ease-firecracker: cubic-bezier(0.16, 1, 0.3, 1);   /* Quick burst, natural settle */
--ease-lantern: cubic-bezier(0.25, 0.46, 0.45, 0.94); /* Gentle sway, warm arrival */
--ease-fortune: cubic-bezier(0.68, -0.55, 0.27, 1.55); /* Anticipation + overshoot */

--duration-spark: 0.15s;
--duration-quick: 0.25s;
--duration-medium: 0.4s;
--duration-celebration: 0.6s;
```

### Hover Philosophy:
- **Warm lantern glow** appears: `background: rgba(222, 41, 16, 0.06)`
- **Upward bounce**: `transform: translateY(-3px)` — energetic lift, not subtle drift
- Gold shimmer sweep on premium elements
- Elements feel alive, responsive, eager — like a horse responding to its rider

### Animations:

```css
@keyframes gallop-bounce {
  0%, 100% { transform: translateY(0); }
  25% { transform: translateY(-4px); }
  50% { transform: translateY(-1px); }
  75% { transform: translateY(-6px); }
}

@keyframes lantern-sway {
  0%, 100% { transform: rotate(-2deg); }
  50% { transform: rotate(2deg); }
}

@keyframes firecracker-burst {
  0% { transform: scale(0.8); opacity: 0; }
  50% { transform: scale(1.15); opacity: 1; }
  100% { transform: scale(1); opacity: 1; }
}

@keyframes gold-shimmer {
  0% { background-position: -200% center; }
  100% { background-position: 200% center; }
}

@keyframes fortune-reveal {
  0% { transform: rotateY(90deg); opacity: 0; }
  60% { transform: rotateY(-10deg); opacity: 1; }
  100% { transform: rotateY(0deg); opacity: 1; }
}

@keyframes ember-pulse {
  0%, 100% { box-shadow: 0 0 8px rgba(222, 41, 16, 0.15); }
  50% { box-shadow: 0 0 24px rgba(222, 41, 16, 0.3); }
}

@keyframes confetti-fall {
  0% { transform: translateY(-10px) rotate(0deg); opacity: 1; }
  100% { transform: translateY(30px) rotate(360deg); opacity: 0; }
}

@keyframes gallop-shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(200%); }
}

/* Loading: galloping horse dots */
@keyframes horse-gallop-loader {
  0%, 80%, 100% { transform: scale(0.6); opacity: 0.3; }
  40% { transform: scale(1); opacity: 1; }
}
```

### Loading States:
- **Galloping dots** — three dots animating in sequence like hoofbeats
- **Spinning coin** — gold coin rotating with fortune character
- **Lantern pulse** — red glow breathing in and out
- Use proverb `龙马精神` as loading text ("Summoning vitality...")

### Success States:
- **Firecracker burst** animation with gold sparks
- Toast shows `马到成功` ("Success upon arrival!")
- Brief gold shimmer washes across the completed element
- Optional: tiny confetti particles (gold & red) for major achievements

---

## Texture & Material References

### Festive Textures:

```css
.lantern-glow {
  background: radial-gradient(ellipse at center,
    rgba(222, 41, 16, 0.15) 0%,
    rgba(222, 41, 16, 0.05) 50%,
    transparent 70%);
}

.red-silk-surface {
  background: linear-gradient(135deg, #DE2910 0%, #C41E10 50%, #8B1A10 100%);
  background-size: 400% 400%;
  /* Optional: animate for subtle silk sheen */
}

.gold-foil-overlay {
  background-image: linear-gradient(
    135deg,
    rgba(255,215,0,0.05) 25%,
    rgba(255,215,0,0.1) 50%,
    rgba(255,215,0,0.05) 75%
  );
  background-size: 200% 200%;
  animation: gold-shimmer 3s ease infinite;
}

.rice-paper-texture {
  background-color: #FFF8F0;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='4' height='4'%3E%3Crect width='4' height='4' fill='%23FFF8F0'/%3E%3Crect width='1' height='1' x='2' y='1' fill='%23FEF0E0' opacity='0.4'/%3E%3C/svg%3E");
  background-size: 4px 4px;
}

.firecracker-string-border {
  border-image: repeating-linear-gradient(
    180deg,
    #DE2910 0px, #DE2910 6px,
    #FFD700 6px, #FFD700 8px,
    #DE2910 8px, #DE2910 14px
  ) 14;
}

/* Decorative cloud/fortune-cloud pattern */
.fortune-cloud-pattern {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 100'%3E%3Cpath d='M30 70 Q50 40 80 55 Q95 30 120 50 Q140 25 170 45 Q180 55 170 65 Q160 80 130 70 Q110 85 80 72 Q55 85 30 70Z' fill='none' stroke='%23FFD700' stroke-width='0.8' opacity='0.1'/%3E%3C/svg%3E");
  background-size: 200px 100px;
  background-repeat: repeat;
}

/* Horse silhouette watermark */
.horse-watermark {
  position: relative;
}
.horse-watermark::before {
  content: '馬';
  position: absolute;
  bottom: 16px;
  right: 16px;
  font-size: 120px;
  font-family: var(--font-display);
  color: rgba(222, 41, 16, 0.04);
  pointer-events: none;
  line-height: 1;
}
```

### Decorative Elements:

```css
.fu-seal {
  /* 福 character seal — red square with gold border */
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 32px;
  height: 32px;
  background: #DE2910;
  color: #FFD700;
  font-family: var(--font-display);
  font-size: 18px;
  font-weight: 700;
  border-radius: 4px;
  border: 2px solid rgba(255, 215, 0, 0.5);
  box-shadow: 0 2px 8px rgba(222, 41, 16, 0.2);
  transform: rotate(-3deg); /* Slightly tilted like a real stamp */
}

.gold-coin {
  /* Ancient coin decoration */
  width: 28px;
  height: 28px;
  background: linear-gradient(135deg, #FFD700, #DAA520);
  border-radius: 50%;
  box-shadow:
    inset 0 0 0 3px rgba(139, 26, 16, 0.2),
    0 2px 6px rgba(218, 165, 32, 0.3);
  /* Square hole would be represented by inner pseudo-element */
}

.lantern-icon {
  /* CSS lantern shape */
  width: 20px;
  height: 28px;
  background: radial-gradient(ellipse, #E8453A 40%, #DE2910 100%);
  border-radius: 50%;
  border: 1px solid rgba(255, 215, 0, 0.4);
  box-shadow: 0 0 12px rgba(222, 41, 16, 0.2);
}
```

---

## Iconography — Galloping Strokes

- **Stroke weight: 2px** — bolder than meditative styles; celebratory confidence
- **Rounded endpoints** — warm, friendly, festive (not sharp or clinical)
- Icon size: **20-24px** inline, **32-40px** standalone
- Prefer **filled icons** for primary actions (the red is the statement)
- Outlined icons for secondary/navigation

### Thematic Icon Motifs:
```
🏮 Lantern       — navigation, home, featured
🧧 Red envelope  — payment, rewards, gifts
🐴 Horse         — speed, achievement, branding
🎆 Fireworks     — celebration, success, completion
💰 Gold ingot    — wealth, savings, premium
🪙 Coin          — transaction, selection, value
🌸 Plum blossom  — spring, renewal, beauty
☁️ Fortune cloud — auspicious, decorative
🎐 Wind chime    — notifications, alerts
🔥 Fire/ember    — trending, hot, urgent
```

---

## Celebratory Character Details

1. **Red dominance, gold hierarchy**: Red is the canvas, gold is the calligraphy — red backgrounds with gold text for maximum festivity
2. **Fortune corners**: 福 character in card corners instead of cinnabar seals — every card is a blessing
3. **Lantern glow halos**: Key elements radiate warm red glow like paper lanterns — `box-shadow: 0 0 30px rgba(222, 41, 16, 0.12)`
4. **Coin-circle motifs**: Circular badges, buttons, and avatars echo ancient coins — wealth symbolism everywhere
5. **Spring couplet symmetry**: Hero banners styled as vertical red scrolls flanking the entrance — bilateral decoration
6. **Firecracker rhythm**: Interactions chain together with bouncy, staccato timing — pop-pop-pop energy
7. **Gold shimmer on achievement**: Success states trigger a gold light sweep across the element — 金光闪闪
8. **Horse watermarks**: Large, faint 馬 characters as background decoration on hero sections
9. **Abundance over restraint**: More color, more warmth, more layering than restrained themes — New Year is for excess
10. **Proverb integration**: Chinese fortune phrases woven into microcopy, toasts, and empty states — every interaction carries a blessing

---

## Recommended shadcn/ui Components

**Base Theme**: `theme-red` — override CSS variables to shift toward Lucky Red + Imperial Gold warmth.

```css
:root {
  --background: 30 100% 97%;       /* #FFF8F0 Rice Paper White */
  --foreground: 0 60% 6%;          /* #1A0505 Ink Black */
  --card: 28 100% 94%;             /* #FEF0E0 Dumpling Cream */
  --card-foreground: 0 60% 6%;
  --primary: 4 82% 47%;            /* #DE2910 Lucky Red */
  --primary-foreground: 30 100% 97%;
  --secondary: 51 100% 50%;        /* #FFD700 Imperial Gold */
  --secondary-foreground: 0 60% 20%;
  --accent: 43 79% 55%;            /* #F0C75E Silk Gold */
  --accent-foreground: 0 60% 6%;
  --muted: 25 60% 90%;             /* Smoke Blush lighter */
  --muted-foreground: 0 30% 35%;
  --destructive: 2 80% 30%;        /* #8B1A10 Ember Red */
  --destructive-foreground: 30 100% 97%;
  --border: 4 60% 88%;             /* Warm red-tinted border */
  --input: 4 30% 85%;
  --ring: 4 82% 47%;               /* Lucky Red ring */
  --radius: 0.5rem;                /* Softer, friendlier radius */
}

.dark {
  --background: 0 50% 7%;          /* #1A0A08 Night Sky */
  --foreground: 30 100% 97%;       /* #FFF8F0 Rice Paper White */
  --card: 350 40% 12%;             /* #2D1215 Charcoal Ember */
  --card-foreground: 30 100% 97%;
  --primary: 4 82% 47%;            /* #DE2910 Lucky Red */
  --primary-foreground: 51 100% 50%;  /* Gold text on red */
  --secondary: 51 100% 50%;        /* #FFD700 Imperial Gold */
  --secondary-foreground: 0 50% 7%;
  --accent: 43 79% 55%;
  --accent-foreground: 30 100% 97%;
  --muted: 350 30% 16%;
  --muted-foreground: 30 40% 65%;
  --border: 350 25% 20%;
  --input: 350 25% 20%;
  --ring: 51 100% 50%;             /* Gold ring in dark mode */
}
```

### 22 Component Styling Guide:

#### 1. Button (@shadcn/button)
Firecracker trigger. Red silk gradient with gold text; hover triggers gold shimmer sweep. Bouncy `--ease-gallop` transition. Gold variant for secondary actions. Ghost variant with red border glow on hover.

#### 2. Card (@shadcn/card)
Red envelope panel. Gold 福 corner badge via `::after`. Hongbao variant: full red gradient with gold coin center decoration. Light variant: Rice Paper with warm red border and fortune cloud watermark.

#### 3. Dialog (@shadcn/dialog)
Fortune reveal. Overlay uses firecracker smoke (`rgba(26, 10, 8, 0.6)`) with subtle red radial glow at center. Content panel: Rice Paper with gold top border. Entry animation: `fortune-reveal` (flip open like a red envelope). Close button: gold coin style.

#### 4. Navigation Menu (@shadcn/navigation-menu)
Festival banner navigation. Red gradient background for primary nav, gold text. Active item underlined with gold (not red). Dropdown panels: Rice Paper background with lantern glow accent. Items separated by gold dot dividers.

#### 5. Sidebar (@shadcn/sidebar)
Night Sky dark background with ember accents. Menu items in Rice Paper White. Active item: gold left border (3px) with subtle red background glow. Section headers in gold, small-caps, `letter-spacing: 0.08em`. Horse icon 🐴 as brand mark at top.

#### 6. Tabs (@shadcn/tabs)
Lantern tabs. Active tab: Lucky Red background with gold text (inverted). Inactive: transparent with Ember Red text. Tab transition uses `--ease-lantern`. Content area: Dumpling Cream background with soft top shadow.

#### 7. Accordion (@shadcn/accordion)
Fortune scroll unfurling. Trigger has gold coin icon (○) instead of chevron. Expanded content slides down with `--ease-firecracker`. Open item gets red left border accent. Content area has faint fortune cloud pattern.

#### 8. Input (@shadcn/input)
Wishing well field. Rounded corners (8px). Focus: red glow ring + gold border. Placeholder text in muted warm tone. Filled state shows subtle Rice Paper background warmth.

#### 9. Select (@shadcn/select)
Fortune picker. Trigger: gold bottom border accent. Dropdown: Rice Paper background, items gain lantern glow on hover. Selected item marked with small red dot (●) to the left. Coin icon for value indicator.

#### 10. Badge (@shadcn/badge)
Fortune tag. Pill-shaped (`border-radius: 20px`) by default. Red/gold gradient for featured items. Left-border accent for status variants. Fortune badge variant: gold shimmer background with Burnished Gold text.

#### 11. Alert / Alert Dialog (@shadcn/alert, @shadcn/alert-dialog)
Temple bell warning. Red gradient left border (4px) for critical. Gold left border for info. Background: Dumpling Cream, slightly warmer than cards. Alert Dialog uses fortune-reveal animation. Include thematic icon (🏮 or 🎐).

#### 12. Separator (@shadcn/separator)
Festival divider. Default: `1px solid rgba(255, 215, 0, 0.2)` (gold tint). Major section breaks: centered 福 or ◆ character flanked by gold lines. Firecracker-string pattern variant for celebratory sections.

#### 13. Form / Field / Label (@shadcn/form, @shadcn/field, @shadcn/label)
Offering arrangement. Labels in Ember Red, bold, with slight letter-spacing. Error messages in Firecracker Red with 🔥 icon. Success validation in Jade Green with ✓. Field groups: 20px minimum vertical spacing. Fortune-phrase helper text for encouragement.

#### 14. Avatar (@shadcn/avatar)
Gold coin frame. Circular with `3px solid #FFD700` border. Fallback: Lucky Red background with gold initials. Hover: ember-pulse animation on the gold border.

#### 15. Tooltip (@shadcn/tooltip)
Fortune whisper. Night Sky background, gold text. Rounded corners (8px). Subtle gold border. Entry: fade + slight scale from `--ease-firecracker`. Arrow matches dark background.

#### 16. Progress (@shadcn/progress)
Galloping path. Track: `rgba(222, 41, 16, 0.08)`. Fill: `linear-gradient(90deg, #DE2910, #FFD700)` — red to gold (effort → reward). Height: 6px (bolder than meditative). Shimmer sweep animation on the fill. Shows 马到成功 at 100%.

#### 17. Switch (@shadcn/switch)
Yin-yang fortune toggle. Unchecked: muted warm tone. Checked: Lucky Red track with gold thumb. Transition: `--ease-gallop` for satisfying bouncy snap. Thumb emits subtle ember glow when active.

#### 18. Table (@shadcn/table)
Feast registry. Header: Red gradient background with gold text. Row borders: faint gold (`rgba(255, 215, 0, 0.1)`). Alternating rows: Rice Paper White / Dumpling Cream. Hover: lantern glow background. Selected rows: gold left border accent.

#### 19. Scroll Area (@shadcn/scroll-area)
Scrollbar thumb: Coin Gold, rounded. Track: invisible. Thumb on hover: Lucky Red. Width: 8px. Smooth momentum scrolling.

#### 20. Sonner / Toast (@shadcn/sonner)
Fortune announcement. Default: Night Sky background with gold left border and gold text. Success variant: Red gradient with gold text, shows `马到成功`. Entry: slides up with `--ease-firecracker` + subtle ember glow. Auto-dismiss: 4s.

#### 21. Skeleton (@shadcn/skeleton)
Fortune loading state. Pulse between Smoke Blush and Dumpling Cream. Use galloping-dots animation for skeleton cards. Never cool gray — always warm. Can show faint 馬 watermark during extended loads.

#### 22. Dropdown Menu / Context Menu (@shadcn/dropdown-menu, @shadcn/context-menu)
Fortune selection. Rice Paper background with warm shadow. Items on hover: lantern glow red (`rgba(222, 41, 16, 0.06)`). Active items: gold dot indicator (●) left-aligned. Separator: faint gold line. Icons in Lucky Red.

---

## Block Pattern Recommendations:

| Pattern | Theme Application |
|---|---|
| **dashboard-01** | Reunion feast table layout; triple-card 福禄寿 stats in red/gold; horse watermark hero; fortune proverb banner |
| **sidebar-01** | Night Sky sidebar with gold accents; galloping horse brand mark; ember glow active states |
| **sidebar-07** | Floating red envelope sidebar; warm red shadow, gold header banner |
| **login-01** | Centered fortune gate; hong bao card style with gold coin seal; 恭喜发财 welcome text |
| **login-03** | Split: left panel as red silk surface with gold calligraphy proverb; right as Rice Paper form with lantern glow focus |

---

## Key Design Principles Summary

1. **福 as Foundation** — Fortune is the root emotion; every interaction should feel lucky, warm, and generous
2. **Red canvas, gold calligraphy** — Red is the ground; gold is the meaning written upon it; this hierarchy never inverts
3. **Horse momentum** — Interactions arrive with energy and resolve with triumph; bouncy, confident, forward-charging
4. **Abundance over austerity** — New Year celebrates excess; layer textures, use rich gradients, let gold flow freely
5. **Lantern warmth** — Every glow, shadow, and highlight is tinted warm (red or gold, never blue or cool gray)
6. **Coin geometry** — Circles dominate: pills, avatars, buttons, badges echo the shape of prosperity
7. **Firecracker rhythm** — Quick, chain-reaction timing; interactions cascade with pop-pop-pop energy
8. **Fortune in the details** — Chinese proverbs in microcopy, 福 seals on cards, horse watermarks in backgrounds
9. **Feast-table gathering** — Elements cluster generously like dishes on a reunion dinner table, organized but abundant
10. **Celebration is the default state** — No element should feel solemn; even errors are delivered warmly, with encouragement

---

> **马到成功，万事如意** — *Success gallops in, and all things go as you wish.*