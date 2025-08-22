# iMednet EDC API OpenAPI Specification

This repository contains the OpenAPI 3.1.0 specification for the iMednet Electronic Data Capture (EDC) REST API. This specification provides a detailed, machine-readable definition of the iMednet API, allowing developers to easily understand and interact with its resources.

## About iMednet and the EDC API

**iMednet** is a comprehensive platform for managing clinical trial data. The **Electronic Data Capture (EDC)** system is a core component of this platform, used for collecting, cleaning, and managing data from clinical studies.

The **Mednet EDC REST API** provides a programmatic, single-point of access for reading and writing data stored across iMednet data services. It is designed for integrating external applications, automating workflows, and building custom data analysis pipelines.

## How This Specification Works

This repository's primary artifact is the `mednet.yaml` file, which is an [OpenAPI Specification](https://swagger.io/specification/). This file allows you to:

*   **Explore the API:** Use tools like [Swagger UI](https://swagger.io/tools/swagger-ui/) or [ReDoc](https://github.com/Redocly/redoc) to generate interactive, human-readable documentation from the `mednet.yaml` file. This is a great way to visualize the available endpoints, their parameters, and their responses.
*   **Generate Client SDKs:** Use code generation tools like [OpenAPI Generator](https://openapi-generator.tech/) to automatically create client libraries for various programming languages (e.g., Python, Java, JavaScript, etc.). This significantly speeds up development time by providing pre-built methods for interacting with the API.
*   **Automate Testing:** The specification can be used to generate test cases and automate API testing, ensuring that integrations are robust and reliable.

### Authentication

The iMednet EDC API uses a combination of two API keys for authentication, which must be included in the headers of every request:

*   `x-api-key`: Your primary API key.
*   `x-imn-security-key`: Your security key (secret).

You must obtain these keys from iMednet to use the API.

Here is an example of how to make a request using `curl`:

```bash
curl -X GET https://edc.prod.imednetapi.com/api/v1/edc/studies/STUDYKEY/sites \
  -H 'x-api-key: YOUR_API_KEY' \
  -H 'x-imn-security-key: YOUR_SECURITY_KEY' \
  -H 'Content-Type: application/json'
```

### API Resources

The API is organized around several key resources in the iMednet EDC system. The available endpoints allow you to manage:

*   **Studies:** List all studies accessible by your API key.
*   **Sites:** List the clinical sites associated with a study.
*   **Subjects:** List and manage subjects enrolled in a study.
*   **Forms:** List form definitions.
*   **Records:** Create or update subject records (eCRFs).
*   **Visits:** List subject visit instances.
*   **Intervals:** List visit definitions.
*   **RecordRevisions:** Retrieve record revisions (audit trail entries).
*   **Queries:** List data queries.
*   **Users:** List users and their roles within a study.
*   **Variables:** List variables (fields) in a study.
*   **Codings:** List coding activities in a study.
*   **Jobs:** Retrieve the status of asynchronous jobs.

For a complete list of endpoints and their detailed descriptions, please refer to the `mednet.yaml` file or use a tool like Swagger UI to explore the API interactively.

### Filtering

The iMednet REST API allows you to filter results by providing optional filtering criteria in the `filter` query parameter.

**Operators**

The following operators are supported:

| Operator | Description        |
|----------|--------------------|
| `<`      | Less than          |
| `<=`     | Less than or equal |
| `>`      | Greater than       |
| `>=`     | Greater than or equal|
| `==`     | Equal              |
| `!=`     | Not equal          |

**Connectors**

You can combine multiple filter criteria using connectors:

| Connector | Description   |
|-----------|---------------|
| `;`       | AND condition |
| `,`       | OR condition  |

**Examples**

*   Return all forms with a Form ID greater than 10:
    `filter=formId>10`
*   Return all subject-related Forms:
    `filter=formType=="SUBJECT"`
*   Return all subject-related Forms with a Form ID greater than 10:
    `filter=formId>10;formType=="SUBJECT"`

**Filtering on Record Data**

To filter on the dynamic `recordData` attribute, use the `recordDataFilter` parameter. This parameter supports the same operators as `filter`, plus the `~=` (contains) operator.

### Versioning

There are two version numbers to be aware of:

1.  **API Version:** This specification documents version **1.3.6** of the iMednet EDC API's functionality.
2.  **Specification Version:** The OpenAPI specification document itself (`mednet.yaml`) is version **1.0.14**. This version will be incremented as the specification is updated to reflect new changes in the API.

## Postman Collection

This repository includes a [Postman collection](postman_collection.json) that you can import to start making requests to the API right away.

To import the collection into Postman:
1.  Click the "Import" button in Postman.
2.  Select the `postman_collection.json` file from this repository.
3.  The collection will be imported and you can start exploring the API endpoints.

## Linting

This repository includes a configuration for the [Spectral linter](https://github.com/stoplightio/spectral) to ensure the OpenAPI specification follows best practices.

To run the linter, you need to have Node.js and npm installed. Then, install Spectral:

```bash
npm install -g @stoplight/spectral-cli
```

Once installed, you can run the linter from the root of the repository:

```bash
spectral lint mednet.yaml
```

## Current Project State

This OpenAPI specification is up-to-date and reflects the functionality available in version 1.3.6 of the iMednet EDC API. It is considered stable and can be used for building production-ready integrations.

## Usage Example

To get started with a tool like Swagger UI, you can use a local HTTP server to serve the `mednet.yaml` file. For example, using Python:

```bash
python -m http.server 8000
```

You can then open Swagger UI (for example, using a [public Docker image](https://hub.docker.com/r/swaggerapi/swagger-ui/)) and point it to `http://localhost:8000/mednet.yaml` to view the interactive API documentation.
