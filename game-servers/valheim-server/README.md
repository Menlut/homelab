# Valheim Server

A containerized dedicated Valheim server with persistent world configuration
and optional BepInEx support.

## Implementation Highlights

- Publishes the required Valheim UDP ports.
- Stores server state in a persistent configuration directory.
- Keeps server identity and password values outside the public Compose file.
- Configures a 5 GB memory reservation and 10 GB memory limit.
- Supports custom server arguments and BepInEx through environment variables.

## Security and Sanitization

The public Compose file does not contain the real server name, world name, or
server password. These values are represented by placeholders in
`.env.example`.

## Skills Demonstrated

- Dedicated server hosting
- UDP networking
- Secret management
- Persistent application state
- Resource management
