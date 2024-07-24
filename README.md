# Sptrng Security JWT Auth App

## Overview

Sptrng is a secure task management application with backend functionalities created using Spring Boot. The app leverages Spring Security with JWT (JSON Web Tokens) for authentication, including access and refresh tokens, and uses PostgreSQL as its database. It provides endpoints for user management and task management with comprehensive CRUD operations.

## Features

- **User Authentication**: Signup, signin, and refresh token functionality using JWT.
- **Task Management**: Create, update, delete, and retrieve tasks with associated points.
- **User Management**: Update user information and retrieve authenticated user details.

## Technologies Used

- **Backend**: Spring Boot
- **Security**: Spring Security with JWT
- **Database**: PostgreSQL
- **ORM**: JPA (Java Persistence API)
- **Cookies**: Used for storing JWT tokens

## Endpoints

### Authentication

- **Signup**
  - **URL**: `/api/v1/auth/signup`
  - **Method**: `POST`
  - **Body**: `SignUpRequest` (JSON)
  - **Response**: `JwtAuthenticationResponse`
  
- **Signin**
  - **URL**: `/api/v1/auth/signin`
  - **Method**: `POST`
  - **Body**: `SignInRequest` (JSON)
  - **Response**: `JwtAuthenticationResponse`
  
- **Refresh Token**
  - **URL**: `/api/v1/auth/refresh`
  - **Method**: `POST`
  - **Cookie**: `refreshToken`
  - **Response**: `JwtAuthenticationResponse`

### Task Management

- **Create Task**
  - **URL**: `/api/v1/task`
  - **Method**: `POST`
  - **Body**: `TaskRequest` (JSON)
  - **Response**: `Task`

- **Get Tasks**
  - **URL**: `/api/v1/task`
  - **Method**: `GET`
  - **Response**: List of `Task`

- **Get Task by ID**
  - **URL**: `/api/v1/task/{id}`
  - **Method**: `GET`
  - **Response**: `Task`

- **Delete Task**
  - **URL**: `/api/v1/task/{id}`
  - **Method**: `DELETE`
  - **Response**: Status of the deletion operation

- **Add Point**
  - **URL**: `/api/v1/task/{id}`
  - **Method**: `POST`
  - **Body**: `TaskPointRequest` (JSON)
  - **Response**: Updated `Task`

- **Delete Point**
  - **URL**: `/api/v1/task/{taskId}/{pointId}`
  - **Method**: `DELETE`
  - **Response**: Status of the deletion operation

- **Set Point Completion**
  - **URL**: `/api/v1/task/{taskId}/{pointId}`
  - **Method**: `PUT`
  - **Request Parameter**: `completed` (boolean)
  - **Response**: Updated `Task`

### User Management

- **Update User**
  - **URL**: `/api/v1/user/update`
  - **Method**: `PUT`
  - **Body**: `UserInfo` (JSON)
  - **Response**: Updated `User`

- **Get Authenticated User ID**
  - **URL**: `/api/v1/user/authenticated`
  - **Method**: `GET`
  - **Response**: Authenticated User ID

- **Get User by ID**
  - **URL**: `/api/v1/user/{id}`
  - **Method**: `GET`
  - **Response**: `User`

- **Confirm Email**
  - **URL**: `/api/v1/user/confirmemail`
  - **Method**: `GET` or `POST`
  - **Request Parameter**: `token`
  - **Response**: Status of email confirmation

## Installation

### Prerequisites

- Java 17 or higher
- PostgreSQL database
- Maven or Gradle (for building the project)

### Steps

1. **Clone the Repository**

    ```bash
    git clone https://github.com/yourusername/sptrng-security-jwt-auth-app.git
    ```

2. **Navigate to the Project Directory**

3. **Configure the Database**

   Update `src/main/resources/application.properties` with your PostgreSQL database configuration:

    ```properties
    spring.datasource.url=jdbc:postgresql://localhost:5432/yourdatabase
    spring.datasource.username=yourusername
    spring.datasource.password=yourpassword
    ```

4. **Build the Project**

    If you're using Maven:

    ```bash
    mvn clean install
    ```

    Or if you're using Gradle:

    ```bash
    ./gradlew build
    ```

5. **Run the Spring Application**
