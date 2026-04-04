# Design System Document: Industrial Intelligence

## 1. Overview & Creative North Star

### The Creative North Star: "The Kinetic Command Center"
This design system moves beyond the utility of a standard warehouse tool to create a "Kinetic Command Center." It is designed for high-stakes industrial environments where speed and precision are paramount. Instead of a flat, static interface, we employ a sophisticated "Dark Mode Editorial" aesthetic—combining the weight of industrial machinery with the ethereal lightness of high-tech data visualization.

The design breaks the "template" look through:
*   **Intentional Asymmetry:** Strategic use of whitespace and off-center focal points to guide the eye toward critical action items.
*   **Atmospheric Depth:** Utilizing a palette of deep obsidians and electric purples to create a sense of focused immersion.
*   **Scale Contrast:** Heroic typography for system headers juxtaposed with ultra-refined micro-labels for technical data.

---

## 2. Colors

The color palette is engineered for high-contrast legibility in low-light industrial settings, using a tiered logic of "Surface Depth."

### Primary & Accent Palette
*   **Primary (`#bac3ff`):** Used for primary labels and high-priority states.
*   **Primary Container (`#5c6bc0`):** The signature "Action" color, providing a vibrant, technological glow.
*   **Tertiary (`#c3c0ff`):** Reserved for versioning (e.g., "V18.3") and secondary data highlights.

### Surface & Neutral Hierarchy
*   **Background / Surface (`#10141a`):** The foundation. A deep, void-like navy that minimizes eye strain.
*   **Surface Container (Lowest to Highest):**
    *   `Lowest (#0a0e14)`: Deep wells for input fields.
    *   `Low (#181c22)`: Primary sectioning.
    *   `High (#262a31)`: Elevated cards and active modals.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** Boundaries must be defined solely through background color shifts. To separate a list from a dashboard, place the list items on a `surface-container-low` background against the `surface` background.

### The "Glass & Gradient" Rule
For "Floating" or "Hero" components (like the "Launch System" button), use a subtle linear gradient: `primary-container` to `secondary-container`. For modal overlays, use `surface-variant` with a 24px `backdrop-blur` to create a "Frosted Industrial Glass" effect.

---

## 3. Typography

The system utilizes a dual-font approach: **Inter** for technical precision and **Noto Sans TC / PingFang TC** for localized clarity.

*   **Display Large (Hero Title):** `Inter`, 3.5rem, Bold. Used for "倉儲庫位控管系統". This should feel authoritative and architectural.
*   **Headline Medium (Versioning):** `Inter`, 1.75rem, Medium. Use `tertiary` color for "V18.3" to create a distinct visual layer from the title.
*   **Title Small (Primary Actions):** `Inter/Noto Sans TC`, 1rem, Semi-Bold. Used for button labels like "啟動系統".
*   **Body Medium (Data):** `Inter`, 0.875rem. The workhorse for SKU numbers and warehouse locations.
*   **Label Small (Micro-Metadata):** `Inter`, 0.6875rem, All Caps. Used for secondary metadata to maintain a clean, "spec-sheet" look.

---

## 4. Elevation & Depth

We convey hierarchy through **Tonal Layering** rather than traditional drop shadows or strokes.

*   **The Layering Principle:** Stack `surface-container-highest` elements on top of `surface-dim` backgrounds. The visual "lift" comes from the change in luminosity, not a simulated shadow.
*   **Ambient Shadows:** If a floating element (like a mobile scanner FAB) requires a shadow, it must be:
    *   `Blur: 32px`, `Spread: 0`, `Opacity: 6%`, `Color: #000000`.
*   **The Ghost Border Fallback:** For input fields, use a `1px` border using `outline-variant` at **15% opacity**. It should be felt rather than seen.
*   **Glassmorphism:** Apply to global navigation bars. Use `surface` at 80% opacity with a `20px` backdrop blur to allow warehouse data to scroll "underneath" the glass.

---

## 5. Components

### Buttons (Rounded-Full)
*   **Primary:** `rounded-full`, background: `primary-container`, text: `on-primary-container`. Use a subtle inner glow (top-down) for a tactile feel.
*   **Tertiary:** `rounded-full`, background: transparent, border: `ghost-border`, text: `primary`.

### Cards & Lists
*   **Rule:** Forbid divider lines.
*   **Implementation:** Use a `16px` vertical spacing scale. Group related data onto a `surface-container-low` card. When a card is hovered/active, transition its background to `surface-container-high`.

### Input Fields
*   **Visual Style:** "Sunken" appearance. Use `surface-container-lowest` with a 4px corner radius (breaking from the rounded-full button style to signify "utility").
*   **Active State:** The `ghost-border` transitions to a 100% opaque `primary` glow.

### Chips (Industrial Tags)
*   **Status Chips:** Small, `rounded-full` elements using low-saturation versions of `error` or `primary` to indicate bin status (Full/Empty/Restocking) without cluttering the UI.

---

## 6. Do's and Don'ts

### Do
*   **DO** use extreme vertical spacing to separate the Title, Version, and Action button as seen in the core layout.
*   **DO** ensure the "V18.3" text is always in the `tertiary` (light purple) color to maintain the established visual hierarchy.
*   **DO** use `Inter` for all alphanumeric strings (SKUs, Quantities, Versions) to maintain a tech-centric feel.

### Don't
*   **DON'T** use pure white (#FFFFFF) for body text; use `on-surface-variant` (#c6c5d3) to reduce glare in warehouse environments.
*   **DON'T** use "Rounded-Full" for data tables or input fields; reserve the pill-shape exclusively for high-level triggers and status chips to maintain a "Button = Action" mental model.
*   **DON'T** use 100% opaque borders. If you think you need a line, try a 4px gap or a subtle color shift first.