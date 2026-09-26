# Summary
---
This is a Data flow and Threat/Safety model report for crAPI - a vulnerable web application designed to educate about API security.
Uses STRIDE framework
# Asset Information
---
- **Name:** crAPI
- **Description:** crAPI application is modeled as a B2C application that allows any user to get their car servicing done by a car mechanic. A user can create an account on the WebApp, manage his/her cars, search for car mechanics, submit servicing request for any car, and purchase car accessories from the vendor. The WebApp also has a community section where users can contribute with blog posts and comments.
- **Internet Facing:** Yes
- **Authentication Type:** PASSWORD
# Threat modeling DFD
---
### Data flow diagram
![data-flow-diagram](../../images/Pasted%20image%2020260926192839.png)
### Data flow reports
#### External entities
- **User**: A person interacting with the system for car service
- **Mail service**: Here mail service plays as a third-party service that provide extra functionality for the authentication process.
- **Admin user**: User with high privileges.
#### Processes
- **Authentication Process**: Handles user login and authentication, including login with email token. 
- **Reset password process**: Handle the generation and verification of the OTP. Potential vulnerability related to the OTP code.
- **User profile edit process**: Handle user profile video update and convert. Including profile video deletion action executed by admin user.
- **Email changing process**: Handle the submission of new emails from user to the application. It includes the process of verifying the Email token.
- **Posts handling process**: Manages posts and comments in the forum.
- **Coupon handling process**: Manages discount coupon created by users, including create, validate and applying coupon codes to discount items.
- **Product managing process**: Handles the process of adding new products into the catalog
- **Order tracking process**: Handles the ordering process from creation, update to tracking orders.
- **Mechanic & service management process**: Covering mechanic-related processes including assigning, and tracking service reports.
#### Data stores
- **User database**: Stores all user data, including login credentials and profile information. Security considerations include potential exposure of sensitive data.
- **Workshop database**: Stores all data related to service and workshop, including mechanic informations, product informations and order data.
- **Community database**: Stores community related data including posts, comments, and coupons.
#### Trust Boundaries
- **Internet Boundary**: Separates external actors (User, Admin, Mail Service) from internal API endpoints. Enforces authentication and input validation.
- **Service Authorization Boundary**: Separates incoming requests from microservice business logic. Enforces role-based and object-level access controls (protecting against BOLA/BFLA).
- **Data Persistence Boundary**: Separates backend process execution from database storage layers. Restricts direct data access to authenticated micro-service queries.
# Threat table
---

| Threat | STRIDE category | Attack Vector | Impact level | Risk rating | Affected components |
| ------ | --------------- | ------------- | ------------ | ----------- | ------------------- |
|        |                 |               |              |             |                     |
