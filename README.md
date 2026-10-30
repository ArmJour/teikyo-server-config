# Extra mods

Extra mods for our server, on top of the **Create+** modpack.

- **Minecraft:** 1.21.1
- **Loader:** NeoForge
- **Modpack:** Create+ **6.0.0-alpha-f** (Modrinth). The version must match the server exactly.

This repository only contains the mods that are **not** in the modpack. Your own mods and the pack mods are never touched.

## First-time setup

1. In the Modrinth app, install **Create+** and pick version **6.0.0-alpha-f**.
2. Open the profile, click **Open folder**, and go into the `mods` folder.
3. Open a terminal in that folder (Windows: right-click in the folder, **Open in Terminal**) and run:

       git init -b mods
       git remote add origin https://github.com/ArmJour/teikyo-server-config.git
       git fetch origin mods
       git checkout -b mods --track origin/mods

   You need [Git](https://git-scm.com/downloads) installed. The extra jars now sit next to your other mods, and nothing you already had is removed.
4. Launch the profile from the Modrinth app.

## Updating

Close the game, open the same `mods` folder in a terminal, and run:

    git pull

Jars added to the repository are copied in. Jars removed from the repository are deleted from your folder. Other mods stay as they are.

## Without Git

Click **Code, Download ZIP** on the `mods` branch, unzip it, and copy the `.jar` files into your profile's `mods` folder. You then have to repeat this for every update, and delete removed jars by hand.

## Notes for the maintainer

`*.jar` is ignored on purpose, so a player's other mods do not show up in `git status`. Add each extra mod with `git add -f name.jar`.

## Extra mods in this repository

- **Ping Wheel** 1.12.2 (MIT license, needed on both client and server)
- **What Are They Up To** 1.21.0-1.2.7 (needed on both client and server; needs CoroUtil, which the Create+ pack already includes)
- **Kaleidoscope Cookery** 1.6.0 (needed on both client and server). By YSBB, TartaricAcid and azumic, licensed [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/); original at https://modrinth.com/mod/kaleidoscope-cookery. Not for commercial use.
- **Create Aeronautics: Transmission & Linkage** 0.2.8 (needed on both client and server). By enxv233, licensed [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/); original at https://modrinth.com/mod/create-aeronautics-transmission-linkage. Not for commercial use.

Keep `Barista` and `statuseffectbars` in the pack; the server just skips them.

## Required libraries

The Modrinth pack marks these as optional, so Prism disables them (`.jar.disabled`) when it installs the pack, even though other mods need them. They are included here as ready-to-use `.jar` files:

- **Create** 6.0.10 (Create Mod License)
- **Kotlin for Forge** 5.11.0 (LGPL-2.1)
- **GML** 6.0.2 (MIT)
- **MRU** 1.0.19 (All Rights Reserved)
- **Puzzles Lib** 21.1.51 (MPL-2.0)
- **Balm** 21.0.58 (All Rights Reserved)
- **Cloth Config** 15.0.140 (LGPL-3.0)
- **YetAnotherConfigLib** 3.8.2 (LGPL-3.0)
- **Sinytra Connector** 2.0.0-beta.14 (MIT)

If Prism shows "requires ... not installed" errors when you start the game, select the disabled mods in the instance's **Mods** tab and click **Enable**, or rename each `.jar.disabled` file back to `.jar`.

## Server-only mods (players do not install these)

The server also runs the world generation mods Terralith, Tectonic and Lithostitched. Players do not need them.
