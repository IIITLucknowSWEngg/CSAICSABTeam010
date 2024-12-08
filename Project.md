# Scope of the Project

## Software Scope

The Decathlon.com competitor website aims to provide a comprehensive e-commerce platform tailored for sporting goods. It will cater to a wide range of users, including individual customers, sports enthusiasts, teams, and administrators. The system is designed to ensure a seamless shopping experience while incorporating features to promote community engagement and efficient logistics.

### Objectives
- Build a robust platform with multi-sport product categories and user-friendly navigation.
- Enable efficient inventory and order management for administrators.
- Enhance user experience through personalized recommendations, loyalty programs, and real-time stock updates.
- Support localized content and currency for global reach.

### Target Audience
- **Customers**: Individuals looking to purchase sports products, participate in events, or access sports-related content.
- **Teams/Organizations**: Clubs, schools, or corporate groups managing bulk orders.
- **Administrators**: Users managing inventory, customer data, and promotions.
- **Vendors**: Suppliers updating product details and stock levels.

### Exclusions
The current scope excludes advanced features like Augmented Reality (AR), Virtual Try-On, Affiliate Marketing, and other non-essential integrations that can be considered in future iterations.

---

## Methodology

The development of this project will follow an **Agile Software Development** methodology to ensure flexibility, iterative improvements, and active collaboration between stakeholders.

### Key Phases

#### 1. **Requirements Gathering**
- Collect functional and non-functional requirements from stakeholders, including:
  - Product Catalog Management
  - User Management
  - Logistics and Inventory Integration
  - Promotions and Loyalty Programs
- Reference industry standards such as **IEEE Std 830-1998** and **SWEBOK v3.0**.

#### 2. **Planning and Design**
- Design a modular architecture with the following components:
  - **Front-End**: Responsive UI using React.js or Angular.
  - **Back-End**: RESTful API services powered by Node.js or Python.
  - **Database**: Use MongoDB for flexible data storage.
- Create wireframes and prototypes for core features like product browsing, cart management, and checkout.

#### 3. **Development**
- Use an iterative sprint model to develop the system in manageable chunks.
- Prioritize core features in early sprints:
  - User Authentication
  - Product Listings and Details
  - Shopping Cart and Checkout
- Incorporate advanced features in later sprints, such as Loyalty Programs and Multi-language Support.

#### 4. **Testing**
- Conduct extensive testing, including:
  - **Unit Testing**: Test individual components for functionality.
  - **Integration Testing**: Verify the seamless interaction between front-end, back-end, and database layers.
  - **Performance Testing**: Ensure the platform can handle up to 10,000 concurrent users.
  - **Security Testing**: Validate encryption protocols and role-based access controls.

#### 5. **Deployment**
- Deploy the platform on a scalable cloud service such as AWS or Google Cloud.
- Implement CI/CD pipelines for automated deployment and updates.
- Ensure real-time backups and disaster recovery mechanisms are in place.

#### 6. **Maintenance and Iteration**
- Gather user feedback post-launch and prioritize updates or feature additions.
- Monitor system performance and reliability through uptime tracking tools like **Uptime.is**.

---

## Included Features

### Core Features
| Feature                 | Description                                               | Status (Included)      |
|:------------------------|:----------------------------------------------------------|:-----------------------|
| User Registration        | Allows users to create an account via Google OAuth registration.                        | ✅ |
| User Authentication      | Provides secure login and logout functionality.           | ✅ |
| Product Listings         | Displays all products available for purchase.             | ✅ |
| Product Details          | Shows detailed information about each product.            | ✅ |
| Shopping Cart            | Enables users to add products and review their cart.      | ✅ |
| Checkout Process         | Facilitates the purchase of items in the cart.            | ✅ |
| Order History            | Allows users to view past orders and their details.       | ✅ |
| Search Functionality     | Provides a way to search for products by keyword.         | ✅ |
| Product Reviews          | Allows users to leave and view reviews for products.      | ✅ |
| User Profile Management  | Enables users to manage their profile and settings.       | ✅ |
| Wishlist                 | Users can save favorite products for future purchases.    | ✅ |

### Advanced Features
| Feature                 | Description                                               | Status (Included)       |
|:------------------------|:----------------------------------------------------------|:-----------------------|
| Product Comparison       | Allows comparison of multiple products side-by-side.      | ✅ |
| Inventory Management     | Manage stock levels and product availability.             | ✅ |
| Admin Dashboard          | Provides an interface for administrators to manage the site. | ✅ |
| Discount Codes           | Allows users to apply promotional codes during checkout.  | ✅ |
| Multi-language Support   | Provides content in multiple languages.                   | ✅ |
| Loyalty Programs         | Rewards frequent customers with points redeemable for discounts or other benefits. | ✅ |
| Social Media Sharing     | Enables users to share products or reviews on social media platforms. | ✅ |

### Integrations
| Feature                 | Description                                               | Status (Included)       |
|:------------------------|:----------------------------------------------------------|:-----------------------|
| Payment Gateway          | Integration with payment processors for transactions.     | ✅ |
| Shipping Integration     | Integrates with shipping services to handle deliveries.   | ✅ |
| Email Notifications      | Sends email updates for order confirmations and other events. | ✅ |
| Social Media Login       | Allows users to log in using their social media accounts. | ✅ |
| Local Sports Events Integration | Recommends nearby sports events based on user location. | ✅ |

---

## Excluded Features

### Core Features
| Feature                 | Description                                               | Status (Excluded)       |
|:------------------------|:----------------------------------------------------------|:-----------------------|
| Subscription Service     | Provides subscription-based access or benefits.           | ❌ |
| Membership Tiers         | Different levels of membership with various perks.        | ❌ |
| Live Chat Support        | Real-time chat assistance for users.                      | ❌ |

### Advanced Features
| Feature                 | Description                                               | Status (Excluded)       |
|:------------------------|:----------------------------------------------------------|:-----------------------|
| Augmented Reality (AR)   | Interactive AR features for product visualization.        | ❌ |
| Virtual Try-On           | Allows users to try on products virtually.                | ❌ |
| Advanced Analytics       | Detailed analytics and reporting features for admin.      | ❌ |

### Integrations
| Feature                 | Description                                               | Status (Excluded)       |
|:------------------------|:----------------------------------------------------------|:-----------------------|
| Affiliate Marketing      | System for managing affiliate partnerships.               | ❌ |
| Third-Party Reviews      | Integration with external review platforms.               | ❌ |
