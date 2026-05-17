# Database Integration Plan

## 1. Overview
Synex Digital will utilize a MySQL database to manage dynamic content such as blog posts, case studies, career openings, and submitted contact inquiries. The provided schema (`synex-next-imran.sql`) will serve as the foundation.

## 2. Technology Choice
- **Database:** MySQL
- **ORM (Object-Relational Mapping):** Prisma (Recommended for Next.js App Router for excellent TypeScript integration and developer experience) or Drizzle ORM.
- **Client:** `@prisma/client`

## 3. Integration Workflow

### Step 1: Environment Setup
Store the connection string securely in `.env`:
```env
DATABASE_URL="mysql://user:password@host:port/synex_db"
```

### Step 2: ORM Initialization (Prisma Example)
1. Initialize Prisma: `npx prisma init`
2. Update the generated `schema.prisma` file to match the structure defined in `synex-next-imran.sql`. This involves translating the raw SQL `CREATE TABLE` statements into Prisma models.

### Step 3: Database Client Instantiation
Create a singleton database client in `/lib/db/index.ts` to prevent connection exhaustion during development (hot reloading):

```typescript
import { PrismaClient } from '@prisma/client'

const prismaClientSingleton = () => {
  return new PrismaClient()
}

declare global {
  var prismaGlobal: undefined | ReturnType<typeof prismaClientSingleton>
}

const prisma = globalThis.prismaGlobal ?? prismaClientSingleton()

export default prisma

if (process.env.NODE_ENV !== 'production') globalThis.prismaGlobal = prisma
```

### Step 4: Data Fetching Strategy (Server Components)
Leverage Next.js Server Components to fetch data directly from the database without needing API routes for read operations. This is faster and more secure.

*Example in a Page Component (`app/(site)/blog/page.tsx`):*
```tsx
import prisma from '@/lib/db'
import BlogCard from '@/components/cards/BlogCard'

export default async function BlogPage() {
  const posts = await prisma.post.findMany({
    where: { published: true },
    orderBy: { createdAt: 'desc' }
  })

  return (
    <div className="grid gap-6 md:grid-cols-3">
      {posts.map(post => <BlogCard key={post.id} data={post} />)}
    </div>
  )
}
```

### Step 5: Data Mutation Strategy (Server Actions)
Use Next.js Server Actions for handling form submissions (e.g., Contact Form, Newsletter Signup) instead of traditional API routes.

*Example Server Action (`app/actions/contact.ts`):*
```typescript
'use server'
import prisma from '@/lib/db'

export async function submitContactForm(formData: FormData) {
  const name = formData.get('name')
  // ... validation logic ...
  
  await prisma.inquiry.create({
    data: { name: name as string /* ... */ }
  })
  
  return { success: true }
}
```

## 4. Security & Optimization
- **Connection Pooling:** Ensure the database host supports connection pooling (e.g., via PgBouncer or Prisma Accelerate) if traffic scales.
- **Prepared Statements:** Using Prisma automatically protects against SQL injection via parameterized queries.
- **Caching:** Utilize Next.js `unstable_cache` or standard `fetch` caching mechanisms for database queries that don't change often (like service lists or team members).
