# Design System Strategy: The Quiet Authority

## 1. Overview & Creative North Star
This design system is built upon the North Star of **"The Quiet Authority."** It is a digital manifestation of precision, high-performance, and editorial intent. We are moving away from the "generic SaaS" aesthetic of rounded cards and heavy borders toward a world of architectural structure and tonal depth.

The goal is to create a portfolio experience that feels like a physical gallery at night—where light is used sparingly to guide the eye and objects are defined by their presence against the void rather than by boxes. We break the "template" look by using intentional asymmetry, generous white space (negative space), and a dramatic typographic scale that favors legibility and impact over density.

## 2. Colors: Tonal Architecture
The palette is rooted in deep obsidian and charcoal, using a sophisticated hierarchy of "Surfaces" to define space.

### The "No-Line" Rule
To achieve a high-end feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined solely through background color shifts or subtle tonal transitions. 
*   *Implementation:* Instead of a line between a header and a hero section, transition from `surface` (#0e0e0e) to `surface-container-low` (#131313).

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use the Material tiers to create "nested" depth:
*   **Base:** `surface` (#0e0e0e).
*   **Deep Pockets:** `surface-container-lowest` (#000000) for inset elements like code blocks or secondary modules.
*   **Raised Elements:** `surface-container` (#191a1a) through `surface-container-highest` (#252626) for cards and modals.

### The "Glass & Gradient" Rule
Floating elements (like navigation bars or hovering cards) should utilize **Glassmorphism**.
*   **Token Use:** Use `surface` or `surface-variant` at 70% opacity with a `24px` backdrop-blur. 
*   **Signature Textures:** For the primary CTA or hero backgrounds, avoid flat fills. Use a subtle linear gradient from `primary` (#4cd7f6) to `primary_container` (#004e5c) at a 135-degree angle to provide a "lit from within" professional polish.

## 3. Typography: Editorial Precision
The typography system uses a pairing of **Manrope** for structure and **Inter** for utility.

*   **Display & Headline (Manrope):** These are your architectural anchors. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero statements. This conveys a "Modernist" brand identity that feels curated and authoritative.
*   **Body & Label (Inter):** Inter provides the high-performance, readable feel required for project descriptions. Use `body-lg` for primary narratives to maintain a premium "long-form" feel.
*   **Hierarchy Tip:** Contrast a `display-sm` headline with a `label-md` uppercase tag in `primary` color to create a sophisticated, high-contrast lockup.

## 4. Elevation & Depth: Tonal Layering
In this design system, depth is felt, not seen. We reject traditional "drop shadows" in favor of environmental light.

*   **The Layering Principle:** Stack surfaces to create lift. Place a `surface-container-high` card on a `surface` background. The difference in hex values is enough to define the shape without visual clutter.
*   **Ambient Shadows:** If a floating effect is required (e.g., a modal), use a shadow with a blur radius of at least `40px` at `6%` opacity. The shadow color should be `surface-container-lowest` (#000000) to mimic natural light absorption.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, it must be a **Ghost Border**: use `outline-variant` (#484848) at `15%` opacity. It should be barely perceptible.
*   **Interaction:** On hover, a card should not move "up"; instead, transition its background from `surface-container` to `surface-bright` (#2c2c2c).

## 5. Components

### Buttons
*   **Primary:** Filled with `primary` (#4cd7f6), text in `on_primary` (#004754). Use `DEFAULT` (0.25rem) rounding for a sharp, technical look.
*   **Secondary:** Ghost style. No fill, with a `primary` label. On hover, apply a `surface-variant` background at 30% opacity.
*   **Tertiary:** `label-md` text only, with a small 16px arrow icon.

### Cards (Portfolio Work)
*   **Structure:** No borders. Use `surface-container-low` (#131313). 
*   **Spacing:** Minimum `32px` internal padding. 
*   **Rule:** Forbid the use of divider lines. Separate content using `title-md` for headers and `body-sm` for metadata, separated by vertical white space from the standard scale.

### Chips (Tech Stack/Tags)
*   Use `secondary_container` (#393c3d) with `on_secondary_container` (#bdc0c1) text.
*   Rounding: `full` (9999px) to contrast against the sharp-edged cards.

### Input Fields
*   **Resting:** `surface_container_highest` (#252626) background, no border.
*   **Active:** A 1px bottom-border using `primary` (#4cd7f6). This provides a "high-performance" focus state without boxing the user in.

### The "Signature" Navigation
*   A centered, floating dock using glassmorphism.
*   Background: `surface` at 80% with `backdrop-blur: 12px`.
*   Rounding: `xl` (0.75rem).

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical layouts. For example, left-align a headline and right-align the body copy on a 12-column grid to create a custom editorial feel.
*   **Do** use `primary` sparingly. It should be a "spark" in the dark, used only for the most critical CTAs or status indicators.
*   **Do** leverage the `surface_bright` token for subtle "rim lighting" on top edges of components to simulate a light source from above.

### Don't:
*   **Don't** use 100% white (#ffffff). Use `on_surface` (#e7e5e4) for text to reduce eye strain and maintain the "Quiet Authority" atmosphere.
*   **Don't** use standard 8px grid-based dividers. If you need to separate sections, use a `64px` to `128px` vertical gap.
*   **Don't** use heavy shadows. If you can see the shadow clearly, it’s too dark. It should feel like a soft glow or a natural occlusion.