# Modifying the Journal

## Getting started

As of version 1.3.2, you can add custom pages and profiles to the fishing journal through the use of a datapack! This can be especially useful for modpack creators or mod developers who want to add other fish to the journal that aren't already built in.

To get started, either download the example datapack from [this page](https://github.com/Lightning-64/Tide-example-datapack) by pressing code -> download zip and extracting the files, or just use it as a guide to create your own.

If you downloaded the example datapack, you can open the `pack.mcmeta` and change the description to whatever you want. You should also rename the main folder to something else.

---

## Adding a journal page

To add fish to the journal, you need a page to put them on. If you want to add fish to a page that already exists, you can skip this step.

Page data is stored in the `pages` folder at `data/tide/journal/pages`. To create a page, create a json file with the id of the page you want to create, or modify the existing `example.json`

### Json file structure

* **`id`**: This is the ID of the page you want to create. It should be all lowercase with no spaces, such as `example` or `example_page`. This id is referenced whenever you want to add a fish to the page.
* **`name`**: This is the text name of the page that is displayed on the top of the screen. Give it the actual name of your page, such as "Example Page", or use a valid translation key.
* **`content`**: This is the description text that appears below the fish at the bottom of every page. This is to describe what the fish on this page are.
* **`icon`**: This is the item ID of the icon for the page that shows up when the page is unlocked. For example, to make it display some oak planks, you would use `minecraft:oak_planks`.
* **`unlocked_by_default`**: Most journal pages are unlocked when you find a fish that is on the page. Alternatively, you can have the page unlocked from the very beginning by setting this to `true`. Note that this will not unlock the fish on the page by default, only the page itself.

---

## Adding a fish profile

Fish profile data is stored in the `profiles` folder at `data/tide/journal/profiles`. To create a profile, create a json file with the id of the fish profile you want to create, or modify the existing `example_fish.json`

### Json file structure

* **`item`**: The item ID of the fish that you want to add. For example, to add a profile for a cod, you would write `minecraft:cod`.
* **`description`**: The information text that appears below the fish. You can include any relevant information about the fish here, or leave it blank (`""`) to have no description.
* **`page`**: This is the ID of the page that you want this profile to appear on! This is the same name used in the `id` parameter of the page json. If you want to add the fish to an existing page from the tide mod, here's the list of IDs for those pages:
> * Freshwater page: `freshwater`
> * Saltwater page: `saltwater`
> * Underground page: `underground`
> * Depths page: `depths`
> * Biome fish page: `biome`
> * Lava fish page: `lava`
> * Nether page: `nether`
> * End page: `end`
> * Legendary page: `legendary`
* **`location`**: This is a key used to describe where the fish is commonly found! You **must** set this to one of the following options:
> * `any`: "Any"
> * `overworld`: "Overworld"
> * `freshwater`: "Lakes and Rivers"
> * `saltwater`: "Oceans"
> * `underground`: "Underground (stone layer)"
> * `depths`: "Deep underground (deepslate layer)"
> * `lava`: "Overworld lava pools"
> * `nether`: "Nether lava oceans"
> * `end`: "End lakes and ponds"
> * `badlands`: "Badlands"
> * `birch`: "Birch forests"
> * `cherry`: "Cherry groves"
> * `deep_dark`: "Deep dark"
> * `desert`: "Desert"
> * `dripstone`: "Dripstone caves"
> * `forest`: "Oak and mixed forests"
> * `frozen`: "Cold and frozen biomes"
> * `jungle`: "Jungles"
> * `lush_caves`: "Lush caves"
> * `mountain`: "Mountains and peaks"
> * `mushroom`: "Mushroom islands"
> * `plains`: "Plains"
> * `savanna`: "Savannas"
> * `swamp`: "Swamps"
> * `taiga`: "Taigas"
> * `everbright`: "Everbright" (for blue skies mod)
> * `everdawn`: "Everdawn" (for blue skies mod)
> * `shipwrecks`: "Shipwrecks"
> * `structures`: "Some structures"
* **`location`**: This is a key used to describe what conditions the fish is commonly found in! You **must** set this to one of the following:
> * `any`: "Any"
> * `normal`: "Average"
> * `cold`: "Cold"
> * `warm`: "Warm"
> * `very_hot`: "Very hot" (used for lava fish)
> * `lucky`: "Maximum luck" (used for midas fish)
> * `full_new_moon`: "Full/new moon" (used for voidseeker)
> * `night_full_moon`: "At night, full moon" (used for starfish)
> * `raids`: "During raids" (for fish of thieves mod)
> * `thunderstorms`: "During thunderstorms"

---

## Removing a fish

As of version 1.3.3, you can remove existing profile entries from the journal! This could be done if there are conflicts. Note that this won't remove the item from the game itself, it will only remove the journal entry for the fish. This system will also work on modded fish.

Removal data is stored in the `removals` folder at `data/tide/journal/removals`. To remove an entry, create a json file titled something like remove_name-of-fish, or modify the existing `example.json`

### Json file structure

* **`item`**: This is the item ID of the fish that you want to remove! For example, if you want to remove trout from the journal, simply put in `tide:trout` for this option. If you want to remove something like the sailfish, enter `tide:sailfish`!

---

That's all. If your page or profiles don't load properly or you can't see them in the mod, check to make sure everything is spelled and formatted correctly. Alternatively, you can look for parsing errors in the logs that might relate to the datapack.