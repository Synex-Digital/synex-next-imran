# Privacy Policy Page Plan

## 1. Page Purpose
Fulfill legal requirements by detailing how Synex Digital collects, uses, and protects user data.

## 2. Target User Intent
Understand data handling practices, usually required by compliance teams or concerned users.

## 3. Recommended Route
`/privacy-policy` (Handled by `app/(site)/privacy-policy/page.tsx`)

## 4. Page Sections
1. **Header:** "Privacy Policy" with last updated date.
2. **Content Blocks:** Standard legal boilerplate (Data Collection, Usage, Cookies, Third-Party Services, User Rights).

## 5. Section-by-Section Content Guidance
- Use clear, hierarchical headings (H2, H3) for readability.
- Mention Cal.com usage for booking data.

## 6. Suggested UI Components
- `<LegalLayout>` (A constrained-width container for text readability).

## 7. Animation and Interaction Guidance
- Minimal. Focus is on fast loading and readability.

## 8. Image Usage Guidance
- None required.

## 9. CTA Strategy
- None required.

## 10. SEO Metadata Suggestions
- **Title:** `Privacy Policy | Synex Digital`
- Add a `<meta name="robots" content="noindex">` if you prefer legal pages stay out of search results (optional, but often standard).

## 11. Database Content Requirements
- None. Fully static.

## 12. Responsive Design Behavior
- Constrain text width on large screens to prevent excessively long lines of text (e.g., `max-w-4xl mx-auto`).

## 13. Development Notes for Next.js and Tailwind
- Use the `@tailwindcss/typography` plugin (`prose` class) to style the raw HTML/Markdown content effortlessly.

## 14. Reusable Components Needed
- `LegalContainer`
