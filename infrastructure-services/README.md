# Infrastructure Services

Core networking, reverse proxy, local DNS, dashboard, Docker administration,
and database administration services.

## Overview

This directory contains foundational services used by the rest of the
homelab.

AdGuard Home provides local DNS resolution, Caddy routes web traffic to
internal services, Homepage provides a central dashboard, Portainer provides
Docker administration, and pgAdmin provides centralized PostgreSQL
administration.

Remote access to selected services is provided through a Tailscale mesh VPN
instead of direct router port forwarding. Administrative interfaces remain
intended for trusted devices and networks.

## Shared Domain Requirement

This deployment assumes control of a domain used for internal service
hostnames and the integration between AdGuard Home and Caddy.

Real domain names, DNS records, certificate data, and provider credentials are
not published.

## Services

| Service | Purpose |
|---|---|
| [AdGuard Home](adguard/) | Local DNS resolution and network-level filtering. |
| [Caddy](caddy/) | Reverse proxy and HTTPS entry point for internal web services. |
| [Homepage](homepage/) | Centralized service dashboard. |
| [Portainer](portainer/) | Docker administration and container visibility. |
| [pgAdmin](database-admin/) | Centralized PostgreSQL administration. |

## Service Flow

```text
Trusted local / remote device
            |
            v
      AdGuard Home DNS
            |
            v
       Caddy proxy
            |
            v
   Internal web service
```

Homepage provides a central entry point for services, while Portainer and
pgAdmin provide administrative interfaces for Docker and PostgreSQL
respectively.

## Skills Demonstrated

- Local DNS and service discovery
- Reverse proxy architecture
- Domain and hostname management
- HTTP/HTTPS service routing
- Container administration
- PostgreSQL administration
- External Docker networks
- Resource reservations and limits
- Secure remote access without router port forwarding
- Public configuration sanitization
