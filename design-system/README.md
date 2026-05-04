# Kipfoot Design System

## Overview

Kipfoot is a **dark-first, premium engineering tool platform** — a curated suite of interactive calculation, analysis, and visualization tools for engineers. Think of it as a Raycast-style launcher shell housing neal.fun-style individual tool cards, with Nicky Case-style progressive disclosure inside each tool.

The platform targets professional engineers who value precision, speed, and clarity. The UI is dense but clean — every element earns its place. No filler, no decoration that doesn't serve a function.

## Products / Surfaces

1. **Homepage / App Shell** — Raycast-inspired dark hero, top ribbon nav, colorful tool carousel. The entry point and launcher.
2. **Tool Library** — Neal.fun-style visual cards grouped by discipline/workflow. Browse and launch tools.
3. **Individual Tools** — Dense engineering UI with input panels, KPI cards, interactive diagrams, calculation traces, and expandable explanations.
4. **Learning Layer** — Nicky Case-style expandable "learn more", equation traces, and assumption details embedded inside tools.

## Sources

This design system was synthesized from the following reference briefs (no live codebases or Figma files were provided at creation time):

- **Raycast** — https://www.raycast.com/ (baseline app shell, dark aesthetic, colorful cards)
- **Neal.fun** — https://neal.fun/ (tool library card pattern)
- **Nicky Case / Nutshell** — https://ncase.me/nutshell/ (progressive disclosure)
- **Bartosz Ciechanowski** — https://ciechanow.ski/ (visuals supporting written content)
- **The Pudding** — https://pudding.cool/ (curated editorial knowledge library)
- **Linear** — https://linear.app/ (dense elegant dark UI, premium product polish)

---

## CONTENT FUNDAMENTALS

### Voice & Tone
- **Direct, precise, confident.** No hedging, no filler. Engineers trust the tool to be right.
- **Terse but not cold.** Short sentences. Active voice. No unnecessary adjectives.
- **"You" not "I".** Tool addresses the user, not the other way around.
- **No emoji** in UI. Emoji undermine the professional engineering tone.
- **No marketing fluff.** Labels are nouns or verb-noun pairs: "Bay Diagram", "Run Analysis", "Export Report".
- **Units always explicit.** Never assume the user knows "kips" vs "kN". State the unit.
- **Numbers formatted with commas** for thousands, 2 decimal places for precision values.

### Casing Conventions
- **Navigation & Labels:** Title Case — "Tool Library", "Structural Analysis"
- **Buttons & CTAs:** Title Case — "Run Analysis", "Export PDF"  
- **Body copy / descriptions:** Sentence case
- **Code & tokens:** lowercase_snake_case
- **Error messages:** Sentence case, specific ("Moment capacity exceeded by 12%", not "Error occurred")

### Specific Copy Examples
- Tool card: "Beam Analysis" / "Calculate bending moment, shear, and deflection for simply supported and continuous beams."
- CTA: "Open Tool" (not "Get Started", not "Launch", not "Try Now")
- Section header: "Structural" (not "Structural Tools" — label already carries context)
- Empty state: "No tools match this filter." (not "Oops! Nothing here yet 😕")
- Loading: "Calculating…" (not "Loading…")

### What Kipfoot is NOT
- Not a SaaS dashboard with vanity metrics
- Not a consumer product with friendly onboarding
- Not a spreadsheet replacement
- Not a chat interface

---

## VISUAL FOUNDATIONS

### Color System
Dark-first. Near-black base with layered surface hierarchy. Colorful accent cards break the monochrome shell.

**Base surfaces (dark):**
- `--bg-base`: `#0c0c0f` — near-black page background
- `--bg-surface`: `#141418` — card / panel background
- `--bg-raised`: `#1c1c22` — elevated modals, popovers
- `--bg-overlay`: `#242430` — hover state surfaces, secondary panels

**Foreground / text:**
- `--fg-1`: `#f0f0f4` — primary text, headlines
- `--fg-2`: `#a0a0b0` — secondary text, labels
- `--fg-3`: `#606070` — muted / disabled / placeholder text
- `--fg-inv`: `#0c0c0f` — text on light/colored surfaces

