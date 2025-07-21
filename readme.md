# Secure Notes

## Project Description
Secure Notes is a full-stack application designed to provide users with a secure and private platform for storing and managing their notes. The application ensures data confidentiality and integrity through robust security measures, including user authentication, authorization, and secure API communication. It features a Spring Boot backend for API services and a React frontend for a dynamic user interface.

## File Structure

```
Secure Notes/
├── notes/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/
│   │   │   │       └── secure/
│   │   │   │           └── notes/
│   │   │   │               ├── config/
│   │   │   │               │   └── OAuth2LoginSuccessHandler.java
│   │   │   │               ├── controllers/
│   │   │   │               │   ├── AdminController.java
│   │   │   │               │   ├── AuditLogController.java
│   │   │   │               │   ├── AuthController.java
│   │   │   │               │   ├── CsrfController.java
│   │   │   │               │   └── NoteController.java
│   │   │   │               ├── dtos/
│   │   │   │               │   └── UserDTO.java
│   │   │   │               ├── HelloController.java
│   │   │   │               ├── models/
│   │   │   │               │   ├── AppRole.java
│   │   │   │               │   ├── AuditLog.java
│   │   │   │               │   ├── Note.java
│   │   │   │               │   ├── PasswordResetToken.java
│   │   │   │               │   ├── Role.java
│   │   │   │               │   └── User.java
│   │   │   │               ├── NotesApplication.java
│   │   │   │               ├── repositories/
│   │   │   │               │   ├── AuditLogRepository.java
│   │   │   │               │   ├── NoteRepository.java
│   │   │   │               │   ├── PasswordResetTokenRepository.java
│   │   │   │               │   ├── RoleRepository.java
│   │   │   │               │   └── UserRepository.java
│   │   │   │               ├── security/
│   │   │   │               │   ├── jwt/
│   │   │   │               │   │   ├── AuthEntryPointJwt.java
│   │   │   │               │   │   ├── AuthTokenFilter.java
│   │   │   │               │   │   └── JwtUtils.java
│   │   │   │               │   ├── request/
│   │   │   │               │   │   ├── LoginRequest.java
│   │   │   │               │   │   └── SignupRequest.java
│   │   │   │               │   ├── response/
│   │   │   │               │   │   ├── LoginResponse.java
│   │   │   │               │   │   ├── MessageResponse.java
│   │   │   │               │   │   └── UserInfoResponse.java
│   │   │   │               │   ├── SecurityConfig.java
│   │   │   │               │   └── services/
│   │   │   │               │       ├── UserDetailsImpl.java
│   │   │   │               │       └── UserDetailsServiceImpl.java
│   │   │   │               │   └── WebConfig.java
│   │   │   │               ├── services/
│   │   │   │               │   ├── AuditLogService.java
│   │   │   │               │   ├── impl/
│   │   │   │               │   │   ├── AuditLogServiceImpl.java
│   │   │   │               │   │   ├── NoteServiceImpl.java
│   │   │   │               │   │   ├── TotpServiceImpl.java
│   │   │   │               │   │   └── UserServiceImpl.java
│   │   │   │               │   ├── NoteService.java
│   │   │   │               │   ├── TotpService.java
│   │   │   │               │   └── UserService.java
│   │   │   │               └── util/
│   │   │   │                   ├── AuthUtil.java
│   │   │   │                   └── EmailService.java
│   │   │   ├── resources/
│   │   │   │   ├── static/
│   │   │   │   └── templates/
│   │   ├── test/
│   │   │   └── java/
│   │   │       └── com/
│   │   │           └── secure/
│   │   │               └── notes/
│   │   │                   └── NotesApplicationTests.java
│   ├── pom.xml
│   └── mvnw mvnw.cmd
├── secure-notes-react/
│   ├── public/
│   │   ├── favicon.ico
│   │   ├── index.html
│   │   ├── logo192.png
│   │   ├── logo512.png
│   │   ├── manifest.json
│   │   └── robots.txt
│   ├── src/
│   │   ├── App.js
│   │   ├── App.test.js
│   │   ├── components/
│   │   │   ├── aboutPage/
│   │   │   │   └── AboutPage.js
│   │   │   ├── AuditLogs/
│   │   │   │   ├── Admin.js
│   │   │   │   ├── AdminAreaSidebar.js
│   │   │   │   ├── AdminAuditLogs.js
│   │   │   │   ├── AuditLogsDetails.js
│   │   │   │   ├── UserDetails.js
│   │   │   │   └── UserList.js
│   │   │   ├── Auth/
│   │   │   │   ├── AccessDenied.js
│   │   │   │   ├── ForgotPassword.js
│   │   │   │   ├── Login.js
│   │   │   │   ├── OAuth2RedirectHandler.js
│   │   │   │   ├── ResetPassword.js
│   │   │   │   ├── Signup.js
│   │   │   │   └── UserProfile.js
│   │   │   ├── contactPage/
│   │   │   │   └── ContactPage.js
│   │   │   ├── Errors.js
│   │   │   ├── Footer/
│   │   │   │   └── Footer.js
│   │   │   ├── InputField/
│   │   │   │   └── InputField.js
│   │   │   ├── LandingPage.js
│   │   │   ├── LandingPageCom/
│   │   │   │   ├── Brands/
│   │   │   │   │   ├── BrandItem.js
│   │   │   │   │   └── Brands.js
│   │   │   │   ├── CardSlider.js
│   │   │   │   ├── State.js
│   │   │   │   └── Testimonial/
│   │   │   │       ├── Testimonial.js
│   │   │   │       └── TestimonialItem.js
│   │   │   ├── Navbar.js
│   │   │   ├── Notes/
│   │   │   │   ├── AllNotes.js
│   │   │   │   ├── CreateNote.js
│   │   │   │   ├── NoteDetails.js
│   │   │   │   └── NoteItems.js
│   │   │   ├── NotFound.js
│   │   │   ├── PopModal.js
│   │   │   └── ProtectedRoute.js
│   │   ├── index.css
│   │   ├── index.js
│   │   ├── logo.svg
│   │   ├── reportWebVitals.js
│   │   ├── services/
│   │   │   └── api.js
│   │   ├── setupTests.js
│   │   ├── store/
│   │   │   └── ContextApi.js
│   │   └── utils/
│   │       ├── Buttons.js
│   │       ├── tableColumn.js
│   │       └── truncateText.js
│   ├── package.json
│   ├── package-lock.json
│   └── tailwind.config.js
└── readme.md
```

