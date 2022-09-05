# The Admin Panel

## Structure

The Admin Panel, that you can access at `<url>/admin` is made of two parts:

- The **monitoring** section
- The **configuration** section

### The Monitoring section

Here you can create and run batches of game, monitor player statuses, and export the data.

### The Configuring section

Here you can create factors and treatments before creating batches.

<!-- ## Deleting Game and Player data but keeping Treatments, Factors, and Lobby Configurations

In the **Monitoring section**, you can click on **Reset** and then `Reset Games` to clean the data from previous instances/tests. It will remove the current _batches_, _games_, _players_ but it will keep the _treatments_, _factors_, and _lobby configurations_. -->

<!-- ## Deleting all the data and settings of an experiment

In the **Admin Panel**, in the **Monitoring tab**, you can click on **Reset** and then `Reset Entire App` to clean the whole database. It will remove all of the data in the database. -->

## Retiring Players: How players can play again, even if they got gameFull, LobbyTimedOut, etc.

Players can only play once. If there was a problem (e.g., the lobby timed out or the game was full), or if you want players to play again, you can _retire_ them which allows them to play again.

In the **monitoring tab**, in the **players tab**, you can see the status of every Player. At the bottom of the page, you can select a type of **exit status** and retire every player with that status.

Once _retired_, players can refresh their page/return to the link of your game and they will be randomly allocated to a game with the same treatment as before. They are allocated to a game with the same treatment so that they don't discover a game with different conditions or instructions.

<!--
## Lobby Configuration

In the **Configuration tab**, in **Lobby Configurations**, you can set important aspects of the Lobby such as:

* The `Timeout Type` (whole lobby or individual)
* The `Timeout Duration in Seconds`
* The `Timeout Strategy` (fail, ignore)
* The `Extend Count`

### What happens when the Lobby times-out?

When players start a Game, they go through Intro Steps, and when they have finished the Intro Steps they arrive at a Lobby where they are set as **ready** and they wait for other players to join until there are as many ready players as the number set in the `playerCount` factor.

However, it is possible that there won't be enough players and you don't want players to wait indefinitely in the Lobby for others to join. Hence, you can set a time after which the Lobby times-out.

This is set in the **Configuration tab**, in **Lobby Configurations**. What happens when the Lobby times-out depends on these settings.

If `Timeout Type` is set to _Lobby_ then the countdown to the timeout starts as soon as the first player reaches the Lobby. Here the `Timeout Stragety` determines what happens when the Lobby times-out:

* If set to _Fail_, the Game will fail (it will be terminated) and the current players waiting in the Lobby [will be sent to the Exit Steps set for them](../faq/faq.md#how-can-i-show-a-different-exit-step-to-players-depending-on-whether-they-have-finished-the-game-or-if-the-game-was-cancelled-had-a-problem) with their Exit Status set to _gameLobbyTimedOut_.
* If set to _Ignore_, it will start the Game anyway, even if there aren't enough players.

If `Timeout Type` is set to _Individual_ then a different countdown starts for each player when they reach the Lobby. If the Lobby times-out, the player[ will be sent to the Exit Steps set for them](../faq/faq.md#how-can-i-show-a-different-exit-step-to-players-depending-on-whether-they-have-finished-the-game-or-if-the-game-was-cancelled-had-a-problem) with their Exit Status set to _playerLobbyTimedOut_, but the Game will not fail (i.e., players can still join the game). With `Extend Count` you can set the number of times the player needs to timeout before they are sent to the Exit Steps. If `Extend Count` is set to 0, then after one timeout the player is sent to the Exit Steps, if it is set to 1, then after two timeouts the player is sent to the Exit Steps. -->

## Treatments and factors settings

The treatments and factors are saved in a `.empirica/treatments.yaml`. It is
often shared by simply comitting it to your code versionning system (e.g. Git).

You can edit treatments and factors manually in that file (make sure to reload
the admin page after any edits).

Alternatively, you can edit these directly in the admin UI, which will update
the `.empirica/treatment.yaml` file for you.
