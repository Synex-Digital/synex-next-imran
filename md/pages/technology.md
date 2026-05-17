# Technology Page Plan

## 1. Page Purpose
Showcase technical depth. Prove to technical stakeholders (CTOs, VPs of Eng) that Synex utilizes modern, scalable, and secure technology stacks.

## 2. Target User Intent
Verify tech stack alignment. Ensure the agency uses modern frameworks (React, Next.js, Node) rather than legacy systems.

## 3. Recommended Route
`/technology` (Handled by `app/(site)/technology/page.tsx`)

## 4. Page Sections
1. **Hero:** "Built on modern foundations."
2. **Tech Stack Categories:**
   - Frontend (React, Next.js, Tailwind)
   - Backend (Node.js, Python, Go)
   - Database (MySQL, PostgreSQL, MongoDB, Redis)
   - Infrastructure & DevOps (AWS, Vercel, Docker, GitHub Actions)
   - AI & Data (OpenAI, LangChain, TensorFlow)
3. **Architecture Philosophy:** Why we choose these tools (Performance, Scalability, DX).
4. **CTA:** Discuss technical architecture.

## 5. Section-by-Section Content Guidance
- **Categories:** Group technologies logically. Use the official logo for each technology.
- **Philosophy:** A brief text section explaining the preference for App Router, Server Components, and strong typing (TypeScript).

## 6. Suggested UI Components
- `<PageHeader>`
- `<TechCategoryGrid>` (Contains multiple `<TechLogoCard>`s)
- `<TechLogoCard>` (Logo + Name)
- `<PhilosophyBlock>` (Text + Icon)

## 7. Animation and Interaction Guidance
- **Logo Cards:** Simple hover lift and border glow (`border-[#4555fd]`).
- **Grid Reveal:** Staggered fade-in for tech logos within a category.

## 8. Image Usage Guidance
- **Logos:** Ensure all technology logos are SVG or high-res PNGs centered within a 1:1 aspect ratio container.

## 9. CTA Strategy
- Direct to contact with a specific prompt: "Have a specific stack requirement? Let's discuss your architecture."

## 10. SEO Metadata Suggestions
- **Title:** `Our Tech Stack | Modern Engineering at Synex Digital`
- **Description:** `We build robust, scalable applications using Next.js, React, Node.js, Python, AWS, and cutting-edge AI technologies.`

## 11. Database Content Requirements
- Completely static page. No DB requirements.

## 12. Responsive Design Behavior
- **Mobile:** Tech grids reduce to 2 or 3 columns (small icons).
- **Desktop:** Wide grids (4-6 columns) for tech logos.

## 13. Development Notes for Next.js and Tailwind
- Excellent candidate for 100% Server Components.
- Use a local JSON file or constants array to map through the technologies and render the grid to keep the `page.tsx` clean.

## 14. Reusable Components Needed
- `PageHeader`
- `TechLogoCard`
