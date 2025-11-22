# Prompt Engineering 

## What is Prompt Engineering?

Prompt Engineering is the practice of designing, structuring, and refining prompts (instructions) given to AI tools like GitHub Copilot or ChatGPT to get the most accurate, creative, and context-aware outputs.

It’s similar to giving clear requirements to a developer: the better the specification, the better the implementation.

---

## Why is it Important for Developers?

- Helps generate clean, structured code faster.
- Reduces chances of wrong or incomplete outputs.
- Guides AI to follow **coding standards** and **best practices**.
- Saves time in writing boilerplate code or documentation.

---

## How to Structure a Prompt (Java/Angular Developer Perspective)

1. **Be Clear and Specific**
   - Bad: *"Write code for login"*  
   - Good: *"Generate a Spring Boot REST controller with a POST endpoint `/login` that accepts username/password and returns a JWT token."*

2. **Add Context**
   - Include project type, framework, and constraints.
   - Example: *"In Angular 16, create a reactive form with validation for email and password, including error messages."*

3. **Define Output Requirements**
   - Example: *"Write a Java class `Employee` with fields id, name, department, salary. Include constructor, getters, setters, and `toString` method."*

4. **Iterate and Refine**
   - Start simple, then refine if output is not satisfactory.

---

## Easy Way to Remember (C.A.R.E.)
- **C**ontext → Specify framework/language (Java, Angular, Spring, etc.)
- **A**ction → What should AI do? (Generate, Refactor, Explain, Optimize)
- **R**equirements → Constraints (add validations, follow SOLID, etc.)
- **E**xpected Output → Desired format (class, function, Angular component)

---

## Best Practices
- Always mention the **language** (Java, TypeScript, HTML, etc.).
- Use **role-specific instructions** (“as a Java developer…”, “as an Angular front-end developer…”).
- Add **examples of inputs/outputs** for clarity.
- Refine prompts iteratively instead of writing vague ones.
- Keep prompts professional (avoid incomplete slang).

---

## Zero-shot, One-shot, and Few-shot Prompting

### Zero-shot Prompting
- **Definition**: Asking AI to solve a task without giving any examples.
- **Example**:  
  *"Write a Java class `Address` with fields: street, city, state, zipCode, country. Include constructor, getters, setters, and toString."*

### One-shot Prompting
- **Definition**: Providing **one example** so the AI understands the format you expect.
- **Example**:  
  *"Here is an example of a Java class with getters and setters:  
  ```java
  class Employee {
      private String name;
      private int age;
      // constructor, getters, setters
  }
  ```  
  Now, create a class `Book` with title, author, ISBN, price, and publisher in the same style."*

### Few-shot Prompting
- **Definition**: Providing **multiple examples** to guide the AI toward a consistent output style.
- **Example**:  
  *"Here are two examples of Java POJOs:  
  ```java
  class Car {
      private String brand;
      private int year;
      // constructor, getters, setters
  }
  ```  
  ```java
  class Student {
      private String name;
      private double gpa;
      // constructor, getters, setters
  }
  ```  
  Now, create a class `Course` with courseName, courseCode, credits, and instructor."*

---

## 30+ Example Prompts for Java/Angular Developers

### Java Prompts
1. Create a POJO `Book` with fields title, author, ISBN, and price. Add constructor, getters, setters, and toString method.
2. Generate a Spring Boot REST controller for `/students` with CRUD operations.
3. Write JUnit 5 test cases for a service method that calculates employee bonus.
4. Refactor this Java code to follow SOLID principles: [paste code].
5. Explain this Java Stream API code step by step: [paste code].
6. Optimize this SQL query used in Spring Data JPA: [paste query].
7. Write a Java class that connects to PostgreSQL using JDBC.
8. Generate a `Comparator` for sorting employees by salary in descending order.
9. Create a Java Enum for OrderStatus with values NEW, PROCESSING, SHIPPED, DELIVERED.
10. Write a Spring Boot configuration for connecting to Redis cache.

### Angular Prompts
11. Generate an Angular 16 component `UserProfile` with HTML and CSS.
12. Create a reactive form in Angular with email and password fields, including validation.
13. Write a service in Angular to call a REST API endpoint `/orders` using HttpClient.
14. Generate Angular routing module with routes for home, about, and contact pages.
15. Convert this Angular template-driven form into a reactive form.
16. Add custom error messages for validation in an Angular reactive form.
17. Write an Angular interceptor to attach JWT tokens to every HTTP request.
18. Create a search pipe in Angular that filters an array of strings by a search term.
19. Generate unit tests for Angular service using Jasmine and Karma.
20. Create an Angular Material table to display a list of employees.

### Mixed Java + Angular Prompts
21. Write a REST API in Spring Boot for `/books` and generate Angular service to consume it.
22. Create a Spring Boot + Angular integration where Angular uploads a file to backend.
23. Write a DTO class in Java and show how Angular frontend consumes it.
24. Generate sample JSON response for an Order API and write Angular interface for it.
25. Write a Spring Boot Security config to allow only authenticated Angular users.
26. Generate Java + Angular code for login and token validation flow.
27. Write an Angular service for pagination and a Spring Boot API to support it.
28. Create a Java utility method that returns JSON and an Angular component to render it.
29. Show how to handle CORS between Angular frontend and Spring Boot backend.
30. Write prompts to compare synchronous vs asynchronous calls in Angular and Java.

---

## Summary

- **Prompt Engineering = Better Instructions → Better Output**
- Use **C.A.R.E. framework** (Context, Action, Requirements, Expected Output)
- Apply **Zero-shot, One-shot, Few-shot** depending on complexity
- Always **iterate and refine** prompts for better results
