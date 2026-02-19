## UI Design System: Tropical Jungle Theme

### Core Design Philosophy

Create an interface embodying **vibrant tropical energy** and **high-contrast drama** through the lens of the **jungle** -- celebrating the dense layering of exotic flora, the interplay of dappled light and deep shadow, and the intense saturation found only in equatorial ecosystems. Inspired by the lush canopy paintings of Henri Rousseau, Amazonian biodiversity, and the electric palette of toucans and orchids, UI components should feel alive with color, rooted in dark rich soil, and bursting through a canopy of shadow. The design honors the **understory** -- the layered depth beneath the canopy -- as the primary spatial metaphor.

**Guiding Principles:**
- **Exuberancia** -- Abundance; the jungle never does anything halfway, every surface teems with life
- **Contraste** -- High contrast; the sharp divide between sun-drenched canopy and shadowed forest floor
- **Estratificacion** -- Stratification; the jungle layers emergent, canopy, understory, and forest floor into distinct visual tiers
- **Vitalidad** -- Vitality; saturated color pulses with the energy of a living ecosystem
- **Enredadera** -- Entanglement; vines and roots connect disparate elements into one organic system
- **Resplandor** -- Radiance; bioluminescent glows and sun-piercing shafts of light punctuate the darkness

---

### Color Palette

**Dense Shade (Backgrounds):**
- **Canopy Shadow**: `#0D1B0F` -- the near-black of the deep forest floor at midnight
- **Undergrowth**: `#142418` -- dense fern shadow, primary surface background
- **Leaf Litter**: `#1C3422` -- decomposing organic matter, elevated surface background
- **Moss Bed**: `#243D2C` -- the soft green-black of moss on stone, card backgrounds
- **Humid Haze**: `rgba(13, 27, 15, 0.85)` -- atmospheric overlay, fog caught between trees

**Jungle Green (Primary):**
- **Emerald Canopy**: `#00A651` -- the vivid green of sunlit leaves, primary interactive color
- **Fern Frond**: `#2ECC71` -- bright young fern, success states and active indicators
- **Deep Vine**: `#1B7A3D` -- mature vine green, secondary buttons and borders
- **Chlorophyll**: `#34D058` -- the raw green of photosynthesis, links and highlights
- **Shadow Leaf**: `#0E5C2F` -- leaf in shade, pressed/active states

**Parrot Yellow (Action):**
- **Macaw Gold**: `#FFD600` -- the blazing chest of a golden macaw, primary call-to-action
- **Pollen Dust**: `#FFE44D` -- scattered pollen in a shaft of light, hover states
- **Firefly Glow**: `#FFC107` -- warm bioluminescent pulse, warnings and attention
- **Sunbeam**: `#FFEB3B` -- a single beam breaking through the canopy, focus rings

**Hibiscus Orange (Accent):**
- **Hibiscus Flame**: `#FF6B2C` -- the impossible orange of a jungle hibiscus, primary accent
- **Orchid Coral**: `#FF8A50` -- tropical orchid warmth, secondary accent
- **Toucan Beak**: `#FF5722` -- the sharp orange-red of a toucan's bill, destructive actions
- **Mango Flesh**: `#FFAB40` -- ripe mango interior, badges and tags

**Tropical Sky (Text & Light):**
- **Clearing Blue**: `#E0F7FA` -- the pale blue sky visible through a gap in the canopy, primary text on dark
- **Waterfall Mist**: `#B2EBF2` -- cool mist rising from a jungle waterfall, secondary text
- **Morpho Wing**: `#00BCD4` -- the iridescent blue of a Morpho butterfly, focus borders and highlights
- **Lagoon**: `#0097A7` -- deep jungle pool reflecting sky, link color
- **Storm Sky**: `#78909C` -- overcast tropical sky, disabled and muted text

**Material References:**
- Bioluminescent glow: `rgba(0, 255, 100, 0.15)`
- Wet leaf surface: `rgba(255, 255, 255, 0.08)`
- Dappled sunlight: `rgba(255, 214, 0, 0.12)`

