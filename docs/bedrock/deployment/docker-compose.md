The [examples](https://github.com/itzg/docker-minecraft-bedrock-server/blob/master/examples) directory contains [an example Docker compose file](https://github.com/itzg/docker-minecraft-bedrock-server/blob/master/examples/docker-compose.yml) that declares:

- a service running the bedrock server container and exposing UDP port 19132
- a volume to be attached to the service

The service configuration includes some examples of configuring the server properties via environment variables:

``` yaml
environment:
  EULA: "TRUE"
  GAMEMODE: survival
  DIFFICULTY: normal
```

From with in the `examples` directory, you can deploy the composition by using:

``` bash
docker-compose up -d
```

You can follow the logs using:
``` bash
docker-compose logs -f bds
```
