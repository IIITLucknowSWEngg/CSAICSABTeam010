## 1. System Context Diagram
![System Context Diagram](https://github.com/user-attachments/assets/10e7e959-4fb3-47f3-9074-35a623a94ffb)
```plantuml
@startuml
!theme plain

actor "Player (Customer)" as Player
actor "Admin" as Admin
actor "Inventory Manager" as InventoryManager

' --- Frontend Layer ---
package "Frontend Layer" {
  entity "Decathlon Website (Web App)" as Frontend
}

' --- Backend Layer ---
package "Backend Layer" {
  entity "Backend API" as BackendAPI
  entity "Order Management Service" as OrderService
  entity "Payment Service API" as PaymentAPI
  entity "Shipping Service API" as ShippingAPI
  entity "Notification Service API" as NotificationAPI
  entity "User Account Service" as UserService
  entity "Analytics Service API" as AnalyticsAPI
}

' --- Data Layer ---
package "Data Layer" {
  entity "Product Database" as ProductDB
  entity "Order Database" as OrderDB
  entity "User Database" as UserDB
}

' --- External Services Layer ---
package "External Services Layer" {
  entity "Payment Gateway" as PaymentGateway
  entity "Shipping Provider" as ShippingProvider
  entity "Notification Service" as ExternalNotification
  entity "Third-Party Analytics" as ThirdPartyAnalytics
}

' --- Interactions between Actors and Containers ---

' Player interactions with the Frontend
Player --> Frontend : Browse Products
Player --> Frontend : Add to Cart
Player --> Frontend : Make Order
Player --> Frontend : Track Shipment
Player --> Frontend : View Order History

' Admin interactions with the Frontend
Admin --> Frontend : Manage Products
Admin --> Frontend : Manage Orders

' Frontend interactions with Backend API
Frontend --> BackendAPI : Send User Request\n(Add Item, Place Order)
Frontend --> BackendAPI : Request Product Data
Frontend --> BackendAPI : Request User Login/Registration

' Backend API interactions with Backend Services
BackendAPI --> ProductDB : Fetch Product Info
BackendAPI --> OrderService : Create/Update Orders
BackendAPI --> UserService : Manage User Profiles
BackendAPI --> PaymentAPI : Process Payments
BackendAPI --> ShippingAPI : Dispatch Orders
BackendAPI --> NotificationAPI : Send Order Confirmation
BackendAPI --> AnalyticsAPI : Log User Actions

' Payment API interactions with External Services
PaymentAPI --> PaymentGateway : Process Payment
ShippingAPI --> ShippingProvider : Request Shipping Details
NotificationAPI --> ExternalNotification : Send Notifications\n(Order Confirmation, Updates)

' Data Layer interactions
OrderService --> OrderDB : Save Order Data
UserService --> UserDB : Save User Information
ProductDB --> BackendAPI : Provide Product Details

' Inventory Management interactions
InventoryManager --> ProductDB : Update Stock Information
InventoryManager --> Frontend : Update Product Data

@enduml
```
---



## 2. Container Diagram
![Container Diagram](https://github.com/user-attachments/assets/2eb7fa6d-5779-486c-8b19-c5b5bb0b5bd5)
```plantuml
@startuml
!theme plain

actor "Player (Customer)" as Player
actor "Admin" as Admin
actor "Inventory Manager" as InventoryManager

' --- Frontend Layer ---
package "Frontend Layer" {
  entity "Decathlon Website (Web App)" as Frontend
}

' --- Backend Layer ---
package "Backend Layer" {
  entity "Backend API" as BackendAPI
  entity "Order Management Service" as OrderService
  entity "Payment Service API" as PaymentAPI
  entity "Shipping Service API" as ShippingAPI
  entity "Notification Service API" as NotificationAPI
  entity "User Account Service" as UserService
  entity "Analytics Service API" as AnalyticsAPI
}

' --- Data Layer ---
package "Data Layer" {
  entity "Product Database" as ProductDB
  entity "Order Database" as OrderDB
  entity "User Database" as UserDB
}

' --- External Services Layer ---
package "External Services Layer" {
  entity "Payment Gateway" as PaymentGateway
  entity "Shipping Provider" as ShippingProvider
  entity "Notification Service" as ExternalNotification
  entity "Third-Party Analytics" as ThirdPartyAnalytics
}

' --- Interactions between Actors and Containers ---

' Player interactions with the Frontend
Player --> Frontend : Browse Products
Player --> Frontend : Add to Cart
Player --> Frontend : Make Order
Player --> Frontend : Track Shipment
Player --> Frontend : View Order History

' Admin interactions with the Frontend
Admin --> Frontend : Manage Products
Admin --> Frontend : Manage Orders

' Frontend interactions with Backend API
Frontend --> BackendAPI : Send User Request\n(Add Item, Place Order)
Frontend --> BackendAPI : Request Product Data
Frontend --> BackendAPI : Request User Login/Registration

' Backend API interactions with Backend Services
BackendAPI --> ProductDB : Fetch Product Info
BackendAPI --> OrderService : Create/Update Orders
BackendAPI --> UserService : Manage User Profiles
BackendAPI --> PaymentAPI : Process Payments
BackendAPI --> ShippingAPI : Dispatch Orders
BackendAPI --> NotificationAPI : Send Order Confirmation
BackendAPI --> AnalyticsAPI : Log User Actions

' Payment API interactions with External Services
PaymentAPI --> PaymentGateway : Process Payment
ShippingAPI --> ShippingProvider : Request Shipping Details
NotificationAPI --> ExternalNotification : Send Notifications\n(Order Confirmation, Updates)

' Data Layer interactions
OrderService --> OrderDB : Save Order Data
UserService --> UserDB : Save User Information
ProductDB --> BackendAPI : Provide Product Details

' Inventory Management interactions
InventoryManager --> ProductDB : Update Stock Information
InventoryManager --> Frontend : Update Product Data

@enduml

```
---

## 3. Component Diagram
![Component Diagram](https://github.com/user-attachments/assets/e4c7f29b-c82a-4b87-b8d1-5a13d7c057bf)
```plantuml
@startuml
!theme plain

actor "Admin" as Admin

package "Admin Layer" {
  component "Admin Dashboard" as AdminDashboard
  component "Product Management" as ProductManagement
  component "Order Management" as AdminOrderManagement
  component "User Management" as UserManagement
  component "Inventory Management" as InventoryManagement
  component "Analytics & Reporting" as AnalyticsReporting
}

' --- Interactions ---
Admin --> AdminDashboard : View Dashboard
Admin --> ProductManagement : Manage Products
Admin --> AdminOrderManagement : Manage Orders
Admin --> UserManagement : Manage Users
Admin --> InventoryManagement : Update Inventory
Admin --> AnalyticsReporting : View Reports

' --- Component Interactions ---
ProductManagement --> AdminDashboard : Display Product Data
AdminOrderManagement --> ProductManagement : Fetch Product Info
AdminOrderManagement --> UserManagement : Fetch User Data
InventoryManagement --> ProductManagement : Update Stock Levels
AnalyticsReporting --> AdminOrderManagement : Fetch Order Data
AnalyticsReporting --> ProductManagement : Fetch Product Data

@enduml

```
---

## 4. Class Diagram
![Class Diagram](https://github.com/user-attachments/assets/b8211967-a36c-497f-9725-bcb58eea5249)
```plantuml
@startuml
!theme plain

' Define the classes and their attributes
class "Product" {
  +String productID
  +String name
  +String description
  +Double price
  +Integer stockQuantity
  +String category
  +String brand
  +String imageURL
  +addProduct() : void
  +updateProduct() : void
  +deleteProduct() : void
}

class "Order" {
  +String orderID
  +Date orderDate
  +Double totalAmount
  +String status
  +String paymentStatus
  +String shippingStatus
  +addOrder() : void
  +updateOrderStatus() : void
  +cancelOrder() : void
}

class "User" {
  +String userID
  +String username
  +String email
  +String password
  +String address
  +String phone
  +authenticate() : Boolean
  +updateProfile() : void
  +changePassword() : void
}

class "Cart" {
  +String cartID
  +List<Product> items
  +Integer quantity
  +addToCart() : void
  +removeFromCart() : void
  +viewCart() : List<Product>
}

class "Payment" {
  +String paymentID
  +String orderID
  +String paymentMethod
  +Double amount
  +String paymentStatus
  +processPayment() : Boolean
  +refundPayment() : Boolean
}

class "Shipping" {
  +String shippingID
  +String orderID
  +String shippingStatus
  +String shippingAddress
  +Date estimatedDeliveryDate
  +shipOrder() : void
  +updateShippingStatus() : void
}

' Define NoSQL Database classes to represent collections
class "ProductCollection" {
  +addProduct(product: Product) : void
  +removeProduct(productID: String) : void
  +getProductByID(productID: String) : Product
}

class "OrderCollection" {
  +addOrder(order: Order) : void
  +updateOrder(orderID: String, status: String) : void
  +getOrderByID(orderID: String) : Order
}

class "UserCollection" {
  +addUser(user: User) : void
  +getUserByID(userID: String) : User
  +updateUser(userID: String, userDetails: User) : void
}

' Relationships between classes
ProductCollection --* "Product" : stores >
OrderCollection --* "Order" : stores >
UserCollection --* "User" : stores >
Order --* "Payment" : processes >
Order --* "Shipping" : ships >

' Add dependencies (e.g., methods or class calls)
User "1" -- "0..*" Order : places >
Cart "1" -- "0..*" Product : contains >

@enduml

```
---

## 5. Activity Diagram
![Activity Diagram](https://github.com/user-attachments/assets/425d18f9-33ae-428a-ae0a-f7bc59b61836)
```plantuml
@startuml
!theme plain

start

:Browse Products;
:Select Product;

fork
  :Add Product to Cart;
  :Update Cart;
fork again
  :View Cart;
  :Proceed to Checkout;
end fork

:Fill in Shipping Details;
:Choose Payment Method;

partition "Payment Process" {
  :Enter Payment Details;
  :Process Payment;
  :Receive Payment Confirmation;
}

:Confirm Order;
:Send Order Confirmation;

stop

@enduml

```
---

## 6. State Diagram
![State Diagram](https://github.com/user-attachments/assets/991c606f-2a3e-4530-8e03-9c18caaef88e)
```plantuml
@startuml
!theme plain

[*] --> Created

Created --> PendingPayment : Order Created
PendingPayment --> PaymentProcessed : Payment Successful
PaymentProcessed --> Shipped : Ship Order
Shipped --> Delivered : Deliver Order
[*] --> Cancelled : Cancel Order

PendingPayment --> Cancelled : Payment Failed
PaymentProcessed --> Cancelled : Cancel Order

Cancelled --> [*] : End

@enduml

```
---

## 7. Sequence Diagram
![Sequence Diagram](https://github.com/user-attachments/assets/d7fe0ee5-b7fa-4875-8c1e-6aa309df690b)
```plantuml
@startuml
!theme plain

actor "Player" as Player
participant "Web Interface" as WebInterface
participant "Cart" as Cart
participant "Order Service" as OrderService
participant "Payment System" as PaymentSystem
participant "Shipping Service" as ShippingService

== Start Order Process ==
Player -> WebInterface : Browse Products
Player -> WebInterface : Add Product to Cart
WebInterface -> Cart : Add Product

== Checkout Process ==
Player -> WebInterface : Proceed to Checkout
Player -> WebInterface : Enter Shipping Details
WebInterface -> OrderService : Create Order

== Payment Process ==
Player -> WebInterface : Choose Payment Method
WebInterface -> PaymentSystem : Process Payment
PaymentSystem -> PaymentSystem : Validate Payment
PaymentSystem -> WebInterface : Payment Success
WebInterface -> OrderService : Confirm Order

== Shipping Process ==
OrderService -> ShippingService : Ship Order
ShippingService -> OrderService : Shipping Confirmed

== Confirmation ==
OrderService -> WebInterface : Send Order Confirmation
WebInterface -> Player : Display Confirmation

@enduml

```
---

## 8. Deployment Diagram
![Deployment Diagram](https://github.com/user-attachments/assets/9a31645c-e60b-486d-92a1-09e5085803be)
```plantuml
@startuml
!theme plain

node "Web Server 1" {
  component "Web Interface" as WebInterface
}

node "Application Server" {
  component "Order Service" as OrderService
  component "Cart" as Cart
}

node "Database Server" {
  component "NoSQL Database" as NoSQLDatabase
}

node "External Services" {
  component "Payment System" as PaymentSystem
  component "Shipping Service" as ShippingService
}

WebInterface --> Cart : Access Cart Data
WebInterface --> OrderService : Create and Confirm Orders
OrderService --> NoSQLDatabase : Store Order Data
OrderService --> PaymentSystem : Process Payment
OrderService --> ShippingService : Manage Shipping
@enduml

```
---
## 9. Swimlane Diagram
<img width="541" alt="Screenshot 2024-12-08 at 4 48 36 PM" src="https://github.com/user-attachments/assets/f6cae31a-59b0-4428-a7f3-b9ec1d594b84">

```plantuml
@startuml
|Customer|
start
:Browse Products;
:Select Category and Filter;
:View Product Details;
:Add to Cart;
|Admin|
:Manage Product Listings;
:Approve/Reject New Listings;
:Monitor Inventory;
|Customer|
:Proceed to Checkout;
:Enter Address and Payment Details;
|Payment Gateway|
:Process Payment;
|Admin|
:Validate Payment;
|Customer|
:Receive Order Confirmation;
:Track Order Status;
stop
@enduml
```

