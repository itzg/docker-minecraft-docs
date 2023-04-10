
### Running a Canyon server

[Canyon](https://github.com/canyonmodded/canyon) is a fork of CraftBukkit for Minecraft Beta 1.7.3. It includes multiple enhancements whilst also retaining compatibility with old Bukkit plugins and mods as much as possible.

    -e VERSION=b1.7.3 -e TYPE=CANYON

!!! note 

    Only `VERSION=b1.7.3` is supported. Since that version pre-dates the health check mechanism used by this image, that will need to be disabled by setting `DISABLE_HEALTHCHECK=true`.

By default, the latest build will be used; however, a specific build number can be selected by setting `CANYON_BUILD`, such as

    -e CANYON_BUILD=11
