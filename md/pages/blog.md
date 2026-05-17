# Blog Page Plan

## 1. Page Purpose
Drive organic traffic through SEO-optimized content. Establish thought leadership in software engineering, AI, and digital strategy.

## 2. Target User Intent
Learn about new technologies, find solutions to specific technical or business problems, and gauge the agency's expertise.

## 3. Recommended Route
- List View: `/blog`
- Single View: `/blog/[slug]`

## 4. Page Sections (List View)
1. **Hero:** "Insights & Engineering Notes."
2. **Featured Post:** Highlight the most recent or most important article.
3. **Categories/Tags:** Filter by Engineering, Design, AI, Business.
4. **Post Grid:** Chronological list of articles.
5. **Newsletter Signup:** Capture emails.

## 5. Page Sections (Single View)
1. **Article Header:** Title, Author (with 1:1 avatar), Date, Reading Time.
2. **Featured Image:** Large header image (1:1 ratio preferred for consistency if displayed in a specific layout, otherwise standard 16:9).
3. **Article Content:** Markdown/Rich text rendered content.
4. **Share Buttons:** Twitter, LinkedIn.
5. **Author Bio:** Brief blurb about the writer.
6. **Related Posts:** 2-3 similar articles.
7. **CTA:** Contact for related services.

## 6. Suggested UI Components
- `<BlogCard>`
- `<NewsletterForm>`
- `<MarkdownRenderer>` (e.g., `next-mdx-remote` or similar if using MDX, or standard HTML renderer for DB content).
- `<AuthorBadge>`

## 7. Animation and Interaction Guidance
- **Cards:** Standard hover lift and glow.
- **Reading Progress:** A thin progress bar at the top of the single article view that fills as the user scrolls.

## 8. Image Usage Guidance
- **Thumbnails (List):** STRICTLY 1:1 aspect ratio.
- **Author Avatars:** STRICTLY 1:1 aspect ratio, rounded full (`rounded-full`).

## 9. CTA Strategy
- Newsletter signup in the list view.
- Soft service CTA at the end of the article ("Need help with [Topic]? Let's talk.").

## 10. SEO Metadata Suggestions
- **List Title:** `Engineering Blog & Insights | Synex Digital`
- **Single Title:** `[Post Title] | Synex Digital`
- **Crucial:** Implement Article Schema (`application/ld+json`) on single post pages.

## 11. Database Content Requirements
- Fetch from database via Prisma.
- `prisma.post.findMany({ where: { published: true }, include: { author: true } })`

## 12. Responsive Design Behavior
- **Mobile:** Typography must be perfectly legible (minimum 16px body, 1.6 line height).
- **Desktop:** Constrain article reading width (e.g., `max-w-3xl`) to ensure comfortable line lengths.

## 13. Development Notes for Next.js and Tailwind
- Use `prose` class from `@tailwindcss/typography` plugin for styling the main article content easily. Customize the `prose` colors to match the dark theme in `tailwind.config.ts`.

## 14. Reusable Components Needed
- `BlogCard`
- `NewsletterForm`
- `AuthorBadge`
