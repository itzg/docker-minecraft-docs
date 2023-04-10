
### Running a Limbo server

A [Limbo](https://github.com/LOOHP/Limbo) server can be run by setting `TYPE` to `LIMBO`.

Configuration options with defaults:

- `LIMBO_BUILD`=LATEST

  The `VERSION` will be ignored so locate the appropriate value from [here](https://ci.loohpjames.com/job/Limbo/) to match the version expected by clients.

- `FORCE_REDOWNLOAD`=false
- `LIMBO_SCHEMA_FILENAME`=default.schem
- `LEVEL`="Default;${LIMBO_SCHEMA_NAME}"

!!! note

    Instead of using format codes in the MOTD, Limbo requires [JSON chat content](https://minecraft.fandom.com/wiki/Raw_JSON_text_format#Java_Edition). If a plain string is provided, which is the default, then it gets converted into the required JSON structure. 
