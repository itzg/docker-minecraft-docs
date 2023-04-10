
### Running a Purpur server

A [Purpur](https://purpurmc.org/) server, which is "a drop-in replacement for Paper servers designed for configurability and new, fun, exciting gameplay features."

    -e TYPE=PURPUR

!!! note

    The `VERSION` variable is used to lookup a build of Purpur to download

Extra variables:
- `PURPUR_BUILD=LATEST` : set a specific Purpur build to use
- `FORCE_REDOWNLOAD=false` : set to true to force the located server jar to be re-downloaded
- `USE_FLARE_FLAGS=false` : set to true to add appropriate flags for the built-in [Flare](https://blog.airplane.gg/flare) profiler
- `PURPUR_DOWNLOAD_URL=<url>` : set URL to download Purpur from custom URL.
