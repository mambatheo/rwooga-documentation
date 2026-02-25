# Admin Dashboard

The Admin Dashboard is a comprehensive, multi-module management interface restricted to users with `ADMIN` or `STAFF` roles. It provides full transparency and control over the studio's operations.

---

## Inventory & Creative Management

### Catalog Control
- **Product CRUD**: Create, read, update, and delete product records.
- **Category Management**: Define new service silos and their specific data requirements (e.g., custom form fields).
- **Media Upload Strategy**: A robust modal-based system for uploading:
    - High-resolution thumbnails.
    - Video demonstrations.
    - Interactive 3D source files (STL, OBJ, GLB).

### Marketing & Growth
- **Discounts**: Manage time-limited percentage or fixed-amount price reductions across the catalogue.
- **Feedback Moderation**: A mandatory review queue to approve or reject customer ratings and comments before they appear publicly.

---

## Operations & Fulfillment

### Order Processing
A master view of all platform transactions. 
- **Actions**: Status updates, manual order adjustments, and communication tracking.

### Returns & Refunds
An administrative workflow for handling dissatisfied clients.
- **RMA Management**: Reviewing and approving return requests.
- **Financial Refunds**: Finalizing refund records once payment gateway confirmation is received.

### Custom Request Queue
The hub for studio workflow.
- **Status Control**: Moving client briefs from `PENDING` to `IN_PROGRESS` and `COMPLETED`.
- **Global Availability**: A "Kill Switch" toggle (`ControlRequest`) to immediately disable new custom requests during high-demand periods or studio maintenance.

---

## User & System Administration

### User Management
- **Audit**: View all registered users and their details.
- **Security**: Capability to activate/deactivate accounts or elevate user roles (Customer to Staff).

---

## Technical Architecture
The Admin interface is built with highly reusable components (e.g., `ManageOrderModal`, `UserModal`) to ensure consistency and speed when adding new administrative features.
