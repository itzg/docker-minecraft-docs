Also known as behavior or resource packs, in order to add mods into your server you can follow these steps, tested with [OPS (One Player Sleep)](https://foxynotail.com/addons/ops/) and [bedrocktweaks](https://bedrocktweaks.net/resource-packs/)

1. Install the mcpack or mcaddon on the client side first, just to make it easier to copy the files to the server, for Windows 10 files should be located on `C:\Users\USER\AppData\Local\Packages\Microsoft.MinecraftUWP_*\LocalState\games\com.mojang`.
2. Copy over the folders of the mods from either behavior_packs or resource_packs into the server's volume.
> If you want to install them without using a client you should be able to unzip the mods directly into the server's volume, .mcaddon should go into behavior_packs and .mcpack into resource_packs. Both .mcaddon and .mcpack are actually renamed .zip files.
3. On the server's volume we will need to edit `valid_known_packs.json`, you can just copy and paste the definition of another pack and replace path, uuid and version with the mod being installed, uuid and version can be found on the mod behavior or resource _packs/mod/manifest.json, path is the path to the mod's folder.
```
	{
		"file_system" : "RawPath",
		"path" : "behavior_packs/Foxy'sOneP",
		"uuid" : "5f51f7b7-85dc-44da-a3ef-a48d8414e4d5",
		"version" : "3.0.0"
	}
```
4. Lastly create on the server's volume `worlds/$level-name/world_behavior_packs.json`, you'll need to add an entry for each mod like on the previous manifest.json, we only need the uuid now called pack_id and the version replacing dots with commas and double quotes with [ ].
> You can also create a `worlds/$level-name/world_resource_packs.json` but I have seen that putting both resource and behavior packs inside the same json works just fine
```
[
	{
		"pack_id" : "5f51f7b7-85dc-44da-a3ef-a48d8414e4d5",
		"version" : [ 3, 0, 0 ]
	}
]
```
5. Restart the server and the mods should be enabled now! when connecting you will get a prompt asking if you want to "Download & Join" or just "Join", You need to Download & Join if you want to actually see the new resource pack added to the server.
This prompt is exclusive to resource packs as these alter how minecraft looks while behavior packs alter how minecraft functions and don't need to be downloaded or installed on the client side.
> If you want to force the resource pack on all clients, there's an option `texturepack-required=false` in `server.properties` that should be changed to `true`.
> Resource packs can be deleted by going into Settings > Storage > Cached Data, then selecting the pack and clicking on the trash can.

For more information [FoxyNoTail](https://www.youtube.com/watch?v=nWBM4UFm0rQ&t=1380s) did a video explaining the same on a server running on Windows.

## More information

For more information about managing Bedrock Dedicated Servers in general, [check out this Reddit post](https://old.reddit.com/user/ProfessorValko/comments/9f438p/bedrock_dedicated_server_tutorial/).

