# Requirements

* `docker`
* `docker-compose`

# Installation 

```sh
# Clone this repository
git clone https://github.com/minato-devv/fabric-ai-containerized.git
cd fabric-ai-containerized/docker

# Create the directory that will be mounted onto both containers
mkdir -p "$HOME/.config/fabric"

# Install the patterns and strategies, choose a vendor and model
docker run -it --rm -v "$HOME/.config/fabric:/home/appuser/.config/fabric" kayvan/fabric:latest --setup

# Start both services
docker compose up -d
```

## Configure your `mcp.json`:

```json
{
  "mcpServers": {
    "fabric": {
      "url": "http://localhost:8000/message"
  }
}
```
