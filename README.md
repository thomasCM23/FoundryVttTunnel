# Foundry VTT + Cloudflare tunnel (FoundryVttTunnel)

FoundryVttTunnel is a quick and easy way set up foundry and tunnel it to your domain using Cloudflare tunnels.


## Before you get started

### Docker

FoundryVttTunnel uses both docker and docker compose, . Follow the insructions in the dockerdocs

- [Install Docker](https://docs.docker.com/engine/install/)

### Cloudflare tunnel

Set up a Cloudflare tunnel using the documentation.

- [Docs](https://developers.cloudflare.com/tunnel/)

## Using FoundryVttTunnel

Steps:
1. Copy .env-example, rename file to .env
    - fill the variables with the correct values
2. Copy config-example.yml, rename file to config.yml
    - fill the variables with the correct values
3. Run docker compose
    - `docker compose up -d`

## Acknowledgements
- Thanks to [felddy](https://github.com/felddy/foundryvtt-docker) and all the contributors for creating and  maintaining the dockerized Foundry VTT
