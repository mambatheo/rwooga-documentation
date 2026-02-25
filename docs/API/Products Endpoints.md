# Products & Services API Endpoints

These endpoints manage the product catalog, service categories, customer feedback, wishlists, and custom design requests.

## Categories (`/api/v1/products/categories/`)

### List Categories
`GET /api/v1/products/categories/`

Returns a list of all available service categories.

### Get Required Fields
`GET /api/v1/products/categories/{id}/required_fields/`

Returns the specific fields (dimensions, materials, etc.) required for a custom request within this category.

## Products (`/api/v1/products/products/`)

### List Products
`GET /api/v1/products/products/`

Returns a list of products. Supports the following query parameters for filtering and searching:
- `category`: Filter by category ID.
- `published`: `true` or `false`.
- `min_price`: Minimum unit price.
- `max_price`: Maximum unit price.
- `search`: Search in name and descriptions.
- `ordering`: Fields to order by (e.g., `unit_price`, `-created_at`).

### Get Product Detail
`GET /api/v1/products/products/{id}/`

Returns full details for a single product, including associated media and average rating.

### Publish Product (Staff/Admin)
`POST /api/v1/products/products/{id}/publish/`

### Unpublish Product (Staff/Admin)
`POST /api/v1/products/products/{id}/unpublish/`

## Feedback (`/api/v1/products/feedback/`)

### List Feedback
`GET /api/v1/products/feedback/`

Returns feedback for products. Filter by `product` ID using query parameters. Guests and regular users only see published feedback.

### Submit Feedback
`POST /api/v1/products/feedback/`

Submit a new rating and comment for a product.

### Moderate Feedback (Admin)
`POST /api/v1/products/feedback/{id}/moderate/`

Approve or reject feedback visibility.
**Body:** `{"status": "APPROVED"}` or `{"status": "REJECTED"}`

## Wishlist (`/api/v1/products/wishlist/`)

### Get My Wishlist
`GET /api/v1/products/wishlist/my_wishlist/`

Returns the current user's wishlist and its items.

### Toggle Wishlist Item
`POST /api/v1/products/wishlist-items/toggle/`

Adds or removes a product from the user's wishlist.
**Body:** `{"product": "product_uuid"}`

### Clear Wishlist
`DELETE /api/v1/products/wishlist-items/clear/`

## Custom Requests (`/api/v1/products/custom-requests/`)

### Submit Custom Request
`POST /api/v1/products/custom-requests/`

Submit a new design or 3D printing brief. Supports file uploads for reference designs.

### List My Requests
`GET /api/v1/products/custom-requests/`

Returns a list of custom requests submitted by the current user. Staff see all requests.

## Request Control (`/api/v1/products/control-requests/`)

### Get Availability Status
`GET /api/v1/products/control-requests/status/`

Checks if the studio is currently accepting new custom requests.

### Enable/Disable Requests (Admin)
`POST /api/v1/products/control-requests/enable/`
`POST /api/v1/products/control-requests/disable/`
