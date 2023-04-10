
### Game Mode

By default, Minecraft servers are configured to run in Survival mode. You can
change the mode using `MODE` where you can either provide the [standard
numerical values](http://minecraft.gamepedia.com/Game_mode#Game_modes) or the
shortcut values:

- creative
- survival
- adventure
- spectator (only for Minecraft 1.8 or later)

!!! example

    docker run -d -e MODE=creative ...
