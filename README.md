# MCP Client

A TypeScript client implementation for the Model Context Protocol (MCP) using Server-Sent Events (SSE) transport.

## Overview

This client connects to MCP servers over HTTP using Server-Sent Events (SSE) and allows AI assistants like Claude to interact with custom tools exposed by the server. Unlike the standard examples that typically use stdio for local server communication, this client demonstrates how to implement remote server connections via SSE.

## Features

- Connect to MCP servers over HTTP using SSE transport
- Discover and execute tools exposed by the server
- Integrate with Claude or other AI assistants via the Anthropic API
- Maintain interactive chat sessions with tool execution

## Prerequisites

- Node.js (v16 or newer)
- npm or yarn
- An Anthropic API key

## Installation

```bash
# Clone the repository
git clone https://github.com/tyfeng1997/mcp-client.git
cd mcp-client

# Install dependencies
npm install

# Build the TypeScript code
npm run build
```

## Configuration

Create a `.env` file in the root directory with your Anthropic API key:

```
ANTHROPIC_API_KEY=your_api_key_here
```

## Usage

To start the client and connect to an MCP server:

```bash
node build/index.js http://localhost:3001/sse
```

Replace `http://localhost:3001/sse` with the SSE endpoint URL of your MCP server.

### Interactive Chat

Once connected, the client will start an interactive chat session where you can:

1. Type natural language queries
2. The client will send these to Claude
3. If Claude decides to use tools, the client will execute them through the MCP server
4. Results will be displayed in the conversation
5. Type 'quit' to exit

## Common Issues

- **"Not connected" error**: Make sure the server is running and the SSE endpoint is accessible. Also verify that your client code properly awaits the connection promise.
- **Timeout errors**: The server might be taking too long to respond. Check server logs for any issues.
- **Tool execution errors**: Ensure the tool parameters being passed match what the server expects.

## Companion Server

This client is designed to work with the MCP server available at [tyfeng1997/mcp-server](https://github.com/tyfeng1997/mcp-server), which provides a weather information service over SSE. You can also connect it to any other MCP-compliant server that supports SSE transport.

## Development

To modify the client:

1. Make changes to the TypeScript files
2. Rebuild with `npm run build`
3. Run the client to test your changes

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