---

### Typography

**Font Philosophy:** Text should feel carved into bark and illuminated by dappled sunlight -- bold, high-contrast, and unapologetically legible against dark backgrounds. Headings are broad-leafed and commanding; body text is clear and resilient like bamboo.

**Font Stack:**
```css
--font-primary: 'Montserrat', 'Helvetica Neue', -apple-system, sans-serif;
--font-body: 'Inter', 'Segoe UI', -apple-system, sans-serif;
--font-mono: 'Fira Code', 'JetBrains Mono', 'SF Mono', monospace;
--font-display: 'Dela Gothic One', 'Black Ops One', sans-serif;
```

**Type Scale:**
- **Display**: 32-40px, weight 700 (bold, commanding like an emergent tree above the canopy)
- **Heading**: 22-28px, weight 600
- **Section title**: 14-16px, weight 700, `letter-spacing: 0.08em` (uppercase, like species labels on a botanical plate)
- **Body**: 15-16px, weight 400, line-height 1.6
- **Small/Caption**: 12-13px, weight 500
- **Whisper**: 11px, `letter-spacing: 0.06em`, Storm Sky color

**Text Styling:**
- High contrast: light text on dark backgrounds is the default; `#E0F7FA` on `#142418`
- Headings may use `Macaw Gold` (`#FFD600`) for emphasis on dark surfaces
- Use weight hierarchy aggressively: 700 for headings, 400 for body, 500 for captions
- Slight text-shadow on headings for depth: `text-shadow: 0 1px 3px rgba(0, 0, 0, 0.5)`
- Accent text (labels, tags) may use `Hibiscus Flame` or `Fern Frond` directly

---

### Component Patterns

#### Cards & Containers -- *Jungle Terrarium*

Inspired by layered canopy strata and the vivid accent borders of tropical flowers against dark soil:

```css
.card {
  background: #1C3422;
  border: 2px solid rgba(0, 166, 81, 0.3);
  border-radius: 8px;
  padding: 24px 28px;
  box-shadow:
    0 4px 12px rgba(0, 0, 0, 0.4),
    0 1px 0 rgba(255, 255, 255, 0.04) inset;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  border-color: rgba(0, 166, 81, 0.6);
  box-shadow:
    0 8px 24px rgba(0, 0, 0, 0.5),
    0 0 20px rgba(0, 166, 81, 0.08);
}

.card-accent {
  border-left: 4px solid #FF6B2C;
  border-radius: 0 8px 8px 0;
}

.card-elevated {
  background: linear-gradient(170deg, #243D2C 0%, #1C3422 100%);
  border: 2px solid rgba(255, 214, 0, 0.15);
  box-shadow:
    0 8px 32px rgba(0, 0, 0, 0.6),
    inset 0 1px 0 rgba(255, 255, 255, 0.05);
}

.card-canopy {
  background: linear-gradient(180deg, #243D2C 0%, #142418 100%);
  border: 1px solid rgba(0, 166, 81, 0.2);
  border-top: 3px solid #00A651;
}
```

**Border Philosophy:**
- Use vivid 2px borders to separate components from the dark background -- the jungle needs clear boundaries
- Accent borders (`border-left` or `border-top`) act like bright flowers marking paths through the undergrowth
- Border-radius stays moderate (6-12px) -- organic but structured, like rounded river stones

**Depth & Shadow:**
- Shadows are deep and warm-black: `rgba(0, 0, 0, 0.4)` base
- Elevated cards cast longer shadows, mimicking the height of the canopy above the floor
- Subtle inner highlights (`inset 0 1px 0 rgba(255,255,255,0.05)`) simulate wet leaf sheen

---

#### Buttons & Interactive Elements -- *Tropical Blooms*

