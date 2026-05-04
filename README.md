# Style Guide — “Python, With Depth”

Single-page editorial front end built by me, **Zino** Bonin, as “PY Editorial Field Guide / Python Issue 01”.  
It’s a responsive dark/light themed editorial about Python, built with vanilla HTML/CSS/JS and hosted on Firebase (`zino-project.web.app`).

---

## 1. Design philosophy & concept

I designed the page like a magazine: an editorial field guide, not a product landing page.  
Python is treated as a landscape to explore, not just a tool to document.

- Tone: confident, calm, slightly poetic, without drifting into pretentious.  
- Core metaphors: field guides, editorial typography, layered storytelling, expedition/scientific aesthetics.  
- The big serif markers (“Origin”, “Field”, “Culture”) anchor each chapter and sell the “field guide” framing.

---

## 2. Color system

The site runs on a dual-theme system powered by CSS custom properties.

### Dark theme (default)

- Background: `#07131f` — deep navy/charcoal almost black  
- Secondary background: `#0c1d2d` — slightly lighter navy  
- Surface panels: `rgba(15, 33, 52, 0.8)` — semi-transparent dark navy  
- Primary ink: `#f2f7ff` — near-white  
- Soft ink: `#b5c4d7` — cool light gray  
- Faint ink: `#8ca0b6` — gray-blue  
- Accent blue: `#6eb5f2` — bright cyan-blue  
- Deep blue: `#93cbff` — lighter sky blue  
- Accent yellow: `#ffd43b` — saturated yellow  
- Deep yellow: `#ffe277` — pale yellow

This theme is the “true” visual identity: night field work, notebooks, quiet glow.

### Light theme

- Background: `#ffe4f0` — soft pink  
- Secondary background: `#ffd6e8` — warmer pink  
- Surface panels: `rgba(255, 230, 241, 0.8)` — semi-transparent pink  
- Primary ink: `#3f1632` — deep magenta/purple  
- Soft ink: `#7a4768` — muted rose  
- Faint ink: `#9a6c88` — dusty pink  
- Accent blue/pink: `#d45a92` — rich raspberry  
- Deep accent: `#7f254f` — dark wine  
- Yellow accent: `#f3a97a` — warm amber

Light mode is intentionally more playful and print-like, but still feels like the same publication.

### Shared elements

- Code background:  
  - Dark: `#06111c`  
  - Light: `#7a2c55` (magenta)  
- Code text: near-white in both themes  
- Lines / dividers: low-opacity ink (around 14–24% alpha)  
- Shadows: big, soft, ink-tinted — never pure black

---

## 3. Typography

I use three typefaces across the page, all loaded from external CDNs:

| Role         | Typeface       | Style                     | Usage                                            |
|--------------|----------------|---------------------------|--------------------------------------------------|
| Primary      | Space Grotesk  | Sans-serif                | Body text, headings, nav, UI labels              |
| Monospace    | IBM Plex Mono  | Monospace                 | Code blocks, `pre`, `code`, technical labels     |
| Serif accent | Fraunces       | Serif, italic, bold 700   | “Origin / Field / Culture” markers, accent words |

Details that matter:

- Body line-height is `1.55` for easy, long-form reading.  
- In the hero, I mix Space Grotesk with italic Fraunces (“room to grow”) to get that editorial tension.  
- On wide screens (≥1280px), the base font size drops to `76%` (~10.64px root) to keep line lengths comfortable instead of blowing everything up.

---

## 4. Layout & grid

### Container

- Standard max width: `1200px`, expanding to `1480px` on big screens (≥1280px).  
- On mobile, I use `calc(100% - 1.2rem)` so content hugs the viewport without feeling cramped.

### Grids

- Hero: 2-column (`1.02fr / 0.98fr`), collapsing to a single column below 1100px.  
- Ecosystem map: 3 equal columns, then 2 on tablet, 1 on narrow mobile.  
- Manifesto / Principles: 2-column (`0.88fr / 1.12fr`), content left, visual/right column supporting it.  
- Journey: mirrors the manifesto split.