**Accent colors (for tool cards, KPI highlights, category tags):**
- `--accent-orange`: `#ff6b35` — primary brand accent
- `--accent-amber`: `#ffb347` — warm highlight
- `--accent-green`: `#4ade80` — success, positive delta
- `--accent-cyan`: `#22d3ee` — info, interactive states
- `--accent-purple`: `#a78bfa` — learning/docs layer
- `--accent-red`: `#f87171` — error, exceeded capacity

**Borders:**
- `--border-subtle`: `rgba(255,255,255,0.06)` — surface separators
- `--border-default`: `rgba(255,255,255,0.10)` — card outlines
- `--border-focus`: `#ff6b35` — focus ring (orange accent)

### Typography
- **Display / headlines:** "DM Sans" (geometric sans, strong weight contrast)
- **Body / UI:** "IBM Plex Sans" (technical, highly legible at small sizes)
- **Monospace / code / numbers:** "IBM Plex Mono" (code blocks, calculation values, tokens)

Scale follows a modular scale (1.25 ratio):
- `--text-xs`: 11px / mono label
- `--text-sm`: 13px / UI label, secondary
- `--text-base`: 15px / body default
- `--text-md`: 18px / large body, section intros
- `--text-lg`: 22px / card titles
- `--text-xl`: 28px / page section headers
- `--text-2xl`: 36px / hero sub-headlines
- `--text-3xl`: 48px / hero display

**Google Fonts substitution in use:** DM Sans + IBM Plex Sans + IBM Plex Mono — all available on Google Fonts. No proprietary fonts were specified in the brief.

### Spacing & Layout
- Base unit: **4px**
- Scale: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96, 128
- Max content width: **1200px**
- Sidebar widths: 240px (nav), 320px (tool panel)
- Dense grid: **1rem (16px)** gap for tool cards; **1.5rem (24px)** for page sections

### Corner Radii
- `--radius-sm`: 4px — chips, tags, badges
- `--radius-md`: 8px — cards, inputs, buttons
- `--radius-lg`: 12px — modals, large cards
- `--radius-xl`: 16px — hero cards, featured items
- `--radius-full`: 9999px — pills only (status indicators)

### Shadows & Elevation
- Level 0: No shadow (flat surface elements)
- Level 1: `0 1px 3px rgba(0,0,0,0.4)` — subtle card lift
- Level 2: `0 4px 16px rgba(0,0,0,0.5)` — modals, popovers
- Level 3: `0 8px 32px rgba(0,0,0,0.6), 0 0 0 1px rgba(255,255,255,0.06)` — floating panels
- **Glow accents:** `0 0 24px rgba(255,107,53,0.15)` used sparingly on primary CTA buttons

### Backgrounds
- Base: near-black, **no gradients** on page background
- Hero: subtle radial gradient `radial-gradient(ellipse at 60% 0%, rgba(255,107,53,0.08) 0%, transparent 60%)` — barely perceptible warmth
- Tool cards: solid colored surfaces with distinct per-discipline hues (not gradients)
- **No full-bleed photography.** Diagrams, illustrations, and technical visuals only.
- **No background textures or patterns.** Cleanliness is trust.

### Animation
- **Easing:** `cubic-bezier(0.16, 1, 0.3, 1)` (expo-out) for all UI transitions
- **Duration:** 120ms micro-interactions; 200ms panel slides; 300ms modal appears
- **Fades:** opacity 0→1, 200ms
- **No bounces, no spring physics** — this is not a consumer app
- **Hover states:** subtle background shift + border brightening (no opacity changes)
- **Press states:** `scale(0.98)` + 80ms transition — physical, not color-shift

