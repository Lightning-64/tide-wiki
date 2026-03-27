# Custom Rod Accessories

As of version 1.5.0, you can assign data to items so that they can be used as fishing rod accessories (bobbers, hooks, lines) through datapacks. This could be useful for mod or modpack creators who want to create more fishing rod customization options for players.

---

## Creating a bobber

### Item model
The easiest way to add a bobber is to give it an item model that matches one of tide's existing bobber item models. For example, if making a bobber with a basic box-shaped model (like the existing colored stripe ones), you'll want to use the [`tide:item/fishing_bobber`](https://github.com/Lightning-64/Tide/blob/main/common/src/main/resources/assets/tide/models/item/fishing_bobber.json) model. By default, Tide directly renders the bobber's item model on top of the fishing hook, so if the model matches the scale and positioning of the default bobber items, it should render correctly when used. Alternatively, you can copy the default [`tide:item/fishing_bobber`](https://github.com/Lightning-64/Tide/blob/main/common/src/main/resources/assets/tide/models/item/fishing_bobber.json) model and build off of it to create your own model.

### Translation key
Another thing to keep in mind is that in addition to the bobber's regular item ID, Tide displays a shortened version of the bobber's name in the tooltip of a fishing rod item. This text is a separate translation key that will need to be filled out in a lang file, either in a resource pack or a mod's assets files. The key will be called `accessory.item.(namespace).(item_id)`, and should be assigned to a shortened version of the bobber's name. Here's an example using Tide's Red Fishing Bobber:

> en_us.json
>
> _Original item name:_
> ```json
> "item.tide.red_fishing_bobber": "Red Fishing Bobber"
> ```
>
> _Additional shortened name:_
> ```json
> "accessory.item.tide.red_fishing_bobber": "Red Bobber"
> ```

### Adding the item as a bobber
Let's say you have an item called `namespace:test_fishing_bobber`. All you have to do to assign this item as a bobber is to give it the `bobbers` tag. This can be done by creating a file named `bobbers.json` in the `data/tide/tags/item/` path in your datapack, and adding the item to it like this:

> data/tide/tags/item/bobbers.json
> ```json
> {
>   "values": [
>     "namespace:test_fishing_bobber"
>   ]
> }
> ```

## Creating a hook

### Hook entity texture
Creating a fishing hook is similar to creating a bobber, but the item model doesn't matter. All you need to do differently is to add a texture that will be displayed on the fishing hook entity. This file will need to be placed in `assets/tide/textures/entity/fishing_hook/your_item_name.png`. To create the texture, copy [this texture](https://github.com/Lightning-64/Tide/blob/main/common/src/main/resources/assets/tide/textures/entity/fishing_hook/lavaproof_fishing_hook.png) of the lavaproof fishing hook as a guide.

### Translation key
See the [bobber translation key guide](https://lightning-64.github.io/tide-wiki/config/datapacks/custom-rod-accessories/#translation-key) above. As an example, "Lavaproof Fishing Hook" would be shortened to "Lavaproof Hook"

### Adding the item as a hook
Let's say you have an item called `namespace:test_fishing_hook`. Just like for bobbers, all you have to do to assign this item as a hook is to give it the `hooks` tag. This can be done by creating a file named `hooks.json` in the `data/tide/tags/item/` path in your datapack, and adding the item to it like this:

> data/tide/tags/item/hooks.json
> ```json
> {
>   "values": [
>     "namespace:test_fishing_hook"
>   ]
> }
> ```

## Creating a line

### Defining a color
Creating a fishing line will require you to do a little extra work to register the correct color that should be displayed. You'll have to use the new Accessory Data system, which is talked about in more detail in the section below.

To define a color for a line item, you'll need to create a json file in the `data/tide/rod_accessories/` path in your datapack. The file name doesn't matter, but it's recommended to name it after your item.

For creating a line, you need to define two keys in the file:
- `item` - A string containing item ID of the line item you want to add the data to.
- `color` - A string containing the hex code of the color you want to use.

Here's an example with Tide's reinforced fishing line. You may want to copy this code and modify it yourself:

> data/tide/rod_accessories/reinforced_line.json
> ```json
> {
>    "item": "tide:reinforced_line",
>    "color": "#6b6b68"
> }
> ```

### Translation key
See the [bobber translation key guide](https://lightning-64.github.io/tide-wiki/config/datapacks/custom-rod-accessories/#translation-key) above. As an example, "Golden Fishing Line" would be shortened to "Golden Line"

### Adding the item as a line
Let's say you have an item called `namespace:test_fishing_line`. Just like for bobbers and hooks, all you have to do to assign this item as a line is to give it the `lines` tag. This can be done by creating a file named `lines.json` in the `data/tide/tags/item/` path in your datapack, and adding the item to it like this:

> data/tide/tags/item/lines.json
> ```json
> {
>   "values": [
>     "namespace:test_fishing_line"
>   ]
> }
> ```

---

!!! note
    The accessory data system is pretty low on features at the moment, and is currently only used for assigning colors to fishing lines. It will be added to in future updates if necessary.