All grids use `gap: clamp(1.2rem, 4vw, 3rem)` so spacing breathes properly from phone to desktop.

---

## 5. Components

### Sticky navigation

- Height: `5.75rem`, sticks to the top.  
- Background: semi-transparent surface (around 0.84–0.86 alpha) plus backdrop blur.  
- Logo: Python logo in dark mode, my illustrated portrait in light mode.  
- Center nav links: Why Python, Possibilities, Journey, Ecosystem, Culture, Start.  
- Theme toggle on the right: labeled “DARK” / “LIGHT”.  
- Below 960px, nav links collapse into a hamburger.  
- A thin low-opacity bottom border keeps it separated from content.

### Tags / labels

- Small pill labels with a little “PY” icon badge.  
- Copy pattern: `[PY ICON] EDITORIAL FIELD GUIDE / PYTHON ISSUE 01`.  
- Fully uppercase, tight weight, and tracked out for that print vibe.  
- Flat surface background, subtle border, tiny shadow to lift them off the page.

### Section headers

- Category line: small, uppercase, spaced out (e.g. “ECOSYSTEM”, “COMMUNITY AND PHILOSOPHY”).  
- Big decorative wordmark behind: Fraunces (“Origin”, “Field”, “Culture”) as a watermark.  
- Main heading: bold Space Grotesk, sometimes mixed with italic Fraunces for single words or phrases.

### Cards / panels

Used for hero panels, principles, and other content blocks:

- Background: `--surface-flat` (most opaque surface).  
- Border: `1px solid var(--line)` — barely there, but it helps separation.  
- Radius: `--radius-lg = 28px`, so everything feels soft and approachable.  
- Shadow: `--shadow-card`, a gentle diffuse shadow.  
- Hover: card lifts `-6px`, shadow deepens slightly, border gets a bit brighter.  
- Timing: `240ms cubic-bezier(0.2, 1, 0.2, 1)` for movement, `ease` for the shadow.

### Buttons

Two main button types:

1. Primary (Install / Download Python)  
   - 135° gradient from `--blue` to `--blue-deep`.  
   - Text in near-white `#f8fbff`.  
   - Fully pill-shaped (`border-radius: 999px`).  
   - Min-height `3.2rem`, padding `0.9rem 1.25rem`.  
   - Colored drop shadow for depth.  
   - Hover: `translateY(-3px) scale(1.01)` with a `220ms` transition.

2. Secondary (See what it can build)  
   - Transparent background.  
   - `1px` border in `var(--line-strong)`.  
   - Text uses `--ink-soft`.  
   - Same pill shape and sizing as the primary button.

### Code blocks

- Background: `--code-bg` (near-black in dark, magenta `#7a2c55` in light).  
- Text: `--code-ink` (near-white).  
- Font: IBM Plex Mono, applied to all `pre` and `code`.  
- Used for small examples and a highlighted Zen of Python block.

---

## 6. Visual effects & backgrounds

### Page backgrounds

- Dark: linear gradient from `--bg` to `--bg-secondary` (navy stack).  
- Light: radial glow (soft pink around 18%/12%) over a gentle linear gradient.

### Hero glow

The hero gets two very soft glows (`hero-glow-a` and `hero-glow-b`) behind key content to give it a gentle halo and depth without turning into neon.

### Watermarks

I lay large Fraunces words behind content:

- “Origin” in the opening section  
- “Field” around the ecosystem map  
- “Culture” in the community section  

They act like chapter titles in a print publication, but integrated into the layout.

### Accent gradients & shadows

- `--accent-surface`: a 140° gradient that blends blue and yellow with low alpha, tilted differently between dark (blue/magenta leaning) and light (pink/yellow leaning).  
- `--stage-accent`: a CSS variable that changes with the active “Possibility” category.  
- Shadows come in three tiers:  
  - `--shadow`: big dramatic shadow for hero cards (e.g. 24px blur, 72px Y spread on dark).  
  - `--shadow-soft`: medium for regular cards.  
  - `--shadow-card`: subtle base shadow for smaller surfaces.

