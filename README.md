# API Testing – Fake Store API

This project includes a complete suite of API tests I created while practicing QA workflows using the [Fake Store API](https://fakestoreapi.com/).

It covers functional testing across core endpoints (products, authentication, and carts) using Postman collections, environment variables, and test automation with GitHub Actions.

---

## ✅ What I Did

- ✅ Created functional tests for product, authentication, and cart endpoints (positive & negative)
- ✅ Designed structured test cases with clear assertions
- ✅ Used dynamic environment variables and chaining between requests
- ✅ Automated test execution using Newman and GitHub Actions CI
- ✅ Documented all scenarios and assertions directly in this README

---

## 🎯 Why I Did This

I built this project to deepen my practical understanding of API testing in QA, beyond theoretical knowledge.

It helped me practice:
- Writing request/response assertions
- Building data-driven tests
- Integrating Postman with CI pipelines

---

## 🔗 API Reference

All tests are based on the public [Fake Store API](https://fakestoreapi.com/), a mock RESTful e-commerce API.

---

## 📂 Project Structure

| Folder             | Description                                          |
|--------------------|------------------------------------------------------|
| `collection/`      | Postman collection (`.json`) with all 8 test cases   |
| `environment/`     | Postman environment file (`.json`) with variables    |
| `.github/workflows/` | GitHub Actions workflow that runs tests automatically |
| `README.md`        | Test summary, scenario descriptions, and coverage    |

---

## 🧪 Test Scenarios Overview

### ✅ Positive Tests

| Test ID | Method | Endpoint        | Expected Status | Key Assertion                        |
|---------|--------|-----------------|-----------------|--------------------------------------|
| FS_TC1  | GET    | `/products`     | 200             | Returns a non-empty array            |
| FS_TC2  | GET    | `/products/1`   | 200             | `id === 1`; `price` is a number      |
| FS_TC4  | POST   | `/auth/login`   | 200             | Response contains a non-empty `token`|
| FS_TC5  | GET    | `/carts/user/2` | 200             | Returns array of carts for user `2`  |
| FS_TC6  | POST   | `/carts`        | 200             | Response has numeric `id` (cart created) |
| FS_TC7  | PUT    | `/carts/7`      | 200             | Updates `products` array correctly   |

### ❌ Negative Tests

| Test ID | Method | Endpoint            | Expected Behavior                    |
|---------|--------|---------------------|--------------------------------------|
| FS_TC3  | GET    | `/products/9999`    | 200 with empty body (`{}`)           |
| FS_TC8  | DELETE | `/carts/{cartId}`   | 200 \| 204 or 404 if cart doesn't exist |

---
