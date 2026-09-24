# Understanding JWT Authentication in a Node.js API

## Introduction

Authentication is an important part of backend development because an API needs a way to identify users and protect private resources.

While building my Authenticated Blog API, I learned how JSON Web Tokens (JWT) can be used to authenticate users and protect API routes.

## What Is JWT?

JWT stands for JSON Web Token.

A JWT is a token that a server gives to a user after successful authentication. The client can then send the token when making requests to protected endpoints.

The server verifies the token to determine whether the request is authenticated.

## How JWT Authentication Works

The basic flow is:

1. A user creates an account.
2. The user's password is securely hashed before being stored.
3. The user logs in with their email and password.
4. The server verifies the credentials.
5. The server creates a JWT.
6. The client sends the JWT with requests to protected routes.
7. The server verifies the JWT before allowing access.

This means that users can access protected resources without sending their password with every request.

## Protecting API Routes

In my Blog API, JWT authentication is used to protect article routes.

A middleware checks whether a valid token has been provided. If the token is missing or invalid, the request is rejected.

Authentication and ownership are also different concepts. Authentication determines **who the user is**, while ownership checks determine whether that user is allowed to modify a particular article.

## What I Learned

Working with JWT authentication helped me understand how authentication middleware fits into a backend application.

I also learned that authentication should be combined with other security practices, such as password hashing, input validation, and ownership checks.

## Conclusion

JWT authentication is one of the backend concepts I have practiced while building my portfolio projects.

Building the Authenticated Blog API helped me move beyond basic CRUD operations and understand how authentication, authorization, middleware, databases, and API routes work together.
