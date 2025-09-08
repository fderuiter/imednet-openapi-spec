# Contributing to the iMednet EDC API OpenAPI Specification

We welcome contributions to improve the iMednet EDC API OpenAPI Specification. Please follow these guidelines to ensure a smooth and effective contribution process.

## Development Workflow

1.  **Fork the repository:** Create your own fork of the repository to your GitHub account.
2.  **Clone your fork:**
    ```bash
    git clone https://github.com/YOUR_USERNAME/imednet-openapi-spec.git
    cd imednet-openapi-spec
    ```
3.  **Create a new branch:**
    ```bash
    git checkout -b your-feature-branch
    ```
4.  **Make your changes:** Make your desired changes to the API specification or other files.
5.  **Validate your changes:** Before committing, make sure to validate the API specification and format the code:
    ```bash
    npm test
    ```
6.  **Commit your changes:**
    ```bash
    git commit -m "feat: your descriptive commit message"
    ```
7.  **Push to your fork:**
    ```bash
    git push origin your-feature-branch
    ```
8.  **Create a pull request:** Open a pull request from your fork to the main repository.

## Code Style Guidelines

- **OpenAPI Specification:** We use [Spectral](https://github.com/stoplightio/spectral) to enforce a consistent style for the OpenAPI specification.
- **Other Files:** We use [Prettier](https://prettier.io/) to format all other files.

Please make sure your changes pass the linter and the formatter.

## Pull Request Process

1.  Ensure that your pull request includes a clear and descriptive title and description.
2.  The pull request will be reviewed by the maintainers.
3.  Once the pull request is approved, it will be merged into the main branch.

Thank you for your contributions!
