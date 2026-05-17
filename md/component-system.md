# Component System Strategy

## 1. Overview
Synex Digital's website will use a component-based architecture built with React and Tailwind CSS. The goal is modularity, reusability, and consistency across the entire platform.

## 2. Component Hierarchy
We will organize components into specific domains to prevent a cluttered root component directory:

- **`/components/ui` (Base UI Elements)**
  - Primitive, reusable elements.
  - *Examples:* Button, Input, Badge, Dialog, Dropdown, Card.
  - *Tech:* Often built using a library like shadcn/ui or Radix UI for accessibility, styled with Tailwind.

- **`/components/layout` (Structural Components)**
  - Components that dictate the macro structure of pages.
  - *Examples:* Navbar, Footer, PageContainer, Sidebar, Container.

- **`/components/sections` (Page Blocks)**
  - Complex, full-width sections that combine multiple UI elements and layout components. Designed to be dropped into pages.
  - *Examples:* HeroSection, FeatureGrid, TestimonialCarousel, PricingTable, ContactFormSection.

- **`/components/cards` (Data Display)**
  - Specific card layouts for different data types.
  - *Examples:* CaseStudyCard, BlogCard, TeamMemberCard, ServiceCard.

- **`/components/forms` (Input Handling)**
  - Form wrappers and complex input groups.
  - *Examples:* ContactForm, NewsletterSignup, AssessmentForm.

- **`/components/animations` (Motion Wrappers)**
  - Reusable Framer Motion components for consistent scroll reveals and hover effects.
  - *Examples:* FadeIn, SlideUp, HoverScale, ParallaxScroll.

- **`/components/navigation` (Routing UI)**
  - Specialized navigation components.
  - *Examples:* Breadcrumbs, Pagination, MobileMenu.

## 3. Implementation Guidelines

### Props and Types
- All components must be typed using TypeScript.
- Define a strict `Props` interface for every component.
- Use `React.ReactNode` for children props.

### Styling Configuration
- Use `clsx` and `tailwind-merge` (typically combined into a `cn` utility function) to handle dynamic classes and prevent Tailwind class conflicts.
- For components with many visual states (e.g., Buttons), use Class Variance Authority (`cva`) to define design system variants cleanly.

### State Management
- Prefer stateless (dumb) components for UI and Sections.
- Hoist state up to the Page level or specialized Client Components where necessary.
- By default, assume Next.js Server Components. Only add `"use client"` when interactivity (hooks, event listeners) is required.

### 1:1 Image Requirement
- For any component displaying an image (cards, heroes, team grids), enforce an aspect-square wrapper:
```tsx
<div className="relative aspect-square w-full overflow-hidden rounded-xl bg-zinc-900">
  <Image src={src} alt={alt} fill className="object-cover" />
</div>
```

## 4. Best Practices
- **Single Responsibility:** A component should do one thing well. If a section becomes too complex, break it down into smaller sub-components.
- **Consistent Naming:** Use PascalCase for component files (e.g., `HeroSection.tsx`) and standard exports.
- **Avoid Hardcoding:** Pass data (like card content) as props rather than hardcoding text inside the component file, especially for sections used across multiple pages.
