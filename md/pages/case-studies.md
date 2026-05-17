# Case Studies Page Plan

## 1. Page Purpose
Provide concrete proof of competence and success. Detail the problem, solution, and quantifiable results of past projects.

## 2. Target User Intent
Verify claims. Understand how Synex approaches complex problems and what the actual ROI/outcome was for previous clients.

## 3. Recommended Route
- List View: `/case-studies`
- Single View: `/case-studies/[slug]`

## 4. Page Sections (List View)
1. **Hero:** "Our Work. Real Results."
2. **Filters (Optional):** Filter by Industry or Technology.
3. **Case Study Grid:** List of past projects.
4. **CTA:** Start your project.

## 5. Page Sections (Single View)
1. **Project Header:** Title, Client Name, Industry, Tech Stack.
2. **The Challenge:** What was the problem?
3. **The Solution:** How did Synex solve it? (Architecture, design decisions).
4. **The Results:** Quantifiable metrics (e.g., "Increased conversion by 40%", "Reduced load time by 2s").
5. **Testimonial:** Quote from the client.
6. **Gallery:** UI mockups or architecture diagrams.
7. **Next Project CTA:** "Ready to be our next success story?"

## 6. Suggested UI Components
- `<CaseStudyCard>` (Thumbnail, Title, Summary, Tags)
- `<FilterBar>` (Client-side interactive filtering)
- `<MetricHighlight>` (Large numbers for results section)
- `<QuoteBlock>` (For testimonials)

## 7. Animation and Interaction Guidance
- **Grid:** Smooth layout transitions when filtering using Framer Motion (`layout` prop).
- **Cards:** Hover effect to reveal a "Read Full Story" overlay.

## 8. Image Usage Guidance
- **Thumbnails:** MUST be 1:1 aspect ratio. High-quality UI shots or stylized brand images.
- **Gallery (Single View):** Can vary, but 1:1 is preferred for grid consistency if placed in a gallery block.

## 9. CTA Strategy
- Highly prominent CTA at the bottom of every single case study page to capitalize on the inspiration/proof.

## 10. SEO Metadata Suggestions
- **List Title:** `Case Studies & Portfolio | Synex Digital`
- **Single Title:** `[Project Name] Case Study | Synex Digital` (Dynamic)

## 11. Database Content Requirements
- **Crucial:** Needs dynamic routing and database fetching.
- Prisma Query (List): `prisma.caseStudy.findMany({ include: { categories: true } })`
- Prisma Query (Single): `prisma.caseStudy.findUnique({ where: { slug: params.slug } })`

## 12. Responsive Design Behavior
- **Mobile:** Filters become a dropdown. Data visualization/metrics stack vertically.
- **Desktop:** Multi-column grid for the list. Side-by-side text and imagery for the single view.

## 13. Development Notes for Next.js and Tailwind
- Use `generateStaticParams` for the single views to pre-build all case study pages at build time (SSG) for maximum performance.
- Use Next.js `generateMetadata` for dynamic SEO tags based on the database content.

## 14. Reusable Components Needed
- `CaseStudyCard`
- `MetricHighlight`
- `QuoteBlock`
