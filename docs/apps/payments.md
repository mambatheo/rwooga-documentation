# Payments App

Provides a secure interface for financial transactions, primarily focusing on mobile money (MoMo) integration.

## Paypack Integration
The system uses the **Paypack API** for Rwandan MTN and Airtel mobile money transactions.
- **Cash-in**: Triggers a USSD push to the user's phone for immediate payment.
- **Status Polling**: The system can actively poll Paypack for transaction updates if a webhook is delayed.
- **Webhook**: A public endpoint receives automated POST callbacks from Paypack to update payment and order statuses in real-time.

## Payment Model
- **Transaction ID**: Unique internal reference for every attempt.
- **Methods**: `momo` (active) and `card` (stub).
- **Security**: Card numbers are never stored in full; Only masked versions (last 4 digits) are kept for reference.
- **Idempotency**: Prevent duplicate charges for the same order session.

## Error Handling
The app manages various payment failure states (insufficient funds, user cancellation, timeout) and provides descriptive feedback to the frontend.
