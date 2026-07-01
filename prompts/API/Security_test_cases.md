Act as an experienced API Security QA Engineer.

Create manual security test cases for the provided API.

## API information

* API name: [API Name]
* Base URL: [Base URL]
* Environment: [Test / Staging]
* Documentation: [Swagger / OpenAPI / Postman Collection / Link]
* Authentication: [JWT / OAuth 2.0 / API Key / Basic Auth / Cookie]
* User roles: [Roles]
* Test accounts: [Accounts]
* Allowed scope: [Endpoints and Operations]
* Restricted actions: [Actions That Must Not Be Performed]

Test only the authorized environment. Do not perform DoS, destructive actions, uncontrolled load testing or external callbacks without explicit permission.

## Security coverage

Cover:

* Authentication and token validation
* Authorization, IDOR/BOLA and privilege escalation
* Access between users and roles
* Input validation and injection
* Mass assignment and unexpected fields
* Sensitive data exposure
* Business logic abuse
* Replay and duplicate requests
* Rate and resource limits
* Security headers and CORS
* Unsupported HTTP methods
* Error messages and stack traces
* Deprecated, undocumented and admin endpoints
* SSRF, webhooks and external URLs
* File upload, GraphQL and XML risks when applicable

## Test design requirements

Include:

* Positive and negative scenarios
* Anonymous-user tests
* Tests for every user role
* Tests with two users of the same role
* Resource owner and non-owner tests
* Horizontal and vertical privilege escalation
* Boundary and abuse scenarios
* Valid, invalid, missing, expired and malformed authentication
* Verification that rejected requests did not change data
* Verification that error responses do not expose sensitive information
* Manual tests requiring Postman, Burp Suite, OWASP ZAP or human analysis

Do not assume that a `401` or `403` response automatically means the API is secure. Verify that no protected action was completed, no data was changed and no sensitive information was returned.

## Test case format

For every test case provide:

* Test ID
* Title
* Security category
* Priority
* Endpoint and HTTP method
* User role
* Preconditions
* Test data or payload
* Test steps
* Expected secure result
* Expected status code
* Evidence to collect
* Suggested tool
* Severity if failed
* Related OWASP API Security category

Do not duplicate test cases. Adapt all scenarios to the actual endpoints, roles, data model and business logic. Clearly mark assumptions and missing information.

Return the result as a readable PDF file with:

1. Scope and assumptions
2. Role and access matrix
3. Prioritized security checklist
4. Manual security test cases
5. Coverage gaps

Use clear headings, numbered sections and readable tables. Use English for all test cases and report content.
