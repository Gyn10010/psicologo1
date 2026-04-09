# Design System Documentation: The Living Room Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Modern Archivist"**
This design system moves away from the sterile, high-frequency "app" feel and toward a "Living Room Editorial" aesthetic. It is inspired by high-end independent magazines and the quiet confidence of a curated interior space. We achieve this by rejecting traditional digital tropes—like harsh borders and rigid grids—in favor of **intentional asymmetry, deep tonal layering, and high-contrast typography scales.**

The goal is to create a digital environment that feels "slow" and sophisticated. By utilizing the weight of Noto Serif and the gravity of the wine/burgundy palette, we create a sense of permanence and trust. We do not just display information; we curate an experience.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a deep wine tone (#6B1B2A), supported by soft creams and charcoal to ground the experience.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Boundaries must be established solely through background color shifts. Use `surface-container-low` for a section sitting on a `surface` background. If you need to separate content, use the Spacing Scale (specifically `8` or `12`) to create "rivers" of white space rather than lines.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper. 
- **Base Layer:** `surface` (#fff8f5).
- **Sub-sections:** Use `surface-container` (#f5ece7) or `surface-container-low` (#fbf2ed) for large content areas.
- **Emphasis Cards:** Use `surface-container-highest` (#e9e1dc) to draw the eye to specific modules.
- **The "Glass & Gradient" Rule:** For floating navigation or modal overlays, use semi-transparent `surface` colors with a 20px `backdrop-blur`. Apply a subtle linear gradient (from `primary` to `primary-container`) on hero CTAs to add a "soulful" depth that flat color cannot provide.

---

## 3. Typography
We use **Noto Serif** exclusively. This typeface carries the weight of a physical publication, providing a tactile, trustworthy quality to the digital interface.

- **Display (lg, md, sm):** Used for high-impact editorial moments. These should often be center-aligned or placed with intentional asymmetry to break the vertical flow.
- **Headline & Title:** Use these to anchor content sections. The transition from `headline-lg` (2rem) to `title-sm` (1rem) should be sharp and clear to maintain a strong information hierarchy.
- **Body (lg, md, sm):** Set with generous line-height to ensure the "Living Room" feel—calm and readable. 
- **Labels:** Use `label-md` for metadata. Despite the serif, labels remain legible at small sizes (0.75rem) due to the font's high x-height.

---

## 4. Elevation & Depth
We eschew traditional "box shadows" in favor of **Tonal Layering.**

- **The Layering Principle:** To lift a card, place a `surface-container-lowest` (#ffffff) element onto a `surface-container` (#f5ece7) background. This creates a soft, natural lift without digital artifacts.
- **Ambient Shadows:** If a floating element (like a FAB or Popover) is required, use an extra-diffused shadow: `box-shadow: 0 10px 40px rgba(30, 27, 24, 0.06)`. The shadow color is a tinted version of `on-surface`, never pure black.
- **The Ghost Border Fallback:** If accessibility requires a container boundary, use the `outline-variant` (#dbc0c1) at 20% opacity. 

---

## 5. Components

### Buttons
- **Primary:** Background `primary-container` (#6b1b2a), text `on-primary` (#ffffff). Shape: `md` (0.375rem).
- **Secondary:** Background `secondary-fixed` (#ffd9df), text `on-secondary-fixed` (#31111a).
- **Tertiary:** No background. Text `primary` (#4d0316) with an underline that only appears on hover.

### Cards & Lists
- **Rule:** Forbid the use of divider lines.
- **Implementation:** Use `surface-container-low` to group related items. In lists, use `spacing-4` (1.4rem) between items to allow the typography to breathe.

### Input Fields
- **Styling:** Use "Bottom-Line Only" or "Soft Surface" styles. Avoid the four-sided box. 
- **Active State:** The bottom border transitions to `primary` (#4d0316) at 2px thickness.

### Editorial Signature Components
- **The Pull-Quote:** A `display-sm` Noto Serif block, set in `primary`, with a left-padding of `spacing-8`, no border.
- **The Inset Image:** Images should use `rounded-xl` (0.75rem) and be slightly offset from the text column to create a "scrapbook" editorial feel.

---

## 6. Do's and Don'ts

### Do:
- **Do** use `primary` sparingly. It is a powerful "wine" tone; let the `surface` and `cream` neutrals do the heavy lifting.
- **Do** embrace white space. If you think there is enough space, add `spacing-2` more.
- **Do** use `tertiary` (#27231c) for long-form reading text to reduce eye strain compared to pure black.

### Don't:
- **Don't** use 1px solid borders for sectioning. It breaks the "Living Room" editorial flow.
- **Don't** use "Standard" Material ripples. Use a soft fade transition for buttons to maintain a calm atmosphere.
- **Don't** cram content. If a screen feels busy, move secondary information into a `surface-container` modal or separate page.