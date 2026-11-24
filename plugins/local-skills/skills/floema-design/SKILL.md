---
name: floema-design
description: Design system skill for floema. Activate when building UI components, pages, or any visual elements. Provides exact color tokens, typography scale, spacing grid, component patterns, and craft rules. Read references/DESIGN.md before writing any CSS or JSX.
---

# floema Design System

You are building UI for **floema**. Light-themed, warm palette, sans-serif typography (Zimula), compact density on a 4px grid.

## Visual Reference

**IMPORTANT**: Study ALL screenshots below before writing any UI. Match colors, typography, spacing, layout, and motion exactly as shown.

### Homepage

![floema Homepage](screenshots/homepage.png)

> Read `references/DESIGN.md` for full token details.

## Design Philosophy

- **Layered depth** — use shadow tokens to create a sense of physical layering. Each elevation level has a specific shadow.
- **Gradient accents** — gradients are used thoughtfully for emphasis, not decoration.
- **Single typeface** — Zimula carries all text. Hierarchy comes from size, weight, and color — never font mixing.
- **compact density** — 4px base grid. Every dimension is a multiple of 4.
- **warm palette** — the color temperature runs warm, matching the sans-serif typography.
- **Restrained accent** — `#ff0000` is the only pop of color. Used exclusively for CTAs, links, focus rings, and active states.
- **Subtle motion** — transitions smooth state changes. Keep durations under 300ms, use ease-out curves.

## Color System

### Core Palette

| Role | Token | Hex | Use |
|------|-------|-----|-----|
| Background | `--background` | `#ffffff` | Page/app background |
| Surface | `--surface` | `#f2efea` | Cards, panels, modals |
| Text Primary | `--text-primary` | `#241f21` | Headings, body text |
| Text Muted | `--text-muted` | `#beb9b0` | Captions, placeholders |
| Accent | `--accent` | `#ff0000` | CTAs, links, focus rings |
| Border | `--border` | `#524945` | Dividers, card borders |

### Status Colors

| Status | Hex | Use |
|--------|-----|-----|
| Warning | `#f4efd7` | Caution states, pending items |
| Danger | `#ff004d` | Errors, destructive actions |

### Extended Palette

- **color-brightIvory200:** `#e4ded3`
- **color-flourYellow:** `#e9e778`
- **color-stoneBrown500:** `#988f8b`
- **color-black:** `#000000` — Deep background layer or shadow color
- **color-forestGreen600:** `#042d2b` — Deep background layer or shadow color
- **color-stoneBrown600:** `#7a716d`
- **color-brightIvory300:** `#d2cdc4`
- **color-natureKraft:** `#c6af88`

### CSS Variable Tokens

```css
--btn-background-color: transparent;
--btn-background-border: hsla(59,72%,69%,.2);
--btn-background-border-hover: #e9e778;
--btn-background-color: #241f21;
--btn-background-color-hover: rgba(36,31,33,.8);
--btn-background-color: #fff;
--btn-background-color-hover: #fff;
--btn-background-color: transparent;
--btn-background-color-hover: transparent;
--btn-background-border: rgba(36,31,33,.2);
--btn-background-color: #241f21;
--btn-background-color: #241f21;
--btn-background-color-hover: rgba(36,31,33,.8);
--btn-background-color: #fff;
--btn-background-color-hover: #fff;
--btn-background-color: transparent;
--btn-background-color: #241f21;
--btn-background-color-hover: rgba(36,31,33,.8);
--btn-background-color: #fff;
--btn-background-color-hover: #fff;
```

## Typography

### Font Stack

- **Zimula** — Heading 1, Heading 2, Heading 3, Body, Caption

### Font Sources

```css
@font-face {
  font-family: "Zimula";
  src: url("fonts/Zimula-Regular.ttf") format("truetype");
  font-weight: 400;
}
```

### Type Scale

| Role | Family | Size | Weight |
|------|--------|------|--------|
| Heading 1 | Zimula | 500px | 700 |
| Heading 2 | Zimula | clamp(80px,67.91px + 100vw*.031,120px) | 700 |
| Heading 3 | Zimula | clamp(32px,22.64px + 100vw*.024,64px) | 700 |
| Body | Zimula | clamp(14px,13.22px + 100vw*.002,16px) | 400 |
| Caption | Zimula | 14px | 400 |

### Typography Rules

- All text uses **Zimula** — never add another font family
- Max 3-4 font sizes per screen
- Headings: weight 600-700, body: weight 400
- Use color and opacity for text hierarchy, not additional font sizes
- Line height: 1.5 for body, 1.2 for headings

## Spacing & Layout

