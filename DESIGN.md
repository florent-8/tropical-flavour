```markdown
# Design System Manual: High-Heat Tropical Editorial

## 1. Overview & Creative North Star: "The Neon Night Market"
This design system moves away from the sterile, corporate "white-box" food app. Our Creative North Star is **The Neon Night Market**. It captures the energy of street food—vibrant, high-heat, and unapologetically bold—while maintaining the sophisticated layout of a premium food editorial. 

We break the "template" look through **intentional asymmetry** (e.g., overlapping food photography across container boundaries) and **high-contrast typography scales**. The interface should feel like it’s glowing against a dark, moody alleyway. By utilizing deep charcoal foundations and layering vibrant citrus tones, we create "flavor credibility" that feels expensive but accessible.

## 2. Colors & Surface Logic

### The Palette
- **Primary (`#ff9f4a`):** Our "Heat." Use for main actions and key brand moments.
- **Secondary (`#ff725e`):** Our "Spice." Use for urgency, discounts, or "Extra Hot" flavor indicators.
- **Tertiary (`#ffe792`):** Our "Zest." Use for highlights, star ratings, and subtle accents.
- **Neutral/Surface (`#0e0e0e`):** Our "Charcoal." This is the canvas for all photography.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to section off content. Traditional dividers are forbidden. Boundaries must be defined solely through background color shifts. For example, a menu category section (`surface_container_low`) should sit directly on the main `surface` background. The change in depth should be felt, not seen as a line.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers stacked in a dark kitchen.
- **Base Layer:** `surface` (#0e0e0e) for the main background.
- **Section Layer:** `surface_container_low` (#131313) for large content blocks.
- **Card/Interaction Layer:** `surface_container` (#1a1a1a) or `surface_container_high` (#20201f) for interactive elements like product cards.
- **Nesting:** Place a `surface_container_highest` card inside a `surface_container_low` section to create natural lift without shadows.

### The "Glass & Gradient" Rule
To avoid a flat, "Bootstrap" feel:
- **Floating Navigation:** Use `surface` with 80% opacity and a 20px `backdrop-blur` to create a "Smoked Glass" effect.
- **Signature Textures:** Use a subtle linear gradient from `primary` (#ff9f4a) to `primary_container` (#fd8b00) on CTA buttons to mimic the glistening sheen of sauce.

## 3. Typography: The Flavor Scale

Our typography is designed to scream "Flavor" while ensuring the "Order Now" process is frictionless.

- **Display & Headlines (Epilogue):** This is our "Chunky Display" surrogate. It should be tracked tight (-2% to -4%) to feel dense and heavy. Use `display-lg` for hero marketing copy and `headline-lg` for menu categories.
- **Body & Titles (Inter):** Our workhorse. `body-lg` is for descriptions of heat and ingredients. `title-md` is reserved for item names.
- **Hierarchy Logic:** The massive contrast between a 3.5rem Display font and a 0.875rem Body font creates the "Editorial" feel. Do not be afraid of oversized type overlapping food photography.

## 4. Elevation & Depth: Tonal Layering

### The Layering Principle
Depth is achieved by stacking the surface-container tiers. Never use a drop shadow to separate two flat black surfaces; instead, change the token from `surface` to `surface_container_low`.

### Ambient Shadows
When an element must "float" (like a checkout modal), use a high-diffusion shadow:
- **Blur:** 40px - 60px.
- **Opacity:** 8%.
- **Color:** Use a tinted shadow (`#180800` / `on_primary_fixed`) instead of pure black to mimic the warm glow of heat lamps.

### The "Ghost Border" Fallback
If accessibility requires a container edge (e.g., an input field), use the `outline_variant` token at **15% opacity**. 100% opaque borders are strictly prohibited.

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_dim`). Roundedness: `md` (0.375rem). No border. Text color: `on_primary`.
- **Secondary:** Surface-only. Use `surface_container_highest` with a `surface_tint` (Primary) overlay at 10%.
- **Tertiary:** Pure text using `primary` color, bold weight, no container.

### Cards (The "Flavor Card")
- **Visuals:** Forbid divider lines.
- **Layout:** Food photography should bleed to the top and sides. Use `1.4rem` (Spacing 4) internal padding for text. 
- **Separation:** Use a background shift from `surface_container` to `surface_container_high` on hover to indicate interactivity.

### Inputs & Search
- **Style:** Use "Smoked Glass" (Low opacity `surface_variant` with blur). 
- **Active State:** Change border from Ghost Border (15% opacity) to 100% `primary` glow.

### Chips (Flavor Tags)
- **Selection:** Use `secondary_container` with `on_secondary_container` text for "Spicy" tags. 
- **Shape:** Use `full` (9999px) roundedness to contrast against the blockier headlines.

## 6. Do's and Don'ts

### Do:
- **Overlap Elements:** Let a dripping chicken wing image hang over the edge of its container and onto the `display-lg` typography.
- **Use High-Contrast Spacing:** Use `8.5rem` (Spacing 24) for vertical section gaps to create a "premium magazine" feel.
- **Embrace the Dark:** Keep 90% of the UI in the `surface` to `surface_container_high` range.

### Don't:
- **Don't use pure white (#FFFFFF) for everything:** Use `on_surface_variant` (#adaaaa) for secondary text to keep the "moody" vibe.
- **Don't use standard shadows:** No small, crisp, 2px offset shadows. They look "cheap" and digital.
- **Don't use dividers:** If you feel the need to add a line, add `1.4rem` of whitespace instead.