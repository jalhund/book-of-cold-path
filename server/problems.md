# Возможные проблемы

#### Исправление некорректного отображения русских символов

https://serverfault.com/a/894545

Надо выполнить для всех экранов (screen) или выполнить в корне и потом пересоздать экраны

#### У игроков не работают премиумные функции

Проверьте игровой аккаунт и синхронизацию покупок по [инструкции восстановления](../guides/purchase-solution.md). В текущем отдельном сервере verifier.verify_registration сразу возвращает true, поэтому файл verification_server больше не является способом восстановить дополнение.

#### Server does not start

Try to start server using `./clear_start.sh` or `luajit start.lua` and check output