---

## 7. Interactions & animation

JavaScript is a progressive enhancement layer only.  
No JS? The site still works fine — just without motion.

### Scroll reveal

- Elements marked with `data-reveal` start at `opacity: 0` and `translateY(28px)`.  
- An `IntersectionObserver` (threshold `0.18`, `rootMargin: -8%`) watches them.  
- On entry, they animate over `720ms` with `cubic-bezier(0.2, 1, 0.2, 1)` and then stop observing.  
- The revealed state is represented by an `is-visible` class.

### Hover behavior

- Cards and panels: `240ms` `cubic-bezier(0.2, 1, 0.2, 1)` for transform, `ease` for shadow.  
- Buttons: `220ms` transitions for movement and shadow.  
- Nav links: subtle underline or color changes on hover.  
- Everything leans toward smooth, snappy ease-out rather than harsh linear motion.

### Possibilities section (dynamic content)

There’s a “Possibilities” stage with tabs: Web, Automation, Data, AI, Tooling, Learning.

- Clicking a tab swaps the kicker, title, description, tools, outcome, and code example.  
- A `--stage-accent` variable drives the accent styling per category.  
- Transitions smooth out the visual shifts so it feels like one cohesive stage, not a jump cut.

### Theme toggle

- Toggles `data-theme="dark"` and `data-theme="light"` on the root element.  
- Saves the choice in `localStorage`.  
- On first load, if nothing is saved, it respects `prefers-color-scheme`.

---

## 8. Accessibility

I tried to keep the editorial look without sacrificing basic accessibility.

- `aria-pressed` on the theme toggle.  
- `aria-expanded` on the mobile nav trigger.  
- `aria-live="polite"` on the dynamic “Possibilities” content area.  
- `aria-label` on the theme toggle button text.  
- `aria-current="true"` on the active nav link.  
- Smooth scrolling via `scroll-behavior: smooth` on `html`.  
- `prefers-reduced-motion: reduce` is respected — animations drop to ~`0.01ms` so the site is essentially static for those users.

---

## 9. Section structure

This is a single, scrolling page broken into clear chapters:

1. **Hero / Top**  
   - “Python gives ideas room to grow” as the main statement.  
   - Primary CTAs to install/download and to explore.

2. **Why Python**  
   - Four principles (01–04): clarity, many kinds of work, prototype-to-production, readability culture.

3. **Possibilities**  
   - Interactive use-case picker (Web, Automation, Data, AI, Tooling, Learning).  
   - Each view has its own story, tools, outcome, and code snippet.

4. **Journey**  
   - Five-step learning path, roughly from REPL to shipping and sharing.

5. **Ecosystem**  
   - Grid of six categories: Web Foundations, Data Stack, AI/ML, Automation, Quality/Packaging, Visualization.

6. **Culture**  
   - Community notes, a bit of the Zen of Python, plus a field-of-use summary.

7. **Start building**  
   - Final CTA section with three links: Download, Tutorial, PyPI.

---

## 10. Technical stack

| Layer         | Technology                               |
|---------------|------------------------------------------|
| Markup        | Vanilla HTML5, semantic structure        |
| Styling       | Vanilla CSS with custom properties       |
| Interactivity | Vanilla JavaScript, no framework         |
| Hosting       | Firebase (`zino-project.web.app`)        |
| Fonts         | Space Grotesk, IBM Plex Mono, Fraunces   |
| Icons         | Official Python logo, custom “PY” badge  |
| Images        | Portrait illustration drawn by me        |

It’s intentionally a single-page, no-dependency project to show what modern HTML, CSS Grid, custom properties, smooth scroll, IntersectionObserver and a bit of progressive enhancement can do without pulling in a framework.