```css
.button-primary {
  background: linear-gradient(180deg, #FF6B2C 0%, #E65100 100%);
  color: #0D1B0F;
  border: none;
  border-radius: 8px;
  padding: 12px 24px;
  font-weight: 600;
  font-size: 14px;
  letter-spacing: 0.02em;
  text-shadow: 0 1px 0 rgba(255, 255, 255, 0.15);
  box-shadow:
    0 2px 8px rgba(255, 107, 44, 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.2); /* Wet glossy highlight */
  transition: all 0.25s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.button-primary:hover {
  background: linear-gradient(180deg, #FF8A50 0%, #FF6B2C 100%);
  transform: translateY(-2px);
  box-shadow:
    0 6px 20px rgba(255, 107, 44, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.25);
}

.button-primary:active {
  transform: translateY(0px);
  background: linear-gradient(180deg, #E65100 0%, #BF360C 100%);
  box-shadow:
    0 1px 4px rgba(255, 107, 44, 0.2),
    inset 0 2px 4px rgba(0, 0, 0, 0.2);
}

.button-action {
  background: linear-gradient(180deg, #FFD600 0%, #FFC107 100%);
  color: #0D1B0F;
  border: none;
  border-radius: 8px;
  padding: 12px 24px;
  font-weight: 700;
  box-shadow:
    0 2px 8px rgba(255, 214, 0, 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.3);
}

.button-action:hover {
  background: linear-gradient(180deg, #FFEB3B 0%, #FFD600 100%);
  transform: translateY(-2px);
  box-shadow:
    0 6px 20px rgba(255, 214, 0, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.35);
}

.button-ghost {
  background: transparent;
  border: 1.5px solid rgba(0, 166, 81, 0.4);
  color: #2ECC71;
  border-radius: 8px;
  padding: 12px 24px;
}

.button-ghost:hover {
  background: rgba(0, 166, 81, 0.1);
  border-color: #00A651;
  color: #34D058;
}

.button-destructive {
  background: linear-gradient(180deg, #FF5722 0%, #D84315 100%);
  color: #FFFFFF;
  box-shadow:
    0 2px 8px rgba(255, 87, 34, 0.3),
    inset 0 1px 0 rgba(255, 255, 255, 0.15);
}
```

**Glossy "Wet Look" Effect:**
- All primary buttons use `inset 0 1px 0 rgba(255, 255, 255, 0.2)` for a wet-leaf sheen
- Gradients run top-to-bottom, lighter at top, simulating overhead light on a glossy surface
- Hover amplifies the gloss highlight and lifts the element

**Icon Buttons:**
- Circular with vivid backgrounds: `width: 40px; height: 40px; border-radius: 50%`
- Minimum touch target: 44px
- Hover reveals a bioluminescent glow: `box-shadow: 0 0 12px rgba(0, 166, 81, 0.3)`

---

#### Form Elements -- *Vine Inputs*

```css
.input {
  background: rgba(13, 27, 15, 0.6);
  border: 1.5px solid rgba(0, 166, 81, 0.3);
  border-radius: 8px;
  padding: 12px 16px;
  font-size: 15px;
  color: #E0F7FA;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

.input::placeholder {
  color: #78909C;
}

.input:focus {
  outline: none;
  border-color: #00BCD4;
  box-shadow:
    0 0 0 3px rgba(0, 188, 212, 0.15),
    0 0 12px rgba(0, 188, 212, 0.1);
}

.input:hover:not(:focus) {
  border-color: rgba(0, 166, 81, 0.5);
}

.input-error {
  border-color: #FF5722;
  box-shadow: 0 0 0 3px rgba(255, 87, 34, 0.12);
}

.input-success {
  border-color: #2ECC71;
  box-shadow: 0 0 0 3px rgba(46, 204, 113, 0.12);
}

.select {
  background: rgba(13, 27, 15, 0.6);
  border: 1.5px solid rgba(0, 166, 81, 0.3);
  border-radius: 8px;
  padding: 12px 40px 12px 16px;
  color: #E0F7FA;
  appearance: none;
  background-image: url("data:image/svg+xml,..."); /* Custom jungle-green chevron */
}

.checkbox {
  width: 20px;
  height: 20px;
  border: 2px solid rgba(0, 166, 81, 0.4);
  border-radius: 4px;
  background: rgba(13, 27, 15, 0.6);
  /* Checked state: vivid green fill with white checkmark */
}

.checkbox:checked {
  background: #00A651;
  border-color: #00A651;
}

.label {
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.04em;
  color: #B2EBF2;
  margin-bottom: 6px;
}
```