### Base Grid: 4px

Every dimension (margin, padding, gap, width, height) must be a multiple of **4px**.

### Spacing Scale

`2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24` px

### Spacing as Meaning

| Spacing | Use |
|---------|-----|
| 4-8px | Tight: related items (icon + label, avatar + name) |
| 12-16px | Medium: between groups within a section |
| 24-32px | Wide: between distinct sections |
| 48px+ | Vast: major page section breaks |

### Border Radius

Scale: `.2vw, .3vw, .4vw, .5vw, .6vw, .7vw, .8vw, .9vw, 1.2vw, 1.8vw, 2px, 3px, 4px, 6px, 8px, 12px, inherit, 16px, 24px, 30px, 64px, 100%, 999px`
Default: `3px`

### Container

Max-width: `1290px`, centered with auto margins.

### Breakpoints

| Name | Value |
|------|-------|
| xs | 410px |
| md | 743px |
| lg | 1023px |
| lg | 1024px |
| 2xl | 1290px |
| 2xl | 1440px |
| 2xl | 1700px |
| 2xl | 1900px |
| 2xl | 2000px |

Mobile-first: design for small screens, layer on responsive overrides.

## Component Patterns

### Card

```css
.card {
  background: #f2efea;
  border: 1px solid #524945;
  border-radius: 3px;
  padding: 16px;
  box-shadow: 0 6px 12px #0000001a;
}
```

```html
<div class="card">
  <h3>Card Title</h3>
  <p>Card content goes here.</p>
</div>
```

### Button

```css
/* Primary */
.btn-primary {
  background: #ff0000;
  color: #241f21;
  border-radius: 3px;
  padding: 8px 16px;
  font-weight: 500;
  transition: opacity 150ms ease;
}
.btn-primary:hover { opacity: 0.9; }

/* Ghost */
.btn-ghost {
  background: transparent;
  border: 1px solid #524945;
  color: #241f21;
  border-radius: 3px;
  padding: 8px 16px;
}
```

```html
<button class="btn-primary">Get Started</button>
<button class="btn-ghost">Learn More</button>
```

### Input

```css
.input {
  background: #ffffff;
  border: 1px solid #524945;
  border-radius: 3px;
  padding: 8px 12px;
  color: #241f21;
  font-size: 14px;
}
.input:focus { border-color: #ff0000; outline: none; }
```

```html
<input class="input" type="text" placeholder="Search..." />
```

### Badge / Chip

```css
.badge {
  display: inline-flex;
  align-items: center;
  padding: 4px 8px;
  border-radius: 9999px;
  font-size: 12px;
  font-weight: 500;
  background: #f2efea;
  color: #beb9b0;
}
```

```html
<span class="badge">New</span>
<span class="badge">Beta</span>
```

### Modal / Dialog

```css
.modal-backdrop { background: rgba(0, 0, 0, 0.6); }
.modal {
  background: #f2efea;
  border: 1px solid #524945;
  border-radius: 999px;
  padding: 24px;
  max-width: 480px;
  width: 90vw;
  box-shadow: 0 6px 12px #0000001a;
}
```

```html
<div class="modal-backdrop">
  <div class="modal">
    <h2>Dialog Title</h2>
    <p>Dialog content.</p>
    <button class="btn-primary">Confirm</button>
    <button class="btn-ghost">Cancel</button>
  </div>
</div>
```

### Table

```css
.table { width: 100%; border-collapse: collapse; }
.table th {
  text-align: left;
  padding: 8px 12px;
  font-weight: 500;
  font-size: 12px;
  color: #beb9b0;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  border-bottom: 1px solid #524945;
}
.table td {
  padding: 12px;
  border-bottom: 1px solid #524945;
}
```

```html
<table class="table">
  <thead><tr><th>Name</th><th>Status</th><th>Date</th></tr></thead>
  <tbody>
    <tr><td>Item One</td><td>Active</td><td>Jan 1</td></tr>
    <tr><td>Item Two</td><td>Pending</td><td>Jan 2</td></tr>
  </tbody>
</table>
```

### Navigation

```css
.nav {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px 16px;
  border-bottom: 1px solid #524945;
}
.nav-link {
  color: #beb9b0;
  padding: 8px 12px;
  border-radius: 3px;
  transition: color 150ms;
}
.nav-link:hover { color: #241f21; }
.nav-link.active { color: #ff0000; }
```

```html
<nav class="nav">
  <a href="/" class="nav-link active">Home</a>
  <a href="/about" class="nav-link">About</a>
  <a href="/pricing" class="nav-link">Pricing</a>
  <button class="btn-primary" style="margin-left: auto">Get Started</button>
</nav>
```

