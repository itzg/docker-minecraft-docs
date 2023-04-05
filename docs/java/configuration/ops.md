### Op/Administrator Players

Similar to the [whitelist](./whitelist), to add users as operators (aka adminstrators) to your Minecraft server, you can:  

- Provide te url or path to an ops file via `OPS_FILE` environment variable  
    
    !!! example

    ```
    docker run -d -e OPS_FILE=https://config.example.com/extra/ops.json ...
    ```
- Provide a list of usernames and/or UUIDs separated by commas via the `OPS` environment variable  

    !!! example

    ```
    docker run -d -e OPS=user1,uuid2 ...
    ```

If ops configuration already exists, `OPS_FILE` will not be retrieved and any usernames in `OPS` are **added** to the ops configuration. You can enforce regeneration of the ops configuration on each server startup by setting `OVERRIDE_OPS` to "true". This will delete the ops file before processing ops configuration.

!!! note 

    Similar to whitelists, you can provide both `OPS_FILE` and `OPS`, and Minecraft 1.7.5 or earlier will use `ops.txt` rather than `ops.json`.