**Focus State Philosophy:**
- Jungle green borders transform to Morpho Wing blue (`#00BCD4`) on focus -- like a butterfly landing on a vine
- Focus glow is cool-toned to contrast the warm greens, creating immediate visual feedback
- Error states use Toucan Beak (`#FF5722`); success uses Fern Frond (`#2ECC71`)

---

#### Status & Feedback -- *Jungle Signals*

```css
.badge {
  display: inline-flex;
  align-items: center;
  padding: 4px 10px;
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  border-radius: 4px;
  background: rgba(0, 166, 81, 0.15);
  color: #2ECC71;
}

.badge-warning {
  background: rgba(255, 214, 0, 0.15);
  color: #FFD600;
}

.badge-critical {
  background: rgba(255, 87, 34, 0.15);
  color: #FF6B2C;
}

.badge-info {
  background: rgba(0, 188, 212, 0.15);
  color: #00BCD4;
}

.badge-success {
  background: rgba(46, 204, 113, 0.15);
  color: #2ECC71;
}

.progress-bar {
  height: 6px;
  background: rgba(0, 166, 81, 0.15);
  border-radius: 3px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #1B7A3D, #00A651, #2ECC71);
  border-radius: 3px;
  box-shadow: 0 0 8px rgba(0, 166, 81, 0.3);
  transition: width 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.toast {
  background: #243D2C;
  border: 1.5px solid rgba(0, 166, 81, 0.3);
  border-left: 4px solid #2ECC71;
  border-radius: 8px;
  color: #E0F7FA;
  padding: 14px 18px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
}

.toast-error {
  border-left-color: #FF5722;
}

.toast-warning {
  border-left-color: #FFD600;
}
```

---

### Layout Principles -- *Canopy Stratification*

**Spacing Scale:**
`4, 8, 12, 16, 24, 32, 48, 64, 96px`

Use moderate spacing. The jungle is dense; elements live close together but are separated by vivid borders and contrasting colors rather than vast white space. Visual separation comes from color contrast, not distance.

**Grid Philosophy:**
- Dense, layered layouts over minimalist sparse ones
- Sidebar + content is a natural pattern (understory beside the main trail)
- Dashboard grids pack information tightly with accent borders as dividers
- Maximum content width: 720px for reading, 1280px for applications

**Visual Weight Distribution:**
```
+--------------------------------------------+
| [Logo]  Nav  Nav  Nav          [User] [CTA] |  <- Canopy: navigation bar, always visible
|---------------------------------------------|
| Sidebar  |  Main Content Area               |  <- Understory: sidebar filters/nav
| [Tree]   |  +--------+  +--------+          |
| [Tree]   |  | Card   |  | Card   |          |  <- Forest Floor: content cards
| [Tree]   |  +--------+  +--------+          |
| [Tree]   |  +--------+  +--------+          |
|          |  | Card   |  | Card   |          |
+--------------------------------------------+
```

**Dividers & Separators:**
- Vivid thin lines: `1px solid rgba(0, 166, 81, 0.15)` -- like vine tendrils connecting sections
- Thicker accent separators for major sections: `2px solid rgba(255, 107, 44, 0.2)`
- Background color shifts between sections (alternating `#142418` and `#1C3422`) for natural stratification

---

### Interaction Design -- *Jungle Rhythms*

