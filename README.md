# Running Multiple Swagger UI Containers

This guide explains how to run multiple Swagger UI instances in Docker containers, each serving a different OpenAPI specification file. We use different ports for each Swagger UI instance to allow simultaneous access.

## Prerequisites

- Docker must be installed on your machine.
- Download the required OpenAPI JSON files from [Thought Machine Vault Core API Documentation](https://docs.thoughtmachine.net/vault-core/4-6/EN/api/).
- Place the downloaded JSON files in `C:\Users\fathullahharun\Downloads\tm_api_v2`.

## Setup Instructions

1. **Open a Command Line Interface:**
   - You can use Command Prompt, PowerShell, or any other command line tool.
   - Navigate to the directory where you've placed the JSON files:
     ```
     cd C:\Users\fathullahharun\Downloads\tm_api_v2
     ```

2. **Run Docker Commands:**
   - Execute the following Docker commands to run Swagger UI containers for each API:

     ```bash
     docker run -p 80:8080 -e SWAGGER_JSON=/tmp/core_api.json -v C:\Users\fathullahharun\Downloads\tm_api_v2:/tmp swaggerapi/swagger-ui
     docker run -p 81:8080 -e SWAGGER_JSON=/tmp/audit_api.json -v C:\Users\fathullahharun\Downloads\tm_api_v2:/tmp swaggerapi/swagger-ui
     docker run -p 82:8080 -e SWAGGER_JSON=/tmp/access_control_api.json -v C:\Users\fathullahharun\Downloads\tm_api_v2:/tmp swaggerapi/swagger-ui
     docker run -p 83:8080 -e SWAGGER_JSON=/tmp/data_loader_api.json -v C:\Users\fathullahharun\Downloads\tm_api_v2:/tmp swaggerapi/swagger-ui
     docker run -p 84:8080 -e SWAGGER_JSON=/tmp/payment_hub_api.json -v C:\Users\fathullahharun\Downloads\tm_api_v2:/tmp swaggerapi/swagger-ui
     docker run -p 85:8080 -e SWAGGER_JSON=/tmp/workflows_api.json -v C:\Users\fathullahharun\Downloads\tm_api_v2:/tmp swaggerapi/swagger-ui
     docker run -p 86:8080 -e SWAGGER_JSON=/tmp/xpl_api.json -v C:\Users\fathullahharun\Downloads\tm_api_v2:/tmp swaggerapi/swagger-ui
     ```

3. **Access Swagger UI:**
   - Each Swagger UI instance can be accessed on a different port. Open your web browser and go to `http://localhost:<port>` where `<port>` is one of the following:
     - `80` for `core_api.json`
     - `81` for `audit_api.json`
     - `82` for `access_control_api.json`
     - `83` for `data_loader_api.json`
     - `84` for `payment_hub_api.json`
     - `85` for `workflows_api.json`
     - `86` for `xpl_api.json`

## Troubleshooting

If you encounter issues, ensure that Docker is running and that the paths to the JSON files are correct. Remember, the ports you use must be free and not used by other services.

