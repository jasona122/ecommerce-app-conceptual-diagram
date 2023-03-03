 
# E-Commerce Diagram
This is a conceptual diagram to demonstrate how an e-commerce system might operate.

---

Functional Requirements:
- Users can log in and view products
- Users can search for products
- Users can add products to a cart
- Users can proceed to buy the products in the cart
- Relevant products can be recommended to users
- Sellers can add their shop to the platform

Non-Functional Requirements:
- Availability
  - System can handle 2500 req/s with high uptime
- Low latency
  - p99 latency should be low for the best user experience
- Consistency
  - Any reads/writes should be consistent throughout the system, since it will affect product orders