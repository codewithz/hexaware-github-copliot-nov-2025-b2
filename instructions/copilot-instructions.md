# GitHub Copilot Instructions for Spring Boot Java Coding

## 🧭 Purpose
This document provides instructions for GitHub Copilot to follow consistent coding standards when generating Java code for Spring Boot applications. These guidelines ensure the code is **readable, maintainable, and aligned with standard Spring practices**.

---

## ⚙️ General Guidelines

1. Use **4 spaces** per indentation level.  
2. Follow proper **Java naming conventions**.  
3. Include **Javadoc-style comments** for all public classes and methods.  
4. Remove unused imports and redundant code.  
5. Keep classes **single-responsibility** — one public class per file.  

---

## 🧪 Structure and Layering

1. Follow standard Spring Boot layer separation:
    - `controller` → REST APIs  
    - `service` → Business logic  
    - `repository` → Data access (even if simulated without a DB)  
    - `model` or `entity` → Data classes  
2. Use **constructor injection** for dependency management.  
3. **Avoid business logic in controllers** — delegate it to services.  
4. All controllers must use base path prefix:  
   ```
   /api/hexaware/production
   ```

   Example:  
   ```java
   @RestController
   @RequestMapping("/api/hexaware/production/customers")
   ```

---

## 🧱 Entity Guidelines (Non-JPA)

When creating an entity or model class:

1. **Do not use JPA annotations** such as `@Entity`, `@Table`, `@Id`, etc.  
2. Each entity must include:
   - Private fields with clear names and types.
   - **Default (no-args) constructor**.
   - **Parameterized constructor** with all fields.
   - **Getters and setters** for all fields.
   - **Overridden** methods:
     - `toString()` – return key field details.
     - `equals()` and `hashCode()` – compare based on unique fields (e.g., ID or name).  

**Example:**

```java
package com.hexaware.model;

import java.time.LocalDate;
import java.util.Objects;

/**
 * Represents a Customer in the system.
 */
public class Customer {
    private long id;
    private String name;
    private String email;
    private LocalDate dateOfBirth;
    private String accountType;
    private LocalDate dateOfJoin;

    public Customer() {}

    public Customer(long id, String name, String email, LocalDate dateOfBirth,
                    String accountType, LocalDate dateOfJoin) {
        this.id = id;
        this.name = name;
        this.email = email;
        this.dateOfBirth = dateOfBirth;
        this.accountType = accountType;
        this.dateOfJoin = dateOfJoin;
    }

    public long getId() { return id; }
    public void setId(long id) { this.id = id; }

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public String getEmail() { return email; }
    public void setEmail(String email) { this.email = email; }

    public LocalDate getDateOfBirth() { return dateOfBirth; }
    public void setDateOfBirth(LocalDate dateOfBirth) { this.dateOfBirth = dateOfBirth; }

    public String getAccountType() { return accountType; }
    public void setAccountType(String accountType) { this.accountType = accountType; }

    public LocalDate getDateOfJoin() { return dateOfJoin; }
    public void setDateOfJoin(LocalDate dateOfJoin) { this.dateOfJoin = dateOfJoin; }

    @Override
    public String toString() {
        return "Customer{id=" + id + ", name='" + name + "', email='" + email + "'}";
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof Customer)) return false;
        Customer that = (Customer) o;
        return id == that.id && Objects.equals(email, that.email);
    }

    @Override
    public int hashCode() {
        return Objects.hash(id, email);
    }
}
```

---

## 🔤 Naming Conventions

- **camelCase** → variables and methods  
- **PascalCase** → class names  
- **UPPER_SNAKE_CASE** → constants  
- Suffix controllers with `Controller`, e.g., `CustomerController`  
- Prefix interfaces meaningfully, e.g., `UserService`, `ProductRepository`

---

## 🌐 REST API Guidelines

- Base URL:  
  ```
  /api/hexaware/production
  ```
- Use appropriate HTTP verbs:
  - `GET` → Retrieve
  - `POST` → Create
  - `PUT` → Update
  - `DELETE` → Remove  
- Always return `ResponseEntity<?>`
- Include clear and meaningful endpoint names.

**Example:**

```java
@RestController
@RequestMapping("/api/hexaware/production/customers")
public class CustomerController {

    private final CustomerService customerService;

    public CustomerController(CustomerService customerService) {
        this.customerService = customerService;
    }

    /**
     * Retrieve all customers from the system.
     *
     * @return HTTP 200 with the list of customers
     */
    @GetMapping
    public ResponseEntity<List<Customer>> getAllCustomers() {
        List<Customer> customers = customerService.getAllCustomers();
        return new ResponseEntity<>(customers, HttpStatus.OK);
    }
}
```

---

## 🧹 Best Practices

- Use `@RestController` for REST endpoints.  
- Validate inputs using `@Valid` and `@NotNull`.  
- Centralize error handling with `@ControllerAdvice`.  
- Return appropriate HTTP codes (`200`, `400`, `404`, `500`).  
- Log important events and errors using `Slf4j` or similar.  
- Never expose sensitive data directly.  

---

## 🧪 Testing Standards

### 📁 Test File Naming
- Controller → `XxxControllerTest`
- Service → `XxxServiceTest`
- Repository → `XxxRepositoryTest`

### 🧩 Test Methods
Use **JUnit 5** and follow the pattern:
```java
shouldReturnCustomers_whenGetAll()
shouldThrowNotFound_whenCustomerMissing()
shouldRejectInvalidEmail_whenCreateCustomer()
```

### ✅ Coverage
- Controllers ≥ 80%  
- Services ≥ 85%  
- Repository ≥ 75% (if applicable)  

Use **AAA pattern**:  
```java
// Arrange
// Act
// Assert
```

---

## 🔒 Security Guidelines

- Never hardcode credentials, tokens, or secrets.  
- Externalize config using `application.properties` or `application.yml`.  
- Use `@PreAuthorize` / `@Secured` for role-based access.  
- Sanitize all user inputs and log sensitive info cautiously.  
