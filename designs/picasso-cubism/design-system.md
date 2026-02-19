## UI Design System: Picasso / Cubism Inspired Theme

### Core Design Philosophy

Create an interface embodying **Cubist deconstruction** and **analytical abstraction** -- celebrating the simultaneous presentation of multiple perspectives, the fragmentation of form, and the bold assertion of geometric structure. Inspired by Picasso's analytical and synthetic cubism, Braque's papiers colles, and Juan Gris's crystalline compositions, UI components should feel like collaged planes of color overlapping on a studio canvas. The design embraces **rupture** -- the deliberate breaking of conventional visual harmony to reveal deeper structural truth. Traditional UI grids are shattered and reassembled into compositions that are asymmetrical, confrontational, and alive.

**Guiding Principles:**
- **Simultaneite** -- Show multiple facets at once; a card is not one surface but layered planes
- **Passage** -- Let edges dissolve between adjacent forms; boundaries are suggestions, not walls
- **Facettage** -- Break surfaces into geometric facets; nothing is smooth or uniform
- **Collage** -- Mix media, textures, and weights as if pasting cut paper onto canvas
- **Deformation** -- Stretch, skew, and distort with purpose; perfection is the enemy of expression
- **Planarity** -- Flatten depth into overlapping planes; shadows are shapes, not effects

---

### Color Palette

**Canvas Ground (Backgrounds):**
- **Raw Canvas**: `#F2E8D5` -- unprimed linen, the studio surface on which all forms rest
- **Aged Gesso**: `#E8DCC8` -- slightly warmer, the prepared ground of a working painting
- **Studio Dust**: `#DDD0B8` -- deeper warmth for secondary surfaces and recessed areas
- **Parchment Shadow**: `rgba(60, 42, 18, 0.05)` -- atmospheric layering, dust in studio light

**Charcoal Sketch (Primary Palette):**
- **Iron Gall Ink**: `#1A1A1A` -- the deepest mark, primary text and dominant outlines
- **Charcoal Block**: `#2D2D2D` -- dense charcoal, strong structural elements
- **Graphite Mid**: `#5C5C5C` -- mid-tone sketch lines, secondary text
- **Pencil Ghost**: `#9A9A9A` -- light construction lines, tertiary elements
- **Chalk Dust**: `#C4C4C4` -- faintest marks, disabled states and whisper text

**Bullfighter Red (Action):**
- **Matador**: `#C8102E` -- full-blooded red, primary action color, the cape in motion
- **Terracotta**: `#A8301A` -- darker red-brown, pressed/active states
- **Rose Sketch**: `rgba(200, 16, 46, 0.10)` -- red wash for subtle backgrounds and hover states
- **Blush Canvas**: `rgba(200, 16, 46, 0.04)` -- barely-there red tint for large surfaces

**Blue Period (Accent):**
- **Melancholy Blue**: `#1B3A5C` -- deep Picasso blue, for accent elements and secondary actions
- **Cerulean Sketch**: `#2E6B9E` -- brighter blue for interactive highlights
- **Blue Wash**: `rgba(27, 58, 92, 0.10)` -- blue tint for secondary backgrounds
- **Pale Period**: `rgba(27, 58, 92, 0.04)` -- whisper of blue for large areas

**Palette Accents (Used Sparingly):**
- **Ochre Yellow**: `#D4A017` -- warm yellow from synthetic cubism, for warnings and highlights
- **Olive Still-Life**: `#6B7C3E` -- muted green of a studio still-life, for success states
- **Newsprint Tan**: `#B8A88A` -- color of pasted newspaper fragments, for tags and metadata

**Material References:**
- Layered paper edge: `rgba(60, 42, 18, 0.12)`
- Charcoal smudge: `rgba(26, 26, 26, 0.06)`
- Studio varnish: `rgba(210, 190, 140, 0.3)`

---

### Typography

**Font Philosophy:** Text should feel like typeset letters cut from newspapers and reassembled on canvas -- mixing the authority of classical serifs with the mechanical precision of geometric sans-serifs. Headers are declarative, almost sculptural. Body text is clean and functional, like printed type pasted into a collage.

**Font Stack:**
```css
--font-display: 'Playfair Display', 'Georgia', 'Times New Roman', serif;
--font-body: 'DM Sans', 'Helvetica Neue', 'Arial', sans-serif;
--font-mono: 'IBM Plex Mono', 'Courier New', monospace;
--font-accent: 'Archivo Black', 'Impact', sans-serif; /* For rare, bold labels */
```

