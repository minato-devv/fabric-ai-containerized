## Requirements
* Mac with Apple Silicon on macOS 26
* [`apple/container`](https://github.com/apple/container.git)
* [fabric-ai installed and set up](https://github.com/danielmiessler/Fabric/blob/main/README.md#installation)

## Installation

```sh
# Pull the pre-built image
container image pull honeylavender7435/fabric-mcp:v1

# Set environment variables. Fabric-MCP reads the .env file for the DEFAULT_VENDOR, DEFAULT_MODEL, and FABRIC_BASE_URL environment variables
printf "DEFAULT_VENDOR=<your vendor of choice>\nDEFAULT_MODEL=<your model of choice>\nFABRIC_BASE_URL=http://192.168.64.1:8080" >> ~/.config/fabric/.env

# Start your fabric instance
fabric --serve --address 0.0.0.0:8080
```

## Configure your `mcp.json`

```json
{
  "mcpServers": {
    "fabric": {
      "command": "container",
      "args": [
        "run", "--interactive", "--remove",
        "--volume", "~/.config/fabric/.env:/home/appuser/.config/fabric/.env",
        "honeylavender7435/fabric-mcp:v1"
      ]
    }
  }
}
```
