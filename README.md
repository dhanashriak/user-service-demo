User Service Documentation
 User Service Documentation
 Overview
 This documentation provides a comprehensive overview of a Spring Boot-based User Service application.
 The service handles user registration and retrieval, using MongoDB for storage. It includes:- Input validation- Logging with Aspect-Oriented Programming (AOP)- Exception handling- Unit testing using JUnit 5
 REST Endpoints
 1. Register a User
 URL: POST /api/users
 Query Parameter: notify=true (optional)
 Request Body:
 {
 }
  "id": "6",
  "name": "Mohini S",
  "age": 22,
  "email": "abhft@example.com",
  "country": "France",
  "phone": "564568839"
 Validations:
- age must be >= 18
 User Service Documentation- country must be "France"
 2. Retrieve User by ID
 URL: GET /api/users/{id}
 Description: Fetches user details by unique MongoDB ID.
 Technologies Used- Spring Boot 3.1- Spring Data MongoDB- Hibernate Validator- AspectJ- Lombok- JUnit 5
 AOP (Aspect-Oriented Programming)
 Purpose: To separate cross-cutting concerns like logging from the core business logic.
 Implementation: Logs method calls in the controller layer using AspectJ annotations.
 Example Pointcut:
 @Before("execution(* com.example.demo.controller.*.*(..))")
 MongoDB Configuration
 Database Name: userdb
 Collection Name: users
 Connection String:
 spring.data.mongodb.uri=mongodb://localhost:27017/userdb
User Service Documentation
 View Data:
 Use MongoDB Compass or the CLI:
 db.users.find()
 API Testing with Postman
 A) Register a User
 URL: http://localhost:9192/api/users?notify=true
 Method: POST
 B) Retrieve a User
 URL: http://localhost:9192/api/users/{id}
 Method: GET
 UML Diagram
 A UML diagram for the User Service is included in the original document.
