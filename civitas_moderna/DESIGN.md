# Design System Document: Institutional Elegance

## 1. Overview & Creative North Star
**Creative North Star: "The Modern Diplomat"**

This design system moves away from the rigid, boxy layouts of traditional institutional portals. Instead, it adopts the aesthetic of a high-end Italian editorial—think *L'Uomo Vogue* meets a European Consulate. We achieve this through **Institutional Fluidity**: a balance between the authoritative weight of Italian heritage and the airy, glass-like precision of modern Swiss-influenced design.

The system breaks the "template" look by utilizing intentional asymmetry in its layouts, wide typographic tracking for headlines, and a layering system that treats the screen like a physical desk of stacked parchment and frosted glass. We don't use lines to separate ideas; we use space and light.

---

## 2. Colors & Surface Philosophy

The palette is rooted in the "Tricolore," but elevated to a "Ceremonial" tier. We favor deep oceanic blues and crisp off-whites, using green and red only as surgical accents for status and action.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Boundaries must be created through background color shifts. A `surface-container-low` section sitting on a `surface` background is the only way to define a change in content context.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the surface-container tiers to create "nested" depth:
- **Base Layer:** `surface` (#f9f9ff)
- **Content Blocks:** `surface-container-low` (#f0f3ff)
- **Elevated Cards:** `surface-container-lowest` (#ffffff) to provide a crisp, "high-point" pop.
- **Interactive Modals:** `surface-container-highest` (#dce2f3).

### The "Glass & Gradient" Rule
To escape the "flat" look, use **Glassmorphism** for navigation bars and floating action menus. Use `surface` colors at 80% opacity with a `20px` backdrop-blur. 
**Signature Texture:** Use a subtle linear gradient for Hero backgrounds transitioning from `primary` (#003361) to `primary-container` (#1a4a7f) at a 135-degree angle. This adds "soul" and depth that a flat fill cannot provide.

---

## 3. Typography: The Authoritative Voice

The system uses a pairing of **Manrope** (Display/Headlines) for a technical, modern edge and **Inter** (Body/Labels) for world-class legibility.

*   **Display Scale (Manrope):** Use `display-lg` for hero statements. Apply a `-0.02em` letter-spacing to give it a tight, editorial feel.
*   **Headline Scale (Manrope):** `headline-md` should be used for section titles. Pair this with a `secondary` color underline (2px thick, offset by 8px) to anchor the Italian aesthetic.
*   **Body Scale (Inter):** All long-form text uses `body-lg`. Ensure a line-height of 1.6 to maintain a premium "breathing" feel.
*   **Label Scale (Inter):** Used for metadata. Always use `label-md` with `uppercase` styling and `0.05em` tracking to mimic official document stamps.

---

## 4. Elevation & Depth

We eschew traditional shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. The subtle difference in hex code creates a "soft lift" that feels architectural rather than digital.
*   **Ambient Shadows:** If a floating element (like a FAB or Popover) requires a shadow, use: `box-shadow: 0 12px 40px rgba(21, 28, 39, 0.06);`. The shadow color is a tinted version of `on-surface`, never pure black.
*   **The "Ghost Border" Fallback:** For accessibility in form fields, use a "Ghost Border": `outline-variant` (#c3c6d1) at **15% opacity**.
*   **Glassmorphism:** Use semi-transparent surface tokens (e.g., `primary_container` at 90% opacity) with a backdrop blur for header overlays. This integrates the content into the background rather than "pasting" it on top.

---

## 5. Components

### Buttons
*   **Primary:** Solid `primary` (#003361) with `on-primary` text. No shadow. 8px (`DEFAULT`) radius. 
*   **Secondary:** `surface-container-highest` background with `primary` text. This feels like a "pressed paper" button.
*   **Tertiary:** Ghost style. No background, `primary` text, uppercase `label-md` styling.

### Input Fields
*   **Style:** Minimalist. Only a bottom-bar using `outline-variant` at 40% opacity. 
*   **Active State:** The bottom bar transitions to `secondary` (#006d34) to signify "proceed/correct."

### Cards & Lists
*   **Card Rule:** Forbid divider lines. Use `spacing-8` (2rem) of vertical white space to separate list items. 
*   **Composition:** A card should be a `surface-container-lowest` shape on a `surface-container-low` background.

### Institutional Progress Indicators
*   For longer processes (citizenship applications, etc.), use a "Stepped Timeline" component. Use `secondary` (#006d34) for completed steps and `primary_fixed_dim` for upcoming steps.

---

## 6. Do’s and Don'ts

### Do:
*   **Use Asymmetry:** Align a headline to the left but place the body text in a narrower column shifted to the right.
*   **Embrace Whitespace:** If you think there is enough space, add `spacing-4` more. 
*   **Tonal Context:** Always ensure text on `primary-container` uses `on-primary-container` (#91baf7) for sophisticated low-contrast accessibility.

### Don't:
*   **Don't use 1px Dividers:** They clutter the "Modern Italian" aesthetic. Use background shifts.
*   **Don't use pure Black (#000):** Use `on-surface` (#151c27) for all dark text to keep the palette organic.
*   **Don't use high-contrast shadows:** Avoid anything that looks like a "drop shadow" from 2010. If it doesn't look like ambient light, it's too heavy.
*   **Don't use sharp corners:** Stay strictly within the 8px–12px (`DEFAULT` to `md`) range to maintain the "Modern Institutional" feel.