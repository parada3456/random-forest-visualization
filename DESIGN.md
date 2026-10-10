---
name: Random Forest Lab
description: A black, professional teaching instrument for watching a random forest grow, one split at a time.
colors:
  void-black: "#070706"
  surface: "#151511"
  surface-raised: "#1c1c17"
  surface-inset: "#22221b"
  canvas-well: "#0e0e0b"
  scroll-thumb: "#34332a"
  scroll-thumb-hover: "#4a483c"
  ink: "#f1eee4"
  ink-dim: "#c3c0b2"
  ink-muted: "#a6a393"
  chalk: "#ece8db"
  chalk-bright: "#fffdf5"
  chalk-ink: "#0b0b09"
  gold: "#d99b3f"
  series-a: "#56b4e9"
  series-b: "#e66a12"
  series-c: "#f0e442"
  grid-line: "#2b2b24"
  good: "#2fbf6f"
  warn: "#e0a339"
  error: "#e0524a"
typography:
  display:
    fontFamily: "Newsreader, Georgia, serif"
    fontSize: "clamp(20px, 1.9vw, 24px)"
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: "-0.01em"
  headline:
    fontFamily: "Newsreader, Georgia, serif"
    fontSize: "22px"
    fontWeight: 600
    lineHeight: 1.25
  body:
    fontFamily: "IBM Plex Sans Thai, IBM Plex Sans, system-ui, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.55
  label:
    fontFamily: "IBM Plex Sans Thai, IBM Plex Sans, system-ui, sans-serif"
    fontSize: "12px"
    fontWeight: 700
    letterSpacing: "0.14em"
  data:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "18px"
    fontWeight: 600
rounded:
  xs: "3px"
  sm: "7px"
  field: "8px"
  md: "10px"
  segment: "10px"
  well: "12px"
  lg: "16px"
  pill: "999px"
  round: "50%"
spacing:
  xs: "6px"
  sm: "10px"
  md: "14px"
  lg: "22px"
  gutter: "34px"
  control-height: "32px"
components:
  button-primary:
    backgroundColor: "{colors.chalk}"
    textColor: "{colors.chalk-ink}"
    rounded: "{rounded.md}"
    padding: "9px 15px"
  button-primary-hover:
    backgroundColor: "{colors.chalk-bright}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: "9px 15px"
  panel:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.lg}"
    padding: "16px 20px 18px"
  segmented:
    backgroundColor: "{colors.surface-inset}"
    textColor: "{colors.ink-dim}"
    rounded: "{rounded.segment}"
    padding: "4px"
    height: "{spacing.control-height}"
  segmented-active:
    backgroundColor: "{colors.chalk}"
    textColor: "{colors.chalk-ink}"
    rounded: "{rounded.sm}"
  stepper:
    backgroundColor: "{colors.surface-inset}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    height: "{spacing.control-height}"
  stat-tile:
    backgroundColor: "{colors.surface-inset}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: "10px 12px"
---

# Design System: Random Forest Lab

## Overview

**Creative North Star: "The Night Observatory"**

A black room with a few well-lit instruments in it. The page recedes into near-black so the data (colored points, decision boundaries, trees, the error curve) is the only thing that glows. Surfaces are quiet, restrained and precise, the way a good lab instrument or scientific journal is. It should look professional enough to present in front of a class and calm enough to study for an hour.

Density is moderate and information-rich: this is an operating tool for learners, so scanability and consistency beat decoration. Brand lives in details: a serif voice for headings, a monospace voice for numbers, one chalk-white accent used with discipline, and gold reserved for credit. Every kind of input gets the control that fits it (see Components), so the toolbar reads as a set of instruments rather than a row of identical buttons.

**Key Characteristics:**
- Black page, tonal-layered panels, hairline borders; depth from lightness steps and a soft shadow, never from color.
- Two floating columns, each stacking two instrument panels and each with its own vertical scrollbar; the footer is ordinary content at the very end of the page, not pinned.
- Series colors (sky blue, orange, yellow) belong to the data classes only. They never decorate chrome.
- Serif for meaning, a Thai-capable sans for interface, mono for numbers.

