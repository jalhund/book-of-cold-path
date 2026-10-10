# Common problems

#### Correction of incorrect display of Russian or others characters

https://serverfault.com/a/894545

You need to execute for all screens or execute in the root and then recreate the screens

#### Premium features not working for players

Check the game account and purchase synchronization using the [recovery guide](../guides/purchase-solution.md). In the current standalone server, verifier.verify_registration immediately returns true, so verification_server is no longer a way to restore an add-on.

#### Server does not start

Try to start server using `./clear_start.sh` or `luajit start.lua` and check output
