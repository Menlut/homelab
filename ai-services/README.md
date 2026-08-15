# AI Services

Local AI model-serving infrastructure used by applications on the homelab.

## Services

| Service | Purpose |
|---|---|
| [Ollama](ollama/) | Local model runtime exposed to trusted application containers. |

## Design Approach

Ollama stores downloaded model data persistently and joins an external Docker
network so other approved application stacks can use the local model service.

## Skills Demonstrated

- Local model serving
- External Docker networks
- Persistent model storage
- Health checks
- Resource limits
- Service-to-service AI integration
