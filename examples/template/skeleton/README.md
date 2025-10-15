# Express Sample

A simple Express.js server that displays a birthday message.

## Features

- Lightweight Express.js server
- Configurable port via environment variable
- Docker support for containerized deployment
- Birthday message for Rox ❤️

## Prerequisites

- Node.js 18 or higher
- npm
- Docker (optional, for containerized deployment)

## Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```

## Usage

### Running Locally

Start the server:
```bash
npm start
```

Or run directly with Node.js:
```bash
node src/index.js
```

The server will start on port 3000 by default. Visit `http://localhost:3000` to see the birthday message.

### Environment Variables

- `PORT` - The port number to run the server on (default: 3000)

Example:
```bash
PORT=8080 node src/index.js
```

### Docker Deployment

Build the Docker image:
```bash
docker build -t express-sample .
```

Run the container:
```bash
docker run -p 3000:3000 express-sample
```

Or run on a different port:
```bash
docker run -p 8080:3000 -e PORT=3000 express-sample
```

## Project Structure

```
.
├── Dockerfile          # Docker configuration
├── package.json        # Project dependencies and scripts
├── README.md          # This file
└── src/
    └── index.js       # Main server file
```

## API Endpoints

- `GET /` - Returns a birthday message

## License

MIT
