# 🧠 How to Install & Use GitHub Copilot in IntelliJ IDEA

GitHub Copilot can be integrated into IntelliJ-based IDEs using the **official GitHub Copilot plugin**. It enables you to receive AI-powered code suggestions inside your JetBrains IDE.

---

## ✅ Prerequisites

- ✅ **IntelliJ IDEA 2022.3 or later** (Community or Ultimate)
- ✅ A valid **GitHub account**
- ✅ A **GitHub Copilot subscription** (or free student/open-source plan)
- ✅ Internet connectivity

---

## 🚀 Step-by-Step Integration Guide

### 🔹 Step 1: Open IntelliJ and Go to Plugin Marketplace

1. Open IntelliJ IDEA.
2. Go to **Settings / Preferences**:
   - On Windows/Linux: `File > Settings`
   - On macOS: `IntelliJ IDEA > Preferences`
3. Navigate to **Plugins**.
4. Click on the **Marketplace** tab.

---

### 🔹 Step 2: Search and Install GitHub Copilot Plugin

1. In the search bar, type:
   ```
   GitHub Copilot
   ```
2. Find the **official plugin by GitHub**.
3. Click **Install**.
4. Restart IntelliJ IDEA when prompted.

---

### 🔹 Step 3: Sign In to GitHub

1. After restart, go to:
   - `File > Settings > Tools > GitHub Copilot` (Windows/Linux)
   - `IntelliJ IDEA > Preferences > Tools > GitHub Copilot` (macOS)

2. Click **"Sign in to GitHub"**.

3. A browser window will open.
4. **Authorize IntelliJ to access your GitHub Copilot** account.

✅ You will see a success message once login is complete.

---

### 🔹 Step 4: Enable GitHub Copilot Globally

1. In the same **GitHub Copilot settings page**, ensure:
   - ✅ Enable GitHub Copilot
   - ✅ Enable for all languages (optional)
   - ✅ Enable inline suggestions (recommended)

---

### 🔹 Step 5: Start Coding with Copilot!

1. Open any code file (e.g., `.java`, `.py`, `.js`).
2. Start typing a comment or a function name.
   - Example:
     ```java
     // Function to reverse a string
     ```
3. Copilot will automatically show a **gray suggestion inline**.
4. Press `Tab` to accept the suggestion.

---

## 🧪 Testing Copilot

Try writing:

```python
# Function to check if a number is prime
```

You should see Copilot suggest the entire function.

---

## ⚙️ Optional Settings

- **Control Suggestion Behavior**:
  - Delay before suggestions
  - Use Tab / Enter to accept
  - Show multiple suggestions

Go to:  
`Settings > Tools > GitHub Copilot`

---

## 🛠 Troubleshooting

| Issue                                | Fix                                                                 |
|-------------------------------------|----------------------------------------------------------------------|
| Plugin not found                    | Ensure you're using IntelliJ 2022.3+                                 |
| Not getting suggestions             | Sign in again, check subscription, restart IDE                      |
| Suggestions are irrelevant          | Write better intent (comments, clear method names)                  |
| High CPU usage                      | Disable Copilot for large files                                     |

---

## 📎 Useful Links

- 🌐 [GitHub Copilot Plugin (JetBrains Marketplace)](https://plugins.jetbrains.com/plugin/17718-github-copilot)
- 📘 [GitHub Copilot Docs](https://docs.github.com/en/copilot)
- 🎓 [Student Developer Pack (Free Copilot)](https://education.github.com/pack)