### Cards
- Background: `--bg-surface` (#141418)
- Border: `1px solid var(--border-default)`
- Radius: `--radius-lg` (12px)
- Shadow: Level 1
- Hover: border brightens to `rgba(255,255,255,0.16)`, very subtle bg lift to `--bg-overlay`
- No colored left-border accents

### Buttons
- **Primary:** `bg: --accent-orange`, text: `--fg-inv`, radius: `--radius-md`, height: 36px
- **Secondary:** `bg: --bg-overlay`, border: `--border-default`, text: `--fg-1`
- **Ghost:** no bg, no border, text: `--fg-2`, hover: text `--fg-1`
- **Danger:** `bg: #7f1d1d`, border `--accent-red`

### Transparency & Blur
- Used for floating toolbars / top nav: `backdrop-filter: blur(12px)` on `rgba(12,12,15,0.8)`
- Used for overlays/modals: `rgba(0,0,0,0.6)` backdrop
- **Not** used for card bodies — cards are solid

### Imagery & Diagrams
- **Technical diagrams only** — bay diagrams, section views, load envelopes, tributary areas
- Drawn in SVG with the design system's fg/accent palette
- No photography, no stock illustrations, no decorative imagery
- Diagrams are **always functional** — they respond to input, not static art

### Hover / Focus States
- Hover: background shift (never opacity change on the element itself)
- Focus: `outline: 2px solid var(--accent-orange)`, `outline-offset: 2px`
- Active/press: `transform: scale(0.98)`, 80ms

---

## ICONOGRAPHY

Kipfoot uses **Lucide Icons** (stroke-weight 1.5, 16×16 or 20×20). CDN: `https://unpkg.com/lucide@latest/dist/umd/lucide.min.js`

- Icons are always **line/stroke style** — never filled
- Color: `--fg-2` default, `--fg-1` on hover, `--accent-orange` for active/featured states
- Size: 16px in dense UI (sidebar, table rows), 20px in cards and headers
- **Never use emoji as icons.** No unicode symbol substitutes.
- No icon fonts (no FontAwesome). SVG or Lucide only.
- Tool category icons distinguish disciplines (Beam, Column, Foundation, Wind, etc.)

---

## File Index

```
README.md                          — This file (start here)
SKILL.md                           — Agent skill definition for Claude Code
colors_and_type.css                — All CSS custom properties (tokens)

assets/
  logo.svg                         — Kipfoot wordmark (orange K mark + wordmark)
  logo-mark.svg                    — K mark icon only
  favicon.svg                      — 32×32 favicon with dark background

preview/                           — Design System tab cards (700px wide)
  Colors
    colors-base.html               — Dark surface hierarchy + foreground tokens
    colors-accent.html             — Brand accents + discipline category hues
    colors-semantic.html           — Border tokens + status semantics
  Type
    type-scale.html                — Full scale: 11px caption → 64px display
    type-families.html             — DM Sans / IBM Plex Sans / IBM Plex Mono
  Spacing
    spacing-tokens.html            — 4px-base spacing scale
    radius-shadow.html             — Corner radii + elevation shadow levels
  Components
    buttons.html                   — 5 variants × 3 sizes
    badges-tags.html               — Status badges, pills, discipline tags
    inputs.html                    — Text inputs, selects, all states
    cards.html                     — Default / flat / elevated / accent
    tool-card.html                 — Tool library card (neal.fun style)
    nav.html                       — Top nav + sidebar nav
    kpi-card.html                  — Result metric cards + inline row
    expandable.html                — Learn / Equation / Assumptions panels

ui_kits/
  homepage/
    index.html                     — Full homepage: hero, carousel, grid, footer
    README.md
  tool-library/
    index.html                     — Browse page: filter sidebar + tool grid
    README.md
  engineering-tool/
    index.html                     — Beam Analysis tool: inputs, KPIs, diagrams, explanations
    README.md
```

## Quick Start

To use this design system in a new design:

1. Import `colors_and_type.css` (or copy the `:root` block inline)
2. Load Google Fonts: DM Sans + IBM Plex Sans + IBM Plex Mono
3. Reference `assets/logo.svg` for the wordmark
4. Use Lucide Icons CDN for iconography: `https://unpkg.com/lucide@latest`
5. Refer to `ui_kits/engineering-tool/index.html` for the densest component reference

## GitHub Pages Layout

This folder is now structured so it can be served directly as a static GitHub Pages artifact:

```
index.html                         - Master design-system hub and default Pages entry
404.html                           - Static fallback page
.nojekyll                          - Disables Jekyll processing
GITHUB_PAGES.md                    - Deployment options and preflight checklist
COLLABORATION_PERSONA_NOTES.md     - Collaboration/persona development notes

preview/
  index.html                       - Component and token gallery index
  *.html                           - Focused component/token preview cards

ui_kits/
  homepage/index.html              - Prototype entry surface
  tool-library/index.html          - Browse/library surface
  engineering-tool/index.html      - Dense tool surface
```

Recommended first URL after deployment: `/index.html`.
