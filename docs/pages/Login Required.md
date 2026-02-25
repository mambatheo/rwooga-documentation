# Client Portal (Login Required)

These pages are guarded by the `ProtectedRoute` component and provide personalized customer experiences, order management, and custom service requests.

---

## Personalized Shopping

### Cart (`Cart.tsx`)
A centralized management hub for items intended for purchase.
- **Controls**: Real-time quantity adjustments and item removal.
- **Analytics**: Dynamic calculation of subtotals and estimated totals.

### Wishlist (`Wishlist.tsx`)
A curated list of products the user intends to purchase later.
- **Migration**: Authenticated users can move items directly from their wishlist to the active cart.

### Checkout (`Checkout.tsx`)
The final step in the purchase funnel.
- **Steps**: Shipping information collection → Review → Payment Method Selection.
- **Integrations**: Toggle between Mobile Money (MoMo) and Card payment interfaces.

---

## Post-Purchase & History

### Orders (`Orders.tsx`)
A comprehensive list of the user's transaction history.
- **Detail**: Each record displays items purchased, financial totals, and real-time status badges (e.g., `PENDING`, `SHIPPPED`, `DELIVERED`).

### Returns (`Returns.tsx`)
The self-service channel for return requests.
- **Tracking**: Shows the progress of `REQUESTED` returns through administrative approval and refunding.

---

## Custom Services

### Custom Request (`CustomRequest.tsx`)
The engine for bespoke 3D design and printing services.
- **Form**: Leverages category-specific requirements (e.g., requiring dimensions for 3D prints but not for animations).
- **Uploads**: Securely handles file uploads for design briefs and reference models.

### My Custom Requests (`MyCustomRequests.tsx`)
A dedicated tracking page for ongoing studio projects.
- **Visibility**: Allows users to see admin feedback and status updates on their unique design requests.

---

## Account Management

### Profile (`Profile.tsx`)
The user's personal settings dashboard.
- **Features**: 
    - Personal detail updates (Name, Phone).
    - Email change workflow (requires verification).
    - Password updates.
