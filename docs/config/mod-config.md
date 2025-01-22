# Mod Config Settings

Tide uses [Cloth Config](https://modrinth.com/mod/cloth-config) for its config screens, allowing config settings to be modified from within in-game gui. To open the mod's config settings on forge/neoforge, go to `options -> mods` and click on Tide, then open the config menu. To open the mod's config screen on fabric, you'll want to install [Mod Menu](https://modrinth.com/mod/modmenu). Then, you can configure Tide in the same way as forge/neoforge by opening the mod menu, finding Tide, and opening the config menu.

!!! info
    Alternatively, you can modify the config settings by finding Tide's config file in the minecraft instance -> config folder.

Once you open the config screen, there are 3 tabs: general, minigame, and worldgen

## General Settings

Give Journal (`giveJournal`)

- Controls whether new players will be given a fishing journal upon joining a world.
- _Default value: true_

Hold to Cast (`holdToCast`)

- When turned off, fishing rods can be cast by right-clicking once, as opposed to charging to cast them farther or closer. Rod casting will behave like the vanilla system if set to false, and keep Tide's new system if set to true.
- _Default value: true_

Alert Unread Profiles (`showUnread`)

- Turn this off to disable the alerts for when a profile is unread in the journal.
- _Default value: true_

Show New Fish Toasts (`showToasts`)

- Turn this off to disable the notifications (toasts) that appear when a new fish is obtained
- _Default value: true_

Use Vanilla Line Color (`defaultLineColor`)

- If enabled, all fishing lines will be rendered black. This could help avoid lighting issues with shaders, for example. The downside is that you won't be able to see the nice colors of different fishing lines.
- _Default value: false_

Rod Durability Multiplier (`rodDurabilityMultiplier`)

- A number multiplier that increases or decreases the durability of fishing rods by multiplying by the inputted factor. For example, 2.0 would double all fishing rod durabilities and 0.5 would halve them.
- Will require a reload of the Minecraft instance.
- _Default value: 1.0_

Crate Weight (`crateWeight`)

- An integer value. Change this to increase or decrease the chance of a crate being selected in the Minecraft loot table system.
- Will require a reload of the Minecraft instance.
- _Default value: 6_

Crate Quality (`crateQuality`)

- An integer value. Controls how valuable the crates are in the Minecraft loot table system. In other words, you can change this to increase or decrease the amount that the crate chance is scaled with higher fishing luck.
- Will require a reload of the Minecraft instance.
- _Default value: 1_

## Minigame Settings

Do Minigame (`doMinigame`)

- Turn this off to disable the fishing minigame. Fish will be caught like they are in the base game if set to false.
- _Default value: true_

Do Feedback (`doFeedback`)

- Turn this setting off to disable the scoring messages after a minigame (Perfect, Good, Great, etc.)
- _Default value: true_

Do Feedback (`doSuccessSound`)

- Turn this setting off to disable the ding sound played when you win the minigame.
- _Default value: true_

Do Feedback (`doFailSound`)

- Turn this setting off to disable the cutting sound played when you lose the minigame.
- _Default value: true_

Minigame Difficulty (`minigameDifficulty`)

- A multiplier that increases or decreases the speed of the minigame. For example, 0.5 would be twice as easy, while 2.0 would be twice as difficult
- _Default value: 1.0_

## Worldgen Settings

Disable Fishing Boats (`disableFishingBoat`)

- Set this value to true to disable the generation of fishing boat structures.
- _Default value: false_