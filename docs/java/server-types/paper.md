### Running a Paper server

Enable Paper server mode by adding a `-e TYPE=PAPER` to your command-line.

By default, the container will run the latest build of [Paper server](https://papermc.io/downloads) but you can also choose to run a specific build with `-e PAPERBUILD=205`.

    docker run -d -v /path/on/host:/data \
        -e TYPE=PAPER \
        -p 25565:25565 -e EULA=TRUE --name mc itzg/minecraft-server

If you are hosting your own copy of Paper you can override the download URL with `PAPER_DOWNLOAD_URL=<url>`.

If you have attached a host directory to the `/data` volume, then you can install plugins via the `plugins` subdirectory. You can also [attach a `/plugins` volume](#optional-plugins-mods-and-config-attach-points). If you add plugins while the container is running, you'll need to restart it to pick those up.

<!-- TODO: fix link -->
[You can also auto-download plugins using `SPIGET_RESOURCES`.](#auto-downloading-spigotmcbukkitpapermc-plugins-with-spiget)
