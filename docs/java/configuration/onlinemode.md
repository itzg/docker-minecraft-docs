### Online mode

By default, server checks connecting players against Minecraft's account database. If you want to create an offline server or your server is not connected to the internet, you can disable the server to try connecting to minecraft.net to authenticate players with environment variable `ONLINE_MODE`, like this

    docker run -d -e ONLINE_MODE=FALSE ...
