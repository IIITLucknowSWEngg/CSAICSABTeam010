# Software Design Description (SDD)

## 1. Introduction

### 1.1 Purpose
The purpose of this Software Design Description (SDD) is to define the architecture, module design, and system interfaces for the **Decathlon Website Project**. This document serves as a guide for development, ensuring the website meets the functional and non-functional requirements outlined in the Decathlon user Requirements Document (URD) and Software Requirements Specification (SRS).

### 1.2 Scope
The **Decathlon Website Project** is an e-commerce platform aimed at providing Decathlon users with seamless product browsing, purchasing, and customer support experiences. The system includes a front-end website, backend services, content management system (CMS), inventory management, payment processing, and analytics integration.

---

## 2. Design Overview

### 2.1 Architectural Pattern
The Decathlon website employs a **three-tier architecture**:
1. **Presentation Layer**: Front-end interface for customers, store managers, and administrators.
2. **Application Layer**: Back-end services and business logic.
3. **Data Layer**: Database and content storage systems.

### 2.2 System Components
- **Front-end Application**: Built using responsive web technologies (HTML, CSS, JavaScript frameworks).
- **Backend API Services**: Built on RESTful APIs.
- **Database**: Relational database for transactional data and a NoSQL database for product catalogs.
- **Third-party Integrations**: Payment gateways, analytics tools, and CRM.

---

## 3. UML Diagrams(Database Design)

### 3.1 ER Diagram
The ER diagram models the relationships between Decathlon users, products, orders, carts, and other entities in the system.

![ER Diagram](https://github.com/user-attachments/assets/8197baf4-797a-49e9-9664-3b27bf3a7d48)


---

### 3.2 Class Diagram
The class diagram represents the structure of key entities and their relationships in the system.

![Class Diagram](https://github.com/user-attachments/assets/962ca0ec-5a73-4d59-9ddc-1d2af2ccb42b)


---

### 3.3 Sequence Diagram: Order Checkout
The sequence diagram illustrates the process flow for a customer placing an order.

![Sequence Diagram](https://github.com/user-attachments/assets/84372c64-af4f-4d6d-bfee-0c0934557aa6)

---

### 3.4 Activity Diagram: Adding to Cart
The activity diagram describes the flow of adding a product to the shopping cart.

![Activity Diagram](https://github.com/user-attachments/assets/f6190f40-d68d-4284-a493-40f28c7b002d)

---

## 4. API Design
The API design diagram describes how the API functions.It visualizes the key API endpoints and how they are organized by functionality.
<img width="1280" alt="Screenshot 2024-12-01 at 3 42 53 PM" src="https://github.com/user-attachments/assets/ac74b0a7-5bed-4c68-8782-50faa724d578">


---

## 5. Non-Functional Requirements (NFRs)

### 5.1 Performance
- Support for 10,000 concurrent Decathlon users.
- APIs respond within 500ms for 95% of requests.
  
<img width="534" alt="Screenshot 2025-01-01 at 1 08 04 PM" src="https://github.com/user-attachments/assets/dfbbd319-eacc-4596-b275-2e2597452cc9" />



### 5.2 Scalability
- Horizontal scaling for backend services.
- Caching for frequently accessed data.
  
<img width="467" alt="Screenshot 2025-01-01 at 1 16 22 PM" src="https://github.com/user-attachments/assets/d16719dd-d9d2-44cf-82c8-c991de13ea23" />

### 5.3 Security
- Use OAuth 2.0 or JWT for secure session management.
- Encrypt sensitive data at rest (AES-256) and in transit (TLS).
  
![Security Diagram](https://github.com/user-attachments/assets/497f3e5b-bda6-44ff-806d-eb61f3cc4446)

### 5.4 Availability
- Maintain 99.9% uptime with failover mechanisms and load balancing.
  
![Availability Diagram](https://github.com/user-attachments/assets/70c53c36-aa06-4c02-a9d6-1e23f4062baf)

### 5.5 Accessibility
- To promote a more inclusive digital experience, it is essential to achieve compliance with the Web Content Accessibility Guidelines (WCAG) 2.1. These guidelines ensure that websites are accessible to individuals with various disabilities, including those with visual, auditory, motor, and cognitive impairments. By adhering to WCAG 2.1, you can create content that is perceivable, operable, understandable, and robust, making it accessible across a wide range of devices and assistive technologies. This commitment to accessibility not only fosters a more inclusive environment but also enhances usability, user experience, and compliance with legal requirements, reaching a broader audience and supporting equal access for all.

---

## 6. Conclusion

This design document provides a comprehensive overview of the architecture, UML diagrams, API design, and NFRs for the Decathlon website project. It ensures a robust, scalable, and Decathlon user-friendly e-commerce platform aligned with the requirements and best practices.

