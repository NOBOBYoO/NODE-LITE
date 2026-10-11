# Changelog

## [0.5.0] - 2026-10-12

### ✨ Additions

- Added a **Nobody's Leaders 3 compatibility** setting under the Settlers Renaming System. It only appears when Nobody's Leaders 3 is installed, and is on by default. Settlers that Nobody's Leaders 3 names after their settlement, such as Caroline Tenpines, keep those names, and any of them NODE.LITE renamed before get their Nobody's Leaders 3 name back.

### 🔄 Changes

- Redesigned the settler profile. It now opens as a centered window instead of the side panel, so everything about a settler is visible at once.
  - SPECIAL, info, assignments, flags and actions now sit side by side instead of in one long column.
  - The header shows the settler's name. An info column lists their type, settlement, role and bed, and flags a settler with no bed.
  - Unassign bed, Unassign job, Move to Player and Transfer moved to an actions column on the right.
- Redesigned the **Scans Update Bar** as the **Status Indicator**, a compact pill at the top of the menu.
  - Selecting the pill opens details on settlement updates and caravan routes.
  - Shows when scans are paused, when settlements are still being found, when settlements can't be updated, and when the dashboard is showing the save's last known data.
  - A **Recent activity** list records finished full checks, settlements updated after a change, and the result of each settler change.
  - A settler change shows as waiting until every queued change has finished, not just the first one.
  - On Fallout 4 1.10.163, settlement updates show as a full check with progress.
  - It only redraws when something changes, so the menu does less work while it is open.
  - Renamed its Settings toggle to **Status Indicator**.
- Changed caravan routes to be counted natively during each settlement read instead of in a separate script pass, so route counts update together with the settlement numbers.
- Changed the **Full settlement check** default to **120 seconds**. Settings still on the old **30-second** default move to 120 once, and custom values are kept.
- Changed settlement updates so a changed settlement refreshes right away on its own, without restarting a settlement numbers refresh already in progress.
- Changed where dashboard data is stored: each save's F4SE co-save, instead of one file per character, written only when the game saves. After loading a save, the dashboard opens right away with that save's own last known settlements and settlers, then refreshes them in the background. Old files in **Data\F4SE\Plugins\NODE.LITE\cache** are removed on launch.
- Changed the Settlers Renaming System to keep its record of renamed settlers in each save instead of one file per character, so turning renaming off restores the right names for that save. Settlers who have died or left the game are dropped from the record, and an older save reads its character's old list once.

### 🛠️ Fixes

- Fixed loading an older save briefly showing settlements and settlers from a later point of the same character.
- Fixed the Population list showing **Settler** for settlers that other mods name through quests. Their given names now show.
- Fixed a settler change being dropped without notice when settler options were opened, or another change was made, before it started. Changes now wait in a short queue and report a failure if they can't run.
- Fixed the Settlers Renaming System skipping unnamed settlers called **Worker**, such as the ghouls at The Slog. They are now renamed with **Worker** kept in brackets, like faction settlers.
- Fixed synth settlers' type reading **Human (Female (Synth))**. It now reads **Human (Female, Synth)**.
- Fixed **Export network data** always writing hasMapMarker as false. It now reports whether a settlement has a map marker, and the marker coordinates are read from that marker.
- Fixed settlements taken or lost on Fallout 4 1.10.163 never being added to or removed from the dashboard after the first list was read.
- Fixed **Pause Scans** on Fallout 4 1.10.163 never showing as paused, and settlement update problems never being shown.
- Fixed a shorter **Settlement totals** interval on Fallout 4 1.10.163 only taking effect after the update already waiting.

## [0.4.1] - 2026-09-27 (Hotfix)

### 🛠️ Fixes

- NODE.LITE.esp is now flagged as a light plugin (ESL). (Thanks to [@KuroshuKiji](https://www.nexusmods.com/profile/KuroshuKiji))

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
