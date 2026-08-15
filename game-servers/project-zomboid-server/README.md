# Project Zomboid Server

A containerized dedicated Project Zomboid server with persistent server files
and configuration.

## Implementation Highlights

- Publishes the required UDP game ports and TCP service port.
- Uses a grace period during shutdown.
- Persists both server files and server configuration.
- Loads deployment-specific server settings from a local `.env` file.
- Uses an on-demand restart policy.

## Publishing Notes

The uploaded Compose file references `.env` but does not reveal which
variables are stored inside that file. The public `.env.example` therefore
contains instructions only rather than guessed variable names.

## Skills Demonstrated

- Dedicated server hosting
- UDP and TCP networking
- Graceful container shutdown
- Persistent server state
- Externalized configuration