**Type Scale:**
- **Display**: 36-48px, weight 900 (black, monumental, like a painted word on canvas)
- **Heading**: 24-32px, weight 700, `letter-spacing: -0.02em` (tight, compressed energy)
- **Section title**: 14-16px, weight 600, `letter-spacing: 0.14em`, `text-transform: uppercase`
- **Body**: 15-16px, weight 400, line-height 1.65
- **Small/Caption**: 12-13px, weight 500
- **Label**: 11px, weight 700, `letter-spacing: 0.10em`, `text-transform: uppercase`

**Text Styling:**
- Headers use serif font; body uses geometric sans-serif -- this contrast is essential
- Bold weights are encouraged for headers; use weight as a compositional tool
- Occasional text rotation for labels: `transform: rotate(-90deg)` or `transform: rotate(-3deg)`
- Mix sizes dramatically within a composition -- a 48px word next to 12px caption creates cubist tension
- Text color should primarily be Iron Gall Ink `#1A1A1A` on canvas backgrounds

---

### Component Patterns

#### Cards & Containers -- *Fractured Planes*

Inspired by overlapping paper planes in synthetic cubism. Each card is a facet of a larger composition, deliberately asymmetrical, with borders that assert their presence like charcoal outlines on canvas:

```css
.card {
  background: #F2E8D5;
  border: 3px solid #1A1A1A;
  border-radius: 2px 24px 2px 24px; /* Extreme asymmetry -- no two corners alike */
  padding: 24px 28px;
  box-shadow:
    6px 6px 0px 0px rgba(26, 26, 26, 0.08);
  position: relative;
}

.card-faceted {
  border-radius: 32px 2px 28px 2px; /* Reversed asymmetry -- the other facet */
  border-width: 3px 2px 4px 2px; /* Uneven, hand-drawn quality */
  background: #E8DCC8;
}

.card-collage {
  /* Layered plane effect -- slightly rotated, overlapping */
  border-radius: 4px 20px 8px 16px;
  border: 2px solid #1A1A1A;
  transform: rotate(-0.8deg);
  box-shadow:
    8px 8px 0px 0px #DDD0B8,
    12px 12px 0px 0px rgba(26, 26, 26, 0.06);
}

.card-blue-period {
  background: #1B3A5C;
  color: #F2E8D5;
  border: 3px solid #1A1A1A;
  border-radius: 2px 20px 2px 20px;
}
```

**Border Radius Philosophy:**
- Never use uniform roundness -- every corner must differ
- Pair near-sharp corners (2px) with dramatic curves (24-32px)
- Think of corners as facets of a cut gemstone, each angled differently
- Hardcode specific asymmetric values per component variant for consistency

**Depth & Shadow:**
- Shadows are flat and geometric, not diffused -- like cut paper casting a hard edge
- Offset shadows: `6px 6px 0px` creates the layered paper plane effect
- Double shadows suggest multiple overlapping planes
- No blur on primary shadows; cubism rejects atmospheric perspective

---

#### Buttons & Interactive Elements -- *Bold Marks*

```css
.button-primary {
  background: #C8102E;
  color: #F2E8D5;
  border: 3px solid #1A1A1A;
  border-radius: 2px 12px 2px 12px;
  padding: 14px 32px;
  font-family: var(--font-body);
  font-weight: 700;
  font-size: 14px;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  transition: all 0.15s cubic-bezier(0.25, 0.1, 0.25, 1);
  box-shadow: 4px 4px 0px 0px #1A1A1A;
}

.button-primary:hover {
  background: #A8301A;
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0px 0px #1A1A1A;
}

.button-primary:active {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0px 0px #1A1A1A;
}

.button-secondary {
  background: #F2E8D5;
  color: #1A1A1A;
  border: 3px solid #1A1A1A;
  border-radius: 12px 2px 12px 2px;
  padding: 14px 32px;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  box-shadow: 4px 4px 0px 0px #1A1A1A;
}

.button-secondary:hover {
  background: #E8DCC8;
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0px 0px #1A1A1A;
}

.button-ghost {
  background: transparent;
  border: 2px solid #1A1A1A;
  color: #1A1A1A;
  border-radius: 2px 8px 2px 8px;
  padding: 12px 24px;
  font-weight: 600;
}

.button-ghost:hover {
  background: rgba(26, 26, 26, 0.05);
  border-width: 3px;
  padding: 11px 23px; /* Compensate for border growth */
}

.button-blue {
  background: #1B3A5C;
  color: #F2E8D5;
  border: 3px solid #1A1A1A;
  border-radius: 2px 12px 2px 12px;
  box-shadow: 4px 4px 0px 0px #1A1A1A;
}
```