### Extracted Components

These components were found in the codebase:

**Button** (`html`)

**Input** (`html`)

**Badge** (`html`)

## Page Structure

The following page sections were detected:

- **Hero** — Hero section (detected from heading structure)
- **Faq** — FAQ/accordion section
- **Footer** — Page footer with links and info (12 items)
- **Testimonials** — Testimonials/reviews section
- **Cards** — Grid of 5 card elements (5 items)

When building pages, follow this section order and structure.

## Animation & Motion

This project uses **subtle motion**. Transitions smooth state changes without calling attention.

### CSS Animations

- `leafShadowDrift-4d1adb8d`
- `imageLoading`
- `orbit-068e8402`
- `scrollLabelBob-435ca9aa`

### Motion Tokens

- **Duration scale:** `100ms`, `200ms`, `250ms`, `300ms`, `350ms`, `400ms`, `500ms`, `600ms`, `700ms`, `1000ms`, `1300ms`, `3400ms`
- **Easing functions:** `ease`, `cubic-bezier(.19,1,.22,1)`, `cubic-bezier(.175,.885,.32,1.275)`, `cubic-bezier(.12,1.2,.16,2.35)`, `cubic-bezier(1,0,0,1)`, `ease-out`, `cubic-bezier(.075,.82,.165,1)`, `cubic-bezier(.215,.61,.355,1)`
- **Animated properties:** `transform`, `background-color`, `opacity`

### Motion Guidelines

- **Duration:** Use values from the duration scale above. Short (100ms) for micro-interactions, long (3400ms) for page transitions
- **Easing:** Use `ease` as the default easing curve
- **Direction:** Elements enter from bottom/right, exit to top/left
- **Reduced motion:** Always respect `prefers-reduced-motion` — disable animations when set

## Depth & Elevation

### Shadow Tokens

- Floating (dropdowns, popovers): `0 6px 12px #0000001a`
- Overlay (modals, dialogs): `0 12px 40px #0000001f`

### Z-Index Scale

`0, 1, 2, 3, 4, 5, 9, 10, 11, 100, 999, 9999, 10000, 999999`

Use these exact values — never invent z-index values.

## Anti-Patterns (Never Do)

- **No blur effects** — no backdrop-blur, no filter: blur()
- **No zebra striping** — tables and lists use borders for separation
- **No invented colors** — every hex value must come from the palette above
- **No arbitrary spacing** — every dimension is a multiple of 4px
- **No extra fonts** — only Zimula are allowed
- **No arbitrary border-radius** — use the scale: 2px, 3px, 4px, 6px, 8px, 12px, 16px, 24px, 30px, 64px
- **No opacity for disabled states** — use muted colors instead

## Workflow

1. **Read** `references/DESIGN.md` before writing any UI code
2. **Pick colors** from the Color System section — never invent new ones
3. **Set typography** — Zimula only, using the type scale
4. **Build layout** on the 4px grid — check every margin, padding, gap
5. **Match components** to patterns above before creating new ones
6. **Apply elevation** — use shadow tokens
7. **Validate** — every value traces back to a design token. No magic numbers.

## Brand Spec

- **Favicon:** `/favicon-64x64.png`
- **Site URL:** `https://floema.com/en`
- **Brand color:** `#ff0000`
- **Brand typeface:** Zimula

## Quick Reference

```
Background:     #ffffff
Surface:        #f2efea
Text:           #241f21 / #beb9b0
Accent:         #ff0000
Border:         #524945
Font:           Zimula
Spacing:        4px grid
Radius:         3px
Components:     10 detected
```

## When to Trigger

Activate this skill when:
- Creating new components, pages, or visual elements for floema
- Writing CSS, Tailwind classes, styled-components, or inline styles
- Building page layouts, templates, or responsive designs
- Reviewing UI code for design consistency
- The user mentions "floema" design, style, UI, or theme
- Generating mockups, wireframes, or visual prototypes

---

# Full Reference Files

> Every output file is embedded below. Claude has full design system context from /skills alone.

## Design System Tokens (DESIGN.md)

# floema DESIGN.md

> Auto-generated design system — reverse-engineered via static analysis by skillui.
> Frameworks: None detected
> Colors: 20 · Fonts: 1 · Components: 10
> Icon library: not detected · State: not detected
> Primary theme: light · Dark mode toggle: no · Motion: subtle

## Visual Reference

**Match this design exactly** — study colors, fonts, spacing, and component shapes before writing any UI code.

![floema Homepage](../screenshots/homepage.png)

---

