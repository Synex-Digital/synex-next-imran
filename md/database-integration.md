# Database Integration Plan

## 1. Overview
Synex Digital will utilize a MySQL database to manage dynamic content such as blog posts, case studies, career openings, and submitted contact inquiries. The provided schema (`synex-next-imran.sql`) will serve as the foundation.

## 2. Technology Choice
- **Database:** MySQL (Local development via XAMPP)
- **Database Client:** Raw SQL using `mysql2/promise` (Provides excellent async/await support and connection pooling for Next.js).
- **ORM:** None. Direct SQL queries will be used for maximum control and performance.

## 3. Integration Workflow

### Step 1: Environment Setup
Store the database credentials securely in `.env` (configured for a standard local XAMPP setup):
```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=synex_db
```

### Step 2: Database Initialization
1. Ensure the XAMPP MySQL server is running.
2. Import the `synex-next-imran.sql` file into your local XAMPP phpMyAdmin or via MySQL CLI to create the `synex_db` schema.
3. Install the database driver in the Next.js project: `npm install mysql2`

### Step 3: Database Client Instantiation
Create a connection pool in `/lib/db/index.ts` to manage connections efficiently and prevent connection exhaustion during development (hot reloading):

```typescript
import mysql from 'mysql2/promise';

// Define the connection configuration
const dbConfig = {
  host: process.env.DB_HOST,
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_NAME,
  waitForConnections: true,
  connectionLimit: 10,
  queueLimit: 0
};

// Use a singleton pattern to prevent multiple pools in development
declare global {
  var mysqlPool: mysql.Pool | undefined;
}

const pool = globalThis.mysqlPool ?? mysql.createPool(dbConfig);

if (process.env.NODE_ENV !== 'production') globalThis.mysqlPool = pool;

export default pool;
```

### Step 4: Data Fetching Strategy (Server Components)
Leverage Next.js Server Components to fetch data directly from the database without needing API routes for read operations. This is faster and more secure.

*Example in a Page Component (`app/(site)/blog/page.tsx`):*
```tsx
import pool from '@/lib/db'
import { RowDataPacket } from 'mysql2'
import BlogCard from '@/components/cards/BlogCard'

// Define the expected TypeScript shape
interface Post extends RowDataPacket {
  id: number;
  title: string;
  slug: string;
  published: boolean;
  createdAt: Date;
}

export default async function BlogPage() {
  const [rows] = await pool.query<Post[]>(
    'SELECT * FROM posts WHERE published = 1 ORDER BY createdAt DESC'
  );

  return (
    <div className="grid gap-6 md:grid-cols-3">
      {rows.map(post => <BlogCard key={post.id} data={post} />)}
    </div>
  )
}
```

### Step 5: Data Mutation Strategy (Server Actions)
Use Next.js Server Actions for handling form submissions (e.g., Contact Form, Newsletter Signup) instead of traditional API routes.

*Example Server Action (`app/actions/contact.ts`):*
```typescript
'use server'
import pool from '@/lib/db'

export async function submitContactForm(formData: FormData) {
  const name = formData.get('name');
  const email = formData.get('email');
  // ... validation logic ...
  
  // Use .execute() instead of .query() for automatic prepared statements
  await pool.execute(
    'INSERT INTO inquiries (name, email) VALUES (?, ?)',
    [name, email]
  );
  
  return { success: true }
}
```

## 4. Security & Optimization
- **Connection Pooling:** The `mysql2` pool manages connections automatically, which is essential for serverless or edge environments.
- **Prepared Statements:** ALWAYS use `pool.execute()` with parameter arrays (`[var1, var2]`) for data mutations or queries with user input. This inherently protects against SQL injection. Never concatenate variables directly into the SQL string.
- **Caching:** Utilize Next.js `unstable_cache` or standard `fetch` caching mechanisms for database queries that don't change often (like service lists or team members).
