# Events Page Plan

## 1. Page Purpose
Highlight upcoming webinars, tech meetups, and conferences where Synex Digital is speaking or hosting. Build community and generate leads.

## 2. Target User Intent
Register for upcoming educational content or networking events. Watch past event recordings.

## 3. Recommended Route
`/events` (Handled by `app/(site)/events/page.tsx`)

## 4. Page Sections
1. **Hero:** "Join the Conversation."
2. **Upcoming Events:** Highlight cards with dates and registration links.
3. **Past Events (Archive):** Grid of previous webinars with links to recordings.
4. **CTA:** Subscribe for event updates.

## 5. Section-by-Section Content Guidance
- **Upcoming Events:** Emphasize the Date, Time, Topic, and Speaker. Include a prominent "Register" button.
- **Past Events:** Treat similarly to blog posts but link to a video player or YouTube embed.

## 6. Suggested UI Components
- `<EventCard>` (Displays Date prominently like a calendar icon)
- `<VideoEmbed>`
- `<NewsletterForm>`

## 7. Animation and Interaction Guidance
- **Event Cards:** Hover effect highlights the registration button.

## 8. Image Usage Guidance
- **Event Banners:** If used as thumbnails, adhere to the 1:1 aspect ratio constraint.

## 9. CTA Strategy
- Primary: Register for the next event.
- Secondary: Watch on-demand.

## 10. SEO Metadata Suggestions
- **Title:** `Tech Events & Webinars | Synex Digital`
- **Description:** `Join Synex Digital for exclusive webinars, workshops, and meetups focused on software engineering, AI, and digital transformation.`

## 11. Database Content Requirements
- Can be fetched via Prisma if an `Event` model exists, otherwise manage via a local JSON file if events are infrequent.

## 12. Responsive Design Behavior
- Standard grid collapse rules (Mobile: 1 col, Desktop: 2-3 col).

## 13. Development Notes for Next.js and Tailwind
- Ensure timezone formatting is clear (e.g., using `date-fns` to format dates nicely).

## 14. Reusable Components Needed
- `EventCard`
