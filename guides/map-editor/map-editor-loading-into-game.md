# Loading into game

After you have created a map, use the exported **`.map` package**, not the `exported_map/` working directory.

Windows: place the package next to the Cold Path executable or in its `maps/` subfolder. Maps are discovered when opening a new game. **Import map** in Dev menu checks packages and displays errors.

Android: open **Settings - Dev menu - Import map** and select the `.map` with the system picker. You do not need to manually place it in `Android/data`.

The `D:/` location and `ColdPath` filename prefix are no longer required. Multiple maps are supported; the new-game list displays their filenames. A package with an already installed ID is not automatically replaced.

So, you have created a map, put it in special folder. Next, go to the game. New Game - Map - select your map. You will see map you created. Scenario that is there is automatically generated. There is only one country in it. This scenario is needed only in order to make your own based on it. Therefore, next you need to open Scenario Editor, select a custom map \(Custom map\), and create your own scenario for this map. Next, you need to export it \(Export to JSON\), then load it (from the game folder on Windows, or using Import scenario in Dev menu on Android). Done! You can play your scenario on your map!

How to play online? Custom maps are supported: start a single-player game on your map and choose Open server. The package is automatically sent to joining players and cached on their devices. For a standalone server, see [server setup](../../server/customization.md).

Convert old `exported_map/` directories using **Convert legacy map / Convert to .map** in the current editor first.