**Icon Buttons:**
- Square or angular shapes preferred over circles
- Heavy 3px borders with hard-offset shadows
- Touch targets: 44px minimum
- Hover shifts the shadow plane: `transform: translate(-2px, -2px)`

---

#### Form Elements -- *Sketch Lines*

```css
.input {
  background: #F2E8D5;
  border: 2px solid #1A1A1A;
  border-radius: 2px 10px 2px 10px;
  padding: 14px 18px;
  font-size: 15px;
  font-family: var(--font-body);
  color: #1A1A1A;
  transition: border-color 0.15s ease, box-shadow 0.15s ease;
}

.input:focus {
  outline: none;
  border-color: #C8102E;
  box-shadow: 3px 3px 0px 0px rgba(200, 16, 46, 0.15);
}

.input-blue-focus:focus {
  border-color: #1B3A5C;
  box-shadow: 3px 3px 0px 0px rgba(27, 58, 92, 0.15);
}

.input-underline {
  background: transparent;
  border: none;
  border-bottom: 3px solid #1A1A1A;
  border-radius: 0;
  padding: 12px 4px;
}

.input-underline:focus {
  border-bottom-color: #C8102E;
  box-shadow: none;
}

.checkbox {
  width: 22px;
  height: 22px;
  border: 3px solid #1A1A1A;
  border-radius: 2px 6px 2px 6px;
  background: #F2E8D5;
  /* Checkmark styled as a bold slash -- like a charcoal mark */
}

.checkbox:checked {
  background: #1A1A1A;
  /* White angular slash mark, not a smooth curve */
}

.select {
  border: 2px solid #1A1A1A;
  border-radius: 2px 10px 2px 10px;
  background: #F2E8D5;
  padding: 14px 18px;
  appearance: none;
  /* Custom angular chevron indicator */
}

.label {
  font-family: var(--font-body);
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #5C5C5C;
  margin-bottom: 6px;
}
```

**Focus States:**
- Bold color shifts, not subtle glows -- cubism is declarative, not atmospheric
- Border color transitions to Matador Red or Melancholy Blue
- Hard-offset shadow appears on focus: `3px 3px 0px`
- No soft outlines; focus is a structural change, not an aura

---

#### Status & Feedback -- *Palette Markers*

```css
.badge {
  display: inline-flex;
  padding: 4px 14px;
  font-family: var(--font-body);
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.10em;
  text-transform: uppercase;
  border: 2px solid #1A1A1A;
  border-radius: 2px 8px 2px 8px;
  background: #F2E8D5;
  color: #1A1A1A;
}

.badge-critical {
  background: #C8102E;
  color: #F2E8D5;
  border-color: #1A1A1A;
}

.badge-success {
  background: #6B7C3E;
  color: #F2E8D5;
  border-color: #1A1A1A;
}

.badge-warning {
  background: #D4A017;
  color: #1A1A1A;
  border-color: #1A1A1A;
}

.badge-info {
  background: #1B3A5C;
  color: #F2E8D5;
  border-color: #1A1A1A;
}

.progress-bar {
  height: 8px; /* Bold, visible -- not minimal */
  background: #DDD0B8;
  border: 2px solid #1A1A1A;
  border-radius: 2px 4px 2px 4px;
  overflow: hidden;
}

.progress-fill {
  background: #C8102E;
  height: 100%;
  /* No border-radius -- hard geometric edge against the bar */
}

.toast {
  background: #1A1A1A;
  color: #F2E8D5;
  border: 3px solid #1A1A1A;
  border-radius: 2px 16px 2px 16px;
  padding: 16px 24px;
  box-shadow: 6px 6px 0px 0px rgba(26, 26, 26, 0.12);
  font-weight: 600;
}
```

---

### Layout Principles -- *Shattered Grid*

**Spacing Scale:**
`4, 8, 12, 20, 32, 48, 72, 96, 128px`

Prefer dramatic contrasts -- tight groupings next to vast open areas. Cubism compresses and expands space deliberately.

