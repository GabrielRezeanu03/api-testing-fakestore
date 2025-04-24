![API Tests](https://github.com/GabrielRezeanu03/api-testing-fakestore/actions/workflows/api-tests.yml/badge.svg)

# API Testing Project – Fake Store API

📄 **[View latest HTML test report](https://gabrielrezeanu03.github.io/api-testing-fakestore/)**

This project includes a full suite of **automated API tests** built in Postman and executed via **Newman + GitHub Actions** CI.

It covers functional testing for key modules like **products**, **authentication**, and **cart management**, using real requests against the public [Fake Store API](https://fakestoreapi.com/).

---

## ✅ What I Did

- ✅ Wrote **8 functional test cases** (positive & negative scenarios)
- ✅ Validated core endpoints with detailed **assertions** in Postman
- ✅ Used **environment variables** and **chained data** between requests
- ✅ Configured **Newman** for CLI-based execution
- ✅ Integrated test runs with **GitHub Actions CI**
- ✅ Documented all scenarios directly in this `README.md`

---

## 🎯 Why I Did This

I created this project to strengthen my skills in **API testing workflows**, with a focus on:

- Building **automated test collections**
- Writing **assertions** for both successful and failed cases
- Practicing **continuous integration (CI)** using GitHub Actions
- Demonstrating practical QA ability in a real-world testing context

---

## 📂 Project Structure

| Folder               | Description                                                      |
|----------------------|------------------------------------------------------------------|
| `collection/`        | Postman collection with all test cases (`.json` format)          |
| `environment/`       | Postman environment file with global variables                   |
| `.github/workflows/` | GitHub Actions config file to run Newman tests automatically     |
| `README.md`          | This document: full overview, coverage table, and context        |

---

## 🔗 API Under Test

All test cases target endpoints from the [Fake Store API](https://fakestoreapi.com/), a public mock e-commerce RESTful API.

---

## 🧪 Test Scenarios Overview

### ✅ Positive Scenarios

| Test ID  | Method | Endpoint           | Expected Status | Key Assertion                             |
|----------|--------|--------------------|-----------------|-------------------------------------------|
| FS_TC1   | GET    | `/products`        | 200             | Returns a non-empty array                 |
| FS_TC2   | GET    | `/products/1`      | 200             | Valid product: `id === 1`, price is number|
| FS_TC4   | POST   | `/auth/login`      | 200             | Response includes a non-empty `token`     |
| FS_TC5   | GET    | `/carts/user/2`    | 200             | Returns array of carts for user ID `2`    |
| FS_TC6   | POST   | `/carts`           | 200             | Response has numeric `id` (cart created)  |
| FS_TC7   | PUT    | `/carts/7`         | 200             | Updates `products` array successfully     |

### ❌ Negative Scenarios

| Test ID  | Method | Endpoint           | Expected Behavior                         |
|----------|--------|--------------------|-------------------------------------------|
| FS_TC3   | GET    | `/products/9999`   | 200 with empty body `{}`                  |
| FS_TC8   | DELETE | `/carts/7`         | Status `200` or `204`, or 404 if missing  |

---

## ⚙️ CI Integration

Tests are executed automatically using:

- **Newman** CLI for Postman collection execution  
- **GitHub Actions** on every `main` branch push or pull request

You can view test status live via the badge at the top or open the latest [HTML Report](https://gabrielrezeanu03.github.io/api-testing-fakestore/).

---

## ▶️ Running Tests Locally

1. Install Node.js from [https://nodejs.org](https://nodejs.org)
2. Install Newman globally:  
   `npm install -g newman`
3. Run the test suite:  
   `newman run "collection/FakeStore API Tests.postman_collection.json" -e "environment/FakeStore Env.postman_environment.json"`

---

## 🛠 Tools & Stack

- **Postman** – Designing API test collections and scripts  
- **Newman** – Command-line runner for executing Postman tests  
- **GitHub Actions** – Automating test execution on every push/PR  
- **JavaScript** – Assertions and response validation in Postman  
- **Fake Store API** – Public RESTful API used as testing target  

---
