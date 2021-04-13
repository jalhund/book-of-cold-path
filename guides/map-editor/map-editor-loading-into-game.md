# Loading into game

After you have created a map, you need to move it to special folder to load it. The always up-to-date path is written in the lower left corner in the scenario editor.

At the moment it is:  
Android: Android/data/com.DenisMakhortov.ColdPath/files/  
Windows: D:/ \(Attention! On windows, the file should not be named exported\_map, but ColdPathexported\_map. Also with the scneario file. Not game\_data.json, but ColdPathgame\_data.json Not critical yet, but it would be nice to fix and auto-create the Cold Path folder if it is absent\)

So, you have created a map, put it in special folder. Next, go to the game. New Game - Map - select Custom Map. You will see map you created. Scenario that is there is automatically generated. There is only one country in it. This scenario is needed only in order to make your own based on it. Therefore, next you need to open Scenario Editor, select a custom map \(Custom map\), and create your own scenario for this map. Next, you need to export it \(Export to JSON\), then load it \(Load scenario in the Dev menu in the settings\). Done! You can play your scenario on your map!

How to play online? Currently unavailable. It will be necessary to write a some check for map for the players who join + test it well. I'll make it later

