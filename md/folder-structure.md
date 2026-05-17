# Folder Structure Recommendation

## 1. Root Directory Setup
The project will utilize the standard Next.js App Router structure, enhanced with specific directories for scalable architecture.

```txt
synex-next-imran/
├── app/                  # Next.js App Router (Pages & Routing)
│   ├── (site)/           # Route Group: Marketing site pages (shares layout)
│   │   ├── about/
│   │   ├── blog/
│   │   ├── career/
│   │   ├── case-studies/
│   │   ├── contact/
│   │   ├── events/
│   │   ├── industry/
│   │   ├── privacy-policy/
│   │   ├── services/
│   │   ├── technology/
│   │   ├── terms-of-service/
│   │   ├── page.tsx      # Home Page
│   │   └── layout.tsx    # Global Site Layout (Navbar, Footer)
│   ├── api/              # Route Handlers (REST endpoints)
│   │   ├── contact/
│   │   └── webhooks/
│   ├── layout.tsx        # Root HTML Layout (Font injection, Providers)
│   └── globals.css       # Global Tailwind CSS and base styles
├── components/           # Reusable UI Architecture
│   ├── animations/       # Framer Motion wrappers
│   ├── cards/            # Reusable card UI elements
│   ├── forms/            # Form components (Contact, Newsletter)
│   ├── layout/           # Structure components (Navbar, Footer, Grid)
│   ├── navigation/       # Menus, Breadcrumbs
│   ├── sections/         # Large page blocks (Hero, Features, CTA)
│   └── ui/               # Base UI elements (Buttons, Inputs - shadcn style)
├── lib/                  # Utilities and core logic
│   ├── db/               # Database connection and queries (Prisma/Drizzle setup)
│   ├── cal/              # Cal.com integration utilities
│   ├── seo/              # SEO helper functions and default metadata
│   └── utils.ts          # General utility functions (e.g., tailwind merge 'cn')
├── styles/               # Additional style configuration (if needed beyond globals)
├── content/              # Static content, JSON data, or local markdown content
├── public/               # Static assets
│   ├── images/           # Placeholder images (1:1 aspect ratio)
│   ├── icons/            # SVG icons
│   └── fonts/            # Local font files
├── docs/                 # General project documentation
└── md/                   # AI Planning documentation
    ├── prd.md
    ├── style-guide.md
    ├── component-system.md
    ├── folder-structure.md
    ├── database-integration.md
    ├── development-phase.md
    ├── cal-booking-integration.md
    ├── seo-plan.md
    └── pages/            # Individual page instructions
        ├── home.md
        ├── about.md
        └── ...
```

## 2. Key Architectural Decisions

- **Route Groups (`(site)`):** Using a route group allows us to apply a consistent `layout.tsx` (containing the Navbar and Footer) to all public-facing marketing pages without affecting specialized routes (like an admin dashboard or a standalone landing page, if added later).
- **Colocation Avoidance:** Keep complex component logic out of the `app` directory. The `app` directory should strictly handle routing, metadata, and basic data fetching, delegating UI rendering to the `components` directory.
- **Centralized Utils:** The `lib` folder acts as the brain for external integrations and repetitive logic, ensuring code is DRY (Don't Repeat Yourself).
