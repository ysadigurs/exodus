# Design System Strategy: The Wandering Storyteller

## 1. Overview & Creative North Star
This design system is built upon the North Star of **"The Digital Pop-Up Book."** We are moving away from the rigid, flat "app" feel toward an immersive, tactile experience that feels like a physical heirloom. 

To achieve a high-end, bespoke feel for an audience of ages 5-12, we utilize **Organic Asymmetry**. This means bypassing the traditional 12-column grid in favor of overlapping elements, "sticking out" illustrations, and soft, nested layers. The goal is to make the interface feel like a series of ancient scrolls and modern maps layered on a sun-drenched table. By breaking the edges of containers with illustrative elements, we invite the child to explore rather than just "consume" content.

## 2. Colors: A Warm, Adventurous Palette
The palette is rooted in the "Nile-to-Desert" spectrum. We avoid harsh blacks and stark whites to maintain a soft, inviting atmosphere.

*   **Primary (#775600):** The "Ancient Gold." Used for primary actions and key storytelling headers.
*   **Secondary (#005f9c):** The "Sky & Water." Reserved for navigational elements and discovery-based interactions.
*   **Tertiary (#006b1b):** The "Nile Green." Used for progress, growth, and success states.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited. They create a "clinical" look that contradicts the adventurous theme. Instead:
*   **Color-Shift Boundaries:** Define sections by transitioning from `surface` (#fdf7df) to `surface-container-low` (#f7f1d7).
*   **Tonal Nesting:** A card (`surface-container-lowest`) should sit on a background of `surface-container` (#efe9cd) to create a soft, natural edge.

### The "Glass & Gradient" Rule
To add "soul" to the UI, use subtle gradients. 
*   **Hero Backgrounds:** Transition from `primary_container` (#fdbc13) to `surface_bright` (#fdf7df) at a 120-degree angle to mimic a sunrise.
*   **Glassmorphism:** For floating navigation bars or pause menus, use `surface` at 80% opacity with a `20px` backdrop blur. This allows the vibrant illustrations of the Bible stories to bleed through the UI, keeping the child immersed.

## 3. Typography: The Friendly Script
We use two distinct families to balance personality with readability, ensuring full support for Hebrew characters.

*   **Display & Headlines (Plus Jakarta Sans):** Chosen for its geometric clarity and friendly, open apertures.
    *   *Usage:* Use `display-lg` (3.5rem) for chapter titles. Use `headline-md` (1.75rem) for character names.
*   **Body & Titles (Be Vietnam Pro):** A highly legible sans-serif with rounded terminals that mirror the soft corners of our components.
    *   *Usage:* Use `body-lg` (1rem) for story text to ensure it is readable for developing eyes.

**Identity Note:** The hierarchy is intentionally exaggerated. High-contrast sizing (e.g., a `display-lg` headline next to a `body-md` caption) creates an editorial, "premium book" feel.

## 4. Elevation & Depth: Tonal Layering
We reject traditional drop shadows in favor of **Tonal Stacking** and **Ambient Glows**.

*   **The Layering Principle:** 
    *   Level 0 (Base): `surface` (#fdf7df).
    *   Level 1 (Sections): `surface-container-low` (#f7f1d7).
    *   Level 2 (Interactive Cards): `surface-container-lowest` (#ffffff).
*   **Ambient Shadows:** If a button needs to "pop," use a shadow with a blur of `24px` at 6% opacity, using the `on-surface` color (#312f1f). This mimics the soft shadow of a pebble on sand.
*   **The "Ghost Border" Fallback:** If a container needs more definition (e.g., in high-sunlight outdoor use), use `outline-variant` (#b2ad98) at **15% opacity**. Never use a solid, 100% opaque stroke.

## 5. Components: Tactile & Playful

### Buttons: The "Pressable Stone"
Buttons must feel like physical objects.
*   **Primary:** Background `primary`, roundedness `lg` (2rem). Use a 4px bottom-offset "shadow" using `on_primary_fixed_variant` to make it look 3D and "pushable."
*   **Sizing:** Minimum height of `3.5rem` (Spacing 10) to accommodate "fat-finger" navigation.

### Cards: The "Papyrus" Sheet
*   **Style:** No borders. Use `surface-container-lowest` with a `xl` (3rem) corner radius. 
*   **Layout:** Forbid divider lines. Use Spacing `8` (2.75rem) to separate internal content blocks.

### Progress Bars: The "Vine"
*   **Style:** Instead of a flat bar, use a `tertiary` (#006b1b) track. The "thumb" should be a playful icon (like a leaf or a star).

### Input Fields: The "Scribe's Box"
*   **Style:** `surface-container-high` background with a `md` (1.5rem) roundedness. The label should use `label-md` in `primary` color to maintain the warm, adventurous tone.

### Additional Components: Story Map Nodes
*   **Style:** Large, circular `secondary_container` nodes that pulse slightly. These act as the primary way children navigate between Bible stories.

## 6. Do's and Don'ts

### Do:
*   **Overlap Elements:** Let a character illustration (e.g., Noah’s Ark) break the top boundary of a card.
*   **Use Generous White Space:** Use Spacing `12` or `16` between major sections to prevent cognitive overload.
*   **Prioritize Hebrew Legibility:** Ensure line-heights for Hebrew text are 1.5x the font size to accommodate vowel marks (Niqqud).

### Don't:
*   **Use Pure Black:** Never use `#000000`. Use `on_surface` (#312f1f) for all "black" text to keep the warmth.
*   **Use Sharp Corners:** The `none` and `sm` roundedness tokens should be avoided for visible containers.
*   **Use Divider Lines:** Never use a horizontal rule to separate content. Use a background color shift or a `1.4rem` (Spacing 4) vertical gap.