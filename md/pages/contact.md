# Contact Page Plan

## 1. Page Purpose
The primary conversion point. Facilitate easy communication and booking for prospective clients.

## 2. Target User Intent
Reach out to discuss a project, ask a question, or schedule a discovery call.

## 3. Recommended Route
`/contact` (Handled by `app/(site)/contact/page.tsx`)

## 4. Page Sections
1. **Hero:** "Let's Build Something Great."
2. **Split Layout (Main Content):**
   - **Left Side:** Contact information (Email, Phone, Office Address) and brief FAQ or expected response time.
   - **Right Side:** Tabbed interface or stacked choice between "Send a Message" (Standard Form) and "Book a Call" (Cal.com Embed).

## 5. Section-by-Section Content Guidance
- **Contact Info:** Keep it clear and clickable (`mailto:`, `tel:`).
- **Form:** Name, Email, Company, Project Details, Budget Range (Dropdown).
- **Cal.com Embed:** Direct calendar interface.

## 6. Suggested UI Components
- `<ContactForm>` (Client component for validation)
- `<CalBooking>` (Wrapper for `@calcom/embed-react`)
- `<Tabs>` (To switch between Form and Calendar)

## 7. Animation and Interaction Guidance
- **Form Validation:** Instant feedback on field blur. Smooth error message reveals.
- **Submit Button:** Loading state (spinner) while the Server Action processes.

## 8. Image Usage Guidance
- Generally minimal imagery on this page to avoid distracting from the conversion goal.

## 9. CTA Strategy
- "Send Message" (Form submit).
- "Select Time" (Cal.com interaction).

## 10. SEO Metadata Suggestions
- **Title:** `Contact Us | Synex Digital`
- **Description:** `Ready to start your next software project? Contact Synex Digital to schedule a discovery call or request a project estimate.`

## 11. Database Content Requirements
- Form submissions must write to the database.
- Server Action must call: `prisma.inquiry.create({ data: {...} })`

## 12. Responsive Design Behavior
- **Mobile:** Split layout stacks vertically (Contact info top, Form/Calendar bottom).
- **Desktop:** Side-by-side 50/50 split.

## 13. Development Notes for Next.js and Tailwind
- Implement Server Actions for the form submission to avoid creating a separate API route.
- Use `react-hook-form` and `zod` for robust client-side validation before sending data to the server.

## 14. Reusable Components Needed
- `ContactForm`
- `CalBooking`
