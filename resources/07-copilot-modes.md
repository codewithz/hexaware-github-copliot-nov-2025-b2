# ⚡ GitHub Copilot Modes: Agent vs Ask vs Edit

Understanding when to use **Agent**, **Ask**, and **Edit** modes in Copilot can save you hours of effort.  
Think of them as three different *roles* Copilot can play for you.

---

## 1. 🧠 Copilot **Agent Mode**
### What it is
- An **autonomous AI agent** in your IDE.
- Can perform **multi-step tasks** across multiple files.
- Acts like a **junior developer** who takes an assignment and executes it.

### Best For
- Large refactors or feature additions.
- Multi-file changes (Controller → Service → Repository in Java).
- Automating repetitive but structured work.

### Example Prompt
```java
// Prompt in Agent mode:
"Add JWT-based authentication to my Spring Boot app."
```

✅ Copilot will:
- Create configuration classes.
- Update security filters.
- Modify controllers to require authentication.
- Explain the changes step by step.

---

## 2. 💬 Copilot **Ask Mode**
### What it is
- A **chat-based Q&A** mode.
- Doesn’t edit code — instead, it **explains, teaches, and gives snippets**.
- Like having **Stack Overflow + Tech Lead** in your IDE.

### Best For
- Quick learning & concept clarifications.
- Debugging questions.
- Exploring API usage.

### Example Prompt
```text
"What’s the difference between HashMap and ConcurrentHashMap in Java?"
```

✅ Copilot will:
- Explain thread-safety concerns.
- Show side-by-side code examples.
- Suggest when to use each.

---

## 3. ✍️ Copilot **Edit Mode**
### What it is
- Works on a **selected file or block** of code.
- You highlight → Right-click → *Copilot: Edit with Prompt*.
- Copilot rewrites/refactors that section only.

### Best For
- Localized refactoring.
- Style improvements.
- Optimizing logic without changing the overall design.

### Example Prompt
```typescript
// In an Angular service, highlight this function and run Edit mode:
"Refactor this method to use async/await instead of Promises."
```

✅ Copilot will:
- Replace `then()` chains with `async/await`.
- Keep logic intact.
- Improve readability.

---

## 🆚 Quick Comparison

| Mode        | Purpose 🚀 | Scope 📂 | Example Prompt |
|-------------|------------|----------|----------------|
| **Agent**   | Multi-step autonomous coding | Multiple files/projects | *"Add JWT-based authentication to my Spring Boot app."* |
| **Ask**     | Chat-based Q&A | No code changes (info only) | *"Explain Angular lifecycle hooks."* |
| **Edit**    | Refactor/modify code | Selected file/block | *"Refactor this Angular service method with better error handling."* |

---

## 🎯 Easy Way to Remember

- **Agent** = Your *junior developer* (does the task).  
- **Ask** = Your *tech lead/mentor* (explains concepts).  
- **Edit** = Your *pair programmer* (helps refactor code).  

---

## 🛠️ Pro Tip for Testing
When generating unit tests with Copilot in **any mode**, always add comments like:

```java
// Arrange
// Act
// Assert
```

This guides Copilot to follow the **AAA testing pattern**, ensuring cleaner and more structured test cases.

---
