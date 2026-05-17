# Home Page Plan

## 1. Page Purpose
Serve as the primary entry point for Synex Digital, establishing instant credibility as a premium, AI-focused software engineering agency. Introduce core services and drive visitors toward booking a consultation.

## 2. Target User Intent
Quickly evaluate if Synex has the technical chops and premium quality required to handle high-stakes custom software projects. Seek contact or proof of work.

## 3. Recommended Route
`/` (Root page handled by `app/(site)/page.tsx`)

## 4. Page Sections
1. **Hero Section:** High-impact value proposition.
2. **Client Logos:** Social proof (trusted by...).
3. **Core Services Grid:** What we do.
4. **Technology Stack:** Tools we use (brief overview).
5. **Featured Case Studies:** Proof of success.
6. **Testimonials:** Client quotes.
7. **Final CTA (Cal.com embedded or linked):** Push to book.

## 5. Section-by-Section Content Guidance
- **Hero:** H1 should be bold (e.g., "Engineering the Digital Future"). Subtext focusing on scalable, AI-driven solutions. Two buttons: Primary ("Book Discovery Call"), Secondary ("View Our Work").
- **Services:** 3-4 cards highlighting Web Apps, AI Integration, Cloud Architecture, etc.
- **Tech Stack:** Infinite scrolling marquee of logos (React, Next.js, Node, Python, AWS, etc.).
- **Case Studies:** 2 featured projects highlighting the problem, solution, and impact.
- **Final CTA:** A large, gradient-heavy section prompting the user to schedule a call.

## 6. Suggested UI Components
- `<HeroSection>` (complex layout with background glow)
- `<ServiceCard>` (glassmorphism design)
- `<TechMarquee>` (infinite scroll animation)
- `<CaseStudyCard>` (image heavy)
- `<CalBooking>` (in the final CTA section or via modal)

## 7. Animation and Interaction Guidance
- **Hero:** Text fades in and slides up consecutively. Background features a slow, subtle radial gradient shift.
- **Scroll:** Sections fade in as they enter the viewport.
- **Cards:** `<ServiceCard>` should elevate (`-translate-y-2`) and glow (`#4555fd`) on hover.

## 8. Image Usage Guidance
- All case study thumbnails and generic section graphics MUST use a 1:1 square aspect ratio (`aspect-square`).
- Hero might use a stylized 1:1 3D tech abstract graphic aligned to the right.

## 9. CTA Strategy
- Primary action across the page is "Book a Call" routing to Cal.com integration.
- Secondary actions route deeper into the site (Services, Case Studies).

## 10. SEO Metadata Suggestions
- **Title:** `Synex Digital | Advanced Custom Software Engineering & AI Agency`
- **Description:** `Partner with Synex Digital to build high-performance web applications, scalable cloud architectures, and AI-driven solutions. Premium engineering for modern business.`

## 11. Database Content Requirements
- Featured Case Studies can be fetched via Prisma: `prisma.caseStudy.findMany({ where: { featured: true }, take: 2 })`.
- Testimonials can be fetched via Prisma: `prisma.testimonial.findMany({ take: 3 })`.

## 12. Responsive Design Behavior
- **Mobile:** Hero stacks vertically. Grids (Services/Case Studies) become 1 column. Tech marquee moves slower.
- **Desktop:** Hero is 2-column or wide center-aligned. Grids are 2 or 3 columns. Generous macro whitespace.

## 13. Development Notes for Next.js and Tailwind
- Use Server Components by default.
- Client component needed for `<TechMarquee>` (for animation logic) and `<CalBooking>`.
- Use Tailwind's `bg-gradient-to-r` and `backdrop-blur` utilities extensively.

## 14. Reusable Components Needed
- `Button`
- `Badge` (for tech tags)
- `ServiceCard`
- `CaseStudyCard`
- `SectionHeading`
