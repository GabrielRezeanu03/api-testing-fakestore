![API Tests](https://github.com/GabrielRezeanu03/api-testing-fakestore/actions/workflows/api-tests.yml/badge.svg)

# 🧪 API Testing Project – Fake Store API

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
- Showcasing practical QA abilities in a real-world context

---

## 📂 Project Structure

| Folder               | Description                                                  |
| -------------------- | ------------------------------------------------------------ |
| `collection/`        | Postman collection with all test cases (`.json` format)      |
| `environment/`       | Postman environment file with global variables               |
| `.github/workflows/` | GitHub Actions config file to run Newman tests automatically |
| `README.md`          | This document: full overview, coverage table, and context    |

---

## 🔗 API Under Test

All test cases target endpoints from the [Fake Store API](https://fakestoreapi.com/), a public mock e-commerce RESTful API.

---

## 🧪 Test Scenarios Overview

### ✅ Positive Scenarios

| Test ID | Method | Endpoint        | Expected Status | Key Assertion                              |
| ------- | ------ | --------------- | --------------- | ------------------------------------------ |
| FS_TC1  | GET    | `/products`     | 200             | Returns a non-empty array                  |
| FS_TC2  | GET    | `/products/1`   | 200             | Valid product: `id === 1`, price is number |
| FS_TC4  | POST   | `/auth/login`   | 200             | Response includes a non-empty `token`      |
| FS_TC5  | GET    | `/carts/user/2` | 200             | Returns array of carts for user ID `2`     |
| FS_TC6  | POST   | `/carts`        | 200             | Response has numeric `id` (cart created)   |
| FS_TC7  | PUT    | `/carts/7`      | 200             | Updates `products` array successfully      |

### ❌ Negative Scenarios

| Test ID | Method | Endpoint         | Expected Behavior                        |
| ------- | ------ | ---------------- | ---------------------------------------- |
| FS_TC3  | GET    | `/products/9999` | 200 with empty body `{}`                 |
| FS_TC8  | DELETE | `/carts/7`       | Status `200` or `204`, or 404 if missing |

---

## ⚙️ CI Integration

Tests are executed automatically using:

- **Newman** CLI for Postman collection execution
- **GitHub Actions** on each commit to `main`

You can view test status live via the badge at the top of this README.

---

## 🛠 Tools & Stack

- **Postman** (collection design, testing)
- **Newman** (CLI runner for test automation)
- **GitHub Actions** (continuous integration)
- **JavaScript** (test scripts)
- **Fake Store API** (test target)

---

> ✅ This project is ideal for demonstrating real-world API testing skills as part of a QA portfolio.
