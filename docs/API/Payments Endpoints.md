# Payments API Endpoints

These endpoints manage the integration with Paypack for MoMo payments and provide a stub for future card gateway integration.

## Payments (`/api/v1/payments/payments/`)

### List Payments
`GET /api/v1/payments/payments/`

Returns a list of payments for the current user. Staff and Admins see all payment history.

### Initiate MoMo Payment
`POST /api/v1/payments/payments/initiate-momo/`

Initiates an MTN MoMo (Paypack) transaction. Triggers a USSD push notification on the customer's phone.

**Request Body:**
```json
{
  "amount": 5000,
  "phone_number": "0780000000",
  "order": "order_uuid"
}
```

### Initiate Card Payment
`POST /api/v1/payments/payments/initiate-card/`

Initializes a card payment session. (Note: Currently a stub for future direct integration).

### Check Payment Status
`GET /api/v1/payments/payments/{id}/status/`

Returns the current status of a payment. If the payment is MoMo, this endpoint polls the Paypack API for the latest status if it is still `pending` or `processing`.

**Response:**
```json
{
  "transaction_id": "RWO-PAY-XXXXXXXX",
  "status": "successful",
  "is_successful": true,
  "amount": "5000.00",
  "failure_reason": null
}
```

### Cancel Payment
`POST /api/v1/payments/payments/{id}/cancel/`

Allows a user or admin to cancel a `pending` payment session before it expires.

### Webhook (Public)
`POST /api/v1/payments/payments/webhook/`

Callback endpoint for Paypack to notify the system of transaction updates (success/failure). This endpoint automatically updates the associated order status once a payment is confirmed.
