# Accounts App

Handles all user identity, authentication, and authorization.

## Core Models

### `CustomUser`
Uses email as the unique identifier instead of a username.
- **Fields**: `id` (UUID), `email`, `full_name`, `phone_number`, `user_type` (CUSTOMER, STAFF, ADMIN), `is_active`.

### `VerificationCode`
A standalone model for managing 6-digit OTP codes.
- **Labels**: `REGISTER` (account activation), `RESET_PASSWORD` (forgot password), `EMAIL_CHANGE` (email update verification).
- **Expiry**: Codes expire after 10 minutes.

## Authentication Logic

### Registration Flow
1. User submits registration details.
2. An inactive `CustomUser` is created.
3. A `VerificationCode` is generated and sent via email.
4. User submits the code to `verify_email/` to activate the account.

### Login Flow
Standard JWT authentication via `CustomTokenObtainPairSerializer`. Returns both `access` and `refresh` tokens.

### Email Change Flow
Requires verification of the **new** email address via OTP before the user's primary email field is updated.

## Permissions
Custom permission classes (`IsAdmin`, `IsOwnerOrAdmin`) provide granular control over API access.
