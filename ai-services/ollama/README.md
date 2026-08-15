# Ollama

Ollama provides the homelab's local model-serving runtime.

## Implementation Highlights

- Exposes the Ollama API on its standard port.
- Persists downloaded model data outside the container.
- Uses a health check based on the Ollama CLI.
- Applies an 8 GB memory limit.
- Joins an external Docker network used by AI-enabled applications.
- Externalizes concurrency and model-lifetime settings through environment
  variables.

## Skills Demonstrated

- Local AI infrastructure
- Docker health checks
- Persistent model storage
- External service networks
- Resource management