**Grid Philosophy:**
- Deliberately break the 12-column grid; overlap elements, use irregular column spans
- Asymmetric layouts are mandatory -- centered symmetry is forbidden
- Overlap and layer: elements may partially obscure one another like collaged paper
- Slight rotations (-1deg to 1deg) on containers add cubist tension
- Maximum content width: 720px for reading, 1200px for applications

**Visual Weight Distribution:**
```
+-------------------------------+
|  +---------+                  |
|  | HEADER  |   +--------+    |
|  | (heavy) |   | accent |    |   <- Overlapping planes at different angles
|  +----+----+   +---+----+    |
|       |            |         |
|    +--+------------+--+      |
|    |   CONTENT PLANE  |      |   <- Main content, slightly off-axis
|    |   /tilted -0.5deg|      |
|    +------------------+      |
|              +----------+    |
|              | SIDE NOTE |   |   <- Secondary element, counterweight
|              +----------+    |
+-------------------------------+
```

**Dividers & Separators:**
- Bold lines: `3px solid #1A1A1A` -- separators are structural, not decorative
- Diagonal separators using CSS: `border-top: 3px solid #1A1A1A; transform: rotate(-1deg)`
- Or thick dashes: `border-top: 3px dashed #1A1A1A`
- Negative space gaps of 48-72px as alternative to lines

---

### Interaction Design -- *Angular Motion*

**Transition Timing:**
```css
--ease-cubist: cubic-bezier(0.25, 0.1, 0.25, 1);    /* Sharp, decisive movement */
--ease-snap: cubic-bezier(0.68, -0.55, 0.27, 1.55);  /* Overshoot then settle -- bold gesture */
--ease-cut: cubic-bezier(0.77, 0, 0.175, 1);          /* Quick cut, like a collage scissors */
--duration-instant: 0.1s;
--duration-quick: 0.15s;
--duration-medium: 0.25s;
--duration-deliberate: 0.4s;
```

**Hover Philosophy:**
- Elements shift on their plane: `transform: translate(-2px, -2px)` with shadow compensation
- Shadow grows to suggest the element lifting off the canvas
- Background color shifts are stark, not gradient -- immediate, like flipping a plane
- Borders may thicken: `2px -> 3px` for added weight

**Loading States:**
- Geometric shapes rotating and reassembling -- triangles, trapezoids, parallelograms
- Angular spinner composed of intersecting lines, not a smooth circle
- Skeleton screens use angular, faceted placeholder shapes instead of rounded rectangles
- A composition of planes sliding into position, assembling the interface

```css
@keyframes cubist-rotate {
  0% { transform: rotate(0deg) scale(1); }
  25% { transform: rotate(90deg) scale(0.9); }
  50% { transform: rotate(180deg) scale(1.05); }
  75% { transform: rotate(270deg) scale(0.95); }
  100% { transform: rotate(360deg) scale(1); }
}

@keyframes plane-shift {
  0%, 100% { transform: translate(0, 0) rotate(0deg); }
  25% { transform: translate(4px, -2px) rotate(1deg); }
  50% { transform: translate(-2px, 3px) rotate(-0.5deg); }
  75% { transform: translate(3px, 1px) rotate(0.8deg); }
}

@keyframes facet-pulse {
  0%, 100% { opacity: 0.3; clip-path: polygon(20% 0%, 80% 0%, 100% 100%, 0% 100%); }
  33% { opacity: 0.7; clip-path: polygon(0% 0%, 100% 0%, 80% 100%, 20% 100%); }
  66% { opacity: 1; clip-path: polygon(10% 0%, 90% 0%, 100% 100%, 0% 100%); }
}

@keyframes assemble {
  0% { transform: translateX(-20px) rotate(-5deg); opacity: 0; }
  60% { transform: translateX(3px) rotate(0.5deg); opacity: 1; }
  100% { transform: translateX(0) rotate(0deg); opacity: 1; }
}
```

**Page Transitions:**
- Elements slide in from different angles, assembling like a cubist composition
- Stagger entrance: each plane arrives 50-80ms after the previous
- Exit by fragmenting: elements scatter at different angles

---

### Texture & Material References

**Canvas & Paper Textures:**
- Linen canvas grain overlay: `opacity: 0.04` -- the painting surface is always present
- Newsprint dot pattern for metadata areas: halftone effect at low opacity
- Torn paper edges using CSS clip-path for decorative container edges

