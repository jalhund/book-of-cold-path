# Customizing server 

In the last topic, we started the server. Fine! We can now play on the standard version of the server. But I'm sure you now want to customize it for yourself.

Shut down the running server (Double CTRL + C. Make it fast)

Set time for turn
```
nano server_settings.lua
```
It's in seconds and defaults to 180. Let's change it to 210 so it's 3.5 minutes

Use the arrows on your keyboard to navigate to this number and change it (but don't type numbers on the Numpad, type them using the numbers above the letters)

Great, changed. Now you need to save.

Press CTRL+X

Then y

Then enter

So you can edit files on the server. You can edit a lot, a lot. Let's restart our server. Let's go to the main folder of the server.  Starting the server
```
./start.sh
```
Now we can look at what is happening in the console. We can also minimize the current screen. Type on the keyboard:
CTRL + A
CTRL + D

We detached current screen

When connecting to a server after disconnecting, you will be in the same situation. To load the server screen again, type
```
screen -r server1
```

## How to add custom scenario


By default, the server has a map and scenario from the active parkourcat player. This is to make it easier for you to set up your custom maps and scenarios based on an existing example.

So, we want to add scenario to server (if you have just connected to the server, then do not forget to enter the ``screen -r server1`` command from the previous topic to go to the server screen. If you go and the server is running, then turn it off with the Double CTRL + C command)

First you had to create a scenario in the scenario editor and export it as a .lua file. You need to upload the resulting file to the server in the folder scripts/scenarios/<suitable map>

Next you need to decide:
 1) you want this scenario to run when server starts
 2) you want this scenario to be one of those scenarios that automatically starts after the end of the game

If first, then you need to edit start.lua file. Open this file with an editor
```
nano start.lua
```
Find line
```
game_data = require "scripts.scenarios.euro.std"
```
Change it to 
```
game_data = require "scripts.scenarios.<карта>.<сценарий>"
```
Save it. (CTRL + X, type y, press enter) 

If second, then we already need to edit the standard game_switch plugin (you can also write your own plugins, but this is a separate and complicated topic. In order to write plugins, you need to program. But this opens up very great opportunities)

Go to core/server/plugins
```
cd core/server/plugins
```
Edit game_switch plugin
```
nano game_switch.lua
```
Add scenario by analogy with the scenarios that have already been defined

CTRL + X. Enter y. Press enter

Go to server folder
```
cd ../../..
```

Start server 
```
./start.sh
```


## How to add custom map


1. Create a map in Map Editor.
 2. Create `maps` folder. 
 3. Rename `exported_map` folder to map id and place it in the `maps` folder.
 4. Add your scenario made for this custom map to the server

Players do not need to install anything, the map will be loaded automatically when connecting server
