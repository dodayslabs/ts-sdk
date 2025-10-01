# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a TypeScript SDK for the DoDays API, generated using OpenAPI Generator. The repository is configured to use OpenAPI Generator CLI version 7.15.0 to automatically generate TypeScript client code from API specifications.

## Architecture

- **Generator-based SDK**: This project uses OpenAPI Generator to create TypeScript client code from API specifications
- **OpenAPI Specification**: The source OpenAPI spec is located at `../docs/openapi.yaml` (relative to this repository)
- **Generator**: Uses `typescript-fetch` generator to create the SDK
- **Output Directory**: Generated code is placed in the `src/` directory
- **Build Output**: Compiled JavaScript and TypeScript declarations are output to `dist/` directory
- **Node.js Environment**: Configured for Node.js v24.4.1 (specified in .nvmrc)
- **Package Manager**: Uses pnpm (version 10.17.1) as specified in package.json

## Commands

### Build Process

```bash
# Full build (generate + compile)
pnpm build

# Generate SDK from OpenAPI spec (from ../docs/openapi.yaml)
pnpm generate

# Compile TypeScript to JavaScript
pnpm compile
```

### Code Generation

```bash
# Generate TypeScript SDK from OpenAPI specification (manual)
npx openapi-generator-cli generate -i ../docs/openapi.yaml -g typescript-fetch -o src

# View available generators
npx openapi-generator-cli list

# Validate OpenAPI specification
npx openapi-generator-cli validate -i ../docs/openapi.yaml

# Get help for configuration options
npx openapi-generator-cli config-help -g typescript-fetch
```

### Package Management

```bash
# Install dependencies
pnpm install

# Use correct Node.js version
nvm use
```

## Development Notes

- **Source of Truth**: The OpenAPI specification at `../docs/openapi.yaml` is the single source of truth for the API
- **Generated Code**: All code in `src/` is generated and should not be manually edited as it will be overwritten during regeneration
- **Build Artifacts**: The `dist/` directory contains compiled output and is what gets published to npm
- **OpenAPI Generator**: Configuration is stored in `openapitools.json` (currently using version 7.15.0)
- **Generator Type**: Uses `typescript-fetch` generator which creates a lightweight client using the Fetch API
- **Workflow**: When the OpenAPI spec changes, run `pnpm build` to regenerate the SDK and compile it
