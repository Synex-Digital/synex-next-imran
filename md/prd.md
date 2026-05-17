# Product Requirements Document (PRD)

## 1. Project Overview
Synex Digital is a custom software engineering and digital agency. The goal of this project is to create a new, high-performance, conversion-focused website that reflects the company's technical expertise, premium brand, and AI-focused approach. The website will be designed first, followed by development once the design system and page plans are finalized.

## 2. Business Goals
- Establish Synex Digital as a premium, advanced software engineering agency.
- Generate high-quality leads for custom software development projects.
- Streamline the booking process for prospective clients via Cal.com.
- Showcase technical expertise, industry experience, and past success stories.
- Attract top engineering talent to join the team.

## 3. Target Audience
- **Primary:** C-level executives (CTOs, CIOs, CEOs) and VPs of Engineering at mid-market to enterprise companies looking for reliable, high-end software development partners.
- **Secondary:** Product Managers and startup founders seeking to build robust MVPs or scale existing platforms.
- **Tertiary:** Software engineers and tech professionals looking for career opportunities.

## 4. Website Objectives
- Drive targeted traffic through SEO-optimized content (Blog, Industry pages, Technology pages).
- Convert visitors into qualified leads through clear CTAs and easy booking (Cal.com).
- Build trust through case studies, client testimonials, and transparent technology stacks.
- Provide a seamless, fast, and accessible user experience across all devices.

## 5. Brand Direction
- **Vibe:** Premium, futuristic, clean, conversion-focused, trustworthy, and authoritative.
- **Theme:** Modern AI-focused design language.
- **Tone of Voice:** Professional, technical yet accessible, confident, and innovative.

## 6. Visual Design System
- **Aesthetic:** Dark mode preferred (or highly contrasted light mode with deep blue accents), utilizing glassmorphism, subtle glows, and deep gradients to convey a "futuristic tech" feel.
- **Imagery:** 1:1 square format for all placeholders, utilizing high-quality, abstract tech visuals, team photos, and clean UI mockups.
- **Shape Language:** Sharp edges with slight rounding (e.g., `rounded-lg` or `rounded-xl`) for a modern, approachable feel.

## 7. Color System
- **Primary Color:** `#4555fd` (Vibrant Blue). Used for primary CTAs, active states, and key highlights.
- **Secondary Colors:** Deep navy/black for backgrounds (e.g., `#0a0f1c`), slate grays for secondary text and borders.
- **Gradients:** Blue-themed gradients (e.g., `from-[#4555fd] to-[#8a2be2]` or `from-[#1e3a8a] to-[#4555fd]`) for section backgrounds, text gradients, and hover effects.

## 8. Typography Recommendations
- **Primary Font:** `Inter`, `Geist`, or `Plus Jakarta Sans` for clean, highly legible UI text and body copy.
- **Heading Font:** `Outfit`, `Space Grotesk`, or `Clash Display` for bold, technical, and striking headlines.
- **Hierarchy:** Clear distinction between H1 (massive, gradient), H2 (section headers), H3 (card titles), and body text.

## 9. Layout Principles
- **Grid System:** Standard 12-column CSS grid/Tailwind grid for flexible, responsive layouts.
- **Spacing:** Generous whitespace (macro whitespace) to let content breathe and create a premium feel. Use Tailwind's spacing scale consistently (e.g., `py-24` for sections).
- **Alignment:** Left-aligned text for readability, centered for hero sections and key statements.

## 10. Animation and Interaction Principles
- **Scroll Effects:** Reveal animations (fade-in up) as elements enter the viewport (using Framer Motion).
- **Hover Effects:** Subtle scale up (`hover:scale-[1.02]`), glow effects (`hover:shadow-[0_0_15px_#4555fd]`), and gradient shifts on cards and buttons.
- **Click Interactions:** Ripple effects or slight scale down (`active:scale-95`) for tactile feedback.
- **Micro-interactions:** Animated icons, magnetic buttons, and smooth state transitions.
- **Motion Guidelines:** Keep animations swift and purposeful (e.g., `duration-300 ease-out`).

## 11. Component System Strategy
- **Atomic Design:** Build from small UI elements (buttons, inputs) up to complex sections (hero, footer).
- **Reusability:** Create highly configurable components using React props and Tailwind `cva` (Class Variance Authority) for styling variations.
- **Modularity:** Sections should be plug-and-play across different pages.

## 12. Folder Structure Recommendation
Use the Next.js App Router with a route group for site pages:
```txt
/app
  /(site)
    /home
    /about
    /services
...
/components
  /layout
  /sections
  /ui
...
/lib
...
```
*(See `folder-structure.md` for full details)*

