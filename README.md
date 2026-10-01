# Dockge stack configuration

This repository backs up Docker Compose stack definitions and environment templates.
Runtime data, certificates, keys, sockets, and local `.env` files are excluded.

To restore, copy each stack directory into Dockge's stacks directory. Copy each
template from `env-templates/<stack>.env.example` to `<stack>/.env` and fill in values from your secure secrets backup.
For Dozzle, set `DOZZLE_BASIC_AUTH` to the existing htpasswd entry, single-quoted
in `.env` so dollar signs remain literal.

Restore bind-mounted application directories and Docker named volumes from a
separate data backup before starting services when retaining existing state.
Back up local `.env` files securely as well; templates contain no credentials.
External Docker networks referenced by the Compose files must already exist.