## 1. Visual Theme & Atmosphere

This is a **light-themed** interface with a warm, approachable feel. The light background emphasizes content clarity. Typography uses **Zimula** throughout — a clean, modern choice that maintains consistency. Spacing follows a **4px base grid** (compact density), with scale: 2, 4, 6, 8, 10, 12, 14, 16px. The accent color **#ff0000** anchors interactive elements (buttons, links, focus rings). Motion is subtle — smooth transitions (150-300ms) ease state changes without drawing attention.

---

## 2. Color Palette & Roles

| Token | Hex | Role | Use |
|---|---|---|---|
| color-white | `#ffffff` | background | Page background, darkest surface |
| color-brightIvory50 | `#f2efea` | surface | Card and panel backgrounds |
| color-stoneBrown800 | `#241f21` | text-primary | Headings and body text |
| color-brightIvory400 | `#beb9b0` | text-muted | Captions, placeholders, secondary info |
| color-stoneBrown700 | `#524945` | border | Dividers, card borders, outlines |
| accent | `#ff0000` | accent | CTAs, links, focus rings, active states |
| color-red | `#ff004d` | danger | Error states, destructive actions |
| color-creme | `#f4efd7` | warning | Warning states, caution indicators |
| color-replasticVistaBlue | `#85a1c5` | info | Informational highlights |
| color-brightIvory200 | `#e4ded3` | unknown | Palette color |
| color-flourYellow | `#e9e778` | unknown | Palette color |
| color-stoneBrown500 | `#988f8b` | unknown | Palette color |
| color-black | `#000000` | unknown | Palette color |
| color-forestGreen600 | `#042d2b` | unknown | Palette color |
| color-stoneBrown600 | `#7a716d` | unknown | Palette color |
| color-brightIvory300 | `#d2cdc4` | unknown | Palette color |
| color-natureKraft | `#c6af88` | unknown | Palette color |
| color-urbanCoral | `#f76c46` | unknown | Palette color |
| color-golfCeladon | `#bacfa3` | unknown | Palette color |
| border-color | `#c73623` | unknown | Palette color |

### CSS Variable Tokens

```css
--btn-background-color: transparent;
--btn-background-border: hsla(59,72%,69%,.2);
--btn-background-border-hover: #e9e778;
--btn-background-color: #241f21;
--btn-background-color-hover: rgba(36,31,33,.8);
--btn-background-color: #fff;
--btn-background-color-hover: #fff;
--btn-background-color: transparent;
--btn-background-color-hover: transparent;
--btn-background-border: rgba(36,31,33,.2);
--btn-background-color: #241f21;
--btn-background-color: #241f21;
--btn-background-color-hover: rgba(36,31,33,.8);
--btn-background-color: #fff;
--btn-background-color-hover: #fff;
--btn-background-color: transparent;
--btn-background-color: #241f21;
--btn-background-color-hover: rgba(36,31,33,.8);
--btn-background-color: #fff;
--btn-background-color-hover: #fff;
```


---

## 3. Typography Rules

**Font Stack:**
- **Zimula** — Heading 1, Heading 2, Heading 3, Body, Caption

**Font Sources:**

```css
@font-face {
  font-family: "Zimula";
  src: url("fonts/Zimula-Regular.ttf") format("truetype");
  font-weight: 400;
}
```

| Role | Font | Size | Weight |
|---|---|---|---|
| Heading 1 | Zimula | 500px | 700 |
| Heading 2 | Zimula | clamp(80px,67.91px + 100vw*.031,120px) | 700 |
| Heading 3 | Zimula | clamp(32px,22.64px + 100vw*.024,64px) | 700 |
| Body | Zimula | clamp(14px,13.22px + 100vw*.002,16px) | 400 |
| Caption | Zimula | 14px | 400 |

**Typographic Rules:**
- Use **Zimula** for all text — do not mix font families
- Maintain consistent hierarchy: no more than 3-4 font sizes per screen
- Headings use bold (600-700), body uses regular (400)
- Line height: 1.5 for body text, 1.2 for headings
- Use color and opacity for secondary hierarchy, not additional font sizes


---

## 4. Component Stylings

### Layout (1)

**Footer** — `html`

### Navigation (1)

**Navigation** — `html`

### Data Display (3)

**Card** — `html`

**Badge** — `html`

**List** — `html`

### Data Input (2)

**Button** — `html`

**Input** — `html`
- State: :focus, :placeholder

### Overlay (1)

**Modal** — `html`

### Media (2)

**Image** — `html`

**Icon** — `html`



---

## 5. Layout Principles

