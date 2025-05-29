# fullstackjava
# 📝 List Todos App

A full-stack Todo application using **Spring Boot (Backend)** and **React (Frontend)**, demonstrating full **CRUD (Create, Read, Update, Delete)** functionality.

---

## 🔗 GitHub Repositories

- ⚙️ **Backend (Spring Boot)**: [List Todos Backend](https://github.com/your-username/list-todos-backend)
- 🎨 **Frontend (React)**: [List Todos Frontend](https://github.com/your-username/list-todos-frontend)

---

## 📸 CRUD Operation Screenshots

> Images of each CRUD operation from the frontend.

### ➕ Create Todo
![Create Todo](./images/add-todo.png)

### 📋 Read Todos
![Read Todos](./images/List-Todo.png)

### ✏️ Update Todo
![Update Todo](./images/update-todo.png)

### ❌ Delete Todo
![Delete Todo](./images/Delete-Todo.png)

### 📋 After Delete
![Delete Todo](./images/after-add.png)

---

## 🛠️ Tech Stack

- **Frontend:** React, Axios, Bootstrap/Tailwind (optional)
- **Backend:** Spring Boot, Spring Data JPA, Spring Web
- **Database:** MySQL / H2

---

## 🚀 Features

- Add, edit, delete, and view todos
- Full integration between frontend and backend via REST APIs
- Responsive and clean UI
- Component-based architecture

---

## 📦 Setup Instructions

### 🔧 Backend (Spring Boot)

1. Clone the backend repo:
    ```bash
    git clone https://github.com/your-username/list-todos-backend.git
    cd list-todos-backend
    ```

2. Configure your database in `src/main/resources/application.properties`.

3. Build and run:
    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

4. Backend runs at: `http://localhost:8080`

---

### 🎨 Frontend (React)

1. Clone the frontend repo:
    ```bash
    git clone https://github.com/your-username/list-todos-frontend.git
    cd list-todos-frontend
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Start the frontend:
    ```bash
    npm start
    ```

4. Frontend runs at: `http://localhost:3000`

> ⚠️ Make sure CORS is enabled in the backend if accessing from a different origin.

---

# Spring Security with JWT and BCrypt

This project demonstrates the implementation of **Spring Security** with enhanced security using **BCryptPasswordEncoder** for password hashing and **JWT (JSON Web Token)** for stateless authentication and authorization.

GitHub Repository: [https://github.com/your-username/spring-security-jwt](https://github.com/your-username/spring-security-jwt)

## 🔐 Features

* User authentication with JWT token generation.
* Secure password storage using BCrypt.
* Stateless authentication using JWT in headers.
* Token validation and role-based authorization.
* Custom exception handling for security events.
* Secure endpoints with fine-grained access control.

## ⚙️ Tech Stack

* Java 17+
* Spring Boot
* Spring Security
* Spring Web
* Spring Data JPA (optional)
* H2 / MySQL (for persistence, optional)
* JWT (io.jsonwebtoken - JJWT)
* BCryptPasswordEncoder

## 📦 Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/spring-security-jwt.git
   cd spring-security-jwt
   ```

2. **Configure `application.properties`**

   ```properties
   server.port=8080

   # JWT configuration
   jwt.secret=your_jwt_secret_key
   jwt.expiration=3600000  # 1 hour in milliseconds

   # Optional: Database configuration
   spring.datasource.url=jdbc:h2:mem:testdb
   spring.datasource.driverClassName=org.h2.Driver
   spring.datasource.username=sa
   spring.datasource.password=
   spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
   ```

3. **Run the Application**

   ```bash
   ./mvnw spring-boot:run
   ```

## 🔑 Authentication Flow

1. **User Registration** (POST `/api/register`)

   * Password is encoded using `BCryptPasswordEncoder`.

2. **Login** (POST `/api/login`)

   * On success, returns a JWT in the response.

3. **Secure API Call** (GET `/api/secure-data`)

   * JWT must be passed in the `Authorization` header as:

     ```
     Authorization: Bearer <your_token>
     ```

## 📁 Key Files Overview

| File                           | Description                                                    |
| ------------------------------ | -------------------------------------------------------------- |
| `SecurityConfig.java`          | Configures authentication manager, filters, and security rules |
| `JwtUtil.java`                 | Handles JWT token creation, parsing, and validation            |
| `AuthController.java`          | REST controller for login and registration                     |
| `UserDetailsServiceImpl.java`  | Loads user details from the database                           |
| `JwtAuthenticationFilter.java` | Intercepts requests to validate JWT tokens                     |
| `BCryptPasswordEncoder`        | Bean used to hash passwords securely                           |

## 🧪 Sample API Usage

### Register

```json
POST /api/register
{
  "username": "john",
  "password": "password123"
}
```

### Login

```json
POST /api/login
{
  "username": "Shreya",
  "password": "Shreya@2005"
}
```

#### Response

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

### Secure Access

```
GET /api/secure-data
Authorization: Bearer <your_token>
```

## 📸 Screenshots

### Login 

![Login Screenshot](screenshots/login.png)

### JWT Token Generated

![Token Screenshot](screenshots/token.png)

### Access Secure Endpoint with Token

![Secure Access Screenshot](screenshots/secure-access.png)

## ✅ Security Highlights

* ✅ Passwords stored using one-way BCrypt hashing.
* ✅ Stateless JWT authentication—no session storage.
* ✅ Secure endpoints with role-based access control.
* ✅ JWTs include expiration to prevent reuse.




