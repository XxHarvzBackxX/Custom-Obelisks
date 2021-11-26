← [README](README.md)
This document helps mod authors create a content pack for Custom Obelisks.

**See the [main README](README.md) for other info**.

# Content Packs

## CP Element
This framework works in harmony with Content Patcher; you'll need to load your assets through a \[CP] pack. Example:
```js
{
  "Format": "1.23.0",
  "Changes": [
    { // load texture
      "LogName": "Obelisk Texture Load",
      "Action": "Load",
      "Target": "Buildings/NAME",
      "FromFile": "assets/NAME.png"
    },
    { // load blueprint
      "LogName": "Patch Obelisk Blueprint",
      "Action": "EditData",
      "Target": "Data/Blueprints",
      "Entries": {
        "NAME": "709 400 388 250 771 750/3/2/-1/-1/-2/-1/null/Secret Woods Obelisk/Warps you to the Secret Woods./Buildings/none/48/128/-1/null/Farm/7500/true"
      }
    }
  ]
}
```
For more info on Content Patcher, see [the documentation](https://github.com/Pathoschild/StardewMods/blob/develop/ContentPatcher/docs/author-guide.md) for it.
For info on the data entries in `Data/Blueprints`, see [the page on it in the Stardew Wiki](https://stardewvalleywiki.com/Modding:Blueprint_data).

## How-to
In your `manifest.json` file, specify that this is a content pack for CO by placing CO's unique ID inside the `ContentPackFor` field (`harvz.CustomObelisks`).
Next, create a `content.json` file. It should look similar to this:
```js
{
  "Obelisks": [
    {
      "Name": "...",
      "InternalName": "...",
      "WhereToWarp": "...",
      "ToX": 0,
      "ToY": 0
    }
  ]
}
```

## Fields

Field                | Valid Entries                        
-------------------- | ------------------------------- 
Name                 | `(string)` The display name (translations, input your localised name).
InternalName         | `(string)` The internal name (translations, use whatever the internal name is).
WhereToWarp          | `(string)` The internal name of the location to warp to.
ToX                  | `(int)` The X coordinate where to warp the player.
ToY                  | `(int)` The Y coordinate where to warp the player.

An example content pack can be found on the [Nexus page under files tab](https://www.nexusmods.com/stardewvalley/mods/10202?tab=files).

### Multiple Obelisks
To add multiple obelisks, simply add multiple 'Obelisks' entries. Copy and paste the first one, adding a comma to the end, and fill in the appropriate info. Example:
```js
{
  "Obelisks": [
    {
      "Name": "Secret Woods Obelisk",
      "InternalName": "Secret Woods Obelisk",
      "WhereToWarp": "Woods",
      "ToX": 0,
      "ToY": 0
    },
    {
      "Name": "Town Obelisk",
      "InternalName": "Town Obelisk",
      "WhereToWarp": "Town",
      "ToX": 0,
      "ToY": 0
    }
  ]
}
```


# Questions
If you have any questions, feel free to open an issue on the Github, leave a comment on Nexus, or DM me on Discord at `XxHarvzBackxX#3665`!

<large>-Harvz</large>
