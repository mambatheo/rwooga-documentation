# Authentication & User Management Endpoints

The Rwooga platform uses JWT (JSON Web Token) for authentication. All protected endpoints require a `Bearer` token in the `Authorization` header.

## User Authentication (`/api/v1/auth/`)

### Register User
`POST /api/v1/auth/register/`

Creates a new user account. Upon success, an email containing a 6-digit OTP is sent to the provided address. The account remains inactive until verified.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "securepassword123",
  "full_name": "John Doe",
  "phone_number": "0780000000"
}
```

### Verify Email
`POST /api/v1/auth/verify_email/`

Activates the user account using the 6-digit code sent via email. Returns JWT access and refresh tokens.

**Request Body:**
```json
{
  "email": "user@example.com",
  "code": "123456"
}
```

### Resend Verification
`POST /api/v1/auth/resend_verification/`

Resends the registration OTP to the specified email address if the account is still inactive.

**Request Body:**
```json
{
  "email": "user@example.com"
}
```

### Login
`POST /api/v1/auth/login/`

Authenticates an active user and returns JWT tokens.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "securepassword123"
}
```

**Response:**
```json
{
  "access": "jwt_access_token",
  "refresh": "jwt_refresh_token",
  "user": {
    "id": "uuid",
    "email": "user@example.com",
    "full_name": "John Doe"
  }
}
```

### Logout
`POST /api/v1/auth/logout/`

Blacklists the provided refresh token to end the session.

**Request Body:**
```json
{
  "refresh": "jwt_refresh_token"
}
```

### Refresh Token
`POST /api/v1/auth/refresh_token/`

Generates a new access token using a valid refresh token.

**Request Body:**
```json
{
  "refresh": "jwt_refresh_token"
}
```

### Password Reset Request
`POST /api/v1/auth/password_reset_request/`

Initiates the password reset process by sending an OTP to the user's email.

**Request Body:**
```json
{
  "email": "user@example.com"
}
```

### Password Reset Confirm
`POST /api/v1/auth/password_reset_confirm/`

Sets a new password using the OTP received via email.

**Request Body:**
```json
{
  "email": "user@example.com",
  "code": "123456",
  "new_password": "newsecurepassword123"
}
```

---

## User Profile (`/api/v1/profile/`)

### Get Current Profile
`GET /api/v1/profile/me/`

Returns the authenticated user's profile details.

### Update Profile
`PATCH /api/v1/profile/update_profile/`

Updates profile fields such as name and phone number.

### Change Password
`POST /api/v1/profile/change_password/`

Updates the user's password. Requires the old password for validation.

### Email Change Request
`POST /api/v1/profile/email_change_request/`

Initiates an email change by sending a verification code to the **new** email address.

### Email Change Confirm
`POST /api/v1/profile/email_change_confirm/`

Updates the user's email address using the verification code sent to the new email. Returns fresh JWT tokens.
