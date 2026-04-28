# Module 08 | Palette Font Kit (ChatGPT)

<span style="color: #ED7D31;">**ZtM Academy | Vibe Coding Bootcamp | Become an AI-Augmented Developer</span>**

#### Lessons
- Palette Font Kit - Prompt
- Palette Font Kit - Prompt Creation
- Palette Font Kit - Part 2
- Palette Font Kit - Part 3
- Palette Font Kit - Part 4

## Planning

### Project Description
The instructor uses the **ChatGPT Chat Website** and the **ChatGPT 5 Pro LLM** to build a Random Aesthetic Generator web application. This web application produces cohesive color palettes and font pairings and displays their previews. The presented designs can be shuffled, saved/loaded to/from favorites, and exported as CSS variables or JSON objects. It is intended to be a portfolio project to showcase the front-end web development capabilities of learners.

### Project Blueprint and Prompt Creation
The instructor prompts the AI coding assistant to define objectives, audience, features, and design for the Random Aesthetic Generator project. The instructor then directs the AI coding assistant to write the actual prompt (see below) that creates the code for the web application.

## Prompt (Under Construction)

### Role (>)
You are an expert front-end engineer and UX designer. You write clean, accessible, production-ready HTML/CSS/JavaScript for static websites (no build tools, no frameworks). You anticipate edge cases, document decisions in comments, and keep the UI neutral so generated aesthetics are the focus.

### Task (>)
Build a static **Random Aesthetic Generator** that produces cohesive color palettes and font pairings.

#### It must:
1. Generate a 4–6 color palette and display HEX values with copy-to-clipboard on click.
2. Generate a heading/body font pairing (from Google Fonts), load them dynamically, and render a live preview (H1 + paragraph + button sample).
3. Shuffle both with one action (button + keyboard shortcut).
4. Let users **Save/Favorite** combinations (palette + fonts) to `localStorage`, list them, re-apply them, and delete them.
5. Export the current combination as: **CSS variables** (copy block), **JSON** (download or copy).
6. Be **responsive**, **accessible** (WCAG AA contrast checks shown inline), and **polished** (subtle transitions).
7. Provide **light/dark UI modes** (toggle) without affecting generated colors or preview background (keep preview neutral).
8. Start with **3 curated defaults** — “Minimal”, “Playful”, and “Bold” — so the page doesn’t load empty.

### Context (>)
**Primary audience**: hiring managers and recruiters evaluating polish and range.  
**Secondary audience**: designers and developers who may actually use the tool.

#### Design System for the UI Chrome (not the generated output)
(-) Neutral background: light `#f9fafb`, dark `#1e1e1e`, one accent (e.g., **indigo** `#6366f1`) for controls; (-) **card-based layout**, generous spacing, rounded corners, soft shadow; (-) **UI fonts**: Inter (headings) + Source Sans 3 or Roboto (body) for the app shell only.

#### Generated Preview
(-) Shows the chosen pairing applied to a **headline**, **subhead**, **paragraph**, and **sample button**; (-) palette swatches displayed in a **row (or wrapped on mobile)** with HEX labels and copy affordances; (-) **contrast checker**: for each swatch, compute contrast ratio vs. white and vs. black, mark pass/fail badges for **AA normal text (WCAG 2.1)**.

#### Engineering Notes
- **Static only (no server):** use client-side JS and Google Fonts CSS (inject `<link>` for selected families & weights);
- **Keep a small curated list of Google Fonts** (10–20 families) with known good pairings, randomize from that set to ensure quality;
- **Keyboard shortcuts:** `Space` = Shuffle, `S` = Save current, `C` = Copy CSS variables;
- **LocalStorage keys:** `aesthetic.favorites` (array), `aesthetic.settings` (theme preference);
- **Animations:** fade/slide of swatches and preview, 150–250ms, `prefers-reduced-motion` respected;
- **Copy utilities:** use `navigator.clipboard.writeText` with fallbacks.

### Constraints (>)

#### Delivery
- Deliver a **pure static solution:** one `index.html` with embedded `<style>` and `<script>`
- No build steps, no external JS frameworks, no CSS frameworks

#### Accessibility
- Semantic HTML (landmarks, labels), focus states, tab order, and ARIA where needed
- Contrast check badges must be **screen-reader friendly**
- Buttons and interactive swatches must be **keyboard navigable** and show focus rings

#### Performance
- Lazy-load Google Fonts **only when selected** (avoid loading entire set upfront)
- No blocking JS; defer script; minimize layout thrash

#### Code Quality
- Clear sections and comments
- Small, pure functions: `getRandomPalette`, `pickFontPair`, `applyFonts`, `renderPalette`, `renderPreview`, `saveFavorite`, `loadFavorites`, `exportCSSVars`, `exportJSON`, `checkContrast`
- No third-party JS dependencies

#### UI Neutrality
- The **app shell must never override or normalize** the generated palette or preview beyond layout
- The **generated results are the focus**

### Format (Done)
Return **exactly three code blocks** representing files:

1.  **index.html**
    - Includes the full page markup with inline `<style>` and `<script>`
    - Loads `Inter` + `Source Sans 3` (or `Roboto`) for the UI
    - Contains:
        - **Header:** title + dark/light toggle
        - **Main Area:**  
            a. Controls (Shuffle, Save, Copy CSS, Export JSON)  
            b. Palette card (swatches with HEX + copy)  
            c. Font pairing card (family names + live preview)  
            d. Favorites panel (list of saved combos with re-apply/delete)
        - **Footer:** tiny note about keyboard shortcuts and license
2. **`<style>` (inside the same index.html)**
    - Modern, minimal CSS: CSS variables, container widths, grid layout, focus styles
    - Dark mode via `.theme-dark` on `<html>`
    - Transition rules and `@media (prefers-reduced-motion)`
3. **`<script>` (inside the same index.html)**
    - Self-contained JS implementing all behaviors:
        - Curated font list
        - Sample palettes
        - Contrast checker (WCAG 2.1 formula)
        - LocalStorage handling
        - Clipboard utilities
        - Keyboard shortcuts
        - Dynamic Google Fonts `<link>` injection

---

### Acceptance Criteria
- [ ] Page loads with “Minimal” default applied.
- [ ] Shuffle works for both fonts and palette simultaneously.
- [ ] Copying a swatch copies its HEX value.
- [ ] Copy CSS copies `--color-1..n` vars and font families.
- [ ] Export JSON provides a valid schema.
- [ ] Saving adds to Favorites; re-apply and delete functions work.
- [ ] Contrast badges correctly show AA pass/fail vs. white and black.
- [ ] Fully responsive and keyboard accessible.
- [ ] Dark/light toggle persists across reloads.
- [ ] Helpful inline comments included.

## Implementation

### Code Generation and Deployment
The instructor (1) creates local and remote repositories for the project; (2) feeds the master prompt produced earlier into the AI coding assistant to generate the first draft of web application code; (3) directs the AI coding assistant to perform iterative testing and refinement to fine-tune the web application;

## Subtitle

---
