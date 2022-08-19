# Возможные проблемы

#### Исправление некорректного отображения русских символов

https://serverfault.com/a/894545

Надо выполнить для всех экранов (screen) или выполнить в корне и потом пересоздать экраны

#### У игроков не работают премиумные функции

Проверьте файл verification\_server в корне сервера на то, соответствует ли он такому же на github. Или свяжитесь с разработчиком

#### Server does not start

Try to start server using `./clear_start.sh` or `luajit start.lua` and check output