**Transition Timing:**
```css
--ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);
--ease-smooth: cubic-bezier(0.25, 0.46, 0.45, 0.94);
--ease-snap: cubic-bezier(0.68, -0.55, 0.27, 1.55); /* Quick, organic snap like a closing Venus flytrap */
--ease-grow: cubic-bezier(0.22, 1, 0.36, 1); /* Gradual unfurl, like a fern opening */
--duration-fast: 0.15s;
--duration-medium: 0.25s;
--duration-slow: 0.4s;
--duration-dramatic: 0.6s;
```

**Hover Philosophy:**
- Elements brighten on hover, simulating a shaft of sunlight moving across the forest floor
- Border colors intensify: opacity steps from `0.3` to `0.6`
- Subtle lift with shadow increase: `transform: translateY(-2px)` paired with deeper shadow
- Bioluminescent glow appears on interactive elements: `box-shadow: 0 0 16px rgba(0, 166, 81, 0.15)`

**Loading States:**
- Pulsing leaf-green glow, like bioluminescence in the undergrowth
- Vine-drawing animation: a curling tendril SVG path that fills progressively
- Skeleton screens use `#1C3422` base with `#243D2C` shimmer -- moss growing over stone

```css
@keyframes jungle-pulse {
  0%, 100% { opacity: 0.5; box-shadow: 0 0 8px rgba(0, 166, 81, 0.1); }
  50% { opacity: 1; box-shadow: 0 0 20px rgba(0, 166, 81, 0.3); }
}

@keyframes vine-grow {
  0% { stroke-dashoffset: 100%; }
  100% { stroke-dashoffset: 0%; }
}

@keyframes shimmer-moss {
  0% { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

.skeleton {
  background: linear-gradient(
    90deg,
    #1C3422 25%,
    #243D2C 50%,
    #1C3422 75%
  );
  background-size: 200% 100%;
  animation: shimmer-moss 1.8s ease-in-out infinite;
  border-radius: 6px;
}

@keyframes firefly-drift {
  0%, 100% {
    opacity: 0;
    transform: translate(0, 0) scale(0.8);
  }
  20% { opacity: 1; }
  80% { opacity: 0.6; }
  100% {
    opacity: 0;
    transform: translate(30px, -20px) scale(1.2);
  }
}
```

---

### Texture & Material References

**Jungle Textures:**
- Subtle noise overlay on dark backgrounds: `opacity: 0.03` -- the grain of bark and soil
- Glossy wet-leaf highlights on buttons and elevated cards via `inset` box-shadows
- Dappled light pattern: soft radial gradient spots at `opacity: 0.04` scattered on hero sections

**Tropical-Inspired Patterns:**
- Canopy light: radial gradients simulating sun piercing through leaves on overlay backgrounds
- Wet surface reflections: thin `inset` highlight lines on top edges of cards
- Dense shadow layering: multiple `box-shadow` values stacked for realistic depth

```css
.dappled-light {
  background:
    radial-gradient(ellipse at 20% 30%, rgba(255, 214, 0, 0.06) 0%, transparent 50%),
    radial-gradient(ellipse at 70% 60%, rgba(255, 214, 0, 0.04) 0%, transparent 40%),
    radial-gradient(ellipse at 50% 80%, rgba(0, 166, 81, 0.03) 0%, transparent 60%);
}

.wet-surface {
  position: relative;
}
.wet-surface::after {
  content: '';
  position: absolute;
  top: 0;
  left: 5%;
  right: 5%;
  height: 1px;
  background: linear-gradient(
    90deg,
    transparent 0%,
    rgba(255, 255, 255, 0.08) 30%,
    rgba(255, 255, 255, 0.12) 50%,
    rgba(255, 255, 255, 0.08) 70%,
    transparent 100%
  );
}

.bioluminescent-glow {
  background: radial-gradient(ellipse at center,
    rgba(0, 255, 100, 0.12) 0%,
    rgba(0, 255, 100, 0) 70%);
}

.bark-texture {
  background-image: url("data:image/svg+xml,..."); /* Subtle vertical grain pattern */
  background-size: 200px 200px;
  opacity: 0.02;
}
```

