# Useful tips


**Creating plugin**


To implement your plugin, take any existing one as a basis. Check existing features in standard plugins


**Remove license check on connection (make server free to join)**


The current `core/server/plugins/verifier.lua` immediately returns true on registration, and settings disable verify_uuid. Changing verification_mode is no longer needed to allow free joining. Server command permissions still come from permissions.lua. 


**How to rename map**


Renaming a `.map` file does not change its internal ID. To use another ID, update the source map data and the `map` field of all its scenarios consistently, then repack with the editor. Do not edit the binary `.map` with a text editor.

The standalone server package belongs in `maps/<map ID>.map`; register its scenario in scripts/scenario_selection.lua for startup and game_switch for rotation.

**How to run a server on Windows**

Comment out the lines in `plugins_manager.lua` file where custom plugins are automatically loaded from the folder.

It was:
 ```
 if not plugins_data.HOST_IS_PLAYER then
     load_custom_plugins()
 end
 ```
It became:
 ```
 --if not plugins_data.HOST_IS_PLAYER then
     --load_custom_plugins()
 --end
 ```


**How ​​to run a server on Windows without luassl**

This way you can run the server using LuaJIT and LuaSocket without LuaSec. Ordinary Lua is no longer sufficient: luaxxhash.lua uses FFI.
 
Replace lines in files:
 
*server_settings.lua*
 
````
verify_uuid = true,
````
------
````
verify_uuid = false,
````


*environment.lua*
 
````
ssl = require "ssl"
````
------
````
--ssl = require "ssl"
````

## Briefly about what can be changed on the server


On the server, you can change very, very much. You can't add a new resource because it doesn't exist on the client side. But it can be done that nuclear will make the land unsuitable for settlement forever.

You can rebalance the game however you like. You can override the behavior of existing buildings to your heart's content (but the client will see the army in the water provinces with a beacon, even if on the server side it does not give this bonus, because it is written into the code on the client side)

 You can add custom scenarios to the server and play them without any problems. Perhaps there will be a lack of translation, but this can also be fixed if you export the translation data, add the translation into the necessary languages ​​and send it to the players so that they put this translation in the settings

## Project structure:


#### Root


.git - git data

assets - here are data about which province to which you can move on different maps

core - game core

defnet - network module

scripts - helpful scripts

.gitignore - what data should not be sent to the versioning system

admins.dat - admin list (uuid)

banned.dat - banned by uuid

banned_ip.dat - banned by ip

chat.dat - chat history

convert_to_global.bat - bat file, which with one click translates the game sources into the server sources (they are slightly different). I need this thing purely for automation

convert_to_global.lua - the same as above, only here is the lua code, this thing is called by a bat file

environment - any global functions. Like displaying tables on the screen, functions for encoding data in JSON for sending over the network, and also defining global modules that should be available in all scripts, for example, luasocket

game_data.json - diagnostic data if created by your configuration; current start.lua does not automatically load it as a server save

log - server log. What plugins were loaded and when, when what actions took place

luaxxhash.lua - hashing used to verify transferred game state and custom maps

README.md - project description

server_crash - crash log

server_settings.lua - server settings (port, name, time to turn, etc.)

start.bat - bat file to start the server. Makes server restarts automatically after a crash

start.lua - lua script to start the server

start.sh - same as start.bat, only for linux


#### Core


ai - bots

server - main server script and plugins

army_functions.lua - army actions. Hiring, moving, different types of weapons

buildings_calc_functions.lua - building actions processing module

calc_functions - functions that are calculated every turn (how much money is spent on maintaining the army, how much the population will grow)

core.lua - core, all possible actions in the game are defined here. Depending on which game mode (server, client, single player) there is a certain shell above this script. For example, if the game mode is singleplayer and the player has moved an army, then the singleplayer module calls the core module and orders the change to be drawn on the map. If the player is on the server and not the host, then the client module sends a message to the server, and itself calls the core module to change the game data, because action is done

event_system.lua - event system. Example: when someone declares war on someone, a function registered in this system is called. Now used only for the balance of power.

game_values.lua - game values. For example, how much does it cost to hire an army, when inflation starts, how many turns can you change ideology

global_functions.lua - global functions. For example, find the path from one province to another, find out the list of neighbors of the province, get the translation of any country, calculate country points

ideology.lua - a module that describes how ideologies work. For example, what is the bonus to gold depending on the chosen ideology or how the attack should proceed if communism is chosen

offers.lua - message system between countries. For example, someone sent someone a trade or declared war

relations.lua - relations between countries. Start a war, find out who is fighting with whom. Find out if a country is a vassal

timer.lua - timer module. So that every 3 minutes there is next turn or every 30 seconds the server checks the connection

When disabling discovery, explicitly register the needed extra plugins in plugins_list with data and order. Otherwise they will not load, including any administrative commands and rotation you need.
