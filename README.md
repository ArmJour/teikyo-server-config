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

## Mods you download yourself

These mods do not allow redistribution, so their jars are not in this repository. Download the exact version from Modrinth and put it in your profile's `mods` folder:

- **What Are They Up To** `1.21.0-1.2.7` (NeoForge): https://modrinth.com/mod/what-are-they-up-to/version/1.21.0-1.2.7. Needs **CoroUtil**, which the Create+ pack already includes. Keep `Barista` and `statuseffectbars` in the pack; the server just skips them.
