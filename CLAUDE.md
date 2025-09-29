# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a TypeScript SDK for the DoDays API, generated using OpenAPI Generator. The repository is configured to use OpenAPI Generator CLI version 7.15.0 to automatically generate TypeScript client code from API specifications.

## Architecture

- **Generator-based SDK**: This project uses OpenAPI Generator to create TypeScript client code from API specifications
- **Node.js Environment**: Configured for Node.js v24.4.1 (specified in .nvmrc)
- **Package Manager**: Uses pnpm (version 10.17.1) as specified in package.json

## Commands

### Code Generation

```bash
# Generate TypeScript SDK from OpenAPI specification
npx openapi-generator-cli generate

# View available generators
npx openapi-generator-cli list

# Validate OpenAPI specification
npx openapi-generator-cli validate

# Get help for configuration options
npx openapi-generator-cli config-help -g typescript-axios
```

### Package Management

```bash
# Install dependencies
pnpm install

# Use correct Node.js version
nvm use
```

## Development Notes

- The repository currently contains minimal source code as it's designed to be generated
- OpenAPI Generator configuration is stored in `openapitools.json`
- No custom scripts are currently defined in package.json
- Generated code should not be manually edited as it will be overwritten during regeneration
- Use the OpenAPI specification as the source of truth for API changes
