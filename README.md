# Spring Boot OAuth2 Login Template

A production-ready OAuth2 social login starter built with Spring Boot 3 and Spring Security 6.
This template provides clean, minimal, and extensible OAuth2 login integration using Google, GitHub, and any OAuth2/OIDC identity provider.

Perfect for quickly adding secure authentication to any Spring Boot application.

## Features

 OAuth2 Login using Spring Security 6

 Social authentication (Google, GitHub, etc.)

Fully implemented Authorization Code Flow

 In-Memory Client Registration (easily replaceable)

Clean and extensible project structure

 Protected endpoint example: /secure

 Fetches authenticated user information

Ready to be extended for production use

![OAuth2 Login Demo](assets/login-demo.gif)



### How OAuth2 Login Works
User clicks Login
       ↓
Spring redirects to OAuth2 Provider
       ↓
User authenticates on Provider (Google/GitHub)
       ↓
Provider returns Authorization Code
       ↓
Spring exchanges the code for Access Token
       ↓
Spring fetches User Profile
       ↓
User is logged in and redirected to /secure



### 📁 Project Structure
```bash
src/main/java/com/walletwave/spring_boot_oauth2_login_template
│
├── config
│   └── ProjectSecurityConfig.java       # OAuth2 + Security config
│
├── controller
│   └── SecureController.java            # Protected endpoint controller
│
├── resources
│   ├── application.properties           # OAuth2 provider settings
│   └── static/secure.html               # Example secured UI
│
└── SpringBootOauth2LoginTemplateApplication.java
```
## Configuration
Google OAuth2 Example

Add this to application.properties:

spring.security.oauth2.client.registration.google.client-id=YOUR_CLIENT_ID
spring.security.oauth2.client.registration.google.client-secret=YOUR_CLIENT_SECRET
spring.security.oauth2.client.registration.google.scope=openid, profile, email

GitHub OAuth2 Example
spring.security.oauth2.client.registration.github.client-id=XXXX
spring.security.oauth2.client.registration.github.client-secret=YYYY


 You can add any OAuth2/OIDC provider (Keycloak, Okta, Facebook, Azure AD, etc.)
## Run the Application
mvn spring-boot:run


Visit:

http://localhost:8095/secure


You will be redirected to the provider’s login page.

## Protected Endpoint

/secure
Requires OAuth2 authentication.

After login → authenticated user info is displayed.

