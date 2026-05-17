# Cal.com Booking Integration Plan

## 1. Objective
Integrate Cal.com seamlessly into the Synex Digital website to allow prospects to easily schedule consultations, discovery calls, or project scoping sessions directly, without leaving the brand experience.

## 2. Integration Strategy
We will use the `@calcom/embed-react` package to embed the booking interface natively within the Next.js application.

## 3. Implementation Steps

### Step 1: Installation
Install the required package:
```bash
npm install @calcom/embed-react
```

### Step 2: Setup Reusable Component
Create a reusable React component wrapper (`/components/forms/CalBooking.tsx`) to handle the embed logic and styling configuration.

```tsx
'use client'

import { useEffect } from 'react';
import Cal, { getCalApi } from '@calcom/embed-react';

interface CalBookingProps {
  calLink: string; // e.g., "synex-digital/discovery-call"
  theme?: 'dark' | 'light';
}

export default function CalBooking({ calLink, theme = 'dark' }: CalBookingProps) {
  useEffect(() => {
    (async function () {
      const cal = await getCalApi();
      cal("ui", {
        theme: theme,
        styles: { branding: { brandColor: "#4555fd" } },
        hideEventTypeDetails: false,
        layout: "month_view"
      });
    })();
  }, [theme]);

  return (
    <div className="w-full overflow-hidden rounded-xl bg-zinc-900 p-2 border border-zinc-800">
      <Cal 
        calLink={calLink} 
        style={{ width: "100%", height: "100%", overflow: "scroll" }} 
      />
    </div>
  );
}
```

### Step 3: Deployment Locations
The `CalBooking` component will be strategically placed:
1. **Dedicated Booking Page (Optional):** `/contact` or `/book` as the primary destination for CTA buttons.
2. **Modal Implementations:** For "Book a Call" header buttons, launch the Cal.com embed inside a custom, styled modal to keep the user on their current page.

### Step 4: Configuration Details
- **Brand Colors:** Ensure the embed is configured to use the Synex primary color `#4555fd` for calendar selection and buttons to maintain brand consistency.
- **Theme:** Lock the embed to `dark` theme to match the primary website aesthetic.

### Step 5: Event Tracking
Configure Cal.com (via their dashboard or embed callbacks) to redirect to a specific `/thank-you` route upon successful booking. This allows for accurate conversion tracking in Google Analytics or Meta Pixel.
