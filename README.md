![API Tests](https://github.com/GabrielRezeanu03/api-testing-fakestore/actions/workflows/api-tests.yml/badge.svg)
![Report Deploy](https://github.com/GabrielRezeanu03/api-testing-fakestore/actions/workflows/report-deploy.yml/badge.svg)

# 🧪 API Testing Project – Fake Store API

This project includes a complete **automated API testing flow** using Postman, Newman CLI, and GitHub Actions CI.  
It targets a public REST API and features **live HTML reporting via GitHub Pages**.

---

## 📊 Live Test Report

👉 [Click to view the latest HTML report](https://gabrielrezeanu03.github.io/api-testing-fakestore/)

> The report is automatically generated and deployed after each push to `main`.  
> If you see a 404, GitHub Pages may still be refreshing – try again in 1–2 minutes.

---

## ✅ Key Features

- 🧪 **8 functional test cases** (positive + negative)
- 🧾 Custom **assertions** for status codes, response content, and edge cases
- 🔄 **Environment variables** + chained requests
- ⚙️ **CI with GitHub Actions**
- 📊 **Auto-generated HTML report** via Newman
- 🌐 Hosted via **GitHub Pages**

---

## 🧠 Why I Built This

To strengthen my practical QA skills and demonstrate:

- Real-world API test automation using Postman + Newman
- CI integration with GitHub Actions
- Hands-on experience with public REST APIs
- HTML-based reporting + web publishing

---

## 🔗 API Under Test

All tests use endpoints from [Fake Store API](https://fakestoreapi.com/), a public mock RESTful service simulating an e-commerce backend.

---

## 📁 Project Structure

| Folder / File            | Description                                                  |
|--------------------------|--------------------------------------------------------------|
| `collection/`            | Postman collection (.json) with test cases                   |
| `environment/`           | Postman environment file with variables                      |
| `.github/workflows/`     | GitHub Actions CI workflows (`api-tests.yml`, `report-deploy.yml`) |
| `report/`                | Generated at runtime (ignored in `.gitignore`)               |
| `README.md`              | This documentation                                           |

---

## 🧪 Test Scenarios Overview

### ✅ Positive

| ID      | Method | Endpoint         | Check                                |
|---------|--------|------------------|--------------------------------------|
| FS_TC1  | GET    | `/products`      | Array is not empty                   |
| FS_TC2  | GET    | `/products/1`    | ID is `1`, price is a number         |
| FS_TC4  | POST   | `/auth/login`    | Response contains `token`            |
| FS_TC5  | GET    | `/carts/user/2`  | Valid carts returned                 |
| FS_TC6  | POST   | `/carts`         | New cart ID is created               |
| FS_TC7  | PUT    | `/carts/7`       | Cart update reflects in response     |

### ❌ Negative

| ID      | Method | Endpoint           | Check                                 |
|---------|--------|--------------------|---------------------------------------|
| FS_TC3  | GET    | `/products/9999`   | Returns `{}`                          |
| FS_TC8  | DELETE | `/carts/7`         | Accepts 200/204/404 if not found      |

---

## ⚙️ CI/CD Integration

All test cases run automatically on each push to `main`, with two workflows:

- `api-tests.yml`: Runs Newman CLI tests
- `report-deploy.yml`: Generates + publishes HTML report to GitHub Pages

---

## 🛠 Technologies Used

- **Postman** – test design
- **Newman** – command-line runner
- **GitHub Actions** – CI pipelines
- **GitHub Pages** – live report hosting
- **JavaScript** – scripting assertions
- **Markdown** – documentation

---

> ✅ This project is part of my QA portfolio. I use it to showcase end-to-end API testing, CI/CD, and real-time report delivery.
