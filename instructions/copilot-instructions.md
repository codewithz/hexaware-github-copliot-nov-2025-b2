# GitHub Copilot Instructions for Spring Boot Java Coding

## 🧭 Purpose
This document provides instructions for GitHub Copilot to follow consistent coding standards when generating Java code for Spring Boot applications. These guidelines ensure the code is readable, maintainable, and follows common Spring development practices.

---

## ⚙️ General Guidelines

1. Use 4 spaces per indentation level.
2. Follow proper Java naming conventions and structure.
3. Include Javadoc-style comments for public classes and methods.
4. Avoid unused imports and redundant code.
5. Keep class files focused — one public class per file.

---

## 🧪 Structure and Layering

1. Follow standard Spring Boot layer separation:
   - `controller` for REST APIs
   - `controller` should be prefixed as /api/hexaware/prod 
   - `service` for business logic
   - `repository` for database access
   - `model` or `entity` for data classes
2. Use dependency injection with `@Autowired` or constructor injection.
3. Avoid placing business logic in the controller layer.

---

## 🔤 Naming Conventions

- Use **camelCase** for variables and methods.
- Use **PascalCase** for class names.
- Prefix interfaces with meaningful names (e.g., `UserService`, `ProductRepository`).
- Suffix controller classes with `Controller`.

---

## 📦 Import Statements

- Always place imports at the top of the file.
- Organize them as:
  1. `java.*`, `javax.*` imports
  2. Third-party libraries (e.g., Spring Framework, Lombok)
  3. Internal project imports
- Remove unused imports before committing.

---

## 🌐 API Example Style (Injecting Copilot-Generated Code)

```java
@RestController
@RequestMapping("/customers")
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

✅ Follows best practices:
- Uses constructor-based dependency injection  
- Properly scoped endpoint and HTTP verb  
- Uses `ResponseEntity` to manage HTTP response status  
- Clearly named method and variable (`getAllCustomers`)  
- Payload is directly used (`customers`), not a vague variable like `payload`  

---

## 🧹 Best Practices

- Annotate REST APIs with `@RestController` and map endpoints using `@RequestMapping` or HTTP-specific annotations (`@GetMapping`, etc.).
- Use DTOs to avoid exposing entities directly.
- Handle exceptions using `@ControllerAdvice`.
- Use `@Valid` and `@NotNull` for input validation.

---

# 🧪 Test Structure & Best Practices

## 📁 Test Structure & Naming

- **Location:**  
  `src/test/java/...` mirroring main package structure.

- **Class Names:**  
  - `XxxServiceTest`  
  - `XxxControllerTest`  
  - `XxxRepositoryTest`

- **Method Names (JUnit 5):**  
  - `shouldReturnCustomers_whenGetAll()`  
  - `shouldThrowNotFound_whenCustomerMissing()`  
  - `shouldRejectInvalidEmail_whenCreateCustomer()`

---

## ✅ What to Test per Layer

### Controller (Web)
- HTTP status codes, response bodies, headers.  
- Validation failures (`@Valid`, constraint violations).  
- Error handling via `@ControllerAdvice`.

### Service (Business)
- Branching logic, orchestration, transaction boundaries.  
- Interaction with repositories and other services (mocked).  

### Repository (Data)
- Query methods and custom queries.  
- Basic CRUD with realistic schema.  
- Use lightweight DB (**H2**) or **Testcontainers** for realism.

---

## 🧱 Common Patterns

- **AAA:** Arrange → Act → Assert (one assertion group per behavior).  
  > 💡 **Comment for Copilot:** Always use `//Arrange //Act //Assert` in test methods wherever applicable.  
- **Test Doubles:** Mockito (`@Mock`, `@InjectMocks`), `when(...).thenReturn(...)`, `verify(...)`.  
- **Parameterized Tests:** Boundary values, equivalence classes.  
- **Data Builders:** Create reusable valid domain objects, tweak fields per test.

---

## 🎛️ Coverage & Quality

**Targets:**  
- Line coverage ≥ **80%**  
  - Services ≥ **85%**  
  - Controllers ≥ **80%**  
- Branch coverage for complex logic.  
- No assertions on logs or private methods.  
- Prefer **state & contract assertions** over interaction unless it’s orchestration.

---

## 🔒 Security Considerations

- Never hardcode passwords, tokens, or secrets.  
- Externalize configuration using `application.properties` or `application.yml`.  
- Use `@PreAuthorize` and `@Secured` where role-based access is required.  
