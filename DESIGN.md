# Design System Strategy: The Architectural Dev

## 1. Overview & Creative North Star
**Creative North Star: "The Precise Artisan"**
This design system moves beyond the "generic developer portfolio" template. It is rooted in the philosophy of **Architectural Minimalism**—where every pixel is intentional, and the interface feels like a high-end Integrated Development Environment (IDE) reimagined as a digital gallery. 

We avoid the "boxed-in" look of traditional grids. Instead, we use **intentional asymmetry** and **tonal depth** to guide the eye. Large-scale typography serves as a structural element, while subtle glassmorphism provides a sense of physical layering. The aesthetic is "Premium Technical": sophisticated, quiet, yet punctuated by bursts of high-energy color.

---

## 2. Colors & Surface Philosophy
The palette is built on a foundation of "Deep Charcoal" and "Electric Indigo" to provide a high-contrast, tech-forward energy.

### The "No-Line" Rule
Sectioning must be achieved through **background color shifts**, not 1px solid lines. To separate the hero section from a project gallery, transition from `surface` to `surface-container-low`. Use space as the primary separator.

### Surface Hierarchy & Nesting
Treat the UI as stacked sheets of obsidian and frosted glass.
- **Base Layer:** `surface` (#0e0e0e) for the main viewport.
- **Sectional Layer:** `surface-container-low` (#131313) for large content blocks.
- **Interactive Layer:** `surface-container-high` (#20201f) for cards and modals.
- **Nesting Logic:** When placing a card inside a section, the card must be at least one tier higher than its parent (e.g., a `surface-container-highest` card sitting on a `surface-container-low` background).

### The "Glass & Gradient" Rule
Standard flat buttons are prohibited for primary actions. Use a **Signature Gradient** (from `primary` to `primary-container`) to provide "visual soul." For floating navigation or overlays, apply **Glassmorphism**: use `surface-container` at 60% opacity with a `24px` backdrop blur to allow background colors to bleed through softly.

---

## 3. Typography
The type system pairs the technical precision of **Inter** with the structural character of **Space Grotesk**.

*   **Display & Headlines (`Space Grotesk`):** Used for "The Statement." These should be set with tight letter-spacing (-0.02em) to feel architectural and authoritative.
*   **Body & Titles (`Inter`):** Chosen for its neutrality and readability. Titles should be bold to contrast against the lighter body weights.
*   **Labels (`Space Grotesk` / Mono):** Use `label-sm` for technical metadata (e.g., git commits, tech stacks). This reinforces the "developer" aesthetic.

**Hierarchy Tip:** Use `display-lg` for project titles, but keep the surrounding metadata in `label-md` to create a dramatic, editorial scale contrast.

---

## 4. Elevation & Depth
In this system, depth is a function of light and transparency, not shadows.

*   **The Layering Principle:** Avoid drop shadows for flat elements. Rely on the `surface-container` tiers to create a "soft lift."
*   **Ambient Shadows:** If an element must "float" (like a dropdown), use an ultra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow color should never be pure black; it should be a deep tint of the background color.
*   **The "Ghost Border" Fallback:** Where containment is strictly required for accessibility, use a **Ghost Border**. Apply `outline-variant` at 15% opacity. This creates a "suggestion" of a border that feels crisp without cluttering the UI.

---

## 5. Components

### Buttons
*   **Primary:** High-gloss gradient (`primary` to `primary-container`). Roundedness: `md` (0.375rem). Use `on_primary` for text.
*   **Secondary:** Glass-style. `surface-container-highest` at 40% opacity with a `Ghost Border`.
*   **Tertiary:** Text-only in `primary` color. No background.

### Cards & Lists
*   **Strict Rule:** No dividers. Separate list items using `1.5rem` of vertical whitespace or a subtle hover state shift to `surface-container-high`.
*   **Project Cards:** Use `surface-container-low` as the base. On hover, transition to `surface-container-highest` and increase the `backdrop-blur`.

### Input Fields
*   **Style:** Minimalist underline or Ghost Border. Focus state triggers a 1px glow using the `primary` color.
*   **Labels:** Use `label-md` in `on_surface_variant` for a muted, sophisticated look.

### Developer-Specific Components
*   **Code Snippets:** Use `surface-container-lowest` for the block background. Accent syntax highlighting with `tertiary` (Cyber Lime) and `secondary` (Indigo).
*   **Tech Tags (Chips):** Use `surface-variant` with `0.25rem` (sm) rounding. No borders; just a subtle shift in tone.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use extreme whitespace. If you think there’s enough space, add 20% more.
*   **Do** use `tertiary` (Cyber Lime) sparingly—only for "success" states or critical micro-interactions (e.g., "Active for Hire" status).
*   **Do** align text-heavy sections to a 12-column grid but break the grid with large-scale imagery or "ghost" typography overlapping section edges.

### Don't:
*   **Don't** use 100% opaque, high-contrast borders. They break the fluid "Architectural" feel.
*   **Don't** use standard blue for links. Use `primary` (Electric Indigo) to maintain the signature palette.
*   **Don't** use heavy drop shadows on cards. Use tonal layering (`surface` hierarchy) instead.
*   **Don't** use generic icons. Use thin-stroke (1px or 1.5px) SVG icons that match the "tech-forward" aesthetic of the typography.