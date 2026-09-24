# Authenticated Blog API — Case Study

## 1. Problem Statement

Content platforms need a secure way to manage users and their articles. Users should be able to create and manage their own content while preventing unauthorized users from accessing or modifying another user's articles.

The Authenticated Blog API provides a backend system for user authentication and article management. It allows registered users to securely access protected resources and manage their own articles.

## 2. Architecture

The API follows a modular REST architecture using Node.js and Express.js.

The general request flow is:

**Client → Express API → Routes → Middleware → Controllers → Models → MongoDB**

* **Client:** Sends HTTP requests to the API.
* **Routes:** Define endpoints for authentication and article operations.
* **Middleware:** Handles authentication and other supporting tasks.
* **Controllers:** Handle the application's business logic.
* **Models:** Define the structure of users and articles using Mongoose.
* **MongoDB:** Stores user and article data persistently.

JWT authentication is used to protect private routes. When a user logs in successfully, the API provides a token that can be used to access protected resources.

## 3. Technical Trade-offs

### JWT Authentication

JWT was used to authenticate users and protect private API endpoints.

The advantage is that authentication information can be verified through the token without requiring a traditional server-side session for every request.

The trade-off is that tokens must be handled securely. If a token is exposed, it could potentially be used by someone else until it expires or is otherwise invalidated.

### MongoDB vs SQL

MongoDB was used to store users and articles because it integrates well with the Node.js and Mongoose stack used by the project.

A SQL database provides a structured relational model and can be useful when an application requires many complex relationships. MongoDB provides a flexible document-based structure that works well for the project's user and article data.

The trade-off is flexibility and straightforward development versus the relational structure and features offered by SQL databases.

## 4. Security

The API includes several security-related features:

* Passwords are hashed using bcrypt rather than stored as plain text.
* JWT authentication protects private routes.
* Ownership checks prevent users from modifying articles belonging to other users.
* Input validation helps prevent invalid data from entering the system.

## 5. Evidence

Evidence for the project includes:

* Successful user registration and login.
* JWT authentication protecting article routes.
* Article CRUD operations.
* Ownership checks for article access and modification.
* Validation of incoming data.
* MongoDB data persistence.
* API testing results.
* Project structure separating models, routes, validation, and middleware.
* GitHub repository showing the development work.
