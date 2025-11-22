# Find and Fix a Bug

## Introduction
This project contains a class called `ValidateISBN` which is used to validate ISBN numbers (the numbers that appear on the barcode on books).

The class was written using **Test Driven Development (TDD)** techniques, however there is a failing test and the developer cannot work out what is wrong.

---

## The Challenge
- Using GenAI tools, find out what is wrong with the code and fix it.  
- You should be able to explain **why the code wasn't working** and what differences the changes to the code make.  
- Be sure to check that **every change suggested by the GenAI tool is actually needed**.  
- In addition, review the code and identify any improvements that could be made.  
- Determine if the **descriptions of the exceptions** that could be thrown are accurate.  
- As you make any changes, use the tests to check that the code still works!  
- You might also ask the GenAI tools to suggest **additional tests** that could be added to the test suite.  

---

## 🧪 Running Tests from IntelliJ IDEA

You can run the test suite using **Maven** directly in IntelliJ IDEA. Follow these steps:

1. **Open the Maven Tool Window**  
   - In IntelliJ, go to the right-hand side panel.  
   - Look for the **Maven** tab (with an “M” icon).  
   - If you don’t see it, enable it from **View → Tool Windows → Maven**.

2. **Locate the Lifecycle Section**  
   - Inside the Maven window, expand your project.  
   - You will see **Lifecycle**, **Plugins**, and other sections.  
   - Expand **Lifecycle**.

3. **Execute `clean` and `test`**  
   - Double-click on **`clean`** → this removes any previously compiled files.  
   - Then double-click on **`test`** → this will run all test cases in the project.  

4. **Run Using Execute Maven Goal (Manual Entry)**  
   - Alternatively, right-click on your project in IntelliJ.  
   - Select **Run → Run… → Edit Configurations…**.  
   - Click **+** and choose **Maven**.  
   - In the **Command line** box, enter:
     ```bash
     clean test
     ```
   - Apply and Run the configuration.  

5. **Check Results**  
   - IntelliJ will open a **Run tab** showing which tests passed or failed.  
   - Green ✔ means success; Red ✘ means failure.  
   - Use the stack trace to debug if failures occur.

---

## ✅ Summary
- Always run **`mvn clean test`** before and after making changes.  
- Use IntelliJ’s Maven integration to execute goals easily.  
- This ensures your bug fixes and improvements do not break other parts of the system.  
