# API Testing Portfolio — Postman

API testing portfolio project using Postman to validate REST API functionality, error handling, and authentication.

## Project Overview

This project demonstrates API testing using the DummyJSON REST API.

The testing focuses on validating HTTP status codes, response data, CRUD operations, negative scenarios, and authentication using automated Postman assertions.

## Tools & Technologies

- Postman
- JavaScript
- REST API
- JSON
- DummyJSON API
- GitHub

## Testing Scope

The following API scenarios were tested:

| Test Case | Method | Scenario | Result |
|---|---|---|---|
| TC-API-001 | GET | Get existing product | PASS |
| TC-API-002 | GET | Get non-existing product | PASS |
| TC-API-003 | POST | Create a new product | PASS |
| TC-API-004 | PATCH | Update product title | PASS |
| TC-API-005 | DELETE | Delete a product | PASS |
| TC-API-006 | POST | Login with valid credentials | PASS |
| TC-API-007 | GET | Access authenticated endpoint with valid token | PASS |

## Testing Concepts

This project covers:

- Functional API testing
- Positive testing
- Negative testing
- CRUD API testing
- HTTP status code validation
- Response body validation
- JSON response validation
- Authentication testing
- Bearer Token authentication
- Postman environment variables
- Automated assertions
- Collection Runner

## Authentication Flow

The authentication scenario uses the following flow:

```text
Login API
    ↓
Access Token Generated
    ↓
Token Stored in Environment Variable
    ↓
Bearer Token Added to Request
    ↓
Authenticated Endpoint
    ↓
User Data Returned
```

The access token is stored using the Postman environment variable:

```text
{{accessToken}}
```

This avoids hardcoding the token directly into the authenticated request.

## Automated Test Assertions

Postman automated assertions were used to validate:

- HTTP status codes
- Product ID
- Product title
- Product deletion status
- Access token generation
- Authenticated user data
- Username

Example:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

## Negative Testing

Negative testing was performed using a non-existing product endpoint:

```text
GET /products/999999
```

Expected behavior:

- HTTP status code: `404`
- Product not found message is returned

Invalid authentication token handling was also tested separately.

Expected behavior:

- HTTP status code: `401`
- `Invalid/Expired Token!` message is returned

## Test Execution Result

The complete Postman collection was executed using Postman Collection Runner.

| Metric | Result |
|---|---:|
| Total Requests | 7 |
| Total Automated Tests | 14 |
| Passed | 14 |
| Failed | 0 |
| Errors | 0 |
| Overall Result | PASS |

**14 / 14 automated tests passed.**

## Project Structure

```text
api-testing-postman/
│
├── test-cases/
│   └── api-test-cases.md
│
├── test-results/
│   └── test-results.md
│
└── README.md
```

## API

This project uses the DummyJSON REST API:

https://dummyjson.com/

DummyJSON provides simulated REST API endpoints for testing and learning purposes.

## Notes

DummyJSON simulates backend behavior. Therefore, some operations such as product creation, update, and deletion do not represent permanent changes to a production database.

This project is intended as a learning and portfolio project to demonstrate API testing fundamentals using Postman.
