# Industry Page Plan

## 1. Page Purpose
Demonstrate domain expertise. Show that Synex understands the specific challenges and regulatory requirements of various industries.

## 2. Target User Intent
Find evidence that the agency has solved problems similar to theirs in their specific sector (e.g., Healthcare, FinTech, E-commerce).

## 3. Recommended Route
`/industry` (Handled by `app/(site)/industry/page.tsx`)

## 4. Page Sections
1. **Hero:** "Solutions tailored for your sector."
2. **Industry Grid:**
   - FinTech (Security, high volume)
   - Healthcare (HIPAA, data privacy)
   - E-commerce / Retail (Scalability, conversions)
   - SaaS / B2B (Multi-tenant, analytics)
   - Logistics & Supply Chain (Real-time tracking, optimization)
3. **Cross-Industry Capabilities:** What applies everywhere (UX, Performance, Security).
4. **CTA:** Industry-specific consultation.

## 5. Section-by-Section Content Guidance
- **Industry Grid:** Each industry should have a card with a relevant icon/image, a brief description of the challenges solved, and a link to related case studies if available.

## 6. Suggested UI Components
- `<PageHeader>`
- `<IndustryCard>` (Large format card)
- `<FeatureList>` (For cross-industry capabilities)

## 7. Animation and Interaction Guidance
- **Cards:** Subtle hover states. When hovered, display a "View Case Studies" button or text link.

## 8. Image Usage Guidance
- **Industry Graphics:** Abstract representations of the industry (e.g., data charts for FinTech, connected nodes for Logistics). MUST use a 1:1 aspect ratio.

## 9. CTA Strategy
- "Talk to an industry expert." Link to Cal.com booking.

## 10. SEO Metadata Suggestions
- **Title:** `Industries We Serve | FinTech, Healthcare, SaaS | Synex Digital`
- **Description:** `Expert software engineering tailored for FinTech, Healthcare, E-commerce, and SaaS. We build secure, compliant, and scalable industry solutions.`

## 11. Database Content Requirements
- Static definitions of industries, but could dynamically count/link to case studies categorized by industry via Prisma.

## 12. Responsive Design Behavior
- **Mobile:** 1-column layout for industry cards.
- **Desktop:** 2 or 3-column masonry or standard grid layout.

## 13. Development Notes for Next.js and Tailwind
- Keep UI consistent with the Services page but distinct enough to feel like a different content category.

## 14. Reusable Components Needed
- `PageHeader`
- `IndustryCard`