---

### Iconography -- *Jungle Silhouettes*

- Stroke-based icons, weight 2px -- bold and visible against dark backgrounds
- Filled variants preferred for small sizes (16px and below) to maintain legibility in shadow
- Round caps and joins -- organic, vine-like line quality
- Icon size: 18-24px inline, 28-36px standalone

**Style Reference:**
```
Standard:  [ ] O A
Jungle:    [*] @ A  (bold, filled, saturated in green or sky-blue)
```

Consider icons that feel alive and organic:
- Rounded terminals that suggest growth, like the tip of a new vine
- Consistent 2px stroke with occasional 2.5px for emphasis strokes
- Color: `#B2EBF2` (Waterfall Mist) default, `#00A651` (Emerald Canopy) for active states
- Hover color shift to `#FFD600` (Macaw Gold) for interactive icons

---

### Tropical Character Details

1. **Vivid accent borders**: Every card and container uses a `2px` colored border -- components must be visually distinct from the dark background, like flowers against bark
2. **Wet glossy overlays**: `inset 0 1px 0 rgba(255, 255, 255, 0.15)` on buttons and elevated elements -- humidity makes everything glisten
3. **Warm-over-cool contrast**: Orange and yellow accents sit on top of green and teal foundations -- the complementary color tension of the tropics
4. **Dappled light spots**: Subtle radial gradients at low opacity on large surfaces simulate sunlight filtering through leaves
5. **Bioluminescent focus**: Focus states glow with cool blue-green light, like jungle fungi in the dark
6. **Dense packing**: Elements sit closer together than in minimalist themes, separated by color rather than space -- the jungle is abundant
7. **Layered shadows**: Multiple shadow values create genuine depth, as if components exist at different strata of the canopy
8. **Living color**: No grays in success/error/warning states; all feedback colors are vivid and saturated -- nature does not do muted

---

### Recommended shadcn/ui Components

The following 22 components are mapped to the Tropical Jungle theme with specific CSS override guidance for each.

#### 1. **button**
The anchor of the theme. Apply the "wet look" glossy gradient treatment.
```
- Primary: orange gradient (#FF6B2C to #E65100) with inset gloss highlight
- Secondary: yellow gradient (#FFD600 to #FFC107) with dark text
- Ghost: transparent with 1.5px jungle-green border, green text
- Destructive: toucan-beak red (#FF5722) gradient
- All variants: border-radius 8px, font-weight 600
```

#### 2. **card**
Jungle Terrarium treatment. Dark background with vivid accent borders.
```
- Background: #1C3422 (Leaf Litter)
- Border: 2px solid rgba(0, 166, 81, 0.3)
- Hover: border intensifies to 0.6 opacity, deeper shadow
- Card-header text in Clearing Blue (#E0F7FA)
- Card-description in Waterfall Mist (#B2EBF2)
```

#### 3. **input**
Vine Input style. Dark semi-transparent background with green border shifting to sky-blue on focus.
```
- Background: rgba(13, 27, 15, 0.6)
- Border: 1.5px solid rgba(0, 166, 81, 0.3)
- Focus: border-color #00BCD4, glow ring rgba(0, 188, 212, 0.15)
- Text: #E0F7FA; placeholder: #78909C
```

#### 4. **dialog**
Overlay uses Humid Haze backdrop. Dialog surface is elevated card style.
```
- Overlay: rgba(13, 27, 15, 0.85) with backdrop-blur: 4px
- Surface: #243D2C with 2px #00A651 border
- Title: #E0F7FA, weight 600
- Close button: ghost style with Waterfall Mist icon
```

#### 5. **dropdown-menu**
Dark surface with vivid hover states.
```
- Background: #1C3422; border: 1.5px solid rgba(0, 166, 81, 0.25)
- Item hover: background rgba(0, 166, 81, 0.12); text shifts to #2ECC71
- Separator: 1px solid rgba(0, 166, 81, 0.1)
- Border-radius: 8px; box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5)
```

