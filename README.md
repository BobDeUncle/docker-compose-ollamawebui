# Ollama WebUI Docker Setup

This repository contains a Docker Compose configuration for running [Ollama WebUI](https://github.com/ollama-webui/ollama-webui) - a web-based user interface for Ollama.

## Overview

Ollama WebUI provides a user-friendly interface for interacting with Ollama, making it easier to manage and use large language models (LLMs) running locally via Ollama.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/)
- An existing Ollama instance running and accessible at the configured URL

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/BobDeUncle/docker-compose-ollamawebui.git
   cd docker-compose-ollamawebui
   ```

2. Start the container:
   ```bash
   docker compose up -d
   ```

3. Verify installation:
   ```bash
   docker ps
   ```
   You should see the Ollama WebUI container running.

## Usage

### Accessing Ollama WebUI

Ollama WebUI is accessible via a web browser at:
```
http://localhost:8080
```

The interface allows you to:
- Chat with available models
- Manage and download models
- Customize model parameters
- Create and share prompts
- Review chat history

## Configuration

### Customize the `docker-compose.yml`

- **Port**: The default port is 8080. Change `8080:8080` if you need a different port mapping.
- **Ollama API URL**: The `OLLAMA_API_BASE_URL` environment variable points to your Ollama instance. Update this URL to match your Ollama server's address.
- **Restart Policy**: By default, the container will restart automatically unless manually stopped.

## Maintenance

### Updating

To update the Ollama WebUI container to the latest version:

```bash
docker compose pull
docker compose up -d
```

If you want automatic updates, consider adding Watchtower to your Docker Compose file, similar to the example you referenced.

## Troubleshooting

- If you can't connect to the WebUI, verify that the Ollama API URL is correct and that your Ollama instance is running
- Check container logs for any errors: `docker logs ollama-webui`
- Ensure that your network allows connections between the WebUI container and Ollama

## License

Ollama WebUI is an open-source project. For licensing information, visit the [Ollama WebUI GitHub repository](https://github.com/ollama-webui/ollama-webui).

## Related Projects

If you need to set up Ollama itself, check out our companion repository:
- [Docker Compose Ollama](https://github.com/BobDeUncle/docker-compose-ollama) - A complete Docker setup for running Ollama with automatic updates via Watchtower
 
This WebUI container is designed to work seamlessly with the Ollama instance from the above repository. Simply ensure that the `OLLAMA_API_BASE_URL` environment variable points to your running Ollama instance.

## Additional Resources

- [Ollama WebUI GitHub Repository](https://github.com/ollama-webui/ollama-webui)
- [Ollama Documentation](https://github.com/ollama/ollama/tree/main/docs)
- [Ollama Models Library](https://ollama.ai/library)
- [Docker Documentation](https://docs.docker.com/)
