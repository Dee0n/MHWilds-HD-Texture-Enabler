# Monster Hunter Wilds - HD Texture Pack Enabler (LUA)

A specialized REFramework script that force-activates the **High Resolution Texture Pack** toggle in the Graphics Settings. 

### Why this exists?
In certain environments (Family Sharing, Goldberg Emulator, or when running via Hypervisors), the game's internal `DlcService` fails to validate the HD Texture Pack DLC (AppID 3308900), leaving the toggle greyed out even if the files are present. 

Unlike standard DLC unlockers that only hook basic ownership checks, this script targets the specific `isEnabledHqTextureDLC` method used by the REX Engine's UI.

## Requirements
* [REFramework for MH Wilds](https://github.com/praydog/REFramework)
* HD Texture Pack files (`re_dlc_stm_3308900.pak` and `.sub_000.pak`)

## Installation
1. Install **REFramework**.
2. Create a folder named `pak_mods` in your game directory.
3. Move your HD Texture Pack `.pak` files into `pak_mods\`.
4. Place `hd_pak_unlocker.lua` into `reframework\autorun\`.
5. Launch the game and enable the toggle in **Settings -> Graphics**.

## Compatibility & Troubleshooting
### If using "DLCUnlocker LUA Edition" (by Antrix):
The Antrix script explicitly excludes the HD Pack (ID 3) to prevent crashes for users without the files. To make them work together, you **must** edit his script:
* **Find:** `st.force_true = (id ~= 3)`
* **Change to:** `st.force_true = true`

## Credits
* Developed by **Dee0n**
* Special thanks to the REFramework team.
