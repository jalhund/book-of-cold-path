## Game data


`game_data` is a global table with all data about the current game. You can directly work with it to change the behavior of the game on the server.

### How to find out what it contains


You can find out the contents of any table using the built-in function ``debug_log(game_data)`` it will write the result to the log file in the server root


### Change Tips 


Try not to modify this file yourself, but use ready-made modules. For example, if you want two countries to start war with each other, then connect the relations module at the beginning of the plugin (relationships between countries)
 ```
local relations = require "core.relations"
 ```
And in the plugin code itself, at the right time, call
 ```
relations.register_war(land1, land2)
 ```

### game_data summary


I won't list all the content here as it is very large.  Only the main thing that may come in handy more often than others


| field       | short description          |
|------------|---------------------------|
| difficulty | difficulty level         |
| queue      | sequence of moves  |
| step       | current turn               |
| lands      | countries                    |
| provinces  | provinces                 |


**Country data**

Country data is stored in ``game_data.lands[land_id]``, where land_id is the country id (not the name, but the id)

 The main, incomplete content of this table:

| field     | short description          |
|----------|---------------------------|
| ideology | ideology                 |
| money    | player's money               |
| economy  | income/expense data |
| allies   | allies                  |
| enemies  | enemies                     |

**Province data**

Province data is stored in ``game_data.provinces[province]``, where province is the id of the province.

The contents of this table are:

| field  | short description                                                                  |
|-------|-----------------------------------------------------------------------------------|
| water | is it water (true/false)                                                   |
| o     | id of the country that owns it                                                     |
| p     | population                                                                         |
| a     | table with data about the army in this province (key - country id, val - army number) |
| l_a   | currently hired army that will be available next turn              |
| r     | table with resources (how to fill it in, you can see in the fill_resources.lua file)  |
