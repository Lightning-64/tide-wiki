# Custom Bait Items

As of version 1.3.2, it's possible to use json files in a datapack to give bait properties to any item, modded or not. This could be useful for mod or modpack creators who want to add their own bait items for players to use while fishing.

## Creating the files

Json files for bait items should be placed in the `data/tide/bait/` path in your datapack. Additionally, you can create directories there and all the corrent json files will still be registered.

Each item should have its own json file - it's recommended to name the json file after the item id, but the name is technically optional.

## Json file structure

Inside of each bait data file, there are 3 properties that need to be defined:

- `item` - A string containing item ID of the item you want to add the data to.
- `speed_bonus` - An integer containing the speed bonus of the bait item. See [the bait page](/items/bait-items/#stats) for details on what that means.
- `luck_bonus` - An integer containing the luck bonus of the bait item. See [the bait page](/items/bait-items/#stats) for details on what that means.

Here's an example using a torchflower:

> data/tide/bait/torchflower.json
> ```json
> {
>    "item": "minecraft:torchflower",
>    "speed_bonus": 2,
>    "luck_bonus": 1
> }
> ```

You can check out [Tide's bait data files](https://github.com/Lightning-64/Tide/tree/main/common/src/main/resources/data/tide/bait) as a reference if you need it.

---

!!! note
    This system only supports modifying the speed and luck bonus of bait items. For special properties, such as Magnetic Bait's increased crate chance, you'll need to hardcode those features yourself