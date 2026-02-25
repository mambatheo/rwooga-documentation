# Authentication & Authorization

The system implements a robust security model to protect user data and administrative functions.

## Authentication Model
- **Token-Based**: Uses JSON Web Tokens (JWT) via `djangorestframework-simplejwt`.
- **Lifecycle**: Tokens expire and must be rotated using a `refresh_token`.
- **Blacklisting**: Upon logout, refresh tokens are blacklisted on the server to prevent reuse.

## User Roles
There are three distinct user levels:
1. **Customer**: Can browse products, manage their own wishlist, place orders, and submit custom requests.
2. **Staff**: Can manage products, approve/reject custom requests, and view order history.
3. **Admin**: Full access to all system functions, including user management, financial refunding, and system-wide service availability toggles (`ControlRequest`).

## Permissions
- **Object-Level**: Most user resources (orders, profile) are guarded by `IsOwnerOrAdmin`, ensuring users can only access their own records.
- **Service-Level**: Critical staff actions like `moderate` (feedback) or `publish` (products) are strictly limited to authenticated staff or admin users.
- **Public Access**: High-performance catalogue browsing and portfolio viewing are available to guests without login.
