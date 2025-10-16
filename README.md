# Backstage App - ROX Demo

This is a Backstage application scaffolded for ROX demo project.

## Prerequisites

- Node.js (version 20 or 22) - as specified in package.json engines
- Yarn package manager (v4.4.1)

## Environment Setup

1. **Environment Variables**:

   - Copy `.env` file and configure the required variables:
     - `NODE_OPTIONS="--no-node-snapshot"` (already set)
     - `GITHUB_TOKEN="ghp_**************"` (add your GitHub token for integrations)
     - `AUTH_GITHUB_CLIENT_ID="*********"` (SSO client ID)
     - `AUTH_GITHUB_CLIENT_SECRET="*****"` (SSO client Secret)

2. **Install Dependencies**:
   ```sh
   yarn install
   ```

## Running the Application

### Development Mode

Start the development server with hot reloading:

```sh
export $(grep -v '^#' .env | xargs)
yarn dev
```

This runs the backstage-cli repo start command with NODE_OPTIONS set to --no-node-snapshot.

### Alternative Start Command

```sh
yarn dev
```

## Build Commands

### Build Backend Only

```sh
yarn build:backend
```

### Build All Packages

```sh
yarn build:all
```

### Build Docker Image

```sh
yarn build-image
```

## Development Commands

### Type Checking

```sh
# Standard type check
yarn tsc

# Full type check (no skip lib check, no incremental)
yarn tsc:full
```

### Testing

```sh
# Run tests
yarn test

# Run all tests with coverage
yarn test:all

# Run end-to-end tests
yarn test:e2e
```

### Code Quality

```sh
# Auto-fix issues
yarn fix

# Lint changed files (since origin/master)
yarn lint

# Lint all files
yarn lint:all

# Check prettier formatting
yarn prettier:check
```

### Utilities

```sh
# Clean build artifacts
yarn clean

# Create new Backstage components
yarn new
```

## Project Structure

This is a monorepo with the following structure:

- `packages/app/` - Frontend Backstage application
- `packages/backend/` - Backend API server
- `plugins/` - Custom Backstage plugins
- `examples/` - Example configurations and templates

## Notes

- The project uses Yarn workspaces for monorepo management
- TypeScript ~5.8.0 is used for type checking
- Playwright is configured for e2e testing
- Prettier and ESLint are configured for code formatting and linting
