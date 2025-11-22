# Customer Management API – Copilot Workflow (With Prompts)

This page documents the full workflow and **exact prompts** used in Ask Mode, Edit Mode, and Agent Mode of GitHub Copilot Chat to build the Customer Management API under the package `com.hexaware`.

---

## 📁 Step 1 — Create Package Structure

**Packages to create under `com.hexaware`:**

- `model`
- `service`
- `repository`
- `controller`

---

## 📄 Step 2 — Model Package

Inside the `model` package create:

- Enum: `CustomerType`
- Class: `Customer`

---

## 💬 Step 3 — Ask Mode Prompts (Model Generation)

### **Prompt Used (Ask Mode):**

```
Generate variables by name id(long), name, customerType(RED,SILVER,PREMIUM),dateOfBirth(LocalDate),dateOfJoin(LocalDate),accountBalance(float). 
Generate setter, getter, constructors default and parameterized, toString, hashCode and equals.
```

This prompt generates:

- Fields  
- Getters & Setters  
- Default + Parameterized constructors  
- `toString()`  
- `hashCode()`  
- `equals()`  

---

## ✏️ Step 4 — Edit Mode Prompts (Dependencies)

The following prompt was used after switching to Edit Mode and opening `pom.xml`.

### **Prompt Used (Edit Mode):**

```
Add dependency for github faker api.
Add dependency for openapi swagger mvc for api publishing.
```

After this:

- Go to **Maven → Reload Dependencies**

Dependencies added:

- `github faker`
- `springdoc-openapi-starter-webmvc-ui`

---

## 🗂️ Step 5 — Agent Mode Prompts (Repository)

### **Prompt Used (Agent Mode):**

```
Generate a class CustomerRepository which is a Spring Boot component of Repository but not using JPA. 
It should have CRUD operations where it returns 30 customers using Faker API, 
also additional methods for finding by category and filtering by age.
```

The repository must implement:

- `findAll()`
- `findById()`
- `save()`
- `update()`
- `delete()`
- `findByCategory(CustomerType type)`
- `filterByAge(int minAge, int maxAge)`

All customers are stored **in-memory** and generated using Faker.

---

## 🛠️ Step 6 — Agent Mode Prompts (Service Layer)

Before generating service, the following classes were added to context:
- `Customer`
- `CustomerRepository`

### **Prompt Used (Agent Mode):**

```
Generate a class by name CustomerService which is a Spring Boot component of Service, 
and inject the dependency of CustomerRepository using constructor injection 
and write the methods corresponding to CustomerRepository with additional checks for missing values and exception handling.
```

The service includes:

- CRUD with validation & errors  
- Category search  
- Age filter  

---

## 🌐 Step 7 — Agent Mode Prompts (Controller Layer)

Before generating controller, the following were added to context:
- `Customer`
- `CustomerService`
- `CustomerRepository`

### **Prompt Used (Agent Mode):**

```
Generate a class CustomerController to serve the methods in CustomerService.
```

The controller exposes REST endpoints for:

- CRUD  
- Category filter  
- Age filter  

---

## ✅ End of Workflow

This page captures:

- All steps  
- All Copilot modes used  
- Exact prompts  
- Purpose of each step  

You can now include this file in your GitBook or training documentation.

