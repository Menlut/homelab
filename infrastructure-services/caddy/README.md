# Caddy

Caddy is the central reverse proxy for internal homelab web services.

## Implementation Highlights

- Uses host networking for direct access to services running on the host.
- Builds a custom Caddy image with the Cloudflare DNS module.
- Mounts the production Caddyfile read-only.
- Persists Caddy data and runtime configuration outside the container.
- Uses explicit memory reservations and limits.

## Custom Docker Image

The included Dockerfile uses a multi-stage build. `xcaddy` creates a Caddy
binary with the DNS provider module, and that binary is copied into the normal
Caddy runtime image.

## Domain and DNS

This deployment uses a domain controlled by the administrator as part of the
local DNS and reverse-proxy workflow.

The production Caddyfile, real domain names, DNS records, provider
credentials, and certificate data are not published.

`Caddyfile.example` is intentionally only a placeholder because the production
Caddyfile was not part of the source files provided for sanitization.

## Skills Demonstrated

- Reverse proxy architecture
- Multi-stage Docker builds
- Custom Caddy modules
- DNS-based certificate integration
- Configuration and secret separation
- Persistent application state
