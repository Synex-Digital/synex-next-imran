# SEO Strategy Plan

## 1. Core Objectives
- Ensure Synex Digital ranks highly for keywords related to "custom software engineering," "digital agency," and specific technology stacks (e.g., Next.js, Node.js).
- Maximize click-through rates (CTR) from search engine result pages (SERPs) using optimized metadata and schema markup.
- Ensure technical excellence so search engines can crawl and index the site perfectly.

## 2. Technical SEO Implementation (Next.js)

### Metadata API
Utilize Next.js 14+ Metadata API to define title, description, and Open Graph data in the `layout.tsx` (global defaults) and individual `page.tsx` files.

*Example Global Setup (`app/layout.tsx`):*
```tsx
import { Metadata } from 'next'

export const metadata: Metadata = {
  title: {
    template: '%s | Synex Digital',
    default: 'Synex Digital | Advanced Custom Software Engineering',
  },
  description: 'Synex Digital is a premium software engineering agency specializing in modern web apps, AI integration, and scalable digital solutions.',
  openGraph: {
    type: 'website',
    locale: 'en_US',
    url: 'https://synex.digital',
    siteName: 'Synex Digital',
    images: [{ url: '/images/og-default.jpg' }], // Must use 1:1 or standard OG ratio
  },
  twitter: {
    card: 'summary_large_image',
  },
}
```

### Semantic HTML
- Enforce strict use of structural tags: `<nav>`, `<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`.
- **Heading Hierarchy:** Every page MUST have exactly one `<h1>`. Subsections should follow logical `<h2>`, `<h3>` structures without skipping levels.

### Dynamic Routes
For database-driven content (Blogs, Case Studies):
- Use `generateMetadata` in dynamic routes (`app/(site)/blog/[slug]/page.tsx`) to pull the SEO title and description directly from the database record.

## 3. On-Page SEO Best Practices

### Image Optimization
- All images must use the Next.js `<Image>` component for automatic WebP conversion and resizing.
- Every image must have a descriptive `alt` attribute.
- Ensure strict 1:1 aspect ratios for layout stability (prevents Cumulative Layout Shift - CLS).

### Internal Linking
- Implement breadcrumbs for deep pages (e.g., Services, Blog Posts).
- Contextual linking within blog posts and case studies to related service pages.
- Robust footer navigation.

## 4. Performance as SEO
- Achieve green Core Web Vitals.
- Rely heavily on Server Components to minimize client-side JavaScript execution.
- Lazy load off-screen animations and heavy components.

## 5. Structured Data (Schema.org)
Implement JSON-LD schema markup for rich snippets.
- **Organization Schema:** On the Home or About page.
- **Service Schema:** On individual service pages.
- **Article Schema:** On blog posts.
- **BreadcrumbList Schema:** On all nested pages.

*Implementation method: Inject a `<script type="application/ld+json">` tag in the layout or page component.*

## 6. Sitemaps and Robots
- Use `app/sitemap.ts` to dynamically generate a `sitemap.xml` that includes all static pages and dynamically queries the database for all active blog posts, case studies, and career openings.
- Create an `app/robots.ts` file to allow crawling of the site and point to the sitemap.
