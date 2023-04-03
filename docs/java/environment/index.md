### **OS OPTIONS**

<table style="width:100%">
    <thead>
        <tr>
            <th>NAME</th>
            <th>DESCRIPTION</th>
            <th>DEFAULT</th>
            <th>REQUIRED</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>UID</code></td>
            <td>The linux user id to run as</td>
            <td><code>1000</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>GID</code></td>
            <td>The linux group id to run as</td>
            <td><code>1000</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>MEMORY</code></td>
            <td>The image declares an initial and maximum Java memory-heap limit of 1 GB.</td>
            <td><code>1G</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>INIT_MEMORY</code></td>
            <td>Independently sets the initial heap size</td>
            <td><code>1G</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>MAX_MEMORY</code></td>
            <td>independently sets the max heap size</td>
            <td><code>1G</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>TZ</code></td>
            <td>You can configure the timezone to match yours by setting the TZ environment variable.

alternatively, you can mount: <code>/etc/localtime:/etc/localtime:ro

/etc/timezone:/etc/timezone:ro</code>
            </td>
            <td><code>1G</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ENABLE_ROLLING_LOGS</code></td>
            <td>By default the vanilla log file will grow without limit. The logger can be reconfigured to use a rolling log files strategy by setting this to <code>true</code></td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ENABLE_JMX</code></td>
            <td>To enable remote JMX, such as for profiling with VisualVM or JMC, add the environment variable ENABLE_JMX=true</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>JMX_HOST</code></td>
            <td>If JMX is enabled, set JMX_HOST to the IP/host running the Docker container, and add a port forwarding of TCP port 7091</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>USE_AIKAR_FLAGS</code></td>
            <td><a href="https://aikar.co/2018/07/02/tuning-the-jvm-g1gc-garbage-collector-flags-for-minecraft/">Aikar has done some research</a> into finding the optimal JVM flags for GC tuning, which becomes more important as more users are connected concurrently</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>JVM_OPTS</code></td>
            <td>General JVM options can be passed to the Minecraft Server invocation by passing a <code>JVM_OPTS</code> environment variable. The JVM requires -XX options to precede -X options, so those can be declared in <code>JVM_XX_OPTS</code>. Both variables are space-delimited, raw JVM arguments</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>JVM_XX_OPTS</code></td>
            <td>General JVM options can be passed to the Minecraft Server invocation by passing a <code>JVM_OPTS</code> environment variable. The JVM requires -XX options to precede -X options, so those can be declared in <code>JVM_XX_OPTS</code>. Both variables are space-delimited, raw JVM arguments</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>JVM_DD_OPTS</code></td>
            <td>As a shorthand for passing several system properties as -D arguments, you can instead pass a comma separated list of name=value or name:value pairs with JVM_DD_OPTS. (The colon syntax is provided for management platforms like Plesk that don't allow = inside a value.)</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>EXTRA_ARGS</code></td>
            <td>Arguments that would usually be passed to the jar file (those which are written after the filename)</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>LOG_TIMESTAMP </code></td>
            <td>To include the timestamp with each log set to <code>true</code></td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
    </tbody>
</table>

### **SERVER**

<table style="width:100%">
    <thead>
        <tr>
            <th>NAME</th>
            <th>DESCRIPTION</th>
            <th>DEFAULT</th>
            <th>REQUIRED</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>TYPE</code></td>
            <td>The server <a href="../server-types/">type</a></td>
            <td><code>VANILLA</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>EULA</code></td>
            <td>You <strong>MUST</strong> set this to <code>true</code></td>
            <td><code>&nbsp;</code></td>
            <td>✅</td>
        </tr>
        <tr>
            <td><code>VERSION</code></td>
            <td>The minecraft version</td>
            <td><code>LATEST</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>MOTD</code></td>
            <td>Set the server log in message.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>DIFFICULTY</code></td>
            <td>The difficulty level. Available values: <code>peaceful</code>,<code>easy</code>,<code>normal</code>,<code>hard</code></td>
            <td><code>easy</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ICON</code></td>
            <td>The url or file path for the icon image to use for the server. It will be downloaded, scaled, and converted to the proper format.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>OVERRIDE_ICON</code></td>
            <td>The server icon which has been set doesn't get overridden by default. Set this to <code>TRUE</code> to override the icon</td>
            <td><code>FALSE</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>MAX_PLAYERS</code></td>
            <td>The maximum number of players that can join the server.</td>
            <td><code>20</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>MAX_WORLD_SIZE</code></td>
            <td>The maximum possible size in blocks, expressed as a radius.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ALLOW_NETHER</code></td>
            <td>Allows players to travel to the Nether</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ANNOUNCE_PLAYER_ACHIEVEMENTS</code></td>
            <td>Allows server to announce when a player gets an achievement.</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ENABLE_COMMAND_BLOCK</code></td>
            <td>Enables the command blocks.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>FORCE_GAMEMODE</code></td>
            <td>Force players to join in the default game mode.</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>GENERATE_STRUCTURES</code></td>
            <td>Defines whether structures (such as villages) will be generated.</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>HARDCORE</code></td>
            <td>If set to <code>true</code>, players will be set to spectator mode if they die.</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SNOOPER_ENABLED</code></td>
            <td>If set to false, the server will not send data to snoop.minecraft.net server.</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>MAX_BUILD_HEIGHT</code></td>
            <td>The maximum height in which building is allowed. Terrain may still naturally generate above a low height limit.</td>
            <td><code>256</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SPAWN_ANIMALS</code></td>
            <td>Determines if animals will be able to spawn.</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SPAWN_MONSTERS</code></td>
            <td>Determines if monsters will be spawned.</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SPAWN_NPCS</code></td>
            <td>Determines if villagers will be spawned.</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SPAWN_PROTECTION</code></td>
            <td>Sets the area that non-ops can not edit (0 to disable)</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>VIEW_DISTANCE</code></td>
            <td>Sets the amount of world data the server sends the client, measured in chunks in each direction of the player (radius, not diameter). It determines the server-side viewing distance.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SEED</code></td>
            <td>Sets the seed to create the Minecraft world. If you use a negative number, make sure that it is in quotes.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>MODE</code></td>
            <td>Minecraft servers are configured to run in Survival mode by default. You can change the mode using MODE where you can either provide the <a href="http://minecraft.gamepedia.com/Game_mode#Game_modes">standard numerical values</a> or the shortcut values:<br />
            <ul>
                <li>creative</li>
                <li>survival</li>
                <li>adventure</li>
                <li>spectator(minecraft 1.8 or later)</li>
            </ul></td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>PVP</code></td>
            <td>By default, servers are created with player-vs-player (PVP) mode enabled.</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>LEVEL_TYPE</code></td>
            <td>By default, a standard world is generated with hills, valleys, water, etc. A different level type can be configured by setting LEVEL_TYPE to <a href="https://minecraft.fandom.com/wiki/Server.properties#level-type">an expected type listed here</a>.
            </td>
            <td><code>minecraft:default</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>GENERATOR_SETTINGS</code></td>
            <td>For some of the level types, <code>GENERATOR_SETTINGS</code> can be used to further customize the world generation <a href="https://minecraft.fandom.com/wiki/Server.properties#generator-settings">as described here</a>.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>LEVEL</code></td>
            <td>You can either switch between world saves or run multiple containers with different saves by using the LEVEL option</td>
            <td><code>world</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ONLINE_MODE</code></td>
            <td>By default, server checks connecting players against Minecraft's account database. If you want to create an offline server or your server is not connected to the internet, you can disable the server to try connecting to minecraft.net to authenticate players</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ALLOW_FLIGHT</code></td>
            <td>Allows users to use flight on your server while in Survival mode, if they have a mod that provides flight installed.</td>
            <td><code>FALSE</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SERVER_NAME</code></td>
            <td>The server name</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SERVER_PORT</code></td>
            <td>Only change this value if you know what you're doing. It is only needed when using host networking and it is rare that host networking should be used.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>PLAYER_IDLE_TIMEOUT</code></td>
            <td>player-idle-timeout</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ENABLE_JMX</code></td>
            <td>enable-jmx-monitoring</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SYNC_CHUNK_WRITES</code></td>
            <td>sync-chunk-writes</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ENABLE_STATUS</code></td>
            <td>enable-status</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>ENTITY_BROADCAST_RANGE_PERCENTAGE</code></td>
            <td>entity-broadcast-range-percentage</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>FUNCTION_PERMISSION_LEVEL</code></td>
            <td>function-permission-level</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>NETWORK_COMPRESSION_THRESHOLD</code></td>
            <td>network-compression-threshold</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>OP_PERMISSION_LEVEL</code></td>
            <td>op-permission-level</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>PREVENT_PROXY_CONNECTIONS</code></td>
            <td>prevent-proxy-connections</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>USE_NATIVE_TRANSPORT</code></td>
            <td>use-native-transport</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SIMULATION_DISTANCE</code></td>
            <td>simulation-distance</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>EXEC_DIRECTLY</code></td>
            <td>If you would like to docker attach to the Minecraft server console with color and interactive capabilities, then set to <code>true</code></td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>STOP_SERVER_ANNOUNCE_DELAY</code></td>
            <td>To allow time for players to finish what they're doing during a graceful server shutdown, set <code>STOP_SERVER_ANNOUNCE_DELAY</code> to a number of seconds to delay after an announcement is posted by the server.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>PROXY</code></td>
            <td>You may configure the use of an HTTP/HTTPS proxy by passing the proxy's URL</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>CONSOLE</code></td>
            <td>Some older versions (pre-1.14) of Spigot required <code>--noconsole</code> to be passed when detaching stdin</td>
            <td><code>TRUE</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>GUI</code></td>
            <td>Some older servers get confused and think that the GUI interface is enabled.</td>
            <td><code>TRUE</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>STOP_DURATION</code></td>
            <td>When the container is signalled to stop, the Minecraft process wrapper will attempt to send a "stop" command via RCON or console and waits for the process to gracefully finish.</td>
            <td><code>60</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>SETUP_ONLY</code></td>
            <td>If you are using a host-attached data directory, then you can have the image setup the Minecraft server files and stop prior to launching the server process by setting this to <code>true</code></td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>USE_SIMD_FLAGS</code></td>
            <td>Support for optimized SIMD operation</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>DISABLE_HEALTHCHECK</code></td>
            <td>This will disable the HealthCheck.</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <!-- <tr>
            <td><code></code></td>
            <td></td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr> -->
    </tbody>
</table>

### PLUGINS / MODS / CONFIGS

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>COPY_PLUGINS_SRC</code></td>
      <td>Copy the contents of <code>/data/plugins</code> from the defined source.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>COPY_PLUGINS_DEST</code></td>
      <td>Copy the contents of <code>/data/plugins</code> from the defined source to this destination.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>COPY_MODS_SRC</code></td>
      <td>Copy the contents of <code>/data/mods</code> from the defined source.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>COPY_MODS_DEST</code></td>
      <td>Copy the contents of <code>/data/mods</code> from the defined source to this destination.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>COPY_CONFIG_SRC</code></td>
      <td>Copy the contents of <code>/data/config</code> from the defined source.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>COPY_CONFIG_DEST</code></td>
      <td>Copy the contents of <code>/data/config</code> from the defined source to this destination.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>SYNC_SKIP_NEWER_IN_DESTINATION</code></td>
      <td>if you want files from <code>/plugins</code> to take precedence over newer files in <code>/data/plugins</code></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REPLACE_ENV_SUFFIXES</code></td>
      <td>By default, the environment variable processing is performed on synchronized files that match the expected suffixes</td>
      <td><code>yml,yaml,txt,cfg,conf,properties,hjson,json,tml,toml</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REPLACE_ENV_VARIABLES_EXCLUDES</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REPLACE_ENV_VARIABLES_EXCLUDE_PATHS</code></td>
      <td></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REPLACE_ENV_DURING_SYNC </code></td>
      <td>Disable the environment replacement during sync.</td>
      <td><code>true</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REMOVE_OLD_MODS</code></td>
      <td></td>
      <td><code>false</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REMOVE_OLD_MODS_INCLUDE</code></td>
      <td>You can fine tune the removal process by specifying mods to include</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REMOVE_OLD_MODS_EXCLUDE</code></td>
      <td>You can fine tune the removal process by specifying mods to exclude</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>REMOVE_OLD_MODS_DEPTH</code></td>
      <td>The depth of folders to delete for old mods.</td>
      <td><code>16</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **CUSTOM RESOURCE PACK**

<table style="width:100%">
    <thead>
        <tr>
            <th>NAME</th>
            <th>DESCRIPTION</th>
            <th>DEFAULT</th>
            <th>REQUIRED</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>RESOURCE_PACK</code></td>
            <td>A link to a custom resource pack</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RESOURCE_PACK_SHA1</code></td>
            <td>The checksum for the custom resource pack</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RESOURCE_PACK_ENFORCE</code></td>
            <td>Enforce the resource pack on clients</td>
            <td><code>FALSE</code></td>
            <td>⬜️</td>
        </tr>
    </tbody>
</table>

### **[WHITELIST](../configuration/#whitelist-players)**

<table style="width:100%">
    <thead>
        <tr>
            <th>NAME</th>
            <th>DESCRIPTION</th>
            <th>DEFAULT</th>
            <th>REQUIRED</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>ENABLE_WHITELIST</code></td>
            <td>Enable the whitelist to manually manage the whitelist</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>WHITELIST</code></td>
            <td>A list of usernames and/or UUIDs separated by comma</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>WHITELIST_FILE</code></td>
            <td>A url or file path to a whitelist <code>json</code> formatted file.</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>OVERRIDE_WHITELIST</code></td>
            <td>Enforce regeneration of the whitelist on each server startup.</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
    </tbody>
</table>

### **[RCON](../configuration/#rcon)**

<table style="width:100%">
    <thead>
        <tr>
            <th>NAME</th>
            <th>DESCRIPTION</th>
            <th>DEFAULT</th>
            <th>REQUIRED</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>ENABLE_RCON</code></td>
            <td>Should RCON be enabled</td>
            <td><code>true</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RCON_PASSWORD</code></td>
            <td>You <strong>MUST</strong> change this value</td>
            <td><code>minecraft</code></td>
            <td>✅</td>
        </tr>
        <tr>
            <td><code>RCON_PORT</code></td>
            <td>The port for RCON</td>
            <td><code>25575</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>BROADCAST_RCON_TO_OPS</code></td>
            <td>Should RCON be enabled</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RCON_CMDS_STARTUP</code></td>
            <td>RCON commands can be configured to execute when the server starts, a client connects, or a client disconnects</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RCON_CMDS_ON_CONNECT</code></td>
            <td>RCON commands can be configured to execute when the server starts, a client connects, or a client disconnects</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RCON_CMDS_ON_DISCONNECT</code></td>
            <td>RCON commands can be configured to execute when the server starts, a client connects, or a client disconnects</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RCON_CMDS_LAST_DISCONNECT</code></td>
            <td>RCON commands can be configured to execute when the server starts, a client connects, or a client disconnects</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>RCON_CMDS_STARTUP</code></td>
            <td>RCON commands can be configured to execute when the server starts, a client connects, or a client disconnects</td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr>
    </tbody>
</table>

### **[AUTOPAUSE](../autopause/)**

!!! note

    Autopause is not compatible with `EXEC_DIRECTLY=true` and the two cannot be set together.

<table style="width:100%">
    <thead>
        <tr>
            <th>NAME</th>
            <th>DESCRIPTION</th>
            <th>DEFAULT</th>
            <th>REQUIRED</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>ENABLE_AUTOPAUSE</code></td>
            <td>Enable the Autopause functionality</td>
            <td><code>FALSE</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>AUTOPAUSE_TIMEOUT_EST</code></td>
            <td>describes the time between the last client disconnect and the pausing of the process</td>
            <td><code>3600</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>AUTOPAUSE_TIMEOUT_INIT</code></td>
            <td>describes the time between server start and the pausing of the process, when no client connects in-between</td>
            <td><code>600</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>AUTOPAUSE_TIMEOUT_KN</code></td>
            <td>describes the time between knocking of the port (e.g. by the main menu ping) and the pausing of the process, when no client connects in-between</td>
            <td><code>120</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>AUTOPAUSE_PERIOD</code></td>
            <td>describes period of the daemonized state machine, that handles the pausing of the process</td>
            <td><code>10</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>AUTOPAUSE_KNOCK_INTERFACE</code></td>
            <td>Describes the interface passed to the knockd daemon. If the default interface does not work, run the ifconfig command inside the container and derive the interface receiving the incoming connection from its output. The passed interface must exist inside the container. Using the loopback interface (lo) does likely not yield the desired results.</td>
            <td><code>eth0</code></td>
            <td>⬜️</td>
        </tr>
        <tr>
            <td><code>DEBUG_AUTOPAUSE</code></td>
            <td>Adds additional debugging output for AutoPause</td>
            <td><code>false</code></td>
            <td>⬜️</td>
        </tr>
    </tbody>
</table>

### **[AUTOSTOP](../autopause/autostop/)**

!!! note

    AutoStop function is incompatible with the Autopause functionality, as they basically cancel out each other.

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>ENABLE_AUTOSTOP</code></td>
      <td>Enable the AutoStop functionality</td>
      <td><code>FALSE</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>AUTOSTOP_TIMEOUT_EST</code></td>
      <td>describes the time between the last client disconnect and the stopping of the server</td>
      <td><code>3600</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>AUTOSTOP_TIMEOUT_INIT</code></td>
      <td>describes the time between server start and the stopping of the server, when no client connects in-between</td>
      <td><code>1800</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>AUTOSTOP_PERIOD</code></td>
      <td>describes period of the daemonized state machine, that handles the stopping of the serve</td>
      <td><code>10</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>DEBUG_AUTOSTOP</code></td>
      <td>Adds additional logging for AutoStop</td>
      <td><code>false</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>


### **[CURSEFORGE](../server-types/#auto-curseforge-management)**

!!! note

     A CurseForge API key is required to use a CurseForge type server. Go to their [developer console](https://console.curseforge.com/), generate an API key, and set the environment variable CF_API_KEY

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>CF_API_KEY</code></td>
      <td><strong>YOUR</strong> CurseForge (Eternal) API Key.</td>
      <td><code></code></td>
      <td>✅</td>
    </tr>
    <tr>
      <td><code>CF_PAGE_URL</code></td>
      <td>Pass a page URL to the modpack or a specific file</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_MODPACK_ZIP</code></td>
      <td>If the authors of the modpack have disallowed project distribution, then the desired <strong>client</strong> modpack zip will need to be manually downloaded and made available to the container. The path to that file must be passed to this environment variable.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_SLUG</code></td>
      <td>Instead of a URL, the modpack slug can be provided.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_FILE_ID</code></td>
      <td>The mod curseforge numerical ID.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_FILENAME_MATCHER</code></td>
      <td>Specify a substring to match the desired filename</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_EXCLUDE_INCLUDE_FILE</code></td>
      <td>Global and per modpack exclusions can be declared in a JSON file and referenced with this variable. <br /><br />By default, the <a href="https://github.com/itzg/docker-minecraft-server/blob/master/files/cf-exclude-include.json">file bundled with the image</a> will be used, but can be disabled by setting this to an empty string. The schema of this file is <a href="https://github.com/itzg/mc-image-helper#excludeinclude-file-schema">documented here</a>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_EXCLUDE_MODS</code></td>
      <td>Mods can be excluded by passing a comma or space delimited list of project slugs or IDs</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_FORCE_INCLUDE_MODS</code></td>
      <td>Mods can be included by passing a comma or space delimited list of project slugs or IDs</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_FORCE_SYNCHRONIZE</code></td>
      <td>Forces the excludes/includes to be re-evaluated</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_SET_LEVEL_FROM</code></td>
      <td>Some modpacks come with world/save data via a worlds file and/or the overrides provided with the modpack. Either approach can be selected to set the LEVEL to the resulting saves directory by setting this to either:
      <ul>
        <li>WORLD_FILE</li>
        <li>OVERRIDES</li>
      </ul></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_PARALLEL_DOWNLOADS</code></td>
      <td>specify how many parallel mod downloads to perform</td>
      <td><code>4</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>CF_OVERRIDES_SKIP_EXISTING</code></td>
      <td>if set, files in the overrides that already exist in the data directory are skipped. world data is always skipped, if present.</td>
      <td><code>false</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **[FABRIC](../server-types/#running-a-fabric-server)**
<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>FABRIC_LAUNCHER</code></td>
      <td>Path to a custom launcher jar, relative to <code>/data</code></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FABRIC_LAUNCHER_URL</code></td>
      <td>A URL to a custom launcher jar</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FABRIC_LAUNCHER_VERSION</code></td>
      <td>A specific launcher version other than the latest</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FABRIC_LOADER_VERSION</code></td>
      <td>A specific loader version other than the latest</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>


### **[FORGE](../mods-plugins/#forgeapi-usage-to-use-non-version-specific-projects)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>FORGE_VERSION</code></td>
      <td>The specific Forge Version</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FORGE_INSTALLER</code></td>
      <td>Path to a pre-downloaded forge installer</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FORGE_INSTALLER_URL</code></td>
      <td>A Forge installer from a custom location</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FORGE_FORCE_REINSTALL</code></td>
      <td>If an error occurred while installing Forge, it might be possible to resolve by temporarily setting <code>FORGE_FORCE_REINSTALL</code> to <code>true</code>. Be sure to remove that variable after successfully starting the server.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>


### **[QUILT](../server-types/#running-a-quilt-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>QUILT_LAUNCHER</code></td>
      <td>Path to a custom launcher jar, relative to <code>/data</code></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>QUILT_LAUNCHER_URL</code></td>
      <td>Url to a custom launcher jar.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>QUILT_LOADER_VERSION</code></td>
      <td>The specific Quilt Loader Version</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>QUILT_INSTALLER_VERSION</code></td>
      <td>The specific Quilt Launcher Version</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **[BUKKIT](../server-types/#running-a-bukkitspigot-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>FORCE_REDOWNLOAD</code></td>
      <td>If the downloaded server jar is corrupted, set this to <code>true</code> to force a re-download during the next container startup. After successfully re-downloading you should remove this, or set it to <code>false</code>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>BUKKIT_DOWNLOAD_URL</code></td>
      <td>If you are hosting your own copy of Bukkit you can override the download URLs</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **[SPIGOT](../server-types/#running-a-bukkitspigot-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>FORCE_REDOWNLOAD</code></td>
      <td>If the downloaded server jar is corrupted, set this to <code>true</code> to force a re-download during the next container startup. After successfully re-downloading you should remove this, or set it to <code>false</code>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>SPIGOT_DOWNLOAD_URL</code></td>
      <td>If you are hosting your own copy of Spigot you can override the download URLs</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>BUILD_FROM_SOURCE</code></td>
      <td>You can build spigot from source by setting this to <code>true</code></td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>SPIGET_RESOURCES</code></td>
      <td>Set with a comma-separated list of SpigotMC resource IDs to automatically download <a href="https://www.spigotmc.org/resources/">SpigotMC resources/plugins</a> using <a href="https://spiget.org/">the spiget API</a>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **[PAPER](../server-types/#running-a-paper-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>PAPERBUILD</code></td>
      <td>By default, the container will run the latest build of <a href="https://papermc.io/downloads">Paper server</a> but you can also choose to run a specific build with</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PAPER_DOWNLOAD_URL</code></td>
      <td>If you are hosting your own copy of Paper you can override the download URLs</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>SPIGET_RESOURCES</code></td>
      <td>Set with a comma-separated list of SpigotMC resource IDs to automatically download <a href="https://www.spigotmc.org/resources/">SpigotMC resources/plugins</a> using <a href="https://spiget.org/">the spiget API</a>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>


### **[PUFFERFISH](../server-types/#running-a-pufferfish-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>PUFFERFISH_BUILD</code></td>
      <td>Set a specific Pufferfish build to use.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FORCE_REDOWNLOAD</code></td>
      <td>If the downloaded server jar is corrupted, set this to <code>true</code> to force a re-download during the next container startup. After successfully re-downloading you should remove this, or set it to <code>false</code>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>USE_FLARE_FLAGS</code></td>
      <td>To enable the JVM flags required to fully support the <a href="https://blog.airplane.gg/flare">Flare profiling suite</a>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **[PURPUR](../server-types/#running-a-purpur-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>PURPUR_BUILD</code></td>
      <td>Set a specific PURPUR build to use.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>FORCE_REDOWNLOAD</code></td>
      <td>If the downloaded server jar is corrupted, set this to <code>true</code> to force a re-download during the next container startup. After successfully re-downloading you should remove this, or set it to <code>false</code>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>USE_FLARE_FLAGS</code></td>
      <td>To enable the JVM flags required to fully support the <a href="https://blog.airplane.gg/flare">Flare profiling suite</a>.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>PURPUR_DOWNLOAD_URL</code></td>
      <td>Set URL to download Purpur from custom URL.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **[MOHIST](../server-types/#running-a-mohist-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>MOHIST_BUILD</code></td>
      <td>Set a specific Mohist build to use.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>



### **[CANYON](../server-types/#running-a-canyon-server)**

!!! note

    Only `VERSION=b1.7.3` is supported. Since that version pre-dates the health check mechanism used by this image, that will need to be disabled by setting `DISABLE_HEALTHCHECK=true`.

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>CANYON_BUILD</code></td>
      <td>Set a specific CANYON build to use.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>


### **[SPONGEVANILLA](../server-types/#running-a-spongevanilla-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>SPONGEVERSION</code></td>
      <td>Set a specific version of Sponge to use.</td>
      <td><code>STABLE</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **[LIMBO](../server-types/#running-a-limbo-server)**

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>LIMBO_BUILD</code></td>
      <td>Set a specific build to use.</td>
      <td><code>LATEST</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>LIMBO_SCHEMA_FILENAME</code></td>
      <td>The Limbo Schema Filename</td>
      <td><code>default.schem</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>


### **[CRUCIBLE](../server-types/#running-a-crucible-server)**

!!! note

    Crucible is only available for 1.7.10, so be sure to set `VERSION=1.7.10`.

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>CRUCIBLE_RELEASE</code></td>
      <td>Set a specific release to use.</td>
      <td><code>latest</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>LIMBO_SCHEMA_FILENAME</code></td>
      <td>The Limbo Schema Filename</td>
      <td><code>default.schem</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>



### **[FEED THE BEAST](../server-types/#running-a-server-with-a-feed-the-beast-modpack)**

!!! note

    Requires one of the Ubuntu with Hotspot images listed in the [Java versions section](../versions/java/).


<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>FTB_MODPACK_ID</code></td>
      <td>The numerical ID of the modpack to install</td>
      <td><code></code></td>
      <td>✅</td>
    </tr>
    <tr>
      <td><code>FTB_MODPACK_VERSION_ID</code></td>
      <td>The numerical ID of the version to install. If not specified, the latest version will be installed. </td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **MODRINTH**


<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>MODRINTH_PROJECTS</code></td>
      <td>A comma separated list of project slugs (short name) or IDs.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>MODRINTH_DOWNLOAD_OPTIONAL_DEPENDENCIES</code></td>
      <td>required dependencies of the project will always be downloaded and optional dependencies can also be downloaded by setting this to <code>true</code></td>
      <td><code>false</code></td>
      <td>⬜️</td>
    </tr>
    <tr>
      <td><code>MODRINTH_ALLOWED_VERSION_TYPE</code></td>
      <td>the version type is used to determine the newest version to use from each project. The allowed values are <code>release</code>, <code>beta</code>, <code>alpha</code>.</td>
      <td><code>release</code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

### **MODPACK**

Like the `WORLD` option above, you can specify the URL or path of a "mod pack" to download and install into mods for Forge/Fabric or plugins for Bukkit/Spigot. To use this option pass the environment variable `MODPACK`

!!! note

    The referenced URL must be a zip file with one or more jar files at the top level of the zip archive. Make sure the jars are compatible with the particular `TYPE` of server you are running.

<table style="width:100%">
  <thead>
    <tr>
      <th>NAME</th>
      <th>DESCRIPTION</th>
      <th>DEFAULT</th>
      <th>REQUIRED</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>MODPACK</code></td>
      <td>A url to a zip file with one or more jar files at the top level of the zip archive.</td>
      <td><code></code></td>
      <td>⬜️</td>
    </tr>
  </tbody>
</table>

<!-- ✅ ⬜️ -->
<!-- <tr>
            <td><code></code></td>
            <td></td>
            <td><code></code></td>
            <td>⬜️</td>
        </tr> -->
