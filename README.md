# MCP Server with Wikipedia Article Tool

This is an HTTP SSE-based MCP (Managed Control Protocol) server that features a tool for fetching and converting Wikipedia articles to Markdown.

## Features

- MCP server implementation using FastMCP
- Server-Sent Events (SSE) for client-server communication
- Wikipedia article fetching tool
- Conversion of HTML content to Markdown

## Requirements

- Python 3.8+
- Dependencies listed in requirements.txt
- uv (Python package manager)

## Installation

```bash
# Clone the repository
git clone https://github.com/codingaslu/http-sse-mcp-starter.git
cd http-sse-mcp-starter

# Install dependencies using uv
uv pip install -r requirements.txt
```

## Usage

### Starting the Server

```bash
python server.py
```

The server will start on http://localhost:8000 with the following endpoints:
- `/sse`: For SSE connections from clients
- `/messages/`: For handling incoming POST messages

### Using the Client

```bash
# List server capabilities
uv run -- client.py http://localhost:8000/sse

# Fetch a Wikipedia article
uv run -- client.py http://localhost:8000/sse https://en.wikipedia.org/wiki/Python_(programming_language)
```

## MCP Server Capabilities

The MCP server provides:
- Tools: Functions that can be called by clients
- Resources: Data resources available to clients
- Prompts: Pre-defined prompts for AI assistants

The `read_wikipedia_article` tool fetches an article from Wikipedia, parses its content, and converts it to Markdown format.

## License

[MIT License](LICENSE)
