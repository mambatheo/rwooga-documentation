# Products App

The core catalogue and business logic engine for storefront operations.

## Product Hierarchy
- **Categories**: Defines the service type (e.g., 3D Printing, Animation). Categories can define "Required Fields" (like dimensions) needed for custom requests.
- **Products**: Detailed records for items for sale, including unit prices, slugs, and technical specifications (dimensions, materials).

## Media Management
Supports multiple media types for every product:
- **Images**: High-resolution gallery shots.
- **Videos**: Local file uploads or external URLs.
- **3D Models**: Support for STL, OBJ, and GLB files for interactive viewing.

## Marketing Features
- **Discounts**: Flexible system supporting percentage-based and fixed-amount price reductions across specific time ranges.
- **Feedback**: Customer rating system with mandatory admin moderation to ensure quality and prevent spam.
- **Wishlist**: Per-user saved items management.

## Custom Service Engine
- **Custom Requests**: Allows users to upload design briefs and files for specialized studio work.
- **Control System**: Admins can globally toggle the availability of custom requests based on studio capacity.
