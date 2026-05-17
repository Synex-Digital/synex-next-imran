# About Page Plan

## 1. Page Purpose
Humanize the agency. Build trust by explaining the company's origin, core values, and showcasing the leadership/engineering team. 

## 2. Target User Intent
Understand *who* is behind Synex Digital. Assess cultural fit, engineering philosophy, and verify team expertise before committing to a project.

## 3. Recommended Route
`/about` (Handled by `app/(site)/about/page.tsx`)

## 4. Page Sections
1. **Hero/Manifesto:** Our vision and mission.
2. **Our Story:** Brief history and timeline.
3. **Core Values:** Grid of principles (e.g., Code Quality, Transparency).
4. **Leadership/Team Grid:** Profiles of key personnel.
5. **Office/Culture (Optional):** Images of the work environment.
6. **CTA:** Join the team (Careers) or Start a project (Contact).

## 5. Section-by-Section Content Guidance
- **Hero:** Text-heavy, manifesto style. "We build the software that builds your business."
- **Values:** 3-4 distinct values with custom icons. Emphasize engineering excellence and design-first thinking.
- **Team:** Grid layout showing headshots, names, and roles. 

## 6. Suggested UI Components
- `<PageHeader>` (Standardized inner-page hero)
- `<ValueCard>` (Icon + Title + Description)
- `<TeamMemberCard>` (Image + Details)
- `<Timeline>` (Vertical or horizontal timeline component)

## 7. Animation and Interaction Guidance
- **Timeline:** Nodes light up as the user scrolls past them.
- **Team Cards:** On hover, image slightly zooms (`scale-105`), and a social links overlay (LinkedIn/Twitter) fades in.

## 8. Image Usage Guidance
- **Team Headshots:** STRICTLY 1:1 square ratio. High quality, professional but modern (perhaps black and white with a blue brand color hover state).
- **Culture/Office:** Also adhere to the 1:1 aspect ratio constraint for consistency.

## 9. CTA Strategy
- Dual CTA at the bottom: "Looking for a partner? Let's Talk." (Primary) and "Want to build with us? View Careers." (Secondary).

## 10. SEO Metadata Suggestions
- **Title:** `About Us | Synex Digital`
- **Description:** `Meet the team of expert software engineers and designers at Synex Digital. Learn about our mission, values, and engineering philosophy.`

## 11. Database Content Requirements
- Team members can optionally be fetched from the database if dynamic updates are needed: `prisma.teamMember.findMany()`.

## 12. Responsive Design Behavior
- **Mobile:** Team grid collapses to 2 columns or 1 column depending on screen size. Timeline becomes strictly vertical.
- **Desktop:** Elaborate 3-column or 4-column team grid.

## 13. Development Notes for Next.js and Tailwind
- Primarily a static page, so fully leverage Server Components.
- Use `next/image` aggressively for team photos to ensure fast loading and strict aspect ratios.

## 14. Reusable Components Needed
- `PageHeader`
- `ValueCard`
- `TeamMemberCard`
- `CTASection`
