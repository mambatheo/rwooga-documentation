# Authentication & Identity Pages

These pages manage the user lifecycle, ensuring secure access to personalized features and the administrative dashboard.

---

## User Onboarding

### Signup (`Signup.tsx`)
The starting point for new customers.
- **Process**: Users provide their name, email, phone number, and a secure password.
- **Security**: Upon submission, the backend triggers a 6-digit One-Time Password (OTP) to the provided email address.

### Verify Email (`VerifyEmail.tsx`)
The bridge between registration and account activation.
- **Input**: A dedicated interface for entering the 6-digit verification code.
- **Outcome**: Successful validation activates the `CustomUser` record and automatically logs the user in, issuing the initial JWT pair.

---

## Session Management

### Login (`Login.tsx`)
The primary gateway for existing users.
- **Mechanism**: Validates credentials against the backend.
- **Storage**: On success, the JWT `access_token` and `refresh_token` are securely stored in the browser's `localStorage`.

---

## Recovery & Security

### Forgot Password (`ForgotPassword.tsx`)
Initiates the identity recovery process.
- **Action**: Sends a password-reset OTP to the user's registered email.

### Reset Password (`ResetPassword.tsx`)
Allows the user to establish a new password.
- **Requirement**: Validates the reset OTP and ensures the new password meets complexity requirements before updating the backend.
