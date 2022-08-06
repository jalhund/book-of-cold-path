---
description: Game commands
---

# Commands

### Single

* /export - save current game state to json file (for debug)
* /ach - achievement animation (achievements in the game are not completed, there is only animation)
* /uuid - show uuid and write it to uuid.txt
* /draw\_adjacency - on/off the display of provinces that can be moved from the selected
* /music\_on - turn on music
* /music\_off - turn off music
* /nolags - no delays and freezes in multiplayer, but there must be a stable connection (default mode)
* /nodisconnect - there may be freezes and delays, but you can play with an unstable connection with a high ping (choose if you are often kicked in multiplayer)
* /profile \<seconds> - profile game performance over time and save the report to a file
* /hide \<seconds> - hide user interface

### Multiplayer

**For all servers**

* /help - show list of commands
* /ping - show ping
* /uuid - show uuid and write it to uuid.txt file
* /select - select province (for /setciv command)
* /load - load map and scenario from server to single
* /profile - profile game performance over time and save the report to a file

**Commands of standard plugins, if not removed by server owners**

_Players_

* /players - list of players and display who clicked next button and who doesn't
* /m <ник> <сообщение> - personal message

_Premium_

* /rc - change civilization (no more 3 times per game)
* /pass - allow a player to join the official server even if they don't have a license
* /setcolor r g b - set civilization color (RGB 0 - 255). Example: /setcolor 255 0 0 - red
* /rtr - start voting to start a new game

_Admin_

* /kick - kick player
* /mute - mute player
* /unmute - unmute player
* /ban - ban player
* /banip - ban player by ip + standard ban
* /setmap - set next map
* /setscenario - set next scenario
* /nextgame - finish this game and start next
* /scenarios - scenarios list
* /shutdown - shutdown server
* /select - select province
* /setciv - set player on country chosen by command /select
