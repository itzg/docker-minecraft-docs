By default, the server configuration will be created and set based on the following environment variables, but only the first time the server is started. If the `server.properties` file already exists, the values in them will not be changed.

If you prefer to manually manage the `server.properties` file, set `OVERRIDE_SERVER_PROPERTIES` to "false". Similarly, you can entirely skip the startup script's creation of `server.properties` by setting `SKIP_SERVER_PROPERTIES` to "true".

!!! note

    To clear a server property, set the variable to an empty string, such as `-e RESOURCE_PACK=""`. A variables that maps to a server property that is unset, is ignored and the existing `server.property` is left unchanged. 


### Level Type and Generator Settings

By default, a standard world is generated with hills, valleys, water, etc. A different level type can
be configured by setting `LEVEL_TYPE` to [an expected type listed here](https://minecraft.fandom.com/wiki/Server.properties#level-type).

For some of the level types, `GENERATOR_SETTINGS` can be used to further customize the world generation [as described here](https://minecraft.fandom.com/wiki/Server.properties#generator-settings).

### Custom Server Resource Pack

You can set a link to a custom resource pack and set it's checksum using the `RESOURCE_PACK` and `RESOURCE_PACK_SHA1` options respectively, the default is blank:

    docker run -d -e 'RESOURCE_PACK=http://link.com/to/pack.zip?=1' -e 'RESOURCE_PACK_SHA1=d5db29cd03a2ed055086cef9c31c252b4587d6d0'

You can enforce the resource pack on clients by setting `RESOURCE_PACK_ENFORCE` to `TRUE` (default: `FALSE`).

### Level / World Save Name

You can either switch between world saves or run multiple containers with different saves by using the `LEVEL` option,
where the default is "world":

    docker run -d -e LEVEL=bonus ...

!!! note

    if running multiple containers be sure to either specify a different `-v` host directory for each
`LEVEL` in use or don't use `-v` and the container's filesystem will keep things encapsulated.

!!! info

    Refer to the [data directory](../java/data-directory) section for a visual description of where the `$LEVEL` directory is situated.


### Other server property mappings

| Environment Variable              | Server Property                   |
| --------------------------------- | --------------------------------- |
| PLAYER_IDLE_TIMEOUT               | player-idle-timeout               |
| BROADCAST_CONSOLE_TO_OPS          | broadcast-console-to-ops          |
| BROADCAST_RCON_TO_OPS             | broadcast-rcon-to-ops             |
| ENABLE_JMX                        | enable-jmx-monitoring             |
| SYNC_CHUNK_WRITES                 | sync-chunk-writes                 |
| ENABLE_STATUS                     | enable-status                     |
| ENTITY_BROADCAST_RANGE_PERCENTAGE | entity-broadcast-range-percentage |
| FUNCTION_PERMISSION_LEVEL         | function-permission-level         |
| NETWORK_COMPRESSION_THRESHOLD     | network-compression-threshold     |
| OP_PERMISSION_LEVEL               | op-permission-level               |
| PREVENT_PROXY_CONNECTIONS         | prevent-proxy-connections         |
| USE_NATIVE_TRANSPORT              | use-native-transport              |
| ENFORCE_WHITELIST                 | enforce-whitelist                 |
| ENABLE_WHITELIST                  | white-list and whitelist          |
| SIMULATION_DISTANCE               | simulation-distance               |
