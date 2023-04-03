[![Docker Pulls](https://img.shields.io/docker/pulls/itzg/minecraft-bedrock-server.svg)](https://hub.docker.com/r/itzg/minecraft-bedrock-server/)
[![GitHub Issues](https://img.shields.io/github/issues-raw/itzg/docker-minecraft-bedrock-server.svg)](https://github.com/itzg/docker-minecraft-bedrock-server/issues)
[![Build](https://github.com/itzg/docker-minecraft-bedrock-server/workflows/Build/badge.svg)](https://github.com/itzg/docker-minecraft-bedrock-server/actions?query=workflow%3ABuild)
[![Discord](https://img.shields.io/discord/660567679458869252?label=Discord&logo=discord)](https://discord.gg/ScbTrAw)
[![](https://img.shields.io/badge/Donate-Buy%20me%20a%20coffee-orange.svg)](https://www.buymeacoffee.com/itzg)


[itzg/minecraft-bedrock-server](https://hub.docker.com/r/itzg/minecraft-bedrock-server)

The following starts a Bedrock Dedicated Server running a default version and
exposing the default UDP port: 

```bash
docker run -d -it -e EULA=TRUE -p 19132:19132/udp -v mc-bedrock-data:/data itzg/minecraft-bedrock-server
```

!!! note

    if you plan on running a server for a longer amount of time it is highly recommended using a management layer such as [Docker Compose](bedrock/deployment/docker-compose) or [Kubernetes](bedrock/deployment/k8s) to allow for incremental reconfiguration and image upgrades.

### Upgrading to the latest Bedrock server version

With the `VERSION` variable set to `LATEST`, which is the default, then the Bedrock server can be upgraded by restarting the container. At every startup, the container checks for the latest version and upgrades, if needed.

The latest preview version can be requested by setting `VERSION` to `PREVIEW`.


## Community Solutions

- [kaiede/minecraft-bedrock-backup image](https://hub.docker.com/r/kaiede/minecraft-bedrock-backup) by @Kaiede
- [ghcr.io/edward3h/mc-webhook](https://github.com/edward3h/minecraft-webhook) by @edward3h
- [Minecraft Bedrock Server Bridge](https://github.com/macchie/minecraft-bedrock-server-bridge) by @macchie

## Tutorials
[@TheTinkerDad]([url](https://github.com/TheTinkerDad)) provides an excellent tutorial on how to host multiple instances on a single port (19132) so that it's discoverable: https://www.youtube.com/watch?v=ds0_ESzjbfs
