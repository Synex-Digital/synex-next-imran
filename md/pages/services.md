# Services Page Plan

## 1. Page Purpose
Provide a comprehensive overview of Synex Digital's offerings. Detail the methodology, deliverables, and value proposition for each service category.

## 2. Target User Intent
Determine if the agency has the specific capabilities needed for their project (e.g., "Do they do AI integrations?", "Can they build a React Native app?").

## 3. Recommended Route
`/services` (Handled by `app/(site)/services/page.tsx`)

## 4. Page Sections
1. **Hero:** High-level statement on capabilities.
2. **Service Details (List/Scroll Spy):** Deep dives into specific offerings:
   - Custom Web Application Development
   - Mobile App Development
   - AI & Machine Learning Integration
   - Cloud Architecture & DevOps
   - UI/UX Product Design
3. **Our Methodology/Process:** Step-by-step how we work (Discovery -> Design -> Develop -> Deploy).
4. **CTA:** Book a scoping session.

## 5. Section-by-Section Content Guidance
- **Hero:** "End-to-end digital engineering."
- **Service Details:** Each service should have its own block featuring a title, description, key deliverables list (bullet points), and a representative 1:1 graphic.
- **Process:** A 4-step horizontal or vertical flow chart.

## 6. Suggested UI Components
- `<PageHeader>`
- `<ServiceDetailBlock>` (Alternating left/right layout on desktop)
- `<ProcessStep>` (Numbered icon + description)
- `<DeliverableList>` (Checkmark list)

## 7. Animation and Interaction Guidance
- **Service Blocks:** Use scroll-spy. As the user scrolls, a sticky sidebar menu highlights the current service in view.
- **Process Steps:** Reveal sequentially as they enter the viewport.

## 8. Image Usage Guidance
- **Service Graphics:** Abstract 3D renders, clean UI mockups, or stylized code snippets. MUST be strictly 1:1 aspect ratio.

## 9. CTA Strategy
- After each major service block, include a subtle text link: "Discuss this service with us ->"
- Large global CTA at the bottom to book a call via Cal.com.

## 10. SEO Metadata Suggestions
- **Title:** `Our Services | Custom Software & AI Development | Synex Digital`
- **Description:** `Explore Synex Digital's premium services: custom web apps, mobile development, AI integration, UI/UX design, and cloud architecture.`

## 11. Database Content Requirements
- Usually static, but services could be modeled in the database if they need to be linked dynamically to case studies or team members. (Static implementation preferred for performance unless requested otherwise).

## 12. Responsive Design Behavior
- **Mobile:** Alternating left/right layouts stack vertically (Image top, Text bottom). Sticky sidebars become horizontal scroll menus or disappear.
- **Desktop:** Utilize sticky positioning for navigation or imagery while text scrolls alongside.

## 13. Development Notes for Next.js and Tailwind
- Use `position: sticky` and `top-24` in Tailwind for scroll-tracking elements.
- Consider utilizing Intersection Observer (via a hook or Framer Motion's `useInView`) to trigger animations or update active states.

## 14. Reusable Components Needed
- `PageHeader`
- `ServiceDetailBlock`
- `ProcessStep`
- `StickyNav`
