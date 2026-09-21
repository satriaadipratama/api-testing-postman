# API Test Results

## Test Execution

**Project:** API Testing Portfolio  
**Tool:** Postman  
**Test Execution Method:** Postman Collection Runner  

---

## Execution Summary

| Metric | Result |
|---|---:|
| Total Requests | 7 |
| Total Automated Tests | 14 |
| Passed | 14 |
| Failed | 0 |
| Errors | 0 |
| Overall Result | PASS |

---

## Test Execution Result

The API test collection was executed using Postman Collection Runner.

All automated assertions passed successfully.

### Result

**14 / 14 tests passed**

```text
Passed: 14
Failed: 0
Errors: 0
```

---

## Tested API Scenarios

| # | Scenario | Method | Result |
|---|---|---|---|
| 1 | Get existing product | GET | PASS |
| 2 | Get non-existing product | GET | PASS |
| 3 | Create a new product | POST | PASS |
| 4 | Update product title | PATCH | PASS |
| 5 | Delete a product | DELETE | PASS |
| 6 | Login with valid credentials | POST | PASS |
| 7 | Access authenticated endpoint with valid token | GET | PASS |

---

## Validation Performed

The automated tests validated:

- HTTP status codes
- Response body values
- Product ID
- Product title
- Product deletion status
- Access token generation
- Authenticated user data
- Username validation

---

## Negative Testing

A non-existing product request was tested to verify proper error handling.

**Expected:**

- HTTP status code `404`
- Product not found message

**Result:** PASS

Invalid authentication token handling was also tested separately during the learning process.

**Expected:**

- HTTP status code `401`
- Invalid or expired token message

**Result:** PASS

---

## Conclusion

The API test collection completed successfully with:

**14/14 automated tests passed**

No failed tests or execution errors were reported during the final collection run.

The test results demonstrate successful validation of functional API behavior, error handling, and authentication using Postman.
