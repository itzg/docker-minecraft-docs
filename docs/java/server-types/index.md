
## Server types

### Running a Forge Server

Enable [Forge server](http://www.minecraftforge.net/) mode by adding a `-e TYPE=FORGE` to your command-line.

The overall version is specified by `VERSION`, [as described in the section above](#versions) and will run the recommended Forge version by default. You can also choose to run a specific Forge version with `FORGE_VERSION`, such as `-e FORGE_VERSION=14.23.5.2854`.

```
docker run -d -v /path/on/host:/data \
    -e TYPE=FORGE \
    -e VERSION=1.12.2 -e FORGE_VERSION=14.23.5.2854 \
    -p 25565:25565 -e EULA=TRUE --name mc itzg/minecraft-server
```

To use a pre-downloaded Forge installer, place it in the attached `/data` directory and
specify the name of the installer file with `FORGE_INSTALLER`, such as:

```
docker run -d -v /path/on/host:/data ... \
    -e FORGE_INSTALLER=forge-1.11.2-13.20.0.2228-installer.jar ...
```

To download a Forge installer from a custom location, such as your own file repository, specify
the URL with `FORGE_INSTALLER_URL`, such as:

```
docker run -d -v /path/on/host:/data ... \
    -e FORGE_INSTALLER_URL=http://HOST/forge-1.11.2-13.20.0.2228-installer.jar ...
```

In both of the cases above, there is no need for the `VERSION` or `FORGEVERSION` variables.

!!! note
    
    If an error occurred while installing Forge, it might be possible to resolve by temporarily setting `FORGE_FORCE_REINSTALL` to "true". Be sure to remove that variable after successfully starting the server.

### Running a Quilt Server

Enable [Quilt server](https://quiltmc.org/) mode by adding a `-e TYPE=QUILT` to your command-line.

```
docker run -d -v /path/on/host:/data \
    -e TYPE=QUILT \
    -p 25565:25565 -e EULA=TRUE --name mc itzg/minecraft-server
```

By default, the container will install the latest [quilt server launcher](https://quiltmc.org/install/server/), using the latest [quilt-installer](https://github.com/QuiltMC/quilt-installer) against the minecraft version you have defined with `VERSION` (defaulting to the latest vanilla release of the game).

A specific loader or installer version other than the latest can be requested using `QUILT_LOADER_VERSION` and `QUILT_INSTALLER_VERSION` respectively, such as:

```
docker run -d -v /path/on/host:/data ... \
    -e TYPE=QUILT \
    -e QUILT_LOADER_VERSION=0.16.0 \
    -e QUILT_INSTALLER_VERSION=0.4.1
```

!!! note

    If you wish to use an alternative launcher you can: 

    - Provide the path to a custom launcher jar available to the container with `QUILT_LAUNCHER`, relative to `/data` (such as `-e QUILT_LAUNCHER=quilt-server-custom.jar`)
    - Provide the URL to a custom launcher jar with `QUILT_LAUNCHER_URL` (such as `-e QUILT_LAUNCHER_URL=http://HOST/quilt-server-custom.jar`)

See the [Working with mods and plugins](#working-with-mods-and-plugins) section to set up Quilt mods and configuration.

### Running a Bukkit/Spigot server

Enable Bukkit/Spigot server mode by adding a `-e TYPE=BUKKIT` or `-e TYPE=SPIGOT` to your command-line.

```
docker run -d -v /path/on/host:/data \
    -e TYPE=SPIGOT \
    -p 25565:25565 -e EULA=TRUE --name mc itzg/minecraft-server
```

If the downloaded server jar is corrupted, set `FORCE_REDOWNLOAD` to "true" to force a re-download during next container startup. After successfully re-downloading, you should remove that or set to "false".

If you are hosting your own copy of Bukkit/Spigot you can override the download URLs with:

- -e BUKKIT_DOWNLOAD_URL=<url>
- -e SPIGOT_DOWNLOAD_URL=<url>

You can build spigot from source by adding `-e BUILD_FROM_SOURCE=true`

Plugins can either be managed within the `plugins` subdirectory of the [data directory](#data-directory) or you can also [attach a `/plugins` volume](#optional-plugins-mods-and-config-attach-points). If you add plugins while the container is running, you'll need to restart it to pick those up.

[You can also auto-download plugins using `SPIGET_RESOURCES`.](#auto-downloading-spigotmcbukkitpapermc-plugins-with-spiget)

!!! note 

    Some of the `VERSION` values are not as intuitive as you would think, so make sure to click into the version entry to find the **exact** version needed for the download. For example, "1.8" is not sufficient since their download naming expects `1.8-R0.1-SNAPSHOT-latest` exactly.

### Running a Paper server

Enable Paper server mode by adding a `-e TYPE=PAPER` to your command-line.

By default, the container will run the latest build of [Paper server](https://papermc.io/downloads) but you can also choose to run a specific build with `-e PAPERBUILD=205`.

    docker run -d -v /path/on/host:/data \
        -e TYPE=PAPER \
        -p 25565:25565 -e EULA=TRUE --name mc itzg/minecraft-server

If you are hosting your own copy of Paper you can override the download URL with `PAPER_DOWNLOAD_URL=<url>`.

If you have attached a host directory to the `/data` volume, then you can install plugins via the `plugins` subdirectory. You can also [attach a `/plugins` volume](#optional-plugins-mods-and-config-attach-points). If you add plugins while the container is running, you'll need to restart it to pick those up.

[You can also auto-download plugins using `SPIGET_RESOURCES`.](#auto-downloading-spigotmcbukkitpapermc-plugins-with-spiget)

### Running a Pufferfish server

A [Pufferfish](https://github.com/pufferfish-gg/Pufferfish) server, which is "a highly optimized Paper fork designed for large servers requiring both maximum performance, stability, and "enterprise" features."

    -e TYPE=PUFFERFISH

!!! note

    The `VERSION` variable is used to select branch latest, 1.18, or 1.17. Use PUFFERFISH_BUILD to really select the SERVER VERSION number.

Extra variables:
- `PUFFERFISH_BUILD=lastSuccessfulBuild` : set a specific Pufferfish build to use. Example: selecting build 47 => 1.18.1, or build 50 => 1.18.2 etc
- `FORCE_REDOWNLOAD=false` : set to true to force the located server jar to be re-downloaded
- `USE_FLARE_FLAGS=false` : set to true to add appropriate flags for the built-in [Flare](https://blog.airplane.gg/flare) profiler

### Running a Purpur server

A [Purpur](https://purpurmc.org/) server, which is "a drop-in replacement for Paper servers designed for configurability and new, fun, exciting gameplay features."

    -e TYPE=PURPUR

!!! note

    The `VERSION` variable is used to lookup a build of Purpur to download

Extra variables:
- `PURPUR_BUILD=LATEST` : set a specific Purpur build to use
- `FORCE_REDOWNLOAD=false` : set to true to force the located server jar to be re-downloaded
- `USE_FLARE_FLAGS=false` : set to true to add appropriate flags for the built-in [Flare](https://blog.airplane.gg/flare) profiler
- `PURPUR_DOWNLOAD_URL=<url>` : set URL to download Purpur from custom URL.

### Running a Magma server

A [Magma](https://magmafoundation.org/) server, which is a combination of Forge and PaperMC, can be used with

    -e TYPE=MAGMA

!!! note

   There are limited base versions supported, so you will also need to  set `VERSION`, such as "1.12.2", "1.16.5", etc.


### Running a Mohist server

A [Mohist](https://github.com/MohistMC/Mohist) server can be used with

    -e TYPE=MOHIST

!!! note 

   There are limited base versions supported, so you will also need to  set `VERSION`, such as "1.12.2"

By default the latest build will be used; however, a specific build number can be selected by setting `MOHIST_BUILD`, such as

    -e VERSION=1.16.5 -e MOHIST_BUILD=374

### Running a Catserver type server

A [Catserver](http://catserver.moe/) type server can be used with

    -e TYPE=CATSERVER

> **NOTE** Catserver only provides a single release stream, so `VERSION` is ignored

### Running a Loliserver type server

A [Loliserver](https://github.com/Loli-Server/LoliServer) type server can be used with

    -e TYPE=LOLISERVER

!!! note

    Loliserver only provides a single release stream, so `VERSION` is ignored

> **Disclaimer** The retrieval of the serverjar is not bulletproof. It can and probably will change in the future.

### Running a Canyon server

[Canyon](https://github.com/canyonmodded/canyon) is a fork of CraftBukkit for Minecraft Beta 1.7.3. It includes multiple enhancements whilst also retaining compatibility with old Bukkit plugins and mods as much as possible.

    -e VERSION=b1.7.3 -e TYPE=CANYON

!!! note 

    Only `VERSION=b1.7.3` is supported. Since that version pre-dates the health check mechanism used by this image, that will need to be disabled by setting `DISABLE_HEALTHCHECK=true`.

By default, the latest build will be used; however, a specific build number can be selected by setting `CANYON_BUILD`, such as

    -e CANYON_BUILD=11

### Running a SpongeVanilla server

Enable SpongeVanilla server mode by adding a `-e TYPE=SPONGEVANILLA` to your command-line.
    
By default the container will run the latest `STABLE` version.
If you want to run a specific version, you can add `-e SPONGEVERSION=1.11.2-6.1.0-BETA-19` to your command-line.
    
Beware that current [Sponge](https://www.spongepowered.org) `STABLE` versions for Minecraft 1.12 require using [the Java 8 tag](#running-minecraft-server-on-different-java-version):
    
``` shell
docker run -d -v /path/on/host:/data -e TYPE=SPONGEVANILLA \
    -p 25565:25565 -e EULA=TRUE --name mc itzg/minecraft-server:java8-multiarch
```

You can also choose to use the `EXPERIMENTAL` branch.
Just change it with `SPONGEBRANCH`, such as:

``` shell
$ docker run -d -v /path/on/host:/data ... \
    -e TYPE=SPONGEVANILLA -e SPONGEBRANCH=EXPERIMENTAL ...
```

### Running a Limbo server

A [Limbo](https://github.com/LOOHP/Limbo) server can be run by setting `TYPE` to `LIMBO`.

Configuration options with defaults:

- `LIMBO_BUILD`=LATEST

  The `VERSION` will be ignored so locate the appropriate value from [here](https://ci.loohpjames.com/job/Limbo/) to match the version expected by clients.

- `FORCE_REDOWNLOAD`=false
- `LIMBO_SCHEMA_FILENAME`=default.schem
- `LEVEL`="Default;${LIMBO_SCHEMA_NAME}"

!!! note

    Instead of using format codes in the MOTD, Limbo requires [JSON chat content](https://minecraft.fandom.com/wiki/Raw_JSON_text_format#Java_Edition). If a plain string is provided, which is the default, then it gets converted into the required JSON structure. 

### Running a Crucible server

A [Crucible](https://github.com/CrucibleMC/Crucible) server can be run by setting `TYPE` to `CRUCIBLE`.

Configuration options with defaults:

- `CRUCIBLE_RELEASE`=latest

Crucible is only available for 1.7.10, so be sure to set `VERSION=1.7.10`.

## Running a server with a Feed the Beast modpack

!!! note 

    Requires one of the Ubuntu with Hotspot images listed in [the Java versions section](#running-minecraft-server-on-different-java-version).

[Feed the Beast application](https://www.feed-the-beast.com/) modpacks are supported by using `-e TYPE=FTBA` (**note** the "A" at the end of the type). This server type will automatically take care of downloading and installing the modpack and appropriate version of Forge, so the `VERSION` does not need to be specified.

### Environment Variables:
- `FTB_MODPACK_ID`: **required**, the numerical ID of the modpack to install. The ID can be located by [finding the modpack](https://www.feed-the-beast.com/modpack) and locating the ID in this part of the URL:

  ```
  https://www.feed-the-beast.com/modpacks/23-ftb-infinity-evolved-17
                                          ^^
  ```
- `FTB_MODPACK_VERSION_ID`: optional, the numerical ID of the version to install. If not specified, the latest version will be installed. The "Version ID" can be obtained by hovering over a server file entry and grabbing [this ID in the URL](../../assets/images/java/ftba-version-id-popup.png).

### Upgrading

If a specific `FTB_MODPACK_VERSION_ID` was not specified, simply restart the container to pick up the newest modpack version. If using a specific version ID, recreate the container with the new version ID.

### Example

The following example runs the latest version of [FTB Presents Direwolf20 1.12](https://ftb.neptunepowered.org/pack/ftb-presents-direwolf20-1-12/):

``` shell
docker run -d --name mc-ftb -e EULA=TRUE \
  -e TYPE=FTBA -e FTB_MODPACK_ID=31 \
  -p 25565:25565 \
  itzg/minecraft-server:java8-multiarch
```

!!! note 

    Normally you will also add `-v` volume for `/data` since the mods and config are installed there along with world data.
