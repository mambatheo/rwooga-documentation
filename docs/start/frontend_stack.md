# Frontend Technology Stack

The Rwooga frontend is a high-performance Single Page Application (SPA) prioritizing visual excellence and interactive 3D capabilities.

## Core Framework
- **Library**: React 19
- **Build Tool**: Vite (Fast HMR and optimized builds)
- **Language**: TypeScript (Type-safe development)

## Styling & UI
- **CSS**: Tailwind CSS (Utility-first styling).
- **Design System**: Custom Glassmorphism implementation.
- **Icons**: Lucide React.
- **Notifications**: React Hot Toast.

## State Management & Communication
- **Redux**: Redux Toolkit for global state (Cart, Wishlist, Orders).
- **Context API**: React Context for Authentication lifecycle.
- **API Client**: Axios with centralized interceptors for JWT rotation.

## 3D & Visualization
- **3D Viewer**: `@google/model-viewer` for responsive 3D product previews.
- **Assets**: Support for STL, OBJ, and GLB formats safely rendered in-browser.

## Infrastructure
- **Deployment**: Vercel (Edge network for low-latency global delivery).
- **Routing**: React Router 6.
