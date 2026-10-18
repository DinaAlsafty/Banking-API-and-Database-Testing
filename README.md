# Banking API and Database Testing

API and database testing project for a Banking API with a PostgreSQL database, covering accounts, balance, deposits, withdrawals, account blocking, statements, persons, idempotency, rate limiting, request tracing, health monitoring, and database validation.

## Project Overview

- **Application under test:** Banking API (`/api/v1`) running locally
- **Database:** PostgreSQL, validated with DBeaver
- **Test period:** 2026-10-10 to 2026-10-15
- **Tester:** Dina Ashraf Alsafty

## Scope

| Module | Test Cases |
|---|---|
| Account Management | 10 |
| Balance | 7 |
| Deposit | 11 |
| Withdrawal | 12 |
| Account Blocking | 4 |
| Account Statement | 10 |
| Persons | 5 |
| Idempotency | 3 |
| Rate Limiting | 6 |
| API / HTTP Validation | 5 |
| Request ID / Traceability | 2 |
| Health & System Monitoring | 4 |
| Database Validation | 12 |
| **Total** | **91** |

## Testing Types

API functional testing, positive and negative testing, input validation, idempotency testing, rate limit testing, and database validation (PostgreSQL, using DBeaver).

## Project Structure

```
Banking-API-and-Database-Testing/
├── 01-Test-Scenarios/        # Test scenarios per module
├── 02-Test-Cases/            # Detailed test cases (preconditions, steps, test data, expected results, priority)
├── 03-Test-Execution/        # Execution log (actual results, status, bug ID, date, notes)
├── 04-Test-Summary-Report/   # Test summary report
└── README.md
```

## Results

| Total | Passed | Failed | Blocked | Not Run | Pass Rate | Defects |
|---|---|---|---|---|---|---|
| 91 | 91 | 0 | 0 | 0 | 100% | 0 |

Test case priority: 73 High, 18 Medium.

### Highlights

- Missing or malformed input was rejected with `400 Bad Request` and the error code `VALIDATION_ERROR`.
- Repeating a request with the same `Idempotency-Key` returned the same transaction and did not apply it twice.
- The IP rate limit was enforced: the request over the limit returned `429 Too Many Requests` (`RATE_LIMITED`).
- Duplicate transactions were prevented at database level.
- The metrics endpoint exposed Prometheus-formatted metrics and the transaction counters updated.

## Author

**Dina Ashraf Alsafty** — Junior Software Tester | Manual QA | API Testing | ISTQB CTFL

- GitHub: https://github.com/DinaAlsafty
- LinkedIn: https://www.linkedin.com/in/dina-ashraf-alsafty-b2962918a/
- Email: dinaashrafalsafty@gmail.com
