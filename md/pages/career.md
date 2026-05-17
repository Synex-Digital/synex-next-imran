# Career Page Plan

## 1. Page Purpose
Attract top-tier engineering, design, and product talent to join the Synex Digital team.

## 2. Target User Intent
Evaluate company culture, benefits, and view open positions.

## 3. Recommended Route
- List View: `/career`
- Single Job View: `/career/[id]` (Optional, could also just link to an external ATS like Lever/Greenhouse)

## 4. Page Sections
1. **Hero:** "Build the Future with Us."
2. **Culture/Perks:** Why work here? (Remote first, learning budget, top-tier gear).
3. **Open Roles (Job Board):** List of current vacancies categorized by department (Engineering, Design, Management).
4. **Testimonials (Employee):** Quotes from current team members.
5. **Spontaneous Application CTA:** "Don't see a fit? Send us your resume anyway."

## 5. Section-by-Section Content Guidance
- **Perks:** Use an icon grid. Keep descriptions punchy.
- **Job Board:** Clean list layout (Title, Location/Remote, Department) rather than heavy cards.

## 6. Suggested UI Components
- `<PerkCard>`
- `<JobListRow>` (Horizontal list item)
- `<EmployeeQuote>`

## 7. Animation and Interaction Guidance
- **Job Rows:** Background highlight on hover, arrow icon slides right to indicate clickability.

## 8. Image Usage Guidance
- **Culture Imagery:** 1:1 aspect ratio photos of the team collaborating or working remotely.

## 9. CTA Strategy
- "Apply Now" buttons on every job listing.

## 10. SEO Metadata Suggestions
- **Title:** `Careers | Join the Engineering Team | Synex Digital`
- **Description:** `We are hiring top engineers, designers, and strategists. Explore open roles and build the future of software with Synex Digital.`

## 11. Database Content Requirements
- Jobs can be fetched via Prisma: `prisma.job.findMany({ where: { active: true } })`.

## 12. Responsive Design Behavior
- **Mobile:** Job rows might stack department/location data below the title.
- **Desktop:** Job rows span horizontally with data neatly aligned in columns.

## 13. Development Notes for Next.js and Tailwind
- Simple, fast page. If integrating with a 3rd party ATS (Applicant Tracking System) API, do the fetching Server-Side.

## 14. Reusable Components Needed
- `PerkCard`
- `JobListRow`
