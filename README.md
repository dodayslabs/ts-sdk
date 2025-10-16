# DoDays TypeScript SDK

Official TypeScript SDK for the DoDays API, providing type-safe access to all DoDays endpoints.

## Installation

```bash
pnpm add @dodayslabs/ts-sdk
```

## Usage

```typescript
import { Configuration, DefaultApi } from "@dodayslabs/ts-sdk";

const config = new Configuration({
  basePath: "https://api.dodays.co.uk",
  apiKey: "your-api-key",
});

const api = new DefaultApi(config);

// Make API calls
const response = await api.getSomething();
```

## Development

This SDK is automatically generated from the DoDays OpenAPI specification using OpenAPI Generator.

### Prerequisites

- Node.js v24.9.0 (use `nvm use` to switch to the correct version)
- pnpm 10.17.1+

### Setup

```bash
# Install dependencies
pnpm install

# Generate and build the SDK
pnpm build
```

### Available Scripts

- `pnpm build` - Generate SDK from OpenAPI spec and compile TypeScript
- `pnpm generate` - Generate SDK code from [docs/openapi.yaml](https://github.com/dodayslabs/docs)
- `pnpm compile` - Compile TypeScript to JavaScript

### Project Structure

- **Source of Truth**: OpenAPI specification at [docs/openapi.yaml](https://github.com/dodayslabs/docs)
- **Generated Code**: `src/` directory (do not edit manually)
- **Build Output**: `dist/` directory (published to npm)

### Making Changes

1. Update the OpenAPI specification at [docs/openapi.yaml](https://github.com/dodayslabs/docs)
2. Run `pnpm build` to regenerate and compile the SDK
3. The generated code in `src/` will be automatically updated

**Important**: Do not manually edit files in the `src/` directory as they will be overwritten during the next generation.

## Generator Configuration

- **Generator**: OpenAPI Generator CLI v7.15.0
- **Generator Type**: `typescript-fetch` (lightweight Fetch API-based client)
- **Configuration**: See `openapitools.json`

## License

See LICENSE

## Repository

[dodayslabs/ts-sdk](https://github.com/dodayslabs/ts-sdk)
