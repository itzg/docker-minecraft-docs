
### Whitelist Players

!!! note 
    
    It is very important to set this with servers exposed to the internet where you want only limited players to join.

To whitelist players for your Minecraft server, you can:  

- Provide a list of usernames and/or UUIDs separated by commas via the `WHITELIST` environment variable  
  `docker run -d -e WHITELIST=user1,uuid2 ...`
- Provide the url or path to a whitelist file via `WHITELIST_FILE` environment variable  
  `docker run -d -e WHITELIST_FILE=/extra/whitelist.json ...`

When either is set, [whitelisting of connecting users](https://minecraft.fandom.com/wiki/Server.properties#white-list) is enabled . If managing the list manually, `ENABLE_WHITELIST` can be set to "true" to set the `white-list` property.

If whitelist configuration already exists, `WHITELIST_FILE` will not be retrieved and any usernames in `WHITELIST` are **added** to the whitelist configuration. You can enforce regeneration of the whitelist on each server startup by setting `OVERRIDE_WHITELIST` to "true". This will delete the whitelist file before processing whitelist configuration.

!!! note

    You can provide both `WHITELIST_FILE` and `WHITELIST`, which are processed in that order.

!!! note 
    
    UUIDs passed via `WHITELIST` need to be the dashed variant, otherwise it not be recognised and instead added as a username.
    
    If running Minecraft 1.7.5 or earlier, these variables will apply to `white-list.txt`, with 1.7.6 implementing support for `whitelist.json`. Make sure your `WHITELIST_FILE` is in the appropriate format.

To [enforce the whitelist changes immediately](https://minecraft.fandom.com/wiki/Server.properties#enforce-whitelist) when whitelist commands are used , set `ENFORCE_WHITELIST` to "true".
