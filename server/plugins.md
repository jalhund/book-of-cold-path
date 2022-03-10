## Plugins


The servers have different plugins. Each plugin is an independent entity. The plugin can track various server events, and also somehow respond to them using a list of commands defined by the server.


### How to install plugin


1. First way. Edit `plugins_list` table in plugins_manager.lua

2. The same as the first one, but you can not specify the `data` field there, but only `order`, and throw the plugin itself with the .lua extension into `plugins` folder

3. The third way is the most convenient. Just drop plugin into `plugins` folder with the .lua extension, and it will automatically pick up. You no longer need to add them manually in a text editor, just move them to a folder. If you need to adjust the order of calling plugins (first one, then the other), then see the second method of application. 

All use cases are in the plugin manager


### API


* `call_function` - call some function. This can be either a server-side function or a function of another plugin registered in the shared space.
 * `register_function` - register a function, it can then be called using `call_function`. Useful to enable other plugins to get some info. For example, the system plugin defines a kick function with an appropriate message. And this ready-made function can be used by any other plugin
 * `register_command` - register a command. For example, we want the player to receive the message abrakadabra when they enter the command /test
 * `set_data` - set data (required for interaction between plugins)
 * `get_data` - get data (needed for interaction between plugins). For example, you need to find out the player's nickname
 * `remove_data` - remove data
 * `send_data` - send data. You can send data to the client. True, the client will only respond to the data whose list is defined on its side. For example, you can use this plugin to force the player to update map data
 * `set_server_state` - set the state of the server (ready, off, starting)
 * `start` - start the server


#### What events does the plugin track?


* `init` - server start
* `verify_registration` - player verification (the server checks whether to let the player into the game or not)
* `on_player_registered` - player registration on the server (when a player connects, he is given a country, he is added to the list of players)
* `on_player_joined` - moment when the player loaded the map (for example, sending him a request to display the rules before this moment does not make sense, because the player is in the menu)
* `on_player_disconnected` - player is disconnected
* `on_data` - receive data from client
* `before_next` - event before next turn
* `game_over` - game over
* `attribute_message` - message formatting



### Analyze standard afk plugin


```
-- it is necessary for the module to work
local M = {}

-- add timer module
local timer_module = require "core.timer"

-- variables for working with functions of other plugins or the server: send data, call a function, receive data
local send_data
local call_function
local get_data

-- table with data of the last synchronization with clients, store the timer and the last time
local last_sync = {
    -- client = {
    --     timer_id,
    --     last_time
    -- }
}

-- waiting for 30 seconds, if there is no answer, then kick
local afk_sec = 30

-- check client
local function check_client(client)
    -- if the current time minus the time of the last synchronization is more than 30 seconds, then kick
    if socket.gettime() - last_sync[client].last_time > afk_sec then
        call_function("kick", client, { "", get_data("clients_data")[client].name, "lost connection"})
    end
    -- send a message to the client to which he must respond
    local t = {
        type = "ping",
        data = {}
    }
    send_data(to_json(t), client)
end
-- called once at init. Here we define the functions we need
function M.init(api)
    send_data = api.send_data
    call_function = api.call_function
    get_data = api.get_data
end

-- called when a player registers
function M.on_player_registered(client)
    -- fill in the synchronization data of the new client
    last_sync[client] = {
        -- we create a timer that every 30 seconds checks for a connection
        timer_id = timer_module.every(afk_sec, function()
            check_client(client)
        end),
        last_time = socket.gettime()
    }
end

-- if the client is disconnected, then delete the data
function M.on_player_disconnected(client)
    last_sync[client].timer_id:remove()
    last_sync[client] = nil
end

-- if the player sent a response, then we update the synchronization data
function M.on_data(data, ip, port, client)
    if data.type == "pong" then
        last_sync[client].last_time = socket.gettime()
    end
end

return M
```
