# Scenario Editor

How to open Scenario Editor: Settings - Dev menu - Scenario editor.

1. Set map \(map selection\)
2. Load scenario \(load any scenario from the existing ones. You can select some scenario and already based on it create your\)
3. Edit scenario \(yes, edit scenario\)
4. Save scenario \(JSON\) \(save the scenario in json format. Files of this format can be exported using the Load scenario button in Dev\_menu. This is the data format for loading the scenario in the game client\)
5. Save scenario \(Lua\) \(this scenario format is useful for those who want to create a scenario for their server. A file of this format can be dropped into the server scripts folder and played on the Internet using this script\)
6. Menu \(main menu of the game\)

Now let's take a closer look at the Edit scenario menu.

1. Scenario settings \(scenario settings. Here you can change the scenario name and start year\)  
2. List of civilizations \(list of countries. Here you can add a new country, change the existing one or delete\)  
3. Provinces \(open the map for editing provinces data\)  
4. Not ready yet.  
5. Not ready yet.  
6. Back

Let's go through these points in more detail:

1. Scenario settings. Scenario id is the name of the scenario. You can change it to any other. Year - start year. Technology level \(0-21\) - here you can specify the level of technologies open by default in the game
2. List of civilizations. Here is a list of countries. If you select a country from the list, you can change its name, color, or remove the country from the list. There is a Create button at the bottom - it adds a new country. Then you can edit it the way you need
3. Provinces. When you go here, a map opens. There are two buttons at the top. One is blank and the other has a pencil icon. If you click the first, then when you select a province, nothing will happen. And if the second, then when you click on a province, it will belong to the country that is written at the bottom of the screen. By clicking on the Civilization button, you can select a country from the list for editing or create a new one

Scenario creation in short:  
1. Settings - Dev menu - Scenario editor Select a map and a scenario and edit  
2. In the editor menu, do not forget to click the Save scenario \(JSON\) button to save the scenario data along the path that is at the bottom left. \(if it does not save for you, then check the application permission to write files\)  
3. Go to Settings - Dev menu. Choose Load scenario. The script will automatically load in the same path as it is usually exported. You can delete a scenario using the Remove last scenario button \(the last scenario will be removed\). The loaded script will appear in the game creation menu. It will be possible to select it in the same way as the ones built into the game \(the scenario can still be selected for editing in the scenario editor. But after that you will definitely need to save it, delete the last one and load the file\)

![](../.gitbook/assets/oyn-5ioqv-e.jpg)

