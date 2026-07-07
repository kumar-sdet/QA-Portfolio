
# Bug Report 01

## Defect Summary
Application allows login attempt using SQL Injection payload.

| Field | Value |
|-------|-------|
| Module | Login |
| Severity | Critical |
| Priority | High |
| Environment | QA |
| Status | Open |

## Description
The application accepts SQL Injection payloads in the username field without proper validation.

## Steps to Reproduce

1. Open the Login page.
2. Enter the username:
   ```
   ' OR 1=1 --
   ```
3. Enter any password.
4. Click **Login**.

## Actual Result

The application accepts the malicious input instead of validating it securely.

## Expected Result

The application should reject SQL Injection payloads, validate user input, and display an appropriate error message.

## Impact

This vulnerability could allow unauthorized access if backend validation is not implemented correctly.

## Recommendation

Use parameterized queries (prepared statements) and validate/sanitize user input.
