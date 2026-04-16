# Design System Document: High-Fidelity Engineering

## 1. Overview & Creative North Star
**Creative North Star: "The Precision Console"**

This design system is a digital translation of high-end analog rack gear. It moves away from the "flat web" by embracing the weight, texture, and tactile satisfaction of a professional recording studio. We are not building a website; we are machining a high-fidelity instrument. 

To break the "template" look, we employ **Intentional Asymmetry**. Like a classic mixing desk where gain stages and EQ knobs are grouped by function rather than a rigid grid, our layouts should feel engineered and purposeful. We use high-contrast typography scales and overlapping "hardware" panels to create a sense of mechanical depth and professional authority.

---

## 2. Colors & Surface Logic

The palette is rooted in the industrial reliability of deep charcoal and the warmth of vacuum-tube indicators.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. We achieve separation through **Tonal Shifts**. 
- Use `surface-container-low` for a background, and place `surface-container` elements upon it. 
- The boundary is defined by the value change, not a line. This mimics how separate metal plates are joined in a rack unit.

### Surface Hierarchy & Nesting
Treat the UI as a physical chassis. 
- **The Chassis (`surface` / `#131313`):** The base layer of the application.
- **Nested Panels:** Use `surface-container-lowest` to create "recessed" areas for inputs, and `surface-container-highest` for "protruding" control modules. 
- **Signature Textures:** Use a subtle linear gradient from `primary` (#ffd79b) to `primary-container` (#ffb300) on active CTAs to mimic the warm, internal glow of a VU-meter lamp.

### Glass & Light
For floating menus or overlays, use **Glassmorphism**. Apply `surface-variant` with a 70% opacity and a `20px` backdrop blur. This ensures the "machined" background is never lost, maintaining the high-end industrial atmosphere.

---

## 3. Typography
The type system mimics the precision of technical manuals and the sophistication of bespoke gear branding.

- **Display & Headlines (`Space Grotesk`):** This is our industrial label. It’s wide, technical, and authoritative. Use `display-lg` for hero statements to create an "Editorial" impact.
- **Body & Technical Specs (`Inter`):** Chosen for its clinical legibility. It provides the "small print" reliability required for high-fidelity data.
- **Label Scales:** `label-sm` and `label-md` should be used for all UI controls, mimicking the small, etched text found under knobs and switches. Use `uppercase` and `letter-spacing: 0.05em` for all labels to reinforce the hardware aesthetic.

---

## 4. Elevation & Depth: Tonal Layering

We do not use drop shadows to indicate "elevation" in the traditional sense; we use them to simulate **Physical Displacement**.

- **The Layering Principle:** Depth is achieved by stacking. A `surface-container-highest` card sitting on a `surface-dim` background creates a natural lift.
- **Ambient Shadows:** For floating elements (like modals), use a shadow with a `40px` blur, `0%` spread, and `8%` opacity, tinted with `primary-fixed-dim`. This simulates light reflecting off a warm amber indicator onto a charcoal surface.
- **The "Ghost Border" Fallback:** If accessibility requires a border, use `outline-variant` at **15% opacity**. It should be felt, not seen.
- **Tactile Inputs:** Buttons and interactive cards should use an inner shadow (`inset`) when pressed to simulate the physical "click" of a mechanical switch.

---

## 5. Components

### Buttons (Tactile Switches)
- **Primary:** Background is `primary-container` (#ffb300). Sharp `0.25rem` corners. On hover, apply a subtle "inner glow" using a light top border (1px, `primary-fixed`).
- **Secondary:** `surface-container-highest` background with `secondary` text. Mimics a brushed aluminum button.
- **Tertiary:** No background. `label-md` styling. Underlined only on hover with `primary`.

### Input Fields (Precision Dials)
- **Styling:** Recessed look using `surface-container-lowest`. 
- **Indicator:** Instead of a standard blue focus ring, use a `2px` left-side border in `primary` (#ffb300) when active.
- **Forbid Dividers:** In forms, use `spacing-xl` rather than lines to separate field groups.

### Cards & Modules (Hardware Blocks)
- **Rule:** Forbid divider lines.
- **Structure:** A card should be a solid block of `surface-container-high`. Use a `label-sm` header in `primary` to "title" the module, similar to a serial number plate on hardware.

### Additional Signature Component: The VU-Level Indicator
- Use the `tertiary-container` (#00d2fe) for "safe" levels and transition into `primary` (#ffb300) as values increase, providing a high-fidelity feedback loop for user actions.

---

## 6. Do’s and Don’ts

### Do:
- **Use Intentional Asymmetry:** Align high-level typography to the left while keeping controls in a structured, right-aligned "patch bay" layout.
- **Embrace Negative Space:** High-end gear isn't cluttered. Give every control room to breathe.
- **Type as UI:** Treat labels as part of the interface, not just descriptions.

### Don't:
- **No Rounded Pills:** Avoid `full` roundedness unless it's a specific toggle switch. Stick to `sm` (0.125rem) or `md` (0.375rem) to maintain the "machined" look.
- **No Standard Blues/Greens:** All feedback must pass through the `primary` (Amber) or `error` (Red-Orange) palette. 
- **No Borders:** If you feel the need to draw a line, try a background color shift instead. High-end design is about what you leave out.