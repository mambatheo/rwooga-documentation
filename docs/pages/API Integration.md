# Service Layer & API Integration

The frontend communicates with the backend through a decoupled service layer built on top of **Axios**.

## API Configuration (`services/api.ts`)

Centralized Axios instance configuration:
- **Base URL**: Set to `${API_BASE_URL}/api/v1`.
- **Interceptors**:
    - **Request**: Automatically attaches the JWT `access_token` from `localStorage` to the `Authorization` header.
    - **Response**: Handles global error reporting via `react-hot-toast`. It specifically handles **401 Unauthorized** errors by attempting to rotate the access token using the refresh token before logging the user out.

## Service Pattern

Each backend module has a corresponding service file in `services/`:
- `authService.ts`: Register, Login, Verification.
- `productsService.ts`: Catalogue and Category management.
- `ordersService.ts`: Checkout and Order history.
- `paymentsService.ts`: MoMo and Card transaction initiation.
- `wishlistService.ts`: Saved items management.

Example usage:
```typescript
import { productsService } from '@/services/productsService';

const fetchProducts = async () => {
  const { ok, data } = await productsService.getPublishedProducts();
  if (ok) setProducts(data);
};
```

## Error Handling

Standardized error mapping converts HTTP status codes into user-friendly messages displayed via toast notifications, ensuring a professional user experience even during failures.