**Cubist Surface Treatments:**
```css
.canvas-grain {
  background-image: url("data:image/svg+xml,..."); /* Fine crosshatch pattern */
  /* Or use CSS noise: */
  background-image:
    repeating-linear-gradient(
      45deg,
      transparent,
      transparent 2px,
      rgba(60, 42, 18, 0.02) 2px,
      rgba(60, 42, 18, 0.02) 4px
    );
}

.collage-edge {
  /* Torn paper effect -- irregular container edge */
  clip-path: polygon(
    0% 2%, 3% 0%, 12% 1%, 25% 0%, 38% 2%, 50% 0%,
    62% 1%, 75% 0%, 88% 2%, 97% 0%, 100% 3%, 100% 98%,
    97% 100%, 88% 99%, 75% 100%, 62% 98%, 50% 100%,
    38% 99%, 25% 100%, 12% 98%, 3% 100%, 0% 97%
  );
}

.newspaper-overlay {
  /* Halftone dot pattern for collage areas */
  background-image: radial-gradient(
    circle, rgba(26, 26, 26, 0.08) 1px, transparent 1px
  );
  background-size: 4px 4px;
}

.varnish-glaze {
  /* Warm studio varnish over dark surfaces */
  background: linear-gradient(
    135deg,
    rgba(210, 190, 140, 0.08) 0%,
    transparent 50%
  );
}

.layered-planes {
  /* Multiple offset pseudo-elements to create depth */
  position: relative;
}
.layered-planes::before {
  content: '';
  position: absolute;
  inset: 4px -4px -4px 4px;
  background: #DDD0B8;
  border: 2px solid #1A1A1A;
  border-radius: 2px 20px 2px 20px;
  z-index: -1;
}
.layered-planes::after {
  content: '';
  position: absolute;
  inset: 8px -8px -8px 8px;
  background: #E8DCC8;
  border: 1px solid rgba(26, 26, 26, 0.15);
  border-radius: 2px 16px 2px 16px;
  z-index: -2;
}
```

---

### Iconography -- *Angular Constructions*

- Geometric, angular icons -- composed of straight lines and sharp angles
- Stroke weight: 2-3px, heavier than typical UI icons
- Squared-off terminals, not rounded -- like charcoal strokes on canvas
- Icon size: 20-24px inline, 32-40px standalone

**Style Reference:**
```
Standard:  [ ] O /\
Cubist:    [/] <> /|  (faceted, deconstructed, multi-perspective)
```

Consider icons that feel hand-constructed:
- Built from visible geometric primitives (triangles, trapezoids, parallelograms)
- Overlapping shapes rather than unified outlines
- Slight weight variation suggesting charcoal pressure differences
- Prefer Lucide icons with `stroke-width: 2.5` and `stroke-linecap: square`

---

### Cubist Imperfection Details

1. **Uneven borders**: `border-width: 3px 2px 4px 2px` -- hand-drawn charcoal line varies in pressure
2. **Micro-rotation**: `transform: rotate(-0.5deg)` on cards and containers -- nothing sits perfectly level on the studio easel
3. **Offset shadows with no blur**: `box-shadow: 5px 5px 0px #1A1A1A` -- flat shadow planes, not atmospheric effects
4. **Mixed border-radius extremes**: `2px 28px 4px 20px` -- aggressive asymmetry on every cornered element
5. **Overlapping elements**: Cards and sections intentionally overlap by 8-16px using negative margins -- planes intersecting
6. **Color block irregularity**: Accent color applied to only one edge or corner of a component, not uniformly: `border-left: 6px solid #C8102E`
7. **Torn clip-paths**: Containers with slightly irregular edges via CSS `clip-path`, mimicking torn collage paper
8. **Typography scale jumps**: Placing a 48px display heading directly above 12px caption text -- dramatic scale contrast is intentional

---

### Recommended shadcn/ui Components

The following 22 components are the most relevant for expressing the Picasso / Cubism theme. Each includes specific CSS override guidance.

#### 1. **button**
The cornerstone interactive element. Override with heavy 3px black borders, hard-offset box shadows (`4px 4px 0px 0px #1A1A1A`), and asymmetric border-radius (`2px 12px 2px 12px`). Use Matador Red `#C8102E` for primary variant, canvas background for secondary. Uppercase text with `letter-spacing: 0.06em`. Hover shifts the shadow plane via `translate(-2px, -2px)`. Active presses the element into the canvas via `translate(2px, 2px)` with reduced shadow.

