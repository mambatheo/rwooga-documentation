# State Management (Redux Store)

Rwooga uses **Redux Toolkit** for centralized state management across the application.

## Store Configuration (`store/index.ts`)

The root store combines multiple slices to handle different domains of the application.

### Core Slices
- `cart`: Manages items added to the shopping cart, including quantity and persistent storage checks.
- `wishlist`: Tracks products saved by the user.
- `products`: Caches product lists and filtering states.
- `orders`: Manages current and past order data.

### Admin/Dashboard Slices
- `users`: State for the user management dashboard.
- `requests`: Tracks custom service request status and filtering.
- `dashboard`: Handles analytics and summary data for the admin home.

## Persistence

Key states like `cart` and `auth` are synchronized with `localStorage` to ensure a seamless experience across browser refreshes.

## Usage in Components
Hooks like `useSelector` and `useDispatch` are used to interact with the global state, ensuring that UI components remain reactive to data changes.
