# Infrastructure Services

Core networking, reverse proxy, service discovery, dashboard, and container
management services for the homelab.

## Overview

This directory contains the foundational services that support the rest of the
homelab.

AdGuard Home provides local DNS resolution, Caddy routes web traffic to
internal services, Homepage provides a central service dashboard, and
Portainer provides a web interface for managing Docker resources.

Remote access to selected services is provided through a Tailscale mesh VPN
instead of direct router port forwarding. Administrative interfaces remain
restricted to trusted devices and networks.

### Shared Prerequisite

This deployment assumes control of a domain used for internal service
hostnames and the integration between AdGuard Home and Caddy.

Real domain names, DNS records, certificate data, and provider-specific
configuration are excluded from this public repository.

## Services

| Service | Purpose | Documentation |
|---|---|---|
| [AdGuard Home](adguard/) | Provides local DNS resolution and network-level filtering for trusted clients. | Service documentation and sanitized deployment files |
| [Caddy](caddy/) | Acts as the reverse proxy for internal web services and handles HTTP and HTTPS traffic. | Service documentation and sanitized deployment files |
| [Homepage](homepage/) | Provides a centralized dashboard for accessing and monitoring homelab services. | Service documentation and sanitized deployment files |
| [Portainer](portainer/) | Provides a graphical interface for viewing and administering Docker resources. | Service documentation and sanitized deployment files |

## Service Flow

```text
Trusted local and remote devices
              |
              v
       AdGuard Home DNS
              |
              v
      Caddy reverse proxy
              |
              v
     Internal web services
