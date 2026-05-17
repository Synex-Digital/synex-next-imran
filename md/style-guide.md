# Style Guide

## 1. Brand Identity
**Brand Name:** Synex Digital  
**Industry:** Custom Software Engineering / Digital Agency  
**Vibe:** Premium, Futuristic, Clean, Conversion-focused, Authoritative  
**Design Language:** Modern AI-focused, suitable for an advanced engineering agency.

## 2. Color Palette

### Primary Colors
- **Synex Blue (Primary Action):** `#4555fd`
  - *Usage:* Primary buttons, active states, key text highlights, branding elements.
- **Background (Dark Theme Preference):** `#050505` to `#0a0a12`
  - *Usage:* Main application background to emphasize the premium/futuristic feel.
- **Surface (Cards/Containers):** `#11111a` to `#1a1a24`
  - *Usage:* Card backgrounds, modal windows, dropdowns.
- **Text (Primary):** `#ffffff` or `#f8f9fa`
  - *Usage:* Headings, primary body copy.
- **Text (Secondary):** `#a1a1aa` (Zinc-400)
  - *Usage:* Subtitles, descriptive text, muted links.

### Gradients
- **Primary Gradient:** `linear-gradient(to right, #4555fd, #8a2be2)`
  - *Usage:* Hero text fills, primary button hover states, decorative borders.
- **Subtle Glow:** `radial-gradient(circle at center, rgba(69, 85, 253, 0.15) 0%, transparent 70%)`
  - *Usage:* Background ambient lighting behind key sections.

### Utility Colors
- **Success:** `#10b981` (Emerald)
- **Warning:** `#f59e0b` (Amber)
- **Error:** `#ef4444` (Red)
- **Border/Divider:** `#27272a` (Zinc-800)

## 3. Typography

### Headings (Display)
- **Font Family:** `Outfit`, `Space Grotesk`, or `Clash Display`
- **Weight:** Semi-bold (600) to Bold (700)
- **Tracking:** Tighter letter spacing (`tracking-tight`)
- **Usage:** Hero titles, section headings.

### Body Copy (Sans Serif)
- **Font Family:** `Inter`, `Geist`, or `Plus Jakarta Sans`
- **Weight:** Regular (400) to Medium (500)
- **Line Height:** Relaxed (`leading-relaxed`) for readability.
- **Usage:** Paragraphs, descriptions, small UI text.

### Monospace (Technical Details)
- **Font Family:** `JetBrains Mono` or `Fira Code`
- **Usage:** Code snippets, technical specs, API references.

## 4. UI Elements & Components

### Buttons
- **Primary Button:** Background `#4555fd`, white text, slight rounding (`rounded-lg`), subtle glow on hover.
- **Secondary Button:** Transparent background, `#27272a` border, white text, hover background `#11111a`.
- **Interactions:** Scale down on click (`active:scale-95`), smooth transition (`transition-all duration-300`).

### Cards
- **Style:** Surface color background, subtle 1px border (`border-zinc-800`), slight rounding (`rounded-xl` or `rounded-2xl`).
- **Hover State:** Lift up slightly (`-translate-y-1`), border glows to a faint `#4555fd`, background slightly lighter.
- **Glassmorphism:** For overlay cards, use background blur (`backdrop-blur-md`) with semi-transparent dark backgrounds.

### Imagery
- **Format:** Strict 1:1 square ratio for all placeholders, profiles, and thumbnails.
- **Treatment:** Slight darkening overlay or blue tint to match brand colors. Rounded corners to match cards (`rounded-xl`).

## 5. Spacing & Layout
- Utilize a consistent 4pt/8pt grid (Tailwind defaults).
- Emphasize macro whitespace. Sections should have `py-24` or `py-32` spacing on desktop to feel uncluttered and premium.
- Gap between grid items should typically be `gap-6` or `gap-8`.

## 6. Motion & Animation
- **Philosophy:** Purposeful, smooth, and tech-forward. Never jarring.
- **Timing:** Use `ease-out` for entering elements, `ease-in` for exiting. Standard duration `300ms` or `500ms`.
- **Scroll Reveal:** Fade in and slide up (`opacity-0 translate-y-4` to `opacity-100 translate-y-0`) as user scrolls down.
- **Micro-interactions:** Navigation links should have a subtle underline animation on hover. Icons should slightly scale or bounce on interaction.