- **Base spacing unit:** 4px
- **Spacing scale:** 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24
- **Border radius:** .2vw, .3vw, .4vw, .5vw, .6vw, .7vw, .8vw, .9vw, 1.2vw, 1.8vw, 2px, 3px, 4px, 6px, 8px, 12px, inherit, 16px, 24px, 30px, 64px, 100%, 999px
- **Max content width:** 1290px

**Spacing as Meaning:**
| Spacing | Use |
|---|---|
| 4-8px | Tight: related items within a group |
| 12-16px | Medium: between groups |
| 24-32px | Wide: between sections |
| 48px+ | Vast: major section breaks |


---

## 6. Depth & Elevation

### Floating — dropdowns, popovers, modals

- `0 6px 12px #0000001a`

### Overlay — full-screen overlays, top-level dialogs

- `0 12px 40px #0000001f`

### Z-Index Scale

`0, 1, 2, 3, 4, 5, 9, 10, 11, 100, 999, 9999, 10000, 999999`



---

## 7. Animation & Motion

This project uses **subtle motion**. Transitions smooth state changes without demanding attention.

### CSS Animations

- `@keyframes leafShadowDrift-4d1adb8d`
- `@keyframes imageLoading`
- `@keyframes orbit-068e8402`
- `@keyframes scrollLabelBob-435ca9aa`

### Motion Guidelines

- Duration: 150-300ms for micro-interactions, 300-500ms for page transitions
- Easing: `ease-out` for enters, `ease-in` for exits
- Always respect `prefers-reduced-motion`


---

## 8. Do's and Don'ts

### Do's

- Use `#ff0000` for interactive elements (buttons, links, focus rings)
- Use `#ffffff` as the primary page background
- Use **Zimula** for all UI text
- Follow the **4px** spacing grid for all margins, padding, and gaps
- Use the defined shadow tokens for elevation — see Section 6
- Use border-radius from the scale: .2vw, .3vw, .4vw, .5vw, .6vw
- Reuse existing components from Section 4 before creating new ones

### Don'ts

- Don't introduce colors outside this palette — extend the design tokens first
- Don't mix font families — use Zimula consistently
- Don't use arbitrary spacing values — stick to multiples of 4px
- Don't create custom box-shadow values outside the system tokens
- Don't use arbitrary border-radius values — pick from the defined scale
- Don't duplicate component patterns — check Section 4 first
- Don't use backdrop-blur or blur effects

### Anti-Patterns (detected from codebase)

- No blur or backdrop-blur effects
- No zebra striping on tables/lists


---

## 9. Responsive Behavior

| Name | Value | Source |
|---|---|---|
| xs | 410px | css |
| md | 743px | css |
| lg | 1023px | css |
| lg | 1024px | css |
| 2xl | 1290px | css |
| 2xl | 1440px | css |
| 2xl | 1700px | css |
| 2xl | 1900px | css |
| 2xl | 2000px | css |

**Approach:** Use `@media (min-width: ...)` queries matching the breakpoints above.


---

## 10. Agent Prompt Guide

Use these as starting points when building new UI:

### Build a Card

```
Background: #f2efea
Border: 1px solid #524945
Radius: 3px
Padding: 16px
Font: Zimula
Use shadow tokens from Section 6.
```

### Build a Button

```
Primary: bg #ff0000, text white
Ghost: bg transparent, border #524945
Padding: 8px 16px
Radius: 3px
Hover: opacity 0.9 or lighter shade
Focus: ring with #ff0000
```

### Build a Page Layout

```
Background: #ffffff
Max-width: 1290px, centered
Grid: 4px base
Responsive: mobile-first, breakpoints from Section 9
```

### Build a Stats Card

```
Surface: #f2efea
Label: #beb9b0 (muted, 12px, uppercase)
Value: #241f21 (primary, 24-32px, bold)
Status: use success/warning/danger from Section 2
```

### Build a Form

```
Input bg: #ffffff
Input border: 1px solid #524945
Focus: border-color #ff0000
Label: #beb9b0 12px
Spacing: 16px between fields
Radius: 3px
```

### General Component

```
1. Read DESIGN.md Sections 2-6 for tokens
2. Colors: only from palette
3. Font: Zimula, type scale from Section 3
4. Spacing: 4px grid
5. Components: match patterns from Section 4
6. Elevation: shadow tokens
```

## Bundled Fonts (fonts/)

The following font files are bundled in the `fonts/` directory:

- `fonts/Zimula-Regular.ttf`

Use these local font files in `@font-face` declarations instead of fetching from Google Fonts.

## Homepage Screenshots (screenshots/)

![homepage.png](screenshots/homepage.png)

