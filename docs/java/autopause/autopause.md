# AutoPause

### Description

There are various bug reports on [Mojang](https://bugs.mojang.com) about high CPU usage of servers with newer versions, even with few or no clients connected (e.g. [this one](https://bugs.mojang.com/browse/MC-149018), in fact the functionality is based on [this comment in the thread](https://bugs.mojang.com/browse/MC-149018?focusedCommentId=593606&page=com.atlassian.jira.plugin.system.issuetabpanels%3Acomment-tabpanel#comment-593606)).

An autopause functionality has been added to this image to monitor whether clients are connected to the server. If for a specified time no client is connected, the Java process is stopped. When knocking on the server port (e.g. by the ingame Multiplayer server overview), the process is resumed. The experience for the client does not change.

Of course, even loaded chunks are not ticked when the process is stopped.

**You must greatly increase or disable max-tick-time watchdog functionality.** From the server's point of view, the pausing causes a single tick to take as long as the process is stopped, so the server watchdog might intervene after the process is continued, possibly forcing a container restart. To prevent this, ensure that the `max-tick-time` in the `server.properties` file is set to a very large value or -1 to disable it entirely, which is highly recommended. That can be set with `MAX_TICK_TIME` as described in [the section below](#max-tick-time).

!!! note 

    Non-vanilla versions might have their own configuration file, you might have to disable their watchdogs separately. For PaperMC servers, you need to send the JVM flag `-Ddisable.watchdog=true`, this can be done with the docker env variable `-e JVM_DD_OPTS=disable.watchdog:true`

On startup the `server.properties` file is checked and, if applicable, a warning is printed to the terminal. When the server is created (no data available in the persistent directory), the properties file is created with the Watchdog disabled.

The utility used to wake the server (`knock(d)`) works at network interface level. So the correct interface has to be set using the `AUTOPAUSE_KNOCK_INTERFACE` variable when using non-default networking environments (e.g. host-networking, Portainer oder NAS solutions). See the description of the variable below.

A file called `.paused` is created in `/data` directory when the server is paused and removed when the server is resumed. Other services may check for this file's existence before waking the server.

A starting, example compose file has been provided in [examples/docker-compose-autopause.yml](https://github.com/itzg/docker-minecraft-server/blob/master/examples/docker-compose-autopause.yml).

### Enabling Autopause

Enable the Autopause functionality by setting:

```
-e ENABLE_AUTOPAUSE=TRUE
```

Autopause is not compatible with `EXEC_DIRECTLY=true` and the two cannot be set together.

!!! note 

    When configuring kubernetes readiness/liveness health checks with auto-pause enabled, be sure to reference the `mc-health` wrapper script rather than `mc-status` directly.

The following environment variables define the behaviour of auto-pausing:

- `AUTOPAUSE_TIMEOUT_EST`, default `3600` (seconds)
  describes the time between the last client disconnect and the pausing of the process (read as timeout established)
- `AUTOPAUSE_TIMEOUT_INIT`, default `600` (seconds)
  describes the time between server start and the pausing of the process, when no client connects inbetween (read as timeout initialized)
- `AUTOPAUSE_TIMEOUT_KN`, default `120` (seconds)
  describes the time between knocking of the port (e.g. by the main menu ping) and the pausing of the process, when no client connects inbetween (read as timeout knocked)
- `AUTOPAUSE_PERIOD`, default `10` (seconds)
  describes period of the daemonized state machine, that handles the pausing of the process (resuming is done independently)
- `AUTOPAUSE_KNOCK_INTERFACE`, default `eth0`
  <br>Describes the interface passed to the `knockd` daemon. If the default interface does not work, run the `ifconfig` command inside the container and derive the interface receiving the incoming connection from its output. The passed interface must exist inside the container. Using the loopback interface (`lo`) does likely not yield the desired results.

!!! tip

    To troubleshoot, add `DEBUG_AUTOPAUSE=true` to see additional output

### Rootless Autopause

If you're running the container as rootless, you might need to set change the default port forwarder from RootlessKit to slirp4netns.

For Docker, see the following for setup:

- https://docs.docker.com/engine/security/rootless/#networking-errors
- https://rootlesscontaine.rs/getting-started/docker/#changing-the-port-forwarder

For Podman, see the following for setup:
- https://rootlesscontaine.rs/getting-started/podman/#changing-the-port-forwarder
- Run with

  ```
  -e AUTOPAUSE_KNOCK_INTERFACE=tap0 --cap-add=CAP_NET_RAW --network slirp4netns:port_handler=slirp4netns
  ```
