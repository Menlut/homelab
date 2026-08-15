# ARR FileFlows

FileFlows provides automated media processing and uses Intel graphics hardware
for accelerated video workloads.

## Implementation Highlights

- Exposes `/dev/dri` for Intel Quick Sync Video.
- Adds the host render and video groups.
- Separates application configuration, temporary working data, and media
  storage.
- Applies a 1 GB memory reservation and 3 GB memory limit.

## Portability

Host group IDs are environment-specific, so the public Compose file uses
variables instead of publishing the source host's group IDs.

## Skills Demonstrated

- Hardware acceleration
- Linux device passthrough
- Linux group permissions
- Persistent and temporary storage design
- Container resource management
