# 🧑‍💻 GitHub Copilot Chat Cheat Sheet

A quick reference guide for **Chat Commands (/)**, **Extensions (@)**, and **Context (#)** to supercharge your workflow.

---

## ⚡ Chat Commands (/)

| Command      | Purpose                                           | Example Usage |
|--------------|---------------------------------------------------|---------------|
| `/explain`   | Explains how the selected code works              | `/explain` on a factorial function |
| `/feedback`  | Give feedback about Copilot’s suggestions         | `/feedback` |
| `/fix`       | Fixes problems and compile-time errors            | `/fix` on code with missing semicolon |
| `/help`      | Shows guidance and command references             | `/help` |
| `/tests`     | Generates unit tests for selected code            | `/tests` on `Calculator` class |
| `/doc`       | Generates inline docs/docstrings                  | `/doc` on `UserService` |
| `/simplify`  | Refactors code for readability and maintainability| `/simplify` on nested loops |

---

## 🧩 Extensions (@)

| Extension     | Purpose                                | Example Usage |
|---------------|----------------------------------------|---------------|
| `@terminal`   | Run shell/CLI commands                 | `@terminal run mvn clean test` |
| `@vscode` / `@jetbrains` | Ask about IDE actions, errors, navigation | `@jetbrains what does this error mean?` |
| `@github`     | Fetch issues, PRs, or repo details     | `@github list open PRs` |
| `@browser`    | Search or fetch external info          | `@browser search latest Java LTS version` |

---

## 🔗 Context (#)

| Context       | Purpose                                          | Example Usage |
|---------------|--------------------------------------------------|---------------|
| `#filename`   | Reference a file in your project                 | `/fix #ValidateISBN.java` |
| `#symbol`     | Reference a class, method, or variable           | `/explain #calculateChecksum` |
| `#error`      | Point Copilot to a compiler/test error           | `/fix #error` |
| `#selection`  | Use currently highlighted code as context        | `/doc #selection` |

---

## ✅ Best Practices
- Use `/explain` and `/doc` for **learning and onboarding**.  
- Apply `/fix` and `/simplify` during **debugging and refactoring**.  
- Run `/tests` to ensure **coverage and reliability**.  
- Use `@terminal` and `@github` to **bridge IDE with external tools**.  
- Add `#filename` or `#error` to ensure Copilot looks at the **right context**.  

---
