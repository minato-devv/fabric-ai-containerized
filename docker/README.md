# Installation 

```sh
# clone this repository
git clone https://github.com/minato-devv/fabric-mcp-docker.git
cd fabric-mcp-docker

# create the directory that will be mounted onto both containers
mkdir -p "${HOME}/.config/fabric"

# install the patterns and strategies, choose a vendor and model
docker run -it --rm -v "${HOME}/.config/fabric:/home/appuser/.config/fabric" kayvan/fabric:latest --setup

# start both services
docker compose up -d
```

Configure your `mcp.json`:

```json
{
  "mcpServers": {
    "fabric": {
      "url": "http://localhost:8000/message"
  }
}
```
