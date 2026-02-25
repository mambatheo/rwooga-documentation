# Orders, Returns & Refunds API Endpoints

These endpoints manage the lifecycle of customer orders and the administrative processing of returns and refunds.

## Orders (`/api/v1/orders/orders/`)

### List Orders
`GET /api/v1/orders/orders/`

Returns a list of orders for the current user. Staff and Admins see all orders.

### Create Order
`POST /api/v1/orders/orders/`

Create a new order. The `price_at_purchase` is automatically locked based on the current product price at the time of creation.

**Request Body:**
```json
{
  "items": [
    {
      "product": "product_uuid",
      "quantity": 2
    }
  ],
  "customer_notes": "Handle with care",
  "discount": "discount_uuid (optional)"
}
```

### Get Order Detail
`GET /api/v1/orders/orders/{id}/`

### Cancel Order
`DELETE /api/v1/orders/orders/{id}/` (or `POST /api/v1/orders/orders/{id}/cancel/` depending on frontend service implementation)

Only `PENDING` orders can be cancelled.

### Apply Discount
`POST /api/v1/orders/orders/{id}/apply-discount/`

### Order Summary
`GET /api/v1/orders/orders/{id}/summary/`

Returns financial totals, item count, and current status.

## Returns (`/api/v1/orders/returns/`)

### List Returns
`GET /api/v1/orders/returns/`

### Submit Return Request
`POST /api/v1/orders/returns/`

Customers can request a return for products purchased within the last 30 days.

### Approve Return (Staff/Admin)
`POST /api/v1/orders/returns/{id}/approve/`

**Body:** `{"approved_refund_amount": 10000}`

### Reject Return (Staff/Admin)
`POST /api/v1/orders/returns/{id}/reject/`

**Body:** `{"rejection_reason": "Item used excessively"}`

### Complete Return (Staff/Admin)
`POST /api/v1/orders/returns/{id}/complete/`

### Cancel Return (Owner Only)
`POST /api/v1/orders/returns/{id}/cancel_return/`

Customers can cancel their own `REQUESTED` returns.

## Refunds (`/api/v1/orders/refunds/`)

### List Refunds
`GET /api/v1/orders/refunds/`

### Complete Refund (Admin)
`POST /api/v1/orders/refunds/{id}/complete/`

**Body:** `{"transaction_id": "optional_gateway_ref"}`

### Fail Refund (Admin)
`POST /api/v1/orders/refunds/{id}/fail/`
