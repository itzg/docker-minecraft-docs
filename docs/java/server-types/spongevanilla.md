### Running a SpongeVanilla server

Enable SpongeVanilla server mode by adding a `-e TYPE=SPONGEVANILLA` to your command-line.
    
By default the container will run the latest `STABLE` version.
If you want to run a specific version, you can add `-e SPONGEVERSION=1.11.2-6.1.0-BETA-19` to your command-line.
    
Beware that current [Sponge](https://www.spongepowered.org) `STABLE` versions for Minecraft 1.12 require using [the Java 8 tag](../versions/java):
    
```
docker run -d -v /path/on/host:/data -e TYPE=SPONGEVANILLA \
    -p 25565:25565 -e EULA=TRUE --name mc itzg/minecraft-server:java8-multiarch
```

You can also choose to use the `EXPERIMENTAL` branch.
Just change it with `SPONGEBRANCH`, such as:

```
docker run -d -v /path/on/host:/data ... \
    -e TYPE=SPONGEVANILLA -e SPONGEBRANCH=EXPERIMENTAL ...
```