#### 2. **card**
Override `border-radius` to extreme asymmetry: `2px 24px 2px 24px`. Apply 3px solid `#1A1A1A` border. Background is Raw Canvas `#F2E8D5`. Use flat offset shadows `6px 6px 0px 0px rgba(26, 26, 26, 0.08)`. For featured cards, add `::before` pseudo-element as a second offset plane behind the card.

#### 3. **input**
2px solid `#1A1A1A` border with asymmetric radius `2px 10px 2px 10px`. Background Raw Canvas. On focus, border shifts to `#C8102E` with hard shadow `3px 3px 0px 0px rgba(200, 16, 46, 0.15)`. No soft outline ring -- cubism demands hard edges.

#### 4. **badge**
2px solid `#1A1A1A` border, asymmetric radius `2px 8px 2px 8px`. 11px uppercase text, weight 700, wide letter-spacing. Use solid color fills for status variants: red for critical, olive for success, ochre for warning, blue for info. Always maintain the black border regardless of fill color.

#### 5. **dialog**
Override overlay to use `rgba(26, 26, 26, 0.6)` -- darker, more opaque than standard. Dialog panel gets 3px black border, asymmetric radius `4px 28px 4px 28px`, and a flat offset shadow `8px 8px 0px 0px rgba(26, 26, 26, 0.15)`. Background Raw Canvas. Consider a slight rotation `transform: rotate(-0.3deg)` for character.

#### 6. **tabs**
Tab triggers should use thick 3px bottom borders in `#1A1A1A` for the active state, with no border on inactive tabs. Active tab background shifts to `#F2E8D5` with the tab panel below. Use uppercase labels with `letter-spacing: 0.08em`. Tab list itself can have a bold `border-bottom: 3px solid #1A1A1A`.

#### 7. **table**
Override with heavy borders: `border: 2px solid #1A1A1A` on the outer table. Header row gets `background: #1A1A1A; color: #F2E8D5` -- full inversion. Body rows alternate between Raw Canvas and Aged Gesso. Cell borders use `1px solid rgba(26, 26, 26, 0.15)`. Header text is uppercase, weight 700.

#### 8. **separator**
Override to `3px solid #1A1A1A` for primary separators. For decorative variants, use `border-style: dashed`. Consider adding `transform: rotate(-0.5deg)` for visual tension. Muted separators use `2px solid #C4C4C4`.

#### 9. **alert**
3px black border with asymmetric radius `2px 16px 2px 16px`. Background varies by severity: `#F2E8D5` for default, Rose Sketch `rgba(200, 16, 46, 0.10)` for destructive, Blue Wash for info. Left accent border `6px solid` in the status color. Hard offset shadow for elevated alerts.

#### 10. **select**
Same border treatment as input: 2px black border, asymmetric radius. Dropdown panel gets 3px border, flat shadow, and Raw Canvas background. Selected item highlighted with `background: #1A1A1A; color: #F2E8D5`. Custom angular chevron indicator replacing the default.

#### 11. **sidebar**
Override with a bold `border-right: 3px solid #1A1A1A`. Background Aged Gesso `#E8DCC8`. Navigation items use thick left-border indicators (`4px solid #C8102E`) for active state. Section headers in uppercase with wide tracking. Consider the sidebar as a separate "plane" of the composition.

#### 12. **accordion**
Trigger text in serif font (Playfair Display) for contrast with body content. 2px bottom border per item. Chevron icon replaced with an angular indicator -- a triangle or slash mark. Open state: content slides in with the `assemble` animation. Border between items uses `2px solid rgba(26, 26, 26, 0.15)`.

#### 13. **checkbox**
Override to 3px black border, asymmetric radius `2px 6px 2px 6px`, 22px size. Checked state fills with `#1A1A1A` and shows a bold angular slash mark (not a curved checkmark). Focus ring is a hard-offset shadow, not a soft glow.

#### 14. **progress**
8px height, 2px black border with asymmetric radius. Track background Studio Dust `#DDD0B8`. Fill uses Matador Red `#C8102E` with a hard trailing edge (no rounded end). For determinate progress, the fill edge is sharp and geometric.

#### 15. **toggle / toggle-group**
3px black border, asymmetric radius. Pressed state inverts: `background: #1A1A1A; color: #F2E8D5`. Unset state is transparent with visible border. Use hard-offset shadow on hover. Group items share borders to create a connected plane of options.

