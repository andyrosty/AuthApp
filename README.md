# AuthApp - OAuth2 Authentication Application

## Overview
AuthApp is a Spring Boot application that demonstrates OAuth2 authentication using Google Sign-in and GitHub Sign-in. This application provides a simple framework for implementing social login in web applications.

## Features
- OAuth2 authentication with multiple providers
- Google Sign-in integration
- GitHub Sign-in integration
- Spring Security implementation

## Technologies
- Java 17
- Spring Boot 3.4.3
- Spring Security
- Spring OAuth2 Client
- Maven

## Prerequisites
- JDK 17 or later
- Maven 3.6+ or use the included Maven wrapper
- Google OAuth2 credentials (for Google Sign-in)
- GitHub OAuth App credentials (for GitHub Sign-in)

## Getting Started

### Clone the Repository
```bash
git clone <repository-url>
cd AuthApp
```

### Configure OAuth2 Providers
To use the OAuth2 authentication, you need to register your application with the providers and obtain client credentials.

1. **Google OAuth2 Setup**:
   - Go to the [Google Developer Console](https://console.developers.google.com/)
   - Create a new project
   - Enable the Google+ API
   - Create OAuth2 credentials (OAuth client ID)
   - Add authorized redirect URIs (e.g., http://localhost:8080/login/oauth2/code/google)

2. **GitHub OAuth2 Setup**:
   - Go to [GitHub Developer Settings](https://github.com/settings/developers)
   - Create a new OAuth App
   - Add the homepage URL (e.g., http://localhost:8080)
   - Add the authorization callback URL (e.g., http://localhost:8080/login/oauth2/code/github)

3. **Configure application.properties**:
   ```properties
   spring.application.name=AuthApp

   # Google OAuth2 Configuration
   spring.security.oauth2.client.registration.google.client-id=YOUR_GOOGLE_CLIENT_ID
   spring.security.oauth2.client.registration.google.client-secret=YOUR_GOOGLE_CLIENT_SECRET

   # GitHub OAuth2 Configuration
   spring.security.oauth2.client.registration.github.client-id=YOUR_GITHUB_CLIENT_ID
   spring.security.oauth2.client.registration.github.client-secret=YOUR_GITHUB_CLIENT_SECRET
   ```

### Build and Run the Application
Using Maven:
```bash
./mvnw clean install
./mvnw spring-boot:run
```

Or using the JAR file:
```bash
./mvnw clean package
java -jar target/AuthApp-0.0.1-SNAPSHOT.jar
```

The application will be available at http://localhost:8080

## Project Structure
- `AuthAppApplication.java` - Main Spring Boot application class
- `SecurityConfig.java` - Spring Security configuration
- `HomeController.java` - Web controller for handling requests

## Development
This project is currently in development. The following components need to be implemented:
- Complete the security configuration in `SecurityConfig.java`
- Implement endpoints and views in `HomeController.java`
- Add user profile management
- Implement logout functionality

## License
[Specify your license here]

## Contributors
- [Your Name]

## Acknowledgements
- Spring Boot and Spring Security teams
- OAuth2 specification and providers
