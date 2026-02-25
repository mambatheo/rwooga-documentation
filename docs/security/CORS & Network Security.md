# CORS & Network Security

The platform is designed with a decoupled architecture, requiring secure communication between the Vercel-hosted frontend and the Koyeb-hosted backend.

## Cross-Origin Resource Sharing (CORS)
- **Whitelisting**: The backend is configured to only allow requests from the official Rwooga production domain and authorized staging/local development environments.
- **Credentials**: Support for `Authorization` headers is strictly enforced.

## API Protection
- **Vercel Proxy**: The frontend uses a proxy configuration in `vercel.json` to route `/api/v1/*` requests to the backend, reducing CORS complexity and masking the direct backend URL from some basic analysis.
- **Environment Variables**: Sensitive keys (Paypack API keys, Cloudinary secrets) are stored exclusively in the host environment and never exposed to the client-side bundle.

## Secure Communication
- **HTTPS**: Enforced site-wide on both frontend and backend deployments to protect data in transit.
- **Email Security**: OTP codes expire after 10 minutes, minimizing the window for credential hijacking.
