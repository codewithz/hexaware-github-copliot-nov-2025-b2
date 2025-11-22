# 🚀 Final Project: Full-Stack Insurance Premium Calculator (Spring Boot + Angular + Copilot)

## 🎯 Objective

Build a complete full-stack application that calculates insurance premiums based on user inputs. Use:

- 🧠 **GitHub Copilot** for generating boilerplate and logic
- ☕ **Spring Boot (Java)** for the backend
- 🌐 **Angular (TypeScript)** for the frontend
- 💾 **DB2** as the relational database

---

## 🧩 System Overview

Users will input name, age, plan type, and smoker status. The backend (Spring Boot + DB2) will calculate the premium based on rules and return it to the Angular frontend for display.

---

## 🗃️ Database Schema (DB2-compatible `schema.sql` via Copilot)

### 1. `customers`
```sql
CREATE TABLE customers (
  id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  name VARCHAR(100),
  age INT,
  smoker BOOLEAN
);
```

### 2. `plans`
```sql
CREATE TABLE plans (
  id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  name VARCHAR(50), -- BASIC, STANDARD, PREMIUM
  base_premium DOUBLE
);
```

### 3. `premium_calculations`
```sql
CREATE TABLE premium_calculations (
  id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  customer_id INT,
  plan_id INT,
  calculated_premium DOUBLE,
  calculated_on TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (customer_id) REFERENCES customers(id),
  FOREIGN KEY (plan_id) REFERENCES plans(id)
);
```

---

## 🛠️ Backend Task Flow (Spring Boot + DB2)

### ✅ Step 1: Configure DB2 Connection

```properties
# application.properties
spring.datasource.url=jdbc:db2://localhost:50000/INSURANCE
spring.datasource.username=db2inst1
spring.datasource.password=yourpassword
spring.datasource.driver-class-name=com.ibm.db2.jcc.DB2Driver
spring.jpa.database-platform=org.hibernate.dialect.DB2Dialect
```

> Install DB2 JDBC driver if needed.

---

### ✅ Step 2: Generate Entities Using Copilot

> Prompt Copilot:

```java
// Generate JPA entity for Customer with id, name, age, smoker
// Generate JPA entity for Plan with id, name (Enum), basePremium
// Generate JPA entity for PremiumCalculation with customer, plan, calculatedPremium, calculatedOn
```

---

### ✅ Step 3: Create Repositories

```java
public interface CustomerRepository extends JpaRepository<Customer, Integer> {}
public interface PlanRepository extends JpaRepository<Plan, Integer> {}
public interface PremiumCalculationRepository extends JpaRepository<PremiumCalculation, Integer> {}
```

---

### ✅ Step 4: Implement Service Logic

> Prompt Copilot:

```java
// Implement service that calculates premium
// If smoker, add 20%
// If age > 50, add 10%
// Base premium comes from plan
```

---

### ✅ Step 5: Create Controller

Endpoints:
- `POST /api/premium/calculate` – Accepts input, calculates and saves result
- `GET /api/premium/all` – Fetch all calculations

---

### ✅ Step 6: Add Swagger Documentation

> Prompt Copilot:

```java
// Add Swagger annotations to PremiumController
```

---

### ✅ Step 7: Write Unit Tests

> Prompt Copilot:

```java
// Write unit test for PremiumCalculatorService with edge case inputs
```

---

## 💻 Frontend Task Flow (Angular 17+)

### ✅ Step 1: Setup Angular Project

```bash
ng new insurance-premium-ui --routing=true --style=scss
cd insurance-premium-ui
ng generate component premium-form
ng generate component premium-history
```

---

### ✅ Step 2: Create Form

Inputs:
- Name (Text)
- Age (Number)
- Smoker (Checkbox)
- Plan (Dropdown: BASIC, STANDARD, PREMIUM)

> Prompt Copilot:

```ts
// Angular form with name, age, smoker, plan dropdown
// Validate and bind inputs
```

---

### ✅ Step 3: Integrate with Backend (Using HttpClient)

> Prompt Copilot:

```ts
// Use Angular HttpClient to POST form to /api/premium/calculate
// Show calculated premium in UI
```

---

### ✅ Step 4: Display Calculation History

> Prompt Copilot:

```ts
// GET request to /api/premium/all
// Display as Angular Material table or cards
```

---

## 🧠 Copilot Prompts Cheat Sheet

- `// Generate DB2 SQL schema for Customer, Plan, PremiumCalculation`
- `// Create JPA entity for Plan with enum and double basePremium`
- `// Write REST controller to calculate premium`
- `// Swagger annotate controller`
- `// Create Angular form component for premium calculation`
- `// Use Angular HttpClient to send POST to Spring Boot`

---

## ✅ Deliverables

- `schema.sql` for DB2
- Spring Boot backend:
  - Entities, Services, Repositories
  - Controller with Swagger
  - JUnit tests
- Angular frontend:
  - Form, API integration, history display
- Use GitHub Copilot extensively in both frontend and backend

---

🏁 **Goal**: Build a real-world, database-integrated full-stack app using Spring Boot, DB2, and Angular with GitHub Copilot as your AI assistant.