## 13. Tech Stack & CSS Architecture
- **Framework:** Next.js (App Router) for Server-Side Rendering (SSR), Static Site Generation (SSG), and optimal SEO.
- **CSS Architecture (Master File & Inheritance):** We will use a master global stylesheet (`app/globals.css`) containing base Tailwind directives, global typography rules, and CSS variables. Every page automatically inherits this file. If a specific page or component needs custom styling that breaks from the master layout, we will use scoped Tailwind utility classes or CSS Modules (e.g., `page.module.css`) to locally override the global styles without breaking other pages.
- **Database:** MySQL for robust, relational data storage (using Prisma or Drizzle ORM).
- **Animations:** Framer Motion for complex scroll and layout animations.
- **Booking:** Cal.com for seamless scheduling without leaving the site experience.

## 14. Database Integration Planning
- Use the provided `synex-next-imran.sql` schema.
- Implement an ORM (e.g., Prisma) to interact with the MySQL database.
- Create API routes or Server Actions in Next.js to handle data fetching (e.g., blog posts, case studies) and form submissions (e.g., contact form).
*(See `database-integration.md` for full details)*

## 15. Cal.com Booking Integration Plan
- Embed the Cal.com widget directly into the Contact page and key conversion points using `@calcom/embed-react`.
- Configure routing so users are directed to a "Thank You" page upon successful booking to track conversions.
*(See `cal-booking-integration.md` for full details)*

## 16. SEO Strategy
- **Technical SEO:** Utilize Next.js Metadata API for dynamic `<title>`, `<meta>`, and Open Graph tags.
- **Semantic HTML:** Strict use of `<header>`, `<main>`, `<article>`, `<section>`, and proper H1-H6 hierarchy.
- **Performance:** Ensure Core Web Vitals (LCP, FID, CLS) are in the green.
- **Sitemap/Robots:** Auto-generate `sitemap.xml` and `robots.txt`.

## 17. Accessibility Requirements
- **WCAG 2.1 AA Compliance:** Minimum target.
- **Keyboard Navigation:** Ensure all interactive elements are focusable and usable via keyboard.
- **ARIA Labels:** Use ARIA attributes for custom UI components (e.g., modals, accordions).
- **Color Contrast:** Ensure sufficient contrast ratios, especially against dark backgrounds.

## 18. Performance Requirements
- **Images:** Use `next/image` for automatic optimization, WebP format, and lazy loading.
- **Fonts:** Use `next/font` to avoid layout shifts and optimize font loading.
- **Bundle Size:** Keep client-side JavaScript to a minimum by utilizing Server Components by default.

## 19. Responsive Design Requirements
- **All-Device Friendly:** The design must adapt flawlessly to any screen size—from ultrawide 4K monitors down to the smallest mobile devices.
- **Mobile-First Approach:** Design and build for mobile (`sm`) first, then gracefully scale up to tablet (`md`, `lg`) and desktop (`xl`, `2xl`).
- **Touch Targets & Navigation:** Minimum 44x44px for touch interactions on mobile. Mobile navigation must be intuitive and easily accessible.
- **Fluid Layouts:** Ensure content adapts smoothly without horizontal scrolling, using flexible grids and responsive padding.

## 20. Security Considerations
- **Form Protection:** Implement rate limiting, CSRF protection, and honeypots on contact forms.
- **Database Access:** Use environment variables for sensitive credentials. Do not expose ORM queries on the client.
- **Headers:** Implement secure HTTP headers (e.g., Content Security Policy).

## 21. Design-First Workflow
1. Create wireframes based on the page markdown files.
2. Develop a high-fidelity UI design system (Figma) using the defined color palette and typography.
3. Design individual pages, focusing on interactions and responsiveness.
4. Finalize all visual assets (1:1 square placeholders/images).
5. Review and approve designs before moving to development.

## 22. Development-Phase Workflow
1. Initialize Next.js project with Tailwind CSS.
2. Setup folder structure and install necessary dependencies (Framer Motion, Lucide Icons, Cal.com embed).
3. Build the core UI component library (`/components/ui`).
4. Develop global layout components (Navbar, Footer).
5. Build pages section by section, starting with Home.
6. Integrate MySQL database and dynamic content routing.
7. Implement Cal.com booking.
8. Perform QA, accessibility, and performance testing.

## 23. Instructions for AI Agent Usage of Page Markdown Files
- Read the corresponding `md/pages/[page-name].md` file before generating code for a specific page.
- Follow the exact section structure, component recommendations, and CTA strategy defined in the file.
- Implement the requested animations, SEO metadata, and responsive behaviors outlined in the document.
- Adhere to the strict 1:1 image aspect ratio for all image placeholders.
- Treat the markdown file as the absolute source of truth for the page's requirements.