#### 16. **tooltip**
Background `#1A1A1A`, text `#F2E8D5`. 2px border in a slightly lighter tone for definition. Asymmetric radius `2px 10px 2px 10px`. No arrow -- use a small offset shadow instead. Appears with the `assemble` animation (slide + slight rotation).

#### 17. **switch**
Override track with 3px black border, asymmetric radius `2px 14px 2px 14px`. Track background canvas when off, `#1A1A1A` when on. Thumb is a square with `border-radius: 2px 6px 2px 6px` (angular, not a perfect circle). Thumb transition uses `--ease-snap` for a bold, slightly overshooting motion.

#### 18. **skeleton**
Override border-radius to match asymmetric theme values. Background uses a pattern of angular shapes rather than smooth rounded rectangles. Animation uses `plane-shift` keyframes -- subtle geometric movement instead of a smooth shimmer. Color alternates between `#DDD0B8` and `#E8DCC8`.

#### 19. **avatar**
Override to square with asymmetric radius `4px 16px 4px 16px` instead of circular. 2px black border. Fallback background uses Melancholy Blue `#1B3A5C` with canvas-colored initials in a bold serif font. Multiple avatars in a group overlap with hard-offset positioning.

#### 20. **dropdown-menu**
3px solid `#1A1A1A` border, asymmetric radius `2px 16px 2px 16px`, flat offset shadow `6px 6px 0px 0px rgba(26, 26, 26, 0.10)`. Background Raw Canvas. Menu items have no border-radius; hover state uses `background: #1A1A1A; color: #F2E8D5` -- full inversion. Separator between groups is `2px dashed rgba(26, 26, 26, 0.15)`.

#### 21. **sonner (toast)**
Dark background `#1A1A1A` with canvas text. 3px border for structure, asymmetric radius `2px 16px 2px 16px`. Hard offset shadow. Success variant uses left accent border in Olive `#6B7C3E`, error in Matador Red, info in Melancholy Blue. Entry animation uses `assemble` keyframes.

#### 22. **slider**
Track: 6px height, 2px black border. Thumb: 20px square with asymmetric radius `2px 8px 2px 8px`, 3px black border, canvas background. Filled portion of track uses Matador Red. Thumb hover adds offset shadow. Active state uses `--ease-snap` transition.

**Theme Base:** Use `theme-stone` as the foundation, then override with the Cubist canvas tones. Stone's warm neutrals are the closest starting point to the Raw Canvas / Aged Gesso palette.

**Block Patterns:**
- `dashboard-01`: Override card grid to use asymmetric column spans (e.g., `grid-template-columns: 2fr 1.2fr 1fr`). Add micro-rotations to individual cards. Use overlapping margins.
- `sidebar-01` through `sidebar-04`: Heavy right-border separators, uppercase navigation labels, active indicators as bold left-border accents.
- `login-01`: Center panel with extreme asymmetric radius, background contrast between canvas and a Blue Period accent panel. Form inputs with thick borders, primary button in Matador Red.
- Chart types: Use the Cubist palette -- Matador Red, Melancholy Blue, Ochre Yellow, Olive as the chart color series. Bar charts with hard edges (no border-radius on bars). Grid lines at 2px in `#C4C4C4`.

---

### Key Design Principles Summary

1. **Shatter the grid** -- Asymmetry is not a decoration, it is the fundamental structure; reject centered, uniform layouts
2. **Heavy outlines define form** -- 3px black borders are the charcoal lines that construct every element on the canvas
3. **Flat shadow planes** -- Shadows are geometric offset shapes (`6px 6px 0px`), never blurred atmospheric effects
4. **Extreme corner asymmetry** -- Every border-radius must be different at each corner; `2px 24px 2px 24px` is the signature pattern
5. **Collage layering** -- Elements overlap, stack, and partially obscure one another like paper planes pasted on canvas
6. **Color as solid plane** -- Colors fill flat areas boldly; gradients are rare, and when used, are linear and geometric
7. **Serif meets sans-serif** -- The tension between classical display type and geometric body text creates the cubist typographic voice
8. **Decisive interaction** -- Hover and click states are immediate, bold shifts in position and shadow, not gentle fades
9. **Canvas is always visible** -- The warm linen background texture and tone should breathe through every composition
10. **Controlled imperfection** -- Micro-rotations, uneven borders, and irregular clip-paths give each element the hand-constructed quality of studio work

---

*"Every act of creation is first an act of destruction."* -- Pablo Picasso
