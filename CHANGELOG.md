# Changelog

## [0.4.0] - 2026-09-26

### 🛠️ Fallout 4 1.10.163 Support Changes

> **Fallout 4 1.10.163** (Old-Gen) is now fully supported.
> Before this update, NODE.LITE froze that version of the game on the main menu when loading a save. The following notes cover what changed to support this game version.
>
> Old-Gen settlement updates follow their own path, separate from Next-Gen and Anniversary Edition, so they do not stall the game.

- Settlements update one at a time instead of freezing the game after a save loads. The update bar shows the pass, waits **15 seconds**, then reads them again.
- Settings → Scans System → **Advanced** shows only **Settlement totals** and **Pause Scans** on this game version. The other timing options do not apply to it.

> The following changes apply to every game version:

### 🔄 Changes

- **Settlements updated at once** now defaults to **1**, the smoothest setting. Existing settings are kept.
- A full settlement read now takes about **3 seconds** while the dashboard is open, and about **10 seconds** while it is closed.
- If caravan routes stop updating, NODE.LITE tries them again **30 seconds** later. They no longer stay off for the rest of the session.

### 🛠️ Fixes

- **Fallout 4 1.10.163** no longer freezes on the main menu when loading a save.

## [0.3.0] - 2026-09-21

### 🔄 Changes

- NODE.LITE now requires **PrismaUI F4 2.1.1**. Update Prisma before updating NODE.LITE; older Prisma UI builds are no longer supported.
- On a new game, the Network page now shows that no workshops are owned yet, and that settlement updates only start after a workshop is claimed.
- **Settlements Update Bar** is now **Scans Update Bar**.
- Settings → Systems now includes **Scans System**, with **Scans Update Bar** nested under it to show or hide the bar at the top of the menu.
- **Scans System** now includes an **Advanced** toggle for extra scan settings.
- Sub-settings now sit indented under their parent, including renaming, scans, and console.

### 🛠️ Fixes

- **Fixed:** Starting a new game no longer stutters every couple of seconds. NODE.LITE was still checking for settlements every 2 seconds even though no workshops were owned yet.

## [0.2.0] - 2026-09-14

### ✨ Additions

- Introducing the **Settlers Renaming System**: generic settlers named Settler now get a gender-specific first name, and a surname. People in the same settlement may share a surname, so a few of them can feel like family. Unique named people are left alone.
- Added a **Settlers Renaming System** setting, to toggle the system. Turning off the system restores all settlers names to Settler again.
- Minutemen, Nuka-World gangs, and similar workshop groups can also receive names, with the group kept in parentheses. That option can be turned off on its own.
- Settings now include **Interface scale**, so you can make the whole dashboard smaller or larger to fit your screen resolution.
- Settler profiles now include **Unassign bed** and **Unassign job**, so you can free a bed or workplace without moving that person out of the settlement.
- NODE.LITE now appears in the **Prisma Dock** on the ESC menu, with the NODE.LITE badge, a short description, and a link to the Nexus page.

### 🔄 Changes

- The Console page is now off by default. Turn on **Enable Console** in Debug settings to show it in the sidebar. **Console debug mode** is nested under that setting, for extra diagnostic lines in the in-game console and NODE.LITE.log.
- The **Settlement Updates** setting is now **Settlements Update Bar**, so it is clearer that it controls the bar at the top of the menu.

### 🌿 QoL Improvements

- Population table now sorts NPCs alphabetically.

## [0.1.0] - 2026-09-11

- Initial release.
