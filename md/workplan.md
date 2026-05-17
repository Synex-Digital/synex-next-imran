# Synex Digital Website: Master Workplan

This document tracks the step-by-step development process for the Synex Digital website. Check off items as they are completed.

## Phase 1: Project Initialization & Configuration
- [ ] Initialize Next.js app with App Router (`npx create-next-app@latest`).
- [ ] Configure `tailwind.config.ts` (colors: `#4555fd`, dark theme, custom fonts, animation utilities).
- [ ] Set up the master global stylesheet (`app/globals.css`).
- [ ] Create the required folder structure (e.g., `/components`, `/lib`, `/app/(site)`).
- [ ] Install essential dependencies (`framer-motion`, `lucide-react`, `clsx`, `tailwind-merge`).
- [ ] Setup image placeholder assets (1:1 square ratio) in `/public/images`.

## Phase 2: Database & Backend Foundation
- [ ] Setup local MySQL database instance.
- [ ] Import and run `synex-next-imran.sql` schema (e.g., via XAMPP phpMyAdmin).
- [ ] Install `mysql2` and configure environment variables in `.env`.
- [ ] Create raw SQL connection pool singleton in `/lib/db/index.ts` (*Cross-check `md/database-integration.md`*).
- [ ] Install and configure `@calcom/embed-react` for booking.

## Phase 3: Core UI Component Library
- [ ] **UI Primitives:** Button, Input, Textarea, Badge.
- [ ] **Layout Components:** Global Navbar (with mobile hamburger menu) and Footer.
- [ ] **Animation Wrappers:** `<FadeIn>`, `<SlideUp>`, `<HoverScale>` using Framer Motion.
- [ ] **Card Components:** `<ServiceCard>`, `<CaseStudyCard>`, `<BlogCard>`, `<TechLogoCard>`.
- [ ] **Forms:** Reusable Contact Form component with validation (Zod + React Hook Form).
- [ ] **Cal.com Wrapper:** Setup `<CalBooking>` component.

## Phase 4: Static Page Assembly
*Build out the UI for each page using mock data first to perfect responsive layouts. IMPORTANT: Before starting any page, you MUST read its specific planning document in the `md/pages/` directory.*
- [ ] **Home Page** (`app/(site)/page.tsx`): Hero, Logos, Services, Tech, Case Studies, CTA. (*Cross-check `md/pages/home.md`*)
- [ ] **About Page** (`app/(site)/about/page.tsx`): Manifesto, Values, Team Grid. (*Cross-check `md/pages/about.md`*)
- [ ] **Services Page** (`app/(site)/services/page.tsx`): Service details, Process flow. (*Cross-check `md/pages/services.md`*)
- [ ] **Technology Page** (`app/(site)/technology/page.tsx`): Tech stack grids. (*Cross-check `md/pages/technology.md`*)
- [ ] **Industry Page** (`app/(site)/industry/page.tsx`): Industry use cases. (*Cross-check `md/pages/industry.md`*)
- [ ] **Privacy Policy & Terms of Service** (`app/(site)/privacy-policy`, `app/(site)/terms-of-service`): Text layouts. (*Cross-check `md/pages/privacy-policy.md` and `md/pages/terms-of-service.md`*)

## Phase 5: Dynamic Page Integration
*Hook up the UI to the MySQL Database using Server Components. IMPORTANT: Review database content requirements in the corresponding page markdown files in `md/pages/`.*
- [ ] **Case Studies List & Single** (`/case-studies` & `/case-studies/[slug]`): Fetch projects dynamically. (*Cross-check `md/pages/case-studies.md`*)
- [ ] **Blog List & Single** (`/blog` & `/blog/[slug]`): Fetch articles, implement Markdown rendering. (*Cross-check `md/pages/blog.md`*)
- [ ] **Career Page** (`/career`): Fetch open job roles. (*Cross-check `md/pages/career.md`*)
- [ ] **Events Page** (`/events`): Fetch upcoming events/webinars. (*Cross-check `md/pages/events.md`*)
- [ ] **Contact Page** (`/contact`): Implement Server Action to write form submissions to the DB. (*Cross-check `md/pages/contact.md`*)

## Phase 6: Polish, Animations & QA
- [ ] **Responsive Audit:** Test layouts strictly on Mobile, Tablet, and Ultrawide monitors. Fix any horizontal scrolling issues.
- [ ] **Animation Audit:** Ensure scroll reveals and hover effects (glows, scale) are smooth and purposeful.
- [ ] **Image Audit:** Verify strict adherence to the 1:1 image aspect ratio rule across all cards and grids.
- [ ] **Accessibility Audit:** Check color contrast, keyboard navigation, and ARIA labels.

## Phase 7: SEO & Final Deployment
- [ ] Implement global metadata configuration (`app/layout.tsx`).
- [ ] Implement dynamic metadata for Blog and Case Studies.
- [ ] Add JSON-LD Structured Data (Organization, Articles).
- [ ] Generate dynamic `sitemap.xml` and `robots.txt`.
- [ ] Deploy to production hosting (e.g., Vercel).
- [ ] Final end-to-end testing of Contact Form and Cal.com booking on the live URL.
