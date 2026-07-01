Create a complete Postman collection for testing the following API:

## API details

* API name: [API Name]
* Base URL: [Base URL]
* Endpoint: [Endpoint URL]
* HTTP method: [GET / POST / PUT / PATCH / DELETE]
* Authentication type: [No Auth / Bearer Token / Basic Auth / API Key]
* Request headers: [List required headers]
* Path parameters: [List path parameters]
* Query parameters: [List query parameters]
* Request body: [Provide request body structure or example]
* Expected response: [Provide expected response structure or example]

## Collection requirements

Create a Postman collection with clearly named folders and requests.

### 1. Positive test scenarios

Include requests for:

* A valid request with all required data
* A valid request with optional fields
* Valid boundary values, when applicable
* Verification that the response contains the expected data

### 2. Negative test scenarios

Include requests for:

* Missing authentication
* Invalid authentication token or API key
* Missing required headers
* Missing required fields
* Invalid field values
* Invalid data types
* Empty request body
* Invalid path parameters
* Invalid query parameters
* Resource not found
* Unsupported HTTP method, when applicable

### 3. Postman test scripts

Add automated tests to every request using the Postman `pm` API.

The tests should verify:

* HTTP status code
* Response time
* Response content type
* Required response headers
* Response body structure
* Required response fields
* Field data types
* Expected field values
* Error response structure
* Error message
* JSON Schema, when a response schema is available

Use clear test names, for example:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time is below 1000 ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(1000);
});

pm.test("Response is JSON", function () {
    pm.expect(pm.response.headers.get("Content-Type"))
        .to.include("application/json");
});
```

### 4. Variables

Use Postman variables instead of hardcoded values.

Create variables for:

* `base_url`
* `auth_token`
* Resource IDs
* User IDs
* Request data that is reused between requests

Save dynamically created IDs or tokens using Postman test scripts.

Example:

```javascript
const response = pm.response.json();
pm.collectionVariables.set("resource_id", response.id);
```

Use variables in requests:

```text
{{base_url}}/resources/{{resource_id}}
```

### 5. Collection structure

Organize the collection using folders such as:

```text
[API Name]
├── Authentication
├── Positive Tests
├── Negative Tests
├── Validation Tests
└── Cleanup
```

For CRUD APIs, organize requests in this order:

1. Create a resource
2. Get the created resource
3. Update the resource
4. Partially update the resource
5. Delete the resource
6. Verify that the resource was deleted

### 6. Documentation

For every request, provide:

* Request name
* Test purpose
* Preconditions
* Request parameters
* Request body
* Expected status code
* Expected result
* Postman test script

### 7. Output format

Provide:

1. The proposed Postman collection structure
2. A list of all requests
3. Configuration instructions for variables and authentication
4. Request bodies
5. Postman test scripts
6. Expected results
7. A complete Postman Collection JSON file that can be imported directly into Postman

All request names, folder names, variable names, test names, and code comments must be written in English.

Use beginner-friendly JavaScript in Postman test scripts. Avoid unnecessary abstractions and explain where each script should be added in Postman.

