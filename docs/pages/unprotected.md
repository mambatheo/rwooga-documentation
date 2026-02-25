# Public Pages (Guest Access)

These pages are accessible to all visitors without requiring authentication. They focus on brand storytelling, service showcasing, and initial product discovery.

---

## Brand & Studio

### Home (`Home.tsx`)
The entry point of the Rwooga platform. It features a high-impact hero section with primary Call-to-Action (CTA) buttons. 
- **Key Features**: 
    - Studio highlights and value propositions.
    - Promotional banners and featured service categories.
    - Global state consumption for studio availability (Custom Printing toggle).

### About (`About.tsx`)
A dedicated space for the Rwooga brand story.
- **Content Sections**: Studio origins, mission statement, core team profiles, and a showcase of the creative tools and technologies used.

### Contact (`Contact.tsx`)
The primary lead generation point.
- **Integrations**: 
    - Interactive contact form.
    - Direct WhatsApp business link.
    - Embedded Google Maps for studio location.
    - Contact details (Phone, Email, Socials).

---

## Services & Portfolio

### Services (`Services.tsx`)
Detailed breakdown of Rwooga's specialized offerings.
- **Categories**: 3D Modeling, Animation, 3D Printing, and Architectural Visualization. Each section includes technical capabilities and typical project timelines.

### Portfolio (`Portfolio.tsx`)
A visual gallery of completed work.
- **Display**: High-resolution renders and video reels.
- **Filtering**: Users can filter projects by type (e.g., "Animation", "3D Print") to find relevant inspiration.

---

## E-Commerce Entry

### Shop (`Shop.tsx`)
The main product listing page.
- **Functionality**: 
    - Real-time search by product name or description.
    - Category-based filtering.
    - Grid/List view options for product discovery.

### Product Detail (`ProductDetail.tsx`)
A rich, immersive page for single product exploration.
- **Interactive Elements**:
    - **3D Viewer**: Real-time manipulation of the 3D model (STL/GLB).
    - **Media Gallery**: Carousel including high-res images and demonstration videos.
    - **Specifications**: Technical details (dimensions, material options).
    - **Social Proof**: Integrated feedback and rating section.
    - **Actions**: Add to Cart and Toggle Wishlist (supports local storage for guests).
