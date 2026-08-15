# Jellyfin and Seerr

This stack provides media playback through Jellyfin and media request
management through Seerr.

## Jellyfin

Jellyfin receives access to `/dev/dri` for Intel hardware acceleration and
uses separate persistent configuration, cache, and media mounts.

## Seerr

Seerr stores its application configuration outside the container and uses
`init: true` for process management.

## Resource Allocation

| Container | Memory Reservation | Memory Limit | Published Port |
|---|---:|---:|---|
| Jellyfin | 1 GB | 3 GB | 8096 |
| Seerr | 384 MB | 1 GB | 5055 |

## Skills Demonstrated

- Media-server deployment
- Hardware device passthrough
- Persistent storage
- Application lifecycle separation
- Resource management
