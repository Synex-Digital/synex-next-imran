# Development Phase Workflow

## 1. Philosophy
The development phase will strictly adhere to the "Design-First, Develop-Second" methodology. Code is written only after the UI design system and page layout plans (the markdown files) are established. 

## 2. Development Milestones

### Phase 1: Environment & Foundation
1. **Repository Setup:** Initialize Next.js app (`npx create-next-app@latest`).
2. **Tailwind Configuration:** Customize `tailwind.config.ts` with brand colors, fonts, and animation utilities as defined in `style-guide.md`.
3. **Folder Structure:** Create the directories outlined in `folder-structure.md`.
4. **Database Setup:** Connect MySQL, initialize Prisma/ORM based on `synex-next-imran.sql`, and run initial migrations (`database-integration.md`).
5. **Asset Pipeline:** Add 1:1 placeholder images, fonts, and icons.

### Phase 2: UI Component Library
1. **Base Elements:** Develop primitive UI components (`/components/ui`): Buttons, Inputs, Typography wrappers, Badges.
2. **Layout Components:** Build the global Navbar (with responsive mobile menu) and Footer.
3. **Motion System:** Create Framer Motion wrapper components (e.g., `<FadeIn>`, `<SlideUp>`) in `/components/animations`.
4. **Cards & Displays:** Build standard data display components (Blog Card, Service Card) ensuring strict 1:1 image implementation.

### Phase 3: Core Page Assembly (Static First)
*For each page, consult the corresponding `/md/pages/[page].md` document.*
1. **Home Page:** Build the hero, feature grid, and CTA sections.
2. **Core Pages:** Develop About, Services, Technology, and Industry pages using static mock data to ensure layout integrity.
3. **Utility Pages:** Implement Contact, Privacy Policy, and Terms of Service.

### Phase 4: Dynamic Integration & Backend
1. **Cal.com Integration:** Implement the booking embed on the Contact page and Hero CTAs (`cal-booking-integration.md`).
2. **Database Hookup:** Replace static mock data on Blog, Case Studies, and Career pages with real Prisma database queries using Server Components.
3. **Form Actions:** Implement Server Actions for the contact form, ensuring data writes securely to the MySQL database.

### Phase 5: Polish & Optimization
1. **Animation Pass:** Ensure all scroll reveals, hover states, and micro-interactions feel premium and performant.
2. **Responsive Audit:** Test layouts rigorously on mobile, tablet, and desktop viewports. Ensure fluid scaling.
3. **SEO Implementation:** Add dynamic metadata, Open Graph tags, and ensure semantic HTML structures (`seo-plan.md`).
4. **Performance Tuning:** Audit image loading, analyze bundle sizes, and ensure perfect Lighthouse scores.

## 3. AI Agent Instructions During Development
When an AI agent is tasked with building a feature:
1. **Read the PRD & Style Guide:** Ensure the general vibe and technical constraints are understood.
2. **Read the Specific Page Markdown:** Always consult the exact page requirement document before writing code.
3. **Build Modularly:** Create reusable sections in `/components/sections` rather than dumping all code into the `page.tsx` file.
4. **Verify Constraints:** Double-check that all images use the 1:1 aspect ratio constraint and that the primary brand color (`#4555fd`) is utilized correctly.
