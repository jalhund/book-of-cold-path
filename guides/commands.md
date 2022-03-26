---
description: Game commands
---

## Single


* /export - save current game state to json file (for debug) 
* /ach - achievement animation (achievements in the game are not completed, there is only animation)
* /uuid - show uuid and write it to uuid.txt
* /draw_adjacency - on/off the display of provinces that can be moved from the selected
* /music_on - turn on music
* /music_off - turn off music
*  /nolags - no delays and freezes in multiplayer, but there must be a stable connection (default mode)
* /nodisconnect - there may be freezes and delays, but you can play with an unstable connection with a high ping (choose if you are often kicked in multiplayer)


## Multiplayer


**For all servers**


* /help - show list of commands
* /ping - show ping
* /uuid - show uuid and write it to uuid.txt file
* /select - select province (for /setciv command) 
* /load - load map and scenario from server to single


**Commands of standard plugins, if not removed by server owners**


*Players*

* /players - list of players and display who clicked next button and who doesn't
* /m <ник> <сообщение> - personal message

*Premium*

* /rc - change civilization (no more 3 times per game)
* /pass <nickname> - allow a player to join the official server even if they don't have a license
* /setcolor r g b - set civilization color (RGB 0 - 255). Example: /setcolor 255 0 0 - red
* /rtr - start voting to start a new game

*Admin*

* /kick <name> - kick player
* /mute <name> - mute player
* /unmute <name> - unmute player
* /ban <name> <duration in hours> - ban player
* /banip <name> <duration in hours> - ban player by ip + standard ban
* /setmap <map> - set next map
* /setscenario <map> <scenario> - set next scenario
* /nextgame - finish this game and start next
* /scenarios - scenarios list
* /shutdown - shutdown server
* /select - select province
* /setciv <name> - set player on country chosen by command /select
