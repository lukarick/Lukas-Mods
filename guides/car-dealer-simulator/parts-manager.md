# Parts Manager — Guide

**Car Dealer Simulator · v1.0 · by Luka's Mods**

Buy a whole car's worth of parts in one click, straight into your warehouse storage at normal store prices. This page is the full reference. The short version is on [the Nexus page](https://www.nexusmods.com/cardealersimulator/mods/54).

- [Requirements](#requirements)
- [Install](#install)
- [Check That It Loaded](#check-that-it-loaded)
- [Everything It Does](#everything-it-does)
- [Settings](#settings)
- [Uninstall](#uninstall)
- [Compatibility](#compatibility)
- [Known Issues](#known-issues)
- [Report a Bug / Request a Feature](#report-a-bug--request-a-feature)

## Requirements

- Car Dealer Simulator on PC. Tested on the Steam version; the Microsoft Store / Xbox PC version is untested, and UE4SS installs differently there.
- UE4SS (the mod loader), an **EXPERIMENTAL** build. The game uses Unreal Engine 5.4, and the last stable UE4SS release (v3.0.1, February 2024) is older than that, so the stable one won't do. Tested with two experimental builds:
  - `UE4SS_v3.0.1-1164-g5e627997.zip`, whose log says `UE4SS - v3.0.1 Beta #0 - Git SHA #5e627997`
  - the older build whose log says `UE4SS - v3.0.1 Beta #0 - Git SHA #44afb36d`. This is the file on Nexus as "UE4SS v3.0.1-1150-g61b0e95e - Required Modding Framework" (Car Dealer Simulator mod 53). Despite its name, its log reports `#44afb36d`.

  UE4SS goes in `<game folder>\CarDealerSimulator\Binaries\Win64\`, so that `dwmapi.dll` and the `ue4ss\` folder sit next to `CarDealerSimulator-Win64-Shipping.exe`.
- Optional: the "Up 2 You" DLC, for the Sport and Race kits.

> ⚠️ **Use at Your Own Risk.** Any mod can crash a game or damage a save, and this one is no exception: it has been tested, but not on every setup. Back up your saves before you install it, and now and then while you play. They live in `%LOCALAPPDATA%\CarDealerSimulator\Saved\`.
> Parts Manager also spends real in-game money. While auto-stock is switched on it keeps buying, down to the balance you set in Keep Balance Above.

## Install

### Windows

Copy the `PartsManager` folder into

```
<game folder>\CarDealerSimulator\Binaries\Win64\ue4ss\Mods\
```

so that you have `...\ue4ss\Mods\PartsManager\enabled.txt`. `enabled.txt` is what turns the mod on.

### Linux / Steam Deck (Proton)

Partly tested. Under Proton, UE4SS and this mod load and attach to the tablet, but buying and auto-stock have not been tested there yet. If you try it, please report how it went.

1. Install UE4SS and this mod into the same folders as on Windows (inside the game's Steam install folder).
2. In Steam: right-click Car Dealer Simulator > Properties > General > Launch Options, and enter exactly:
   ```
   WINEDLLOVERRIDES="dwmapi=n,b" %command%
   ```
   Without this, the game starts normally but loads NO mods.

## Check That It Loaded

The game starting proves nothing. Check UE4SS's log instead, `...\Binaries\Win64\ue4ss\UE4SS.log`, which should contain:

```
Mod 'PartsManager' has enabled.txt, starting mod.
[PartsManager] v1.0 loaded
```

In the game, the blue Parts Manager icon appears on the tablet and on the office computer's taskbar once a save has loaded. It isn't on the main menu, so don't look for it there.

## Everything It Does

- **Overview:** one screen with your account balance, reputation level, fame level and free storage, plus how many complete cars the parts in storage can build for each kit you have unlocked.
- **Buy Complete Cars:** choose Stock, Sport or Race and a number of cars (-10, -1, +1, +10), then press Buy. You get that many full sets, whatever is already in storage. Turn on "Body & Consumables" to add a windshield, plate repair kit, engine oil, coolant and brake fluid per car.
- **Parts Table** for the selected kit: each part's price, how many one car needs, how many in storage show under Ready (100%) and how many under Needs Repair, and how many cars that covers. Every row has its own car count, so one click is a whole car's worth of that part: brake calipers for 2 cars buys 8.
- **Auto-Stock:** switch it on for a kit, choose how many complete cars to keep in storage, and it checks every 30 seconds while you play, buying whatever is missing. With "Body & Consumables" on, it keeps those for each car too. It starts about a minute after a save has loaded, and never spends below the balance you set in "Keep Balance Above". Buying by hand is not limited by it.
- **Auto Fuses** keeps N of each fuse size in storage, buying packs of 3 as needed.
- **Count Parts Needing Repair** decides whether worn parts count as stock, for both auto-stock and the complete-car counts.

### It's a Normal Purchase

Everything is bought at normal store prices and paid from your balance. Your bank app lists it as "Buying items: Parts Manager". A purchase you can't afford, or that won't fit in storage, is refused before anything is charged: the game's error sound plays and the app says why. The parts are normal game items, and they stay in storage if you uninstall the mod.

### It Won't Spend Your Money Unasked

A brand-new career always starts with auto-stock paused. Click any Auto button in the app when you want it to start. If you play more than one career, set `pause_auto_on_load=1` in `settings.txt` and auto-stock pauses after every save load, with an on-screen notice, until you press an Auto button again.

### Sport and Race Kits

They need the "Up 2 You" DLC, and unlock once every part in them is unlocked by fame level. Until then their tabs show a padlock, and clicking one tells you what is missing. Without the DLC only Stock can be bought.

### What It Doesn't Do

It doesn't sell parts, discount them or repair them, and it only buys into your warehouse storage. Tuning shop items, empty canisters and exhaust tape are left out on purpose.

## Settings

`settings.txt` in the mod folder remembers your choices. Its `per_car.<ProductID>=<amount>` lines set how many of each body part or consumable "Body & Consumables" buys per car; set one to 0 to skip it.

## Uninstall

Delete `...\ue4ss\Mods\PartsManager\`. Parts you bought stay in storage.

## Compatibility

No known conflicts. Parts Manager was tested alongside other mods for this game, but mods change over time, so there's no promise about how any of them will work with it after an update. If two mods misbehave together, please [report it](https://github.com/lukarick/Lukas-Mods/issues/new/choose).

## Known Issues

- Linux / Steam Deck is only partly tested: see [the Proton install notes](#linux--steam-deck-proton).
- Settings are shared by every career, because the game's saves don't say which career they belong to. Auto-stock targets and switches follow you from one career to the next. See [It Won't Spend Your Money Unasked](#it-wont-spend-your-money-unasked).
- Tested on the Steam version only.

## Report a Bug / Request a Feature

Use the buttons in the app's header. "Report a Bug" saves a report file in the mod folder, with your Windows user name removed, and opens the GitHub issue form: drag the file in and press Submit. Under Proton, opening the browser and file manager this way hasn't been verified yet.
