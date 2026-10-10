# Espionage and counter-intelligence

Espionage is a separate add-on. Operations require access to the add-on, an active espionage system in the current game, and your own **Intelligence Agency**. Counter-intelligence is adjusted in the country menu; without the add-on, its slider is locked at the default value.

## Intelligence points

An Intelligence Agency costs **100,000 gold**, uses **10,000 per turn**, and produces **5 intelligence points per turn**. A country may have one agency.

An Intelligence Center costs **10,000 gold**, uses **1,000 per turn**, and produces **1 point per turn**. Centers alone cannot unlock operations: you still need an agency.

## Operations

Select a land province belonging to a living foreign country and open the espionage menu. War is not required: neutral countries, allies and vassals can also be targeted. You cannot target your own country or Undeveloped Land.

| Operation | Cost | Successful effect |
| --- | --- | --- |
| Scout troops | 5 | A snapshot of troop counts in the selected province, valid until the end of the current turn |
| Sabotage | 10 | Destroys the selected ordinary building completely, not just one level |
| Steal technology | 15 | One random technology researched by the target but not by you |
| Incite rebellion | 25 | Creates a rebel country and starts a war between it and the target |

Sabotage needs an eligible building; special scenario objects are excluded. Theft requires at least one eligible technology. Rebellion requires a target with **more than 10 provinces**, a non-Theocracy ideology, and **fewer than 60 countries** in the current game state.

Points are spent even when an operation is intercepted. Scouting is a snapshot taken at execution time, not continuous surveillance.

## Counter-intelligence

The budget ranges from **0% to 50% of gross income per turn**, with a **5%** default. A higher target budget makes hidden operations less likely.

| Target budget | Hidden success | Success revealing the organizer | Failure |
| --- | --- | --- | --- |
| 0% | 100% | 0% | 0% |
| 5% | 80% | 10% | 10% |
| 25% | 0% | 50% | 50% |
| 50% | 0% | 0% | 100% |

Hidden success produces no special spy notification for the target, although a destroyed building or rebellion is visible. Revealed success identifies the organizer. Failure produces an interception notification without identifying the organizer.

<!-- Checked 2026-10-10 against cold-path/core/espionage.lua; core/game_values.lua; scripts/buildings_data.lua; core/core.lua; gui/civ_menu/civ_menu.gui_script; gui/map_interface/available_button.lua. -->
