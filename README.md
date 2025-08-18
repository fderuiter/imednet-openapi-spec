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

### API Endpoints Overview

The API is organized around several key resources in the iMednet EDC system. The available endpoints allow you to manage:

*   **Studies:** List all studies accessible by your API key.
*   **Sites:** List the clinical sites associated with a study.
*   **Subjects:** List and manage subjects enrolled in a study.
*   **Forms & Records:** List form definitions and create or update subject records (eCRFs).
*   **Visits & Intervals:** List visit definitions and subject visit instances.
*   **Audit Trails:** Retrieve record revisions (audit trail entries).
*   **Queries:** List data queries.
*   **Users & Roles:** List users and their roles within a study.
*   **And more...**

For a complete list of endpoints and their detailed descriptions, please refer to the `mednet.yaml` file.

### Authentication

The iMednet EDC API uses a combination of two API keys for authentication, which must be included in the headers of every request:

*   `x-api-key`: Your primary API key.
*   `x-imn-security-key`: Your security key (secret).

You must obtain these keys from iMednet to use the API.

### Versioning

There are two version numbers to be aware of:

1.  **API Version:** This specification documents version **1.3.6** of the iMednet EDC API's functionality.
2.  **Specification Version:** The OpenAPI specification document itself (`mednet.yaml`) is version **1.0.14**. This version will be incremented as the specification is updated to reflect new changes in the API.

## Current Project State

This OpenAPI specification is up-to-date and reflects the functionality available in version 1.3.6 of the iMednet EDC API. It is considered stable and can be used for building production-ready integrations.

## Usage Example

To get started with a tool like Swagger UI, you can use a local HTTP server to serve the `mednet.yaml` file. For example, using Python:

```bash
python -m http.server 8000
```

You can then open Swagger UI (for example, using a [public Docker image](https://hub.docker.com/r/swaggerapi/swagger-ui/)) and point it to `http://localhost:8000/mednet.yaml` to view the interactive API documentation.
