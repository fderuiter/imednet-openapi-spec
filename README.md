# iMednet EDC API OpenAPI Specification

This repository contains the OpenAPI 3.1.0 specification for the iMednet Electronic Data Capture (EDC) REST API. This specification provides a detailed, machine-readable definition of the iMednet API, allowing developers to easily understand and interact with its resources.

## Key Features

- **Comprehensive API Definition:** A detailed and machine-readable OpenAPI 3.1.0 specification.
- **Interactive Documentation:** Explore the API with tools like Swagger UI or ReDoc.
- **Client SDK Generation:** Automatically generate client libraries for various programming languages.
- **Automated Testing:** Use the specification to generate test cases and automate API testing.

## Technology Stack

- **OpenAPI 3.1.0:** The specification language for defining the API.
- **Spectral:** A linter to ensure the OpenAPI specification follows best practices.
- **Prettier:** A code formatter to ensure consistent formatting.
- **Node.js:** Used for running the linter, formatter, and other development scripts.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or later)
- [npm](https://www.npmjs.com/)

### Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/fderuiter/imednet-openapi-spec.git
    cd imednet-openapi-spec
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

### Usage

#### Validate the API Specification

To validate the API specification, run the following command:

```bash
npm run lint
```

This will run the Spectral linter to check the `src/mednet.yaml` file for any errors or warnings.

#### Format the Code

To format the code, run the following command:

```bash
npm run format
```

This will run Prettier to format all the files in the repository.

#### Explore the API with Swagger UI

To explore the API with Swagger UI, you can use a local HTTP server to serve the `src/mednet.yaml` file.

1.  **Start a local HTTP server:**

    ```bash
    python -m http.server 8000
    ```

2.  **Open Swagger UI:**
    Open your web browser and navigate to a public Swagger UI instance (e.g., [https://petstore.swagger.io/](https://petstore.swagger.io/)).

3.  **Load the API specification:**
    In the "Explore" bar, enter the URL to your local `mednet.yaml` file: `http://localhost:8000/src/mednet.yaml`.

## Contributing

We welcome contributions to improve the iMednet EDC API OpenAPI Specification. Please see our [CONTRIBUTING.md](CONTRIBUTING.md) file for detailed guidelines on how to contribute.

## License

This project is licensed under the ISC License. See the [LICENSE](LICENSE) file for details.
