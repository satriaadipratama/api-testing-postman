# API Test Cases

## Project Information

**Project:** API Testing Portfolio  
**Tool:** Postman  
**API:** DummyJSON REST API  
**Testing Type:** Functional API Testing

---

## Test Case Summary

| TC ID | Test Scenario | Method | Expected Result | Result |
|---|---|---|---|---|
| TC-API-001 | Get existing product | GET | Status 200 and product data is returned | PASS |
| TC-API-002 | Get non-existing product | GET | Status 404 and product not found message is returned | PASS |
| TC-API-003 | Create a new product | POST | Status 201 and product data is returned | PASS |
| TC-API-004 | Update product title | PATCH | Status 200 and updated product title is returned | PASS |
| TC-API-005 | Delete a product | DELETE | Status 200 and `isDeleted` is true | PASS |
| TC-API-006 | Login with valid credentials | POST | Status 200 and access token is generated | PASS |
| TC-API-007 | Access authenticated endpoint with valid token | GET | Status 200 and authenticated user data is returned | PASS |

---

# Detailed Test Cases

## TC-API-001 — Get Existing Product

**Method:** GET

**Endpoint:**

```text
GET /products/1
```

**Test Objective:**

Verify that the API can retrieve an existing product successfully.

**Expected Result:**

- HTTP status code is `200`
- Product ID is `1`
- Product data is returned

**Actual Result:**

- HTTP status code: `200`
- Product ID: `1`
- Product data was returned successfully

**Status:** PASS

---

## TC-API-002 — Get Non-Existing Product

**Method:** GET

**Endpoint:**

```text
GET /products/999999
```

**Test Objective:**

Verify that the API handles requests for a non-existing product correctly.

**Expected Result:**

- HTTP status code is `404`
- Response contains a product not found message

**Actual Result:**

- HTTP status code: `404`
- Product not found message was returned

**Status:** PASS

---

## TC-API-003 — Create a New Product

**Method:** POST

**Endpoint:**

```text
POST /products/add
```

**Test Objective:**

Verify that a new product can be submitted through the API.

**Request Body:**

```json
{
  "title": "QA Test Product",
  "price": 100000,
  "category": "test"
}
```

**Expected Result:**

- HTTP status code is `201`
- Product title matches the submitted data

**Actual Result:**

- HTTP status code: `201`
- Product title: `QA Test Product`

**Status:** PASS

---

## TC-API-004 — Update Product Title

**Method:** PATCH

**Endpoint:**

```text
PATCH /products/1
```

**Test Objective:**

Verify that an existing product can be updated successfully.

**Request Body:**

```json
{
  "title": "Updated QA Product"
}
```

**Expected Result:**

- HTTP status code is `200`
- Product title is updated correctly

**Actual Result:**

- HTTP status code: `200`
- Product title: `Updated QA Product`

**Status:** PASS

---

## TC-API-005 — Delete a Product

**Method:** DELETE

**Endpoint:**

```text
DELETE /products/1
```

**Test Objective:**

Verify that the API processes a product deletion request correctly.

**Expected Result:**

- HTTP status code is `200`
- `isDeleted` is `true`

**Actual Result:**

- HTTP status code: `200`
- `isDeleted`: `true`

**Status:** PASS

> **Note:** DummyJSON is a simulated REST API. The response indicates that the product was deleted, but this does not represent verification of permanent deletion from a real production database.

---

## TC-API-006 — Login with Valid Credentials

**Method:** POST

**Endpoint:**

```text
POST /auth/login
```

**Test Objective:**

Verify that valid credentials generate an authentication token.

**Expected Result:**

- HTTP status code is `200`
- Access token is generated
- Access token is not empty

**Actual Result:**

- HTTP status code: `200`
- Access token was generated successfully

**Status:** PASS

---

## TC-API-007 — Access Authenticated Endpoint with Valid Token

**Method:** GET

**Endpoint:**

```text
GET /auth/me
```

**Authorization:**

```text
Bearer {{accessToken}}
```

**Test Objective:**

Verify that an authenticated user can access a protected endpoint using a valid access token.

**Expected Result:**

- HTTP status code is `200`
- Authenticated user data is returned
- Username matches the expected user

**Actual Result:**

- HTTP status code: `200`
- Authenticated user data was returned
- Username: `emilys`

**Status:** PASS

---

# Test Execution Summary

| Metric | Result |
|---|---:|
| Total Test Cases | 7 |
| Total Automated Assertions | 14 |
| Passed | 14 |
| Failed | 0 |
| Errors | 0 |
| Overall Result | PASS |

---

# Testing Scope

This project covers the following API testing concepts:

- GET request testing
- POST request testing
- PATCH request testing
- DELETE request testing
- Positive testing
- Negative testing
- HTTP status code validation
- Response body validation
- JSON response validation
- Authentication testing
- Bearer Token authentication
- Postman environment variables
- Automated assertions
- Collection Runner
