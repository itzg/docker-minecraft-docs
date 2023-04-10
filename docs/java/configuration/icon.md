### Server icon

A server icon can be configured using the `ICON` variable. The image will be automatically
downloaded, scaled, and converted from any other image format:

    docker run -d -e ICON=http://..../some/image.png ...

The server icon which has been set doesn't get overridden by default. It can be changed and overridden by setting `OVERRIDE_ICON` to `TRUE`.

    docker run -d -e ICON=http://..../some/other/image.png -e OVERRIDE_ICON=TRUE...
