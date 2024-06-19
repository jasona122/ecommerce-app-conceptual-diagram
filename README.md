 
# E-Commerce Diagram
This is a conceptual diagram to demonstrate how an e-commerce system might operate.

---
## Actors:
- Customer
- Seller

## Functional Requirements:
### Customers
- Customers can log in and view products
- Customers can search for products
- Customers can add products to a cart
- Customers can proceed to make a payment for the products in the cart
- Relevant products can be recommended to Customers, through a recommendation system

### Sellers
- Sellers can log in to their own management platform
- Sellers can view, add, create, update and delete their products to their own management platform
- Sellers can view analytics (history and predictions) on their products

### Products
- Products will be unstructured, containing a title, description, image URL, and other attributes (e.g. size)

## Non-Functional Requirements:
- Availability
  - For Customers, since viewing and searching product hugely impacts business, we can aim for 99.99% availability
  - For Sellers, we can compromise on availability since product updates would be less frequent, and we prioritize consistency of products above all else; 99.9% availability will be sufficient
- Latency
  - p99 latency should be low for users for the best user experience
  - Target of p50 latency at ~250ms for product search, and p99 at ~500ms
  - Making a payment could take a bit more time, roughly p99 of ~800ms 
  - Sellers would also be able to handle higher latency, but does not have to be as stringent as Customers, p50 of ~500ms, p99 of ~900ms
- Consistency
  - We can compromise on the consistency of search, since viewing products is a key component of our system
  - Consistency of products by seller would have to be prioritized
- Scalability
  - System can handle 2500 req/s from Customers side
  - There will be higher traffic at peak times, such as promotions or holidays
  - Assumption is that Seller side will not be as frequently accessed as Customers'

## Out of Scope:
- We will consider the payments and delivery system to be implemented by a third party, with us calling their APIs through our relevant microservices
- Product reviews will not be handled in this architecture