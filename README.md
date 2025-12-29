# 📚 Book API Automation with Newman

This repository contains a **fully automated API testing framework** for the **Simple Books API**, built using **Postman** and executed via **Newman CLI** with a **professional HTML report**.

---

## 🚀 What This Project Does

- ✅ Tests all major Book API endpoints end-to-end
- 🔁 Uses **random & dynamic data** (bookId, orderId) to avoid hard-coding
- 🧠 Passes data between requests automatically using Postman scripts
- ⚙️ Runs completely from the **command line** using Newman
- 📊 Generates a **fancy HTML report** after execution
- 🔄 Deletes the previous report before generating a new one

This makes the project **CI/CD ready** and reusable for repeated test runs.

---

## 🧪 APIs Covered

- Home Page
- API Status
- List of Books (with filters)
- Get Single Book (random selection)
- Create Book Order
- Update Book Order
- Get All Orders
- Get Single Order
- Delete Order

All requests include **assertions** for status codes and validations.

---

## 🛠 Tools & Technologies Used

- **Postman** – API design, test scripts, environments
- **Newman** – Command-line runner for Postman collections
- **Node.js & npm** – Dependency management
- **newman-reporter-htmlextra** – Advanced HTML reporting
- **Git & GitHub** – Version control

---

## 📁 Project Structure

```
BookApi/
│── Book api.postman_collection.json
│── New Environment.postman_environment.json
│── fancy-report.html   (generated after run)
│── README.md
```

---

## ⚙️ Prerequisites

Make sure the following are installed:

- **Node.js** (v16+ recommended)
- **npm** (comes with Node.js)
- **Newman**

Install Newman globally:

```bash
npm install -g newman
```

Install the HTML reporter:

```bash
npm install -g newman-reporter-htmlextra
```

---

## ▶️ How to Run the Tests (Important)

⚠️ **Before running, delete the previous report** so a fresh report is generated.

### Step 1: Delete old report (if exists)

**PowerShell (Windows):**
```powershell
Remove-Item fancy-report.html -ErrorAction SilentlyContinue
```

---

### Step 2: Run Newman with fancy HTML report

```powershell
newman run "Book api.postman_collection.json" `
-e "New Environment.postman_environment.json" `
-r "cli,htmlextra" `
--reporter-htmlextra-export "fancy-report.html" `
--reporter-htmlextra-title "Book API Automation Report" `
--reporter-htmlextra-darkTheme true
```

---

## 📊 View the Report

After execution:

- Open **fancy-report.html** in any browser
- View charts, request details, assertions, and execution summary

---

## 🤖 Automation Highlights

- 🎯 **Random data selection** (no hard-coded IDs)
- 🔁 **Data-driven execution** using environment & script variables
- 🧠 Automatic chaining of requests (create → update → get → delete)
- 🚫 Zero manual intervention required

---

## 📌 Future Enhancements

- GitHub Actions CI pipeline
- Auto-publish report to GitHub Pages
- Allure reporting integration
- Environment-based execution (QA / Staging)

---

## 👤 Author

**Showrav**  
QA Automation Engineer  
GitHub: https://github.com/Showrav88

---

⭐ If you find this project useful, feel free to star the repository!