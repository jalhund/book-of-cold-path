# Scenario Editor

How to open Scenario Editor: Settings - Dev menu - Scenario editor.

1. Set map \(map selection\)
2. Load scenario \(load any scenario from the existing ones. You can select some scenario and already based on it create your\)
3. Edit scenario \(yes, edit scenario\)
4. Save scenario \(JSON\) \(save the scenario in json format. On Windows, files in this format are loaded from the game folder; on Android, use Import scenario in Dev menu and select the JSON with the system picker. This is the data format for loading the scenario in the game client\)
5. Save scenario \(Lua\) \(this scenario format is useful for those who want to create a scenario for their server. A file of this format can be dropped into the server scripts folder and played on the Internet using this script\)
6. Menu \(main menu of the game\)

Now let's take a closer look at the Edit scenario menu.

1. Scenario settings \(scenario settings. Here you can change the scenario name and start year\)  
2. List of civilizations \(list of countries. Here you can add a new country, change the existing one or delete\)  
3. Provinces \(open the map for editing provinces data\)  
4. Buildings \(buildings editor\)  
5. Not ready yet.  
6. Back

Let's go through these points in more detail:

1. Scenario settings. Scenario id is the name of the scenario. You can change it to any other. Year - start year. Technology level \(0-21\) - here you can specify the level of technologies open by default in the game
2. List of civilizations. Here is a list of countries. If you select a country from the list, you can change its name, color, or remove the country from the list. There is a Create button at the bottom - it adds a new country. Then you can edit it the way you need
3. Provinces. When you go here, a map opens. There are two buttons at the top. One is blank and the other has a pencil icon. If you click the first, then when you select a province, nothing will happen. And if the second, then when you click on a province, it will belong to the country that is written at the bottom of the screen. By clicking on the Civilization button, you can select a country from the list for editing or create a new one. There are also capital assignment and diplomacy modes
4. Buildings.

   Change - select building  
   Control buttons:  
   1\) empty - nothing  
   2\) pencil icon - build selected building  
   3\) red cross - remove all buildings  
   4\) red pencil icon - remove selected building

Scenario creation in short:  
1. Settings - Dev menu - Scenario editor Select a map and a scenario and edit  
2. In the editor menu, do not forget to click the Save scenario \(JSON\) button to save the scenario data along the path that is at the bottom left. \(if it does not save for you, then check the application permission to write files\)  
3. On Windows, the scenario is automatically loaded from the game folder when opening a new game. **Import scenario** in Dev menu repeats the folder check. On Android, click this button and select the JSON with the system picker. Remove custom scenario deletes the selected scenario. The loaded scenario appears in the new-game menu and Scenario Editor.

On Windows, changed JSON with the same filename updates the loaded scenario without deleting it first. A separate Android import with an existing ID creates a version with a free ID. The limit is 16 custom scenarios. For a custom-map scenario, first install its [`.map` package](map-editor/map-editor-loading-into-game.md).

Windows also supports files in `scenarios/` and `maps/<map name>/scenarios/`. If a deleted scenario reappears, remove its source JSON from the scanned folder.


![](../.gitbook/assets/oyn-5ioqv-e.jpg)

