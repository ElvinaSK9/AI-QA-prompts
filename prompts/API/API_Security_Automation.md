Act as an experienced API Security Automation QA Engineer.

Create automated security tests for the provided API.

## API information

* API name: [API Name]
* Base URL: [Base URL]
* Environment: [Test / Staging]
* Documentation: [Swagger / OpenAPI / Postman Collection / Link]
* Authentication: [JWT / OAuth 2.0 / API Key / Basic Auth / Cookie]
* User roles: [Roles]
* Test accounts: [Accounts]
* Request timeout: [Seconds]
* Allowed scope: [Endpoints and Operations]
* Restricted actions: [Actions That Must Not Be Performed]

Use:

* Python
* `pytest`
* `requests`
* `pytest-html`
* `jsonschema`, when schemas are available

## Security coverage

Automate safe checks for:

* Missing, invalid, malformed, expired and revoked authentication
* Token validation and token reuse
* Access with different users and roles
* IDOR/BOLA and access to another user’s resources
* Horizontal and vertical privilege escalation
* Broken function-level authorization
* Unexpected JSON fields and mass assignment
* Missing required fields
* Invalid values, types, formats and boundary values
* Injection payloads that are safe for the authorized environment
* Unsupported HTTP methods
* Missing or invalid headers and content types
* Sensitive data in responses, headers and errors
* Stack traces and internal implementation details
* Security headers and CORS
* Replay and duplicate requests
* Idempotency
* Business workflow manipulation
* Rate-limit checks using a small, safe request count
* Pagination and resource-limit validation
* Deprecated or undocumented endpoints, when known

Do not automate destructive attacks, DoS, uncontrolled load testing, external callbacks or dangerous payloads.

## Test requirements

* All tests must be completely independent.
* Tests must not depend on execution order or shared state.
* Every test must create its own test data and clean it up after execution.
* Every test must be runnable separately.
* Use `yield` fixtures for cleanup where appropriate.
* Use separate accounts for owner, non-owner and different roles.
* Verify that unauthorized requests did not change data.
* Use simple and easy-to-understand code as qa engineer 
* Avoid complex abstractions and advanced design patterns.
* Store reusable requests in a small `ApiClient` class.
* Store configuration in environment variables.
* Redact passwords, tokens, cookies, API keys and personal data from reports.
* Write file names, test names, comments and code in English.

## Reporting

Create a new HTML report for every run:

```text
reports/security_report_YYYYMMDD_HHMMSS.html
```

For every test include:

* Test result
* Request method and URL
* Sanitized request headers
* Request body
* Response status code
* Response time
* Sanitized response headers
* Response body
* Assertion failure details

## Output

Provide:

1. Proposed test coverage
2. Complete project structure
3. Complete code for every file
4. `requirements.txt`
5. `.env.example`
6. Installation instructions
7. Command to run all tests
8. Command to run one test
9. Automatic cleanup
10. Automatic HTML report generation
11. Known limitations and security checks that require manual testing
12. Ready-to-use ZIP project

Do not invent undocumented API behavior. Clearly mark assumptions and known API defects.