## Colors

A near-black warm neutral base, one chalk-white accent, one gold credit color, and three data-series hues. The interface itself is monochrome: all saturated color is data.

### Primary
- **Chalk** (#ece8db): primary buttons, the active segment, tile, chip or tab, slider fill and thumb, switch-on, the final-forest tile outline. Its bright variant **Chalk White** (#fffdf5) is for accent text on dark, link text, hover and focus rings.
- **Chalk Ink** (#0b0b09): text on top of a filled Chalk surface.

### Secondary
- **Credit Gold** (#d99b3f): the "KMITL" credit and a faint corner glow in the page background. Nowhere else.

### Tertiary (data series)
- **Sky Blue** (#56b4e9) is Class A, **Signal Orange** (#e66a12) is Class B and **Lab Yellow** (#f0e442) is Class C: points, tree nodes, decision regions and the class chips that pick them. Sky Blue also draws the OOB loss series and the bootstrap grid.
- The three differ mainly in lightness (bright, mid, brightest), so they stay distinguishable for color-blind viewers; they follow the Okabe-Ito color-blind-safe family, adjusted for a black page. Each clears 6:1 on Void Black.

### Neutral
- **Void Black** (#070706): page background, under a faint cool-grey radial glow top-left and a gold one top-right.
- **Panel Slate** (#151511) to **Raised Slate** (#1c1c17): panel gradient, top to bottom.
- **Inset Slate** (#22221b): stat tiles, chips, secondary buttons, input wells.
- **Canvas Well** (#0e0e0b): wells holding canvases (data canvas, forest tiles).
- **Bone Ink** (#f1eee4) / **Dim Bone** (#c3c0b2) / **Quiet Bone** (#a6a393): primary, secondary, and hint text. Quiet Bone was lifted from #8a8778 so hints clear 4.5:1 on Inset Slate.
- **Hairline** (rgba(255,255,255,0.08)) and **Strong Hairline** (rgba(255,255,255,0.16)): borders. **Grid Line** (#2b2b24): chart grids.
- Status: **Good** (#2fbf6f), **Warn** (#e0a339), **Error** (#e0524a).

### Named Rules
**The Glow-Only-The-Data Rule.** Saturated color belongs to the data. The accent is chalk white; chrome stays neutral.
**The Black Floor Rule.** The page background is always black-family. Never introduce a light theme or a light panel.
**The AA Floor Rule.** Body and hint text is at least 4.5:1 on its surface. Class colors fail 4.5:1 as text on their own tinted fills, so an unselected class chip carries a Bone Ink letter and uses the class color only for its border and tint. Light-on-light pairs must never appear.

## Typography

**Display Font:** Newsreader (with Georgia, serif)
**Body Font:** IBM Plex Sans Thai (with IBM Plex Sans, system-ui, sans-serif)
**Label/Mono Font:** IBM Plex Mono (with ui-monospace)

**Delivery:** All three families are embedded in `index.html` as Latin and Thai subsets, so the page renders identically offline. Nothing loads from a font CDN.

**Character:** Newsreader, an editorial serif drawn for reading on screen, gives the lab a human, teachable voice. IBM Plex Sans Thai runs the interface; it carries the Latin and Thai glyphs of one family, so the member names in the footer match the rest of the page. IBM Plex Mono makes every number feel measured, and shares its design with the sans, so the whole page reads as one engineered family.

### Hierarchy
One scale, defined as CSS tokens (`--fs-label` to `--fs-title`): **12 label, 13 UI, 14 body, 15 intro, 18 value, 22 title, 24 display.** Icon glyphs (the 16px stepper signs, the 15px zoom buttons, the 11px info mark) are not text and sit outside the scale.
- **Display** (600, clamp(20px, 1.9vw, 24px), 1.15): the page title only.
- **Title** (600, 22px, 1.25): panel titles and the tour card title.
- **Value** (mono 600, 18px, tabular numerals): the three stat tiles.
- **Intro** (400, 15px, 1.55): reserved for longer lead-in text; the header lede currently uses Body.
- **Body** (400, 14px, 1.5): the header lede, panel hints, bootstrap summary, status line, switch description, tour text.
- **UI** (13px, weight 500 to 700): buttons, field labels, steppers and number fields, chips, tabs, tooltips, captions, the footer (Thai names read larger at the same size, so 13px with a 1.6 line height).
- **Label** (700, 12px, +0.08em, uppercase where used): stat-tile labels, section titles, legend text, chart ticks, tile labels, canvas badges.
- **Tree and chart text** (SVG): node title 16px and sub-label 14px, drawn so they stay near 12px or more after the tree is scaled to fit; chart ticks 12px at real pixel size.
- **Inputs on touch screens** are 16px so iOS does not zoom the page when they take focus.

### Named Rules
**The Mono-For-Numbers Rule.** Every measured quantity (Gini, error, counts, coordinates) is monospace with tabular figures so columns and live updates do not jitter.

## Layout

A page with a compact title bar on top, two scrolling columns that fill the screen below it, and a footer at the very end. The title bar stays in view when the page scrolls; the footer is not pinned: it sits below the workspace and is reached by scrolling the page a little past the end of a column (about 44px).

The workspace fills the space between header and footer as two equal-width floating columns (gap 22px, side gutter 24px). **Each column is its own scroll container with its own slim, themed scrollbar**, so the learner can keep the model state in view while working on the canvas, and the other way around. Panels float in each column as separate cards (22px apart), and cards fade softly under the header and footer as they scroll. Tooltips are fixed-position so a scrolling column never clips them.

- **Left column:** top, **Data Canvas**; below it, **Hyperparameters & Controls** with the **Step-by-step** and **Play until Convergence** buttons.
  - Data Canvas order: tool row (Add / Erase / Pan, plus Undo and Clear all on the right), Class, Brush size, Density, the canvas, then a Dataset section (Pattern, Noise, Points, Place an exact point).
  - Toolbar rows use a two-column grid: a 92px label column and the control, so every control's left edge lines up. Label tooltips sit beside the label.
- **Right column:** top, **Model State / Structure** (bootstrap weights, per-tree splits, Gini, forest vote); below it, **Error Curve** (stat tiles, chart, legend, and a values table).
  - The chart redraws to fill its 300px box at real pixel size, and its y-axis scales to the data (20%, 40%, 60%, 80% or 100% at the top).
  - Trees are drawn to fit the panel width (never smaller than 78% of natural size) and open centered on the root. Tree tabs show numbers only.
  - Forest Overview tiles are about 110px, with the 240px final-forest tile directly beneath them.
  - Spacing has three tiers, defined as `--sp-1`, `--sp-2`, `--sp-3`: **8px** inside a group (label to its control), **18px** between items, **28px** between groups. Panel padding is 22px top, 24px sides, 24px bottom; the head sits 20px above its first block; panels are 22px apart, matching the gap between columns.
  - Hyperparameters & Controls is split into three labelled boxes (Forest, Features, Each tree): 1px hairline border, 12px corners, a barely lighter fill, 14px apart. The Dataset section in Data Canvas uses the same box. Boxes, not loose rules, are how groups are separated inside a panel.
  - Slider rows put the label on the left and a compact slider (up to 210px) with its value on the right, so their right edge lines up with the steppers above and below them; sliders never run the full width.
  - The run bar (Step-by-step, Play until Convergence, Reset Forest, and the status line) sits at the bottom of the Hyperparameters & Controls panel, separated by a hairline and 24px of space. It scrolls with the panel; it is not pinned.
  - In Model State the number chips are outlined (not filled) so they rank below the Tree Detail / Forest Overview tabs; the bootstrap legend sits directly under its grid, with the summary below it.

Header is a compact bar of about 80px: the title and the "How to use" button on one row, then a one-line principle with "Show more" inline, expanding below it. It stays small so the two columns keep the viewport. There is no eyebrow label above the title. Footer is a single slim row (about 11px vertical padding): group members on the left, "CE KMITL" on the right.

Below 900px the columns stack and the page scrolls as one. Below 520px the toolbar label sits above its control. Scrollbars are slim, dark and themed so they do not break the black surface.

### Named Rules
**The Two Scrolls Rule.** The left and right columns scroll independently and fill the screen under the title bar. The footer is content at the end of the page, never fixed or sticky. Below 900px the columns stack and the page scrolls as one.
**The Small Bars Rule.** The title bar (about 86px) and the footer (about 42px) stay small so the instruments get the viewport.

## Elevation & Depth

Hybrid: tonal layering first, a soft shadow second. Panels read as lifted cards on the black page through a top-lit gradient (Raised Slate to Panel Slate), a hairline border, and one deep ambient shadow. Inner elements (tiles, chips, wells) sit one tonal step lighter or darker inside, with no shadow of their own.

### Shadow Vocabulary
- **Panel Lift** (`box-shadow: 0 18px 40px -18px rgba(0,0,0,0.65), 0 2px 10px -2px rgba(0,0,0,0.45)`): panels and tooltips.
- **Control Lift** (`transform: translateY(-1px)` on hover): buttons rise a pixel, no shadow added.

### Named Rules
**The Tonal-First Rule.** Separate things by a lightness step or a hairline before reaching for a shadow.

## Shapes

Soft-rounded and consistent: 16px for floating panels, 12px for canvas wells, 10px for steppers and segmented blocks (their inner buttons are 7px), 8px for number fields and ghost buttons, 3px for bootstrap grid cells, and a full pill for the How to use button only. Class chips, brush-size chips, dots, slider thumbs and info icons are full circles. Borders are 1px hairlines; the one 2px border is the Chalk outline on the final-forest tile. Canvases are clipped to their rounded wells.

## Components

### Control vocabulary
Each kind of input has one control, chosen for how the value behaves. All compact controls are 32px tall (44px on touch).
- **Mode choice (Tool, Number of Features): segmented block.** One Inset Slate block with a 4px inset; the active segment fills Chalk. Arrow keys move within the group.
- **Color-coded choice (Class): round chips.** 36px circles with a Bone Ink letter, a class-colored border and tint; the selected chip fills with the class color and a ring.
- **Size choice (Brush size): size chips.** Round chips each holding a dot of the actual size, no text; the active chip gets a Chalk ring.
- **Shape choice (Pattern): tiles.** Five equal tiles with a small line glyph over a label.
- **Small whole numbers (Density, Max Depth, Min Samples, Points): stepper.** Minus, a mono number that can be typed into, plus. Values are clamped, and buttons disable at the limits.
- **Wide or continuous ranges (Number of Trees, Bootstrap size): slider.** A 6px track filled with Chalk up to the thumb, with the value in mono to the right of the label.
- **Ordered levels (Noise): stepped slider** with Low, Medium, High labels under its stops.
- **On / off (Random Feature Subspace): switch,** 40x22px. The row is just a header with an info icon and the switch; the explanation lives in the icon's tooltip, not in running text.

### Buttons
- **Shape:** 8px corners for compact ghost buttons; 10px for the main action buttons.
- **Primary:** solid Chalk with Chalk Ink text, 13.5px bold. Hover lifts 1px and brightens to Chalk White. Reserved for the main action in a panel (Step-by-step).
- **Ghost / Secondary:** transparent with a strong hairline; the border turns Chalk on hover. Used for Undo, Clear all, New sample and Add.
- **Accent:** Chalk outline and text, filled Chalk while active (Play until Convergence while playing).
- **Disabled:** 40% opacity, no lift.

### Panels / Containers
- **Corner Style:** 16px.
- **Background:** vertical gradient Raised Slate to Panel Slate.
- **Border:** 1px hairline; **Shadow:** Panel Lift.
- **Padding:** 16px 20px 18px. Each begins with a Headline and a Hint line.

### Inputs / Fields
- **Style:** Inset Slate wells with hairline borders and 8px corners, mono tabular numerals. See Control vocabulary for the specific controls.
- **Focus:** 2px Chalk White outline with 2px offset. **Error:** Error red helper text.

### Stat Tiles
- Inset Slate, 10px radius, uppercase label over a mono value; values turn Good green when converged.

### Info Tips and Explain Toggles
- Dashed-underlined terms and 15px circular "i" icons reveal a dark 220px bubble. "Show more" text buttons in Chalk White expand longer explanations inline. Explanations are always optional, never blocking.

### Signature: Forest Grid and Final Tile
- Each tree is a small canvas tile showing its own decision boundary; the combined forest output is a larger tile with a 2px Chalk outline. Together they are the page's visual payoff.

### Guided tour (How to use)
- A "How to use" ghost pill sits at the right of the header. It opens a nine-step tour (welcome, tools, canvas, dataset, rules, run buttons, model state, error curve, done) and opens once automatically on the first visit.
- The page behind is dimmed to near-black and one target stays lit, outlined 2px in Chalk. A 340px card with the same panel styling sits beside the target; below 900px it becomes a bottom sheet. The card shows step count, a Newsreader title, a short body, progress dots, and Skip / Back / Next (Done on the last step).
- Keyboard: arrow keys move between steps, Escape closes, Tab stays inside the card, and the page behind is inert while it is open. Focus returns to the button that opened it. Motion is a short slide of the spotlight, disabled for reduced motion.

### Empty states
- Before any tree exists, Model State shows one dashed 14px-corner box centered in its area: a small dashed tree glyph, a Newsreader title ("No tree yet", "Nothing to compare yet"), one or two lines of 14px text, and a primary "Grow the first tree" button that does the same as Step-by-step. The bootstrap grid, tree tabs and overview intro are hidden until there is something to show. Empty text is never left as a loose line in the middle of a panel.

### Charts
- SVG on Canvas Well with Grid Line gridlines; Class series colors for lines; a muted bone line for the training series; dark hover tooltip with bold values.

## Do's and Don'ts

### Do:
- **Do** keep every pointer interaction available from the keyboard (canvas: arrows, Enter, +/-, 1-3) and give hit areas at least 44px on touch, using invisible padding rather than bigger visuals.
- **Do** keep a reduced-motion alternative that preserves feedback (a short fade), not a blanket removal of animation.
- **Do** keep the page background black-family (Void Black #070706) with panels stepping lighter.
- **Do** choose the control by the value: segmented for modes, chips for colors and sizes, steppers for small integers, sliders for wide ranges, a switch for on/off.
- **Do** keep the two columns as independent scroll containers with themed slim scrollbars, and give every toolbar row the same label column.
- **Do** put numbers in IBM Plex Mono with tabular figures.
- **Do** use Chalk on at most one primary action per panel.
- **Do** keep the footer to a single slim row at the end of the page: members left, CE KMITL right.
- **Do** keep every expandable explanation optional, placed beside what it explains.

### Don't:
- **Don't** introduce light panels, white backgrounds or light-text-on-light pairs.
- **Don't** use series blue, orange or green for buttons or chrome. The class chips are the one exception because they stand for the classes.
- **Don't** put a row of identical pills where a stepper, slider or switch fits the value better.
- **Don't** pin the footer or let the title bar or footer grow tall.
- **Don't** use a class color as text on a tinted class fill; use Bone Ink.
- **Don't** add gradient text, glassy blur cards, or decorative glow beyond the two faint background radials.
