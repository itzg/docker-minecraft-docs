[![Docker Pulls](https://img.shields.io/docker/pulls/itzg/minecraft-server.svg)](https://hub.docker.com/r/itzg/minecraft-server/)
[![Docker Stars](https://img.shields.io/docker/stars/itzg/minecraft-server.svg?maxAge=2592000)](https://hub.docker.com/r/itzg/minecraft-server/)
[![GitHub Issues](https://img.shields.io/github/issues-raw/itzg/docker-minecraft-server.svg)](https://github.com/itzg/docker-minecraft-server/issues)
[![Discord](https://img.shields.io/discord/660567679458869252?label=Discord&logo=discord)](https://discord.gg/DXfKpjB)
[![Build and Publish](https://github.com/itzg/docker-minecraft-server/workflows/Build%20and%20Publish/badge.svg)](https://github.com/itzg/docker-minecraft-server/actions)
[![](https://img.shields.io/badge/Donate-Buy%20me%20a%20coffee-orange.svg)](https://www.buymeacoffee.com/itzg)

This docker image provides a Minecraft Server that will automatically download the latest stable
version at startup. You can also run/upgrade to any specific version or the
latest snapshot. See the _Versions_ section below for more information.

To simply use the latest stable version, run

    docker run -d -it -p 25565:25565 -e EULA=TRUE itzg/minecraft-server

where, in this case, the standard server port 25565, will be exposed on your host machine.

!!! note

    If you plan on running a server for a longer amount of time it is highly recommended using a management layer such as [Docker Compose](java/deployment/docker-compose) or [Kubernetes](java/deployment/helmcharts) to allow for incremental reconfiguration and image upgrades.

!!! info 

    Be sure to always include `-e EULA=TRUE` in your commands and container definitions, as Mojang/Microsoft requires EULA acceptance.

!!! warning 

    **DO NOT** port forward RCON on 25575 without first setting `RCON_PASSWORD` to a secure value. It is highly recommended to only use RCON within the container, such as with `rcon-cli`. 

By default, the container will download the latest version of the "vanilla" [Minecraft: Java Edition server](https://www.minecraft.net/en-us/download/server) provided by Mojang. The [`VERSION`](java/versions/minecraft) and the [`TYPE`](java/server-types) can be configured to create many variations of desired Minecraft server. 
