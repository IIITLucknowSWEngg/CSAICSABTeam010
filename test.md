# Feature: Decathlon user Registration

## Scenario: Decathlon user registers successfully

### Given:
The Decathlon user is on the registration page.

### When:
The Decathlon user enters valid information (name, email, and password).

### Then:
The Decathlon user should be successfully registered.  
The Decathlon user should be redirected to the login page.

## Decathlon user_reg.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const registrationPage = require('../pages/registrationPage');

describe('Decathlon user Registration', function() {
  it('should register Decathlon user successfully', function() {
    registrationPage.open();
    registrationPage.fillRegistrationForm('John Doe', 'johndoe@example.com', 'Password123');
    registrationPage.submitForm();
    expect(registrationPage.getSuccessMessage()).to.equal('Registration successful');
    expect(browser.getUrl()).to.include('/login');
  });
});
```


# Feature: Product Browsing

## Scenario: Decathlon user browses products successfully

### Given:
The Decathlon user is on the homepage.

### When:
The Decathlon user selects a sport category (e.g., Running).

### Then:
The Decathlon user should be shown the relevant products in the selected category.  
The Decathlon user should be able to filter products by price and brand.

## Product_browsing.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const homepage = require('../pages/homepage');
const productPage = require('../pages/productPage');

describe('Product Browsing', function() {
  it('should display products in the selected category', function() {
    homepage.open();
    homepage.selectCategory('Running');
    expect(productPage.getProductList()).to.not.be.empty;
    expect(browser.getUrl()).to.include('/running');
  });

  it('should filter products by price and brand', function() {
    productPage.filterProducts('Nike', 'Under $50');
    expect(productPage.getFilteredProducts()).to.include('Nike');
    expect(productPage.getFilteredProducts()).to.include('Under $50');
  });
});
```

# Feature: Shopping Cart Management

## Scenario: Decathlon user adds products to the cart successfully

### Given:
The Decathlon user is logged in and viewing a product.

### When:
The Decathlon user clicks the "Add to Cart" button.

### Then:
The product should be added to the cart.  
The Decathlon user should be able to view the updated cart with the added product.

## Shopping_cart.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const productPage = require('../pages/productPage');
const cartPage = require('../pages/cartPage');

describe('Shopping Cart Management', function() {
  it('should add products to the cart successfully', function() {
    productPage.open();
    productPage.addToCart();
    expect(cartPage.getCartItemCount()).to.equal(1);
    expect(cartPage.getCartProductName()).to.include('Product Name');
  });
});
```

# Feature: Checkout Process

## Scenario: Decathlon user checks out successfully

### Given:
The Decathlon user has added products to their cart.

### When:
The Decathlon user navigates to the checkout page and enters valid payment information.

### Then:
The Decathlon user should see an order summary.  
The Decathlon user should receive an order confirmation.

## Checkout.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const checkoutPage = require('../pages/checkoutPage');

describe('Checkout Process', function() {
  it('should complete the checkout process successfully', function() {
    checkoutPage.open();
    checkoutPage.enterPaymentInfo('John Doe', '4111111111111111', '12/25', '123');
    checkoutPage.submitOrder();
    expect(checkoutPage.getOrderConfirmation()).to.include('Order confirmed');
    expect(browser.getUrl()).to.include('/order-summary');
  });
});
```

# Feature: Track Order

## Scenario: Decathlon user tracks their order status

### Given:
The Decathlon user is logged in and has placed an order.

### When:
The Decathlon user navigates to the order tracking page and enters their order ID.

### Then:
The Decathlon user should be shown the current status of their order (e.g., "Shipped", "Delivered").

## Order_tracking.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const orderTrackingPage = require('../pages/orderTrackingPage');

describe('Order Tracking', function() {
  it('should track the order status successfully', function() {
    orderTrackingPage.open();
    orderTrackingPage.enterOrderId('12345');
    expect(orderTrackingPage.getOrderStatus()).to.include('Shipped');
  });
});
```
# Feature: Product Feedback

## Scenario: Decathlon user submits feedback for a product

### Given:
The Decathlon user has purchased a product and is on the product page.

### When:
The Decathlon user submits feedback with a rating and a comment.

### Then:
The feedback should be successfully submitted.  
The Decathlon user should see the feedback on the product page.

## Product_feedback.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const productPage = require('../pages/productPage');

describe('Product Feedback', function() {
  it('should submit product feedback successfully', function() {
    productPage.open();
    productPage.submitFeedback('4', 'Good product, but could be improved');
    expect(productPage.getFeedbackConfirmation()).to.equal('Feedback submitted successfully');
    expect(productPage.getFeedbackText()).to.include('Good product, but could be improved');
  });
});
```

# Feature: Admin Product Management

## Scenario: Admin manages products successfully

### Given:
The admin is logged in and on the admin dashboard.

### When:
The admin adds a new product with name, price, and description.

### Then:
The new product should be visible in the product catalog.  
The product details should be correctly displayed.

## Admin_product_management.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const adminDashboard = require('../pages/adminDashboard');
const productManagementPage = require('../pages/productManagementPage');

describe('Admin Product Management', function() {
  it('should add a new product successfully', function() {
    adminDashboard.open();
    adminDashboard.navigateToProductManagement();
    productManagementPage.addNewProduct('New Product', '29.99', 'A great product.');
    expect(productManagementPage.getProductName()).to.equal('New Product');
    expect(productManagementPage.getProductPrice()).to.equal('29.99');
  });
});
```

# Feature: Support Staff Management

## Scenario: Support staff resolves a customer inquiry

### Given:
The support staff is logged in and viewing a customer inquiry.

### When:
The support staff responds to the inquiry with a solution.

### Then:
The customer should receive a response.  
The support staff should see the status as "Resolved".

## Support_management.js Code:

```javascript
const chai = require('chai');
const expect = chai.expect;
const supportDashboard = require('../pages/supportDashboard');
const supportTicketPage = require('../pages/supportTicketPage');

describe('Support Staff Management', function() {
  it('should resolve a customer inquiry successfully', function() {
    supportDashboard.open();
    supportDashboard.viewInquiry('12345');
    supportTicketPage.respondToInquiry('Solution to the issue');
    expect(supportTicketPage.getTicketStatus()).to.equal('Resolved');
    expect(supportTicketPage.getCustomerResponse()).to.include('Solution to the issue');
  });
});
```