#### 6. **badge**
Jungle Signals style. Translucent colored backgrounds with vivid text.
```
- Default: bg rgba(0, 166, 81, 0.15), text #2ECC71
- Warning: bg rgba(255, 214, 0, 0.15), text #FFD600
- Destructive: bg rgba(255, 87, 34, 0.15), text #FF6B2C
- Border-radius: 4px; font-weight 600; letter-spacing 0.06em
```

#### 7. **tabs**
Canopy stratification metaphor. Active tab is a sunlit clearing.
```
- Tab list border-bottom: 2px solid rgba(0, 166, 81, 0.15)
- Inactive tab: color #78909C
- Active tab: color #FFD600, border-bottom 2px solid #FFD600
- Hover: color #B2EBF2
- Tab content area: no additional border, seamless with background
```

#### 8. **sidebar**
Dense understory navigation. Dark with green accent indicators.
```
- Background: #0D1B0F (Canopy Shadow)
- Active item: bg rgba(0, 166, 81, 0.12), left-border 3px solid #00A651
- Hover item: bg rgba(0, 166, 81, 0.06)
- Section headers: #78909C, uppercase, letter-spacing 0.08em
- Separator: 1px solid rgba(0, 166, 81, 0.08)
```

#### 9. **select**
Mirrors input styling. Dropdown uses dropdown-menu treatment.
```
- Trigger: same as input (dark bg, green border, sky-blue focus)
- Custom chevron icon in Waterfall Mist color
- Selected value: #E0F7FA
- Placeholder: #78909C
```

#### 10. **table**
Data grid with row striping via alternating dark greens.
```
- Header: bg #142418, text #B2EBF2, font-weight 600, uppercase, letter-spacing 0.06em
- Even rows: bg #1C3422
- Odd rows: bg rgba(20, 36, 24, 0.5)
- Hover row: bg rgba(0, 166, 81, 0.08)
- Border: 1px solid rgba(0, 166, 81, 0.1) between rows
```

#### 11. **form** and **field**
Standard Vine Input rules apply. Labels use Waterfall Mist color.
```
- Label: #B2EBF2, font-size 13px, weight 600
- Description/helper text: #78909C, font-size 12px
- Error message: #FF6B2C, font-size 12px
- Field spacing: 20px gap between form fields
```

#### 12. **checkbox** and **switch**
Green-dominant toggle states.
```
- Checkbox unchecked: 2px border rgba(0, 166, 81, 0.4), bg transparent
- Checkbox checked: bg #00A651, border #00A651, white checkmark
- Switch track off: bg rgba(120, 144, 156, 0.3)
- Switch track on: bg #00A651
- Switch thumb: white with subtle shadow
```

#### 13. **progress**
Growing vine metaphor. Green gradient fill with glow.
```
- Track: bg rgba(0, 166, 81, 0.15), height 6px, border-radius 3px
- Fill: gradient #1B7A3D -> #00A651 -> #2ECC71
- Fill glow: box-shadow 0 0 8px rgba(0, 166, 81, 0.3)
```

#### 14. **alert**
Vivid left-border indicator with translucent backgrounds.
```
- Default: bg rgba(0, 166, 81, 0.08), border-left 4px solid #00A651
- Destructive: bg rgba(255, 87, 34, 0.08), border-left 4px solid #FF5722
- Warning: bg rgba(255, 214, 0, 0.08), border-left 4px solid #FFD600
- Border-radius: 8px; padding: 14px 18px
```

#### 15. **sonner** (toast)
Jungle Signals toast treatment. Slides in from bottom-right.
```
- Background: #243D2C; border: 1.5px solid rgba(0, 166, 81, 0.3)
- Accent left-border: 4px, color per severity
- Text: #E0F7FA; description: #B2EBF2
- Shadow: 0 8px 32px rgba(0, 0, 0, 0.5)
- Close button: ghost, Waterfall Mist color
```