## Backend API Endpoints

### AuthController
*   **POST /api/auth/public/signin** - Authenticate user and return JWT token.
*   **POST /api/auth/public/signup** - Register a new user.
*   **GET /api/auth/user** - Get user details.
*   **GET /api/auth/username** - Get current authenticated username.
*   **POST /api/auth/public/forgot-password** - Send password reset email.
*   **POST /api/auth/public/reset-password** - Reset user password.
*   **POST /api/auth/enable-2fa** - Enable 2FA for the authenticated user.
*   **POST /api/auth/disable-2fa** - Disable 2FA for the authenticated user.
*   **POST /api/auth/verify-2fa** - Verify 2FA code for the authenticated user.
*   **GET /api/auth/user/2fa-status** - Get 2FA status for the authenticated user.
*   **POST /api/auth/public/verify-2fa-login** - Verify 2FA code during login.

### AdminController
*   **GET /api/admin/getusers** - Get all users.
*   **PUT /api/admin/update-role** - Update user role.
*   **GET /api/admin/user/{id}** - Get user by ID.
*   **PUT /api/admin/update-lock-status** - Update account lock status.
*   **GET /api/admin/roles** - Get all roles.
*   **PUT /api/admin/update-expiry-status** - Update account expiry status.
*   **PUT /api/admin/update-enabled-status** - Update account enabled status.
*   **PUT /api/admin/update-credentials-expiry-status** - Update credentials expiry status.
*   **PUT /api/admin/update-password** - Update user password.

### AuditLogController
*   **GET /api/audit** - Get all audit logs (Admin only).
*   **GET /api/audit/note/{id}** - Get audit logs for a specific note (Admin only).

### CsrfController
*   **GET /api/csrf-token** - Get CSRF token.

### NoteController
*   **POST /api/notes** - Create a new note for the authenticated user.
*   **GET /api/notes** - Get all notes for the authenticated user.
*   **PUT /api/notes/{noteId}** - Update a specific note for the authenticated user.
*   **DELETE /api/notes/{noteId}** - Delete a specific note for the authenticated user.

### HelloController
*   **GET /hello** - Returns "Hello".
*   **GET /contact** - Returns "Contact".
*   **GET /hi** - Returns "Hi".

## `application.properties` Structure

```properties
spring.application.name=notes
spring.security.user.name=admin
spring.security.user.password=<YOUR_ADMIN_PASSWORD>

spring.datasource.url=jdbc:mysql://localhost:3306/securenotes
spring.datasource.username=<YOUR_DB_USERNAME>
spring.datasource.password=<YOUR_DB_PASSWORD>

spring.jpa.hibernate.ddl-auto=update
# spring.sql.init.mode=always
# spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

spring.app.jwtSecret=<YOUR_JWT_SECRET>
spring.app.jwtExpirationMs=86400000

logging.level.org.springframework.security=DEBUG

# email settings
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=<YOUR_EMAIL_USERNAME>
spring.mail.password=<YOUR_EMAIL_APP_PASSWORD>
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true

# GitHub OAuth2 configuration
spring.security.oauth2.client.registration.github.client-id=<YOUR_GITHUB_CLIENT_ID>
spring.security.oauth2.client.registration.github.client-secret=<YOUR_GITHUB_CLIENT_SECRET>
spring.security.oauth2.client.registration.github.scope=read:user,user:email

# Google OAuth2 configuration
spring.security.oauth2.client.registration.google.client-id=<YOUR_GOOGLE_CLIENT_ID>
spring.security.oauth2.client.registration.google.client-secret=<YOUR_GOOGLE_CLIENT_SECRET>

frontend.url=http://localhost:3000
```

## How to Run the Project

### Backend (Spring Boot)
1.  **Prerequisites**: Ensure you have Java 17 and Maven installed.
2.  Navigate to the `notes` directory:
    ```bash
    cd notes
    ```
3.  Build the project using Maven:
    ```bash
    ./mvnw clean install
    ```
4.  Run the Spring Boot application:
    ```bash
    ./mvnw spring-boot:run
    ```
    The backend will start on `http://localhost:8080`.

### Frontend (React)
1.  **Prerequisites**: Ensure you have Node.js and npm (or yarn) installed.
2.  Navigate to the `secure-notes-react` directory:
    ```bash
    cd secure-notes-react
    ```
3.  Install the dependencies:
    ```bash
    npm install
    # or yarn install
    ```
4.  Start the React development server:
    ```bash
    npm start
    # or yarn start
    ```
    The frontend will start on `http://localhost:3000`.

## Project Requirements

### Backend
*   Java 17
*   Maven
*   MySQL Database (or other compatible database) configured in `notes/src/main/resources/application.properties`

### Frontend
*   Node.js (LTS version recommended)
*   npm or Yarn

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details (Note: You may need to create a LICENSE.md file in the root directory).

## Author

*   **Milind Saini** - *Initial work* - https://github.com/MilindSaini


