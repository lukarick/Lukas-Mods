Parts Manager v1.0 -- by Luka's Mods
Car Dealer Simulator UE4SS mod

WHAT IT DOES
Rebuilding a car means buying every part one at a time, with no idea how
many cars the parts you already own could build. Parts Manager fixes
both. It adds a "Parts Manager" app (blue icon) to the tablet and to the
office computer. The app shows what is in your warehouse storage and how many
complete cars that stock can build, and it buys parts at normal store prices
straight into storage:

  * Complete cars: choose a kit (Stock / Sport / Race) and a number of cars,
    and you get that many full sets, whatever is already in storage.
    "Body & Consumables" adds a windshield, plate repair kit, engine oil,
    coolant and brake fluid per car.
  * Single parts: every row has its own car count, so brake calipers for
    2 cars buys 8.
  * Auto-stock: switch it on for a kit and it keeps the chosen number of
    complete cars of that kit in storage, checking every 30 seconds while you
    play. It starts about a minute after a save has loaded, and never spends
    below the balance you set in "Keep Balance Above". (Buying by hand is not
    limited by it.)
  * Auto Fuses: keeps N of each fuse size in storage (fuses come in packs
    of 3).

Sport and Race kits need the "Up 2 You" DLC, and unlock once every part in
them is unlocked by fame level. Until then their tabs show a padlock, and
clicking one tells you what is missing. Without the DLC only Stock can be
bought.

A brand-new career always starts with auto-stock paused, so the mod never
spends a new player's money without being asked. Click any Auto button in the
app when you want it to start. If you play more than one career, set
pause_auto_on_load=1 in settings.txt: auto-stock then pauses after every save
load, with an on-screen notice, and any Auto button resumes it.

REQUIREMENTS
  * Car Dealer Simulator on PC. Tested on the Steam version; the Microsoft
    Store / Xbox PC version is untested, and UE4SS installs differently there.
  * UE4SS (the mod loader), an EXPERIMENTAL build. The game uses Unreal
    Engine 5.4, and the last stable UE4SS release (v3.0.1, February 2024)
    is older than that, so the stable one won't do. Tested with two
    experimental builds: UE4SS_v3.0.1-1164-g5e627997.zip, whose log says
    "UE4SS - v3.0.1 Beta #0 - Git SHA #5e627997", and the older build
    whose log says "UE4SS - v3.0.1 Beta #0 - Git SHA #44afb36d".
    UE4SS goes in
      <game folder>\CarDealerSimulator\Binaries\Win64\
    so that dwmapi.dll and the ue4ss\ folder sit next to
    CarDealerSimulator-Win64-Shipping.exe.
  * Optional: the "Up 2 You" DLC, for the Sport and Race kits.

USE AT YOUR OWN RISK
  Any mod can crash a game or damage a save, and this one is no
  exception: it has been tested, but not on every setup. Back up your
  saves before you install it, and now and then while you play. They
  live in
      %LOCALAPPDATA%\CarDealerSimulator\Saved\
  Copy that folder somewhere safe.
  Parts Manager also spends real in-game money. While auto-stock is
  switched on it keeps buying, down to the balance you set in Keep
  Balance Above.
  You use this mod at your own risk.

INSTALL -- WINDOWS
  Copy the PartsManager folder into
      <game folder>\CarDealerSimulator\Binaries\Win64\ue4ss\Mods\
  so that you have  ...\ue4ss\Mods\PartsManager\enabled.txt
  enabled.txt is what turns the mod on.

INSTALL -- LINUX / STEAM DECK (PROTON)
  Status: partly tested. Under Proton, UE4SS and this mod load and attach
  to the tablet, but buying and auto-stock have not been tested there yet.
  If you try it, please report how it went (see "Report a Bug" below).
  1. Install UE4SS and this mod into the same folders as on Windows (inside
     the game's Steam install folder).
  2. In Steam: right-click Car Dealer Simulator > Properties > General >
     Launch Options, and enter exactly:
         WINEDLLOVERRIDES="dwmapi=n,b" %command%
     Without this, the game starts normally but loads NO mods.
  Note: "Report a Bug" opens your browser and file manager through Proton;
  this has not been verified yet.

CHECK THAT IT LOADED
  The game starting proves nothing. Check UE4SS's log instead:
      ...\Binaries\Win64\ue4ss\UE4SS.log
  It should contain:
      Mod 'PartsManager' has enabled.txt, starting mod.
      [PartsManager] v1.0 loaded
  In the game, a blue Parts Manager icon appears on the tablet and on the
  office computer's taskbar once a save has loaded -- not on the main menu,
  so don't look for it there.

SETTINGS
  settings.txt (created next to this file) remembers your choices. The
  "per_car.<ProductID>=<amount>" lines set how many of each body part or
  consumable "Body & Consumables" buys per car; set one to 0 to skip it.

UNINSTALL
  Delete  ...\ue4ss\Mods\PartsManager\
  Parts you bought stay in storage. They are normal game items.

REPORT A BUG / REQUEST A FEATURE
  Use the buttons in the app's header. "Report a Bug" saves a report file in
  the mod folder (with your Windows user name removed) and opens the GitHub
  issue form. Drag the file in and press Submit.

LOGO
  The logo (Assets\logo.png) is part of the Luka's Mods branding.
  The mod loads it at runtime; if the file is missing, the app works the same
  without it.
