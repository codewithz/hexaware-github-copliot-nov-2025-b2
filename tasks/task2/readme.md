# 🧩 Problem Statement: Customer Management API (Java + Spring Boot)

This module focuses on building a **complete Customer Management API** in Java using **Spring Boot**, **Faker API**, and **OpenAPI/Swagger**—**without using JPA or any database**.  
The goal is to help learners understand how to structure a Spring Boot application with **Models, Enums, Repository, Service, Controller**, and **Test Cases**, while still working with **in-memory data**.

---

## 🎯 Objective

Build a **Customer Management System** that:

- Generates **30 random customers** using the **Faker API**  
- Stores them in an **in-memory custom repository** (no JPA)
- Provides **CRUD operations**
- Provides **2 extra query methods**:
  - `findByCategory(CustomerType type)`
  - `filterByAge(int minAge, int maxAge)`
- Implements a **Service layer** with business logic
- Exposes all operations via **REST Controllers**
- Publishes API documentation using **Swagger / OpenAPI**
- Includes **unit test cases** for Controller & Service methods

---

## 🏗️ Entities & Requirements

### 1. **Customer Class**

Create a Java class `Customer` with the following fields:

| Field Name       | Type         | Description |
|------------------|--------------|-------------|
| `id`             | `long`       | Unique ID for each customer |
| `name`           | `String`     | Customer's name |
| `type`           | `CustomerType (enum)` | Category: `RED`, `SILVER`, `PLATINUM` |
| `dateOfBirth`    | `LocalDate`  | Customer’s birth date |
| `dateOfJoining`  | `LocalDate`  | When the customer joined |
| `accountBalance` | `float`      | Customer's account balance |

### 1.1 **Enum: CustomerType**

```
RED
SILVER
PLATINUM
```

---

## 📦 Repository Layer (No JPA)

Create a custom `CustomerRepository` class:

### Responsibilities:

1. Use **Faker** to generate **30 random customers** at application startup.
2. Store them internally using:  
   ```java
   private List<Customer> customers;
   ```
3. Implement **CRUD methods**:
   - `findAll()`
   - `findById(long id)`
   - `save(Customer customer)`
   - `update(long id, Customer customer)`
   - `delete(long id)`

4. Implement **Additional Query Methods**:
   - `findByCategory(CustomerType type)`
   - `filterByAge(int minAge, int maxAge)`  
     (Age derived from `dateOfBirth`)

---

## ⚙️ Service Layer

Create `CustomerService` to encapsulate business logic:

- Call repository methods  
- Validate inputs where required  
- Handle exceptions for missing records  
- Provide service methods for:
  - CRUD operations
  - Find by category
  - Filter by age range

Use **constructor injection**.

---

## 🌐 Controller Layer

Create `CustomerController` exposing REST APIs:

| Endpoint | HTTP Method | Description |
|----------|-------------|-------------|
| `/customers` | GET | Get all customers |
| `/customers/{id}` | GET | Get customer by ID |
| `/customers` | POST | Create a new customer |
| `/customers/{id}` | PUT | Update customer |
| `/customers/{id}` | DELETE | Delete customer |
| `/customers/category/{type}` | GET | Filter by category |
| `/customers/age` | GET | Filter by age range (`?min=20&max=40`) |

---

## 🧪 Testing Requirements

Write **unit tests** for:

### Service:
- CRUD
- Category filter
- Age filter
- Negative tests

### Controller:
- `MockMvc` tests  
- Status code validation  
- JSON validation  

---

## 📘 API Documentation (Swagger / OpenAPI)

Use dependency:

```
springdoc-openapi-starter-webmvc-ui
```

Swagger UI URL:

```
http://localhost:8080/swagger-ui/index.html
```

---

## 🎓 Learning Outcomes

- Spring Boot app without JPA
- Faker-generated data  
- Layered architecture  
- Custom repository logic  
- Unit testing with Mockito & MockMvc  
- Swagger documentation  
- Build APIs without a database

