# Orders App

Manages the complete lifecycle of customer purchases, returns, and financial refunds.

## Order Lifecycle
- **Status Flow**: `PENDING` → `PAID` → `PROCESSING` → `DELIVERED` (or `CANCELLED`).
- **Cancellation**: Only allowed for `PENDING` orders.
- **Price Integrity**: Product prices are locked in the `OrderItem` at the moment of order creation to protect against future price changes.

## Return Processing
- **Eligibility**: Customers can request returns for delivered items within 30 days.
- **Workflow**: `REQUESTED` → `APPROVED` → `COMPLETED` (or `REJECTED`).
- **RMA Generation**: Automatically generates unique Return Merchandise Authorization (RMA) numbers.

## Refund Management
- **Tracking**: Links directly to Return records.
- **Status**: `PENDING` → `COMPLETED` or `FAILED`.
- **Integration**: Supports logging external transaction IDs from payment providers.

## Business Rules
- Return approval and refund processing are restricted to Staff and Admin roles.
- Orders must be fully paid before they can be processed for delivery.
