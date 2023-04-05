[RCON](http://wiki.vg/RCON) is enabled by default, so you can `exec` into the container to
access the Minecraft server console:

```
docker exec -i mc rcon-cli
```

Note: The `-i` is required for interactive use of rcon-cli.

To run a simple, one-shot command, such as stopping a Minecraft server, pass the command as arguments to `rcon-cli`, such as:

```
docker exec mc rcon-cli stop
```

_The `-i` is not needed in this case._

If rcon is disabled you can send commands by passing them as arguments to the packaged `mc-send-to-console` script. For example, a player can be op'ed in the container `mc` with: 

```shell
docker exec mc mc-send-to-console op player
            |                     |
            +- container name     +- Minecraft commands start here
```

In order to attach and interact with the Minecraft server, add `-it` when starting the container, such as

    docker run -d -it -p 25565:25565 --name mc itzg/minecraft-server

With that you can attach and interact at any time using

    docker attach mc

and then Control-p Control-q to **detach**.

For remote access, configure your Docker daemon to use a `tcp` socket (such as `-H tcp://0.0.0.0:2375`)
and attach from another machine:

    docker -H $HOST:2375 attach mc

Unless you're on a home/private LAN, you should [enable TLS access](https://docs.docker.com/articles/https/).



### Auto-execute RCON commands

RCON commands can be configured to execute when the server starts, a client connects, or a client disconnects.

!!! note

    When declaring several commands within a compose file environment variable, it's easiest to use YAML's `|-` [block style indicator](https://yaml-multiline.info/).

**On Server Start:**

``` yaml
      RCON_CMDS_STARTUP:  |-
        gamerule doFireTick false
        pregen start 200
```

**On Client Connection:**

``` yaml
      RCON_CMDS_ON_CONNECT:  |-
        team join New @a[team=]
```

**Note:**
* On client connect we only know there was a connection, and not who connected. RCON commands will need to be used for that.

**On Client Disconnect:**

``` yaml
      RCON_CMDS_ON_DISCONNECT:  |-
        gamerule doFireTick true
```

**On First Client Connect**

``` yaml
      RCON_CMDS_FIRST_CONNECT: |-
        pregen stop
```

**On Last Client Disconnect**

``` yaml
      RCON_CMDS_LAST_DISCONNECT: |-
        kill @e[type=minecraft:boat]
        pregen start 200

```

**Example of rules for new players**

Uses team NEW and team OLD to track players on the server. So move player with no team to NEW, run a command, move them to team OLD.
[Reference Article](https://www.minecraftforum.net/forums/minecraft-java-edition/redstone-discussion-and/2213523-detect-players-first-join)

``` yaml
      RCON_CMDS_STARTUP:  |-
        /pregen start 200
        /gamerule doFireTick false
        /team add New
        /team add Old
      RCON_CMDS_ON_CONNECT: |-
        /team join New @a[team=]
        /give @a[team=New] birch_boat
        /team join Old @a[team=New]
      RCON_CMDS_FIRST_CONNECT: |-
        /pregen stop
      RCON_CMDS_LAST_DISCONNECT: |-
        /kill @e[type=minecraft:boat]
        /pregen start 200
```

