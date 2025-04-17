# MCP Filesystem
Test the [Filesystem MCP Server](https://mcpservers.org/servers/modelcontextprotocol/filesystem).

## Run the server
Use the [mcp-proxy](https://github.com/sparfenyuk/mcp-proxy) MCP Server to expose the 
[Filesystem MCP Server](https://mcpservers.org/servers/modelcontextprotocol/filesystem), a `stdio` server,
as a remote SSE server:
```
mcp-proxy --sse-port 9999 -- \
podman run -i --name filesystem --rm \
--mount type=bind,src=${HOME}/Desktop,dst=/projects/Desktop \
--mount type=bind,src=/tmp,dst=/projects/tmp,ro \
mcp/filesystem /projects
```

# Test client
Use the [client](./client.ipynb) notebook to access the server, list the available tools and run a few of them.