#### 16. **tooltip**
Small, dark, high-contrast popup.
```
- Background: #0D1B0F; border: 1px solid rgba(0, 166, 81, 0.2)
- Text: #E0F7FA; font-size 12px
- Border-radius: 6px; padding: 6px 10px
- Shadow: 0 4px 12px rgba(0, 0, 0, 0.5)
- Arrow inherits background color
```

#### 17. **navigation-menu**
Canopy-level navigation bar.
```
- Background: #0D1B0F; border-bottom: 1px solid rgba(0, 166, 81, 0.15)
- Link color: #B2EBF2; hover: #E0F7FA
- Active link: #FFD600 with underline
- Dropdown content: uses dropdown-menu styling
- Padding: 0 24px; height: 56px
```

#### 18. **accordion**
Collapsible sections for dense content organization.
```
- Trigger: text #E0F7FA, hover bg rgba(0, 166, 81, 0.06)
- Chevron: #78909C, rotates 180deg on open with --ease-grow timing
- Border between items: 1px solid rgba(0, 166, 81, 0.1)
- Content area: padding 16px 0; color #B2EBF2
```

#### 19. **avatar**
User identity in the jungle.
```
- Border: 2px solid rgba(0, 166, 81, 0.4)
- Fallback background: #1B7A3D; text: #E0F7FA
- Sizes: sm 32px, md 40px, lg 56px
- Hover: border-color #00A651
```

#### 20. **skeleton**
Moss-shimmer loading placeholder.
```
- Base: #1C3422
- Shimmer: linear-gradient(90deg, #1C3422, #243D2C, #1C3422)
- Animation: shimmer-moss 1.8s ease-in-out infinite
- Border-radius: 6px
```

#### 21. **separator**
Vine-line divider.
```
- Horizontal: 1px solid rgba(0, 166, 81, 0.12)
- For emphasis: 2px solid rgba(255, 107, 44, 0.15)
- Margin: 16px 0 (horizontal), 0 16px (vertical)
```

#### 22. **scroll-area**
Styled scrollbar for the jungle theme.
```
- Scrollbar track: transparent
- Scrollbar thumb: rgba(0, 166, 81, 0.25); hover: rgba(0, 166, 81, 0.4)
- Thumb border-radius: 4px; width: 6px
- Corner: transparent
```

---

### Key Design Principles Summary

1. **Contraste as Clarity** -- High contrast between vivid accents and dark backgrounds is not decoration; it is the primary mechanism for readability and hierarchy
2. **Vivid Borders, Not Empty Space** -- Where minimalist themes use whitespace to separate, the jungle uses 2px colored borders; components are distinct flowers on dark bark
3. **Wet Glossy Surfaces** -- Every elevated interactive element carries an `inset` highlight that simulates humidity and living surfaces
4. **Canopy Stratification** -- Layout layers from darkest (sidebar, `#0D1B0F`) to lightest (card surfaces, `#243D2C`), mimicking the light gradient from forest floor to canopy
5. **Complementary Tension** -- Orange/yellow accents on green/teal foundations create the same visual electricity found in tropical birds and flowers
6. **Bioluminescent Focus** -- Focus states glow with cool Morpho blue (`#00BCD4`), distinct from the warm greens and oranges, making focused elements unmistakable
7. **Dense Abundance** -- The jungle is rich and full; pack information densely and use color to organize rather than empty space
8. **Living Feedback** -- Status colors are always vivid and saturated; muted grays are reserved only for disabled and placeholder states
9. **Organic Motion** -- Animations use spring and grow easings (`cubic-bezier(0.34, 1.56, 0.64, 1)`) that feel alive, never mechanical
10. **Dark-First Design** -- The dark background is the foundation, the soil from which everything grows; light themes are not an option, they are a different biome entirely

---

*"The jungle is not a place you visit. It is a place that enters you -- through the eyes first, then through the skin."* -- Adapted from Alex Shoumatoff