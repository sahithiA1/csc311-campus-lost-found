# Campus Lost & Found — User Authentication

**Student:** Sahithi Attada  
**Course:** CSC 311  
**Assignment:** Module 9 — Lab and Assignment: Security

## Project Description

Campus Lost & Found is a Spring Boot web application that allows students to report and view items found on campus.

This project extends the original Campus Lost & Found application by adding user registration, authentication, and access control using Spring Security.

Users must create an account and sign in before accessing the Lost & Found page.

## Technologies Used

- Java 21
- Spring Boot 4.1.1
- Spring Security
- Spring Data JPA
- Thymeleaf
- H2 Database
- BCrypt Password Encryption (Hashing)
- HTML, CSS, and JavaScript
- Maven

## Features

### User Registration
- Create an account using a username and password.
- Usernames must contain at least 3 characters.
- Passwords must contain at least 6 characters.
- Duplicate usernames are rejected.
- Passwords are securely stored using BCrypt hashing.

### User Authentication
- Custom sign-in page using Thymeleaf.
- Users must sign in to access the Lost & Found application.
- Displays the currently signed-in username.
- Provides a secure sign-out option.
- Shows messages for successful registration, invalid login, and logout.

### Lost & Found
- View reported items.
- Report found items with a title and location.
- Store reported items in the H2 database.
- Protect item-reporting requests using CSRF tokens.

### Security
- Spring Security protects application pages and item endpoints.
- Registration and login pages are publicly accessible.
- Passwords are never stored as plain text.
- Authentication is handled using a database-backed UserDetailsService.

## How to Run the Application

1. Clone or download this GitHub repository.
2. Open the project folder in IntelliJ IDEA.
3. Make sure Java 21 or later is installed.
4. Allow Maven to download the project dependencies.
5. Open `LostfoundApplication.java`.
6. Run the application's `main()` method.
7. Open a browser and navigate to:

   http://localhost:8080

8. Select **Register** to create an account.
9. Sign in using your registered username and password.
10. View or report lost-and-found items.
11. Click **Sign out** when finished.

## H2 Database

The application uses an H2 database to store user accounts and reported items.

The H2 console is available at:

http://localhost:8080/h2-console

Database URL:

`jdbc:h2:file:./data/lostfound-db`

To verify registered users, execute:

```sql
SELECT * FROM APP_USERS;
```

Passwords are stored as BCrypt hashes rather than plain text.

## Testing

The following functionality was tested:

- Redirect to login when not authenticated.
- Register a new account.
- Reject invalid registration details.
- Sign in with valid credentials.
- Reject invalid login credentials.
- Display the signed-in username.
- Report and display found items.
- Sign out successfully.
- Verify BCrypt password hashes in the H2 database.

## Author

**Sahithi Attada**  
CSC 311 — Module 9 Security Assignment