
To configure a flat, creative server instead of the default

``` 
docker run -d -it --name bds-flat-creative \
  -e EULA=TRUE -e LEVEL_TYPE=flat -e GAMEMODE=creative \
  -p 19132:19132/udp itzg/minecraft-bedrock-server
```

## Executing server commands

This image comes bundled with a script called `send-command` that will send a Bedrock command and argument to the Bedrock server console. The output of the command only be visible in the container logs.

For example:

```
docker exec CONTAINER_NAME_OR_ID send-command gamerule dofiretick false
```

Alternatively, with stdin and tty enabled (such as using `-it`), attach to the container's console by its name or ID using:

```shell script
docker attach CONTAINER_NAME_OR_ID
``` 

While attached, you can execute any server-side commands, such as op'ing your player to be admin:

```
gamerule dofiretick false
```

When finished, detach from the server console using Ctrl-p, Ctrl-q

