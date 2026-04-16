# Design System: Cyber-Technical Audio Intelligence

## 1. Overview & Creative North Star
### Creative North Star: "The Tactical Console"
This design system moves beyond standard DAW (Digital Audio Workstation) tropes to create a high-fidelity, "Tactical Console" experience. It is built to feel like an advanced piece of physical rack gear—heavy, precise, and professional—yet reimagined through a futuristic digital lens.

To break the "template" look, we employ **Intentional Asymmetry**. Rather than a rigid 12-column grid, layouts should feel like modular flight-deck panels. We use high-contrast typography scales (the massive `display-lg` against the tiny `label-sm`) to create a sense of data density and hierarchy that mirrors professional radar or diagnostic equipment. Every element must feel "machined" rather than "drawn."

---

## 2. Colors & Surface Philosophy
The palette is rooted in deep obsidian tones, punctuated by high-energy "ignition" accents.

### The Color Roles
- **Primary (`#ffb690` / `#f97316`):** The "Ignition" color. Used for active signal paths, critical knobs, and primary actions. It represents the energy of the audio.
- **Secondary (`#adc6ff` / `#0566d9`):** The "Calibration" color. Used for data visualization, waveforms, and secondary technical readouts.
- **Surface Hierarchy:** We utilize the `surface-container` tokens to create depth without borders.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. 
Boundaries are created exclusively through background shifts. A `surface-container-low` panel (the rack unit) sits on a `surface` background (the room), and a `surface-container-high` module (the knob plate) sits inside that. This creates a "machined" look where components feel inset or extruded rather than outlined.

### The "Glass & Gradient" Rule
Floating panels and HUDs must use **Glassmorphism**. Apply `surface-container-lowest` at 60% opacity with a `20px` backdrop blur. 
- **Signature Texture:** Apply a 2% grain/noise texture overlay to all surfaces. This eliminates "flat" digital banding and gives the UI a tactile, physical "anodized aluminum" finish.

---

## 3. Typography
Typography is the primary driver of the "Cyber-Technical" aesthetic. We pair brutalist displays with precise technical monospaces.

- **Display & Headline (`Space Grotesk`):** Replaces Bebas Neue for a more sophisticated, modern-technical feel. Use `display-lg` for massive decibel readouts or track names. The wide apertures feel architectural.
- **Title & Body (`Manrope`):** Replaces DM Sans. It is the workhorse. It remains legible even at small sizes in dense mixing environments.
- **Labels & Data (`Space Grotesk` / Monospaced):** All technical data (frequencies, gain values, timestamps) must use the `label` scales. These should feel like labels etched into a metal faceplate.

*Hierarchy Note:* Always over-emphasize the difference between data (Large/Bold) and labels (Small/All-Caps).

---

## 4. Elevation & Depth
Depth is not "shadows"—depth is **Tonal Layering**.

- **The Layering Principle:** 
    1. Base: `surface` (#131315)
    2. Main Work Area: `surface-container-low`
    3. Individual Modules: `surface-container-high`
    4. Interactive Controls: `surface-container-highest`
- **Ambient Shadows:** Only use shadows for "floating" elements like context menus or tooltips. Use a 15% opacity version of `primary` or `secondary` as the shadow tint (not black) to simulate light emitting from the screen.
- **The "Ghost Border":** For hardware realism, use the `outline-variant` token at 15% opacity on the *top and left edges only* of a module to create a "specular highlight" effect, making the component look like it has a physical edge.

---

## 5. Components

### Tactile Knobs & Sliders (The "Hardware" Core)
- **The Knob:** Use a circular `surface-container-highest` base. Use the `primary` color for the "indicator" line. Add a subtle radial gradient (Primary to Primary-Container) to the indicator to make it "glow."
- **Sliders:** The track uses `surface-container-lowest`. The thumb/fader uses `surface-container-highest` with a 2px `primary` accent line.

### Buttons
- **Primary:** `primary_container` (#f97316). No border. High-contrast `on_primary_container` text. On hover, add a `primary` outer glow (8px blur).
- **Secondary/Technical:** `surface-container-high` with `secondary` text. These should look like recessed plastic switches.

### Input Fields
- **Design:** Use "Ghost Borders" (10% opacity `outline`). The background should be `surface-container-lowest` to look "cut out" of the interface. 
- **Focus State:** The border glows `secondary` (#3b82f6) and the text shifts to the monospaced `label-md`.

### Cards & Modules
- **Rule:** **Forbid dividers.** To separate a compressor module from an EQ module, use a 24px gap (Spacing Scale) and a slight shift from `surface-container-low` to `surface-container-high`.

### Signal Visualizers (Bespoke)
- **Waveforms:** Use `secondary` with a gradient fill to `secondary_container` at the bottom. Use `0.25rem` (DEFAULT) roundedness on individual bars for a modernized look.

---

## 6. Do’s and Don’ts

### Do:
- **Do** use `primary_container` for the "active" state of a signal path (e.g., a lit-up cable).
- **Do** use technical abbreviations (e.g., "FREQ", "THRES", "GAIN") in `label-sm` All-Caps.
- **Do** lean into asymmetry; let a visualization span 70% of the screen while controls stay tucked in a 30% side panel.

### Don’t:
- **Don’t** use pure white (#FFFFFF). All "white" text should be `on_surface` (#e5e1e4) to prevent eye strain in dark studio environments.
- **Don’t** use standard 4px rounded corners for everything. Use `none` or `sm` (2px) for a sharper, more industrial "machine-cut" edge.
- **Don’t** use standard dropdowns. Use "overlay" glass panels that blur the background, maintaining the "HUD" feel.