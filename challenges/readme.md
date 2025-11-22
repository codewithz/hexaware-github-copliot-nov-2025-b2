# Challenge Project Setup Guide 🚀

Welcome! This guide explains how to correctly set up and open the challenge project on your local machine.  
Please follow the steps carefully so the project loads properly in **IntelliJ IDEA**.

---

## 📂 What You See on GitHub

When you open the challenge folder on GitHub, you’ll notice two items:

### 1. `1-challenge-no-read-me/` (Open Folder)
- Lets you browse the project structure on GitHub.  
- Good for **previewing files online**.  
- ⚠️ **Not usable** for running the project in your IDE.  

### 2. `1-challenge-no-read-me.zip` (Zip File)
- A **downloadable archive** of the project.  
- This is the one you need to **download, extract, and open in IntelliJ**.  

---

## 💻 Step-by-Step: Opening in IntelliJ IDEA

### 1. Download the Zip
- Click on **`1-challenge-no-read-me.zip`**.  
- Save it in your **Downloads** folder or **Desktop**.  

### 2. Extract the Zip
- Right-click → **Extract All…**  
- A folder `1-challenge-no-read-me` will appear with the project files inside.  

### 3. Identify the Maven Project
- Look for the folder containing the **`pom.xml`** file.  
- IntelliJ marks this folder with a **black square icon with a small white line at the bottom**.  
- This is the **Maven root project folder** — always open this folder in IntelliJ.    

### 4. Open Project in IntelliJ
- Open **IntelliJ IDEA**.  
- Go to **File → Open…**  
- Select the **Maven root folder** (with `pom.xml`).  
- IntelliJ will detect it as a Maven project and load dependencies automatically.  

### 5. Wait for Maven Import
- IntelliJ will download and configure Maven dependencies.  
- Once complete, the **project tree** will be visible and ready to run.  

---

## ✅ Common Mistakes to Avoid
- ❌ Don’t open the GitHub folder directly.  
- ❌ Don’t open only `src/`. Always open the root folder with `pom.xml`.  
- ❌ Don’t forget to extract the zip before importing.  

---

## 🎯 Summary
- Use the **zip file** for downloading and running the project.  
- Use the **folder view** only for browsing on GitHub.  
- Always open the folder with **`pom.xml`** (black square icon with white line) in IntelliJ.  

👉 Follow these steps and your project will load smoothly! 🚀
