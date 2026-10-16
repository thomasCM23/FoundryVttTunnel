# Foundry VTT + Cloudflare tunnel (FoundryVttTunnel)

FoundryVttTunnel is a quick and easy way set up foundry and tunnel it to your domain using Cloudflare tunnels.


## Before you get started

### Docker

FoundryVttTunnel uses both docker and docker compose. Follow the instructions in the docker docs

- [Install Docker](https://docs.docker.com/engine/install/)

### Cloudflare tunnel

Set up a Cloudflare tunnel using the documentation.

- [Docs](https://developers.cloudflare.com/tunnel/)

In the tunnel's **Public Hostname** settings in the Cloudflare dashboard, route your domain to one of:
- `http://foundryvtt:30000` (recommended, reaches the container directly over the compose network)
- `http://<HOST_LAN_IP>:30000`

## Using FoundryVttTunnel

Steps:
1. Copy .env-example, rename file to .env
    - fill the variables with the correct values
2. Run docker compose
    - `docker compose up -d`
3. Open your domain and accept the license agreement (only needed once)

## Notes
- The Foundry container has a fixed `hostname`. Foundry ties its license to the hostname, so changing or removing it means accepting the license again.
- `CONTAINER_PRESERVE_CONFIG` is enabled, so changes made in Foundry's **Application Configuration** screen survive restarts. The `FOUNDRY_*` values in `.env` are only used to create `Config/options.json` and `Config/admin.txt` on first start. To re-apply them, stop the stack, delete those files from `DATA_DIR`, and start it again.
- All Foundry data (worlds, modules, config, license) is stored in `DATA_DIR`. Back up that directory.

## Acknowledgements
- Thanks to [felddy](https://github.com/felddy/foundryvtt-docker) and all the contributors for creating and  maintaining the dockerized Foundry VTT
