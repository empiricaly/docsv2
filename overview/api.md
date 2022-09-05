# API

This document describes Empirica's [server](api.md#server), [client](api.md#client) and [shared ](api.md#shared)APIs.

## Server

### `Empirica.onGameStart(callback)`

The `onGameStart` callback is called just before a game starts, when all players are ready, and it must create rounds and stages for the game.

One (and one only) onGameStart callback is required for Empirica to work.

The callback receives one argument, the [`game` object](api.md#game-object), which gives access to the `players` and the treatment for this game.

It also offers the `addRound()` method, which allows to add a round to the `game`. The returned Round object will implement the `addStage(stageArgs)` method, which allows to add a Stage to the Round. The `stageArgs` object to be passed to the stage creation method must contain:

- `duration`: the stage duration, in seconds

Note that the Game has not yet been created when the callback is called, and you do not have access to the other properties of the Game which will be created subsequently.

#### Example

```js
Empirica.gameInit(game => {
  game.players.forEach((player, i) => {
    player.set("score", 0);
  });

  const round1 = game.addRound();
  round1.addStage({
    duration: 120
    name: "Response",
  });

  if (game.treatment.playerCount > 1) {
    round1.addStage({
      duration: 120
      name: "Result",
    });
  }

  const round2 = game.addRound();
  round1.addStage({
    duration: 300
    name: "Response",
    someotherfield: "mydata"
  });

  if (game.treatment.playerCount > 1) {
    round1.addStage({
      duration: 120
      name: "Result",
    });
  }
});
```

### **Game Callbacks**

Game hooks are optional methods attached to various events throughout the game life cycle to update data on the server-side.

Contrary to client side data updates, sever-side updates are synchronous, there is no risk of conflicting updates, and important calculations can be taken at precise points along the game.

``

### `Empirica.onRoundStart(callback)`

`onRoundStart` is triggered before each round starts, and before `onStageStart`. It receives the same options as `onGameStart`, and the [round](api.md#round-object) that is starting.

#### Example

```javascript
Empirica.onRoundStart(({ round }) => {
  round.set("scoreToReach", round.game.get("maxScore"));
});
```

### `Empirica.onStageStart(callback)`

`onRoundStart` is triggered before each stage starts. It receives the same options as `onRoundStart`, and the [stage](api.md#stage-object) that is starting.

#### Example

```javascript
Empirica.onStageStart(({ stage }) => {
  stage.set("randomColor", myRandomColorGenerator());
});
```

### `Empirica.onStageEnd(callback)`

`onStageEnd` is triggered after each stage. It receives the current [game](api.md#game-object), the current [round](api.md#round-object), and [stage](api.md#stage-object) that just ended.

#### Example

```javascript
Empirica.onStageEnd(({ stage }) => {
  const expectedScore = stage.round.get("expectedScore");
  const group = stage.get("score") > expectedScore ? "great" : "not_great";
  stage.set("scoreGroup", group);
});
```

### `Empirica.onRoundEnd(callback)`

`onRoundEnd` is triggered after each round. It receives the current [game](api.md#game-object), and the [round](api.md#round-object) that just ended.

#### Example

```javascript
Empirica.onRoundEnd(({ round }) => {
  let maxScore = 0;
  round.game.players.forEach((player) => {
    const playerScore = player.round.get("score") || 0;
    if (playerScore > maxScore) {
      maxScore = playerScore;
    }
  });
  round.set("maxScore", maxScore);
});
```

### `Empirica.onGameEnd(callback)`

`onGameEnd` is triggered when the game ends. It receives the `game` that just ended.

#### Example

```javascript
Empirica.onGameEnd(({ game }) => {
  let maxScore = 0;
  game.rounds.forEach((round) => {
    const roundMaxScore = round.get("maxScore") || 0;
    if (roundMaxScore > maxScore) {
      maxScore = roundMaxScore;
    }
  });
  game.set("maxScore", maxScore);
});
```

<!--
### _**Change Callbacks**_

{% hint style="danger" %}
We are currently updating documentation for Empirica v2. _**Change Callbacks**_ information here is incorrect.
{% endhint %}

[onSet](api.md#empirica-onset-callback), [onAppend](api.md#empirica-onappend-callback) and [onChange](api.md#empirica-onchange-callback) are called on every single update made by all players in each game, so they can rapidly become **computationally expensive** and have the potential to seriously slow down the app. Use wisely.

It is very useful to be able to react to each update a user makes. Try nontheless to limit the amount of computations and database saves done in these callbacks. You can also try to limit the amount of calls to `set()` and `append()` you make (avoid calling them on a continuous drag of a slider for example) and inside these callbacks use the `key` argument at the very beginning of the callback to filter out which keys your need to run logic against.

If you are not using these callbacks, comment them out, so the system does not call them for nothing.

### `Empirica.onSet(callback)`

`onSet` is called when the experiment code call the `.set()` method on games, rounds, stages, players, playerRounds or playerStages.

#### Example

```javascript
Empirica.onSet(
  (
    game,
    round,
    stage,
    player, // Player who made the change
    target, // Object on which the change was made (eg. player.set() => player)
    targetType, // Type of object on which the change was made (eg. player.set() => "player")
    key, // Key of changed value (e.g. player.set("score", 1) => "score")
    value, // New value
    prevValue // Previous value
  ) => {
    // Example filtering
    if (key !== "value") {
      return;
    }

    // Do some important calculation
  }
);
```

### `Empirica.onAppend(callback)`

`onSet` is called when the experiment code call the `.append()` method on games, rounds, stages, players, playerRounds or playerStages.

#### Example

```javascript
Empirica.onAppend(
  (
    game,
    round,
    stage,
    player, // Player who made the change
    target, // Object on which the change was made (eg. player.set() => player)
    targetType, // Type of object on which the change was made (eg. player.set() => "player")
    key, // Key of changed value (e.g. player.set("score", 1) => "score")
    value, // New value
    prevValue // Previous value
  ) => {
    // Note: `value` is the single last value (e.g 0.2), while `prevValue` will
    // be an array of the previsous values (e.g. [0.3, 0.4, 0.65]).
  }
);
```

### `Empirica.onChange(callback)`

`onChange` is called when the experiment code call the `.set()` or the `.append()` method on games, rounds, stages, players, playerRounds or playerStages.

`onChange` is useful to run server-side logic for any user interaction. Note the extra `isAppend` boolean that will allow to differenciate sets and appends.

#### Example

```javascript
Empirica.onChange(
  (
    game,
    round,
    stage,
    player, // Player who made the change
    target, // Object on which the change was made (eg. player.set() => player)
    targetType, // Type of object on which the change was made (eg. player.set() => "player")
    key, // Key of changed value (e.g. player.set("score", 1) => "score")
    value, // New value
    prevValue, // Previous value
    isAppend // True if the change was an append, false if it was a set
  ) => {
    Game.set("lastChangeAt", new Date().toString());
  }
);
```

### `Empirica.onSubmit(callback)`

`onSubmit` is called when the experiment code call the `.submit()` on a Stage.

Note that onSubmit is only called if `.submit()` is explicitely called on the Stage object. Players for which the stage times out naturally, `onSubmit` will not be triggered.

#### Example

```javascript
Empirica.onSubmit((game, round, stage, player) => {
  stage.set("lastSubmitAt", new Date().toString());
});
```

### _**Adding Bots**_

{% hint style="danger" %}
We are currently updating documentation for Empirica v2. _**Bots**_ information here is incorrect.
{% endhint %}

Adding bots to a game is as simple as defining a few callbacks. You can add different bots with different behaviors.

### `Empirica.bot(name, configuration)`

The `bot` method allows to add a bot with `name` (e.g. "Alice"), while the `configuration` is a set of callbacks that will allow to configure how the bot is suppose to react in certain conditions.

The `configuration` has the follows callbacks:

- `onStageTick`: called during each stage at 1 second interval
- `onStageStart`: **CURRENTLY NOT SUPPORTED** called at the beginning of each

  stage (after `onRoundStart`/`onStageStart`)

- `onStageEnd`: **CURRENTLY NOT SUPPORTED** called at the end of each stage

  (after `onStageEnd`, before `onRoundEnd` if it's the enf of the round)

- `onPlayerChange`: **CURRENTLY NOT SUPPORTED** called each time any (human)

  player has changed a value

All callbacks are called with the following arguments:

- `bot`: is the [`Player` object](broken-reference) representing this bot
- `game`: the current [`Game`](broken-reference)
- `round`: the current [`Round`](broken-reference)
- `stage`: the current [`Stage`](broken-reference)
- `secondsRemaining`: the number of remaining seconds in the stage

#### Example

```jsx
Empirica.bot("bob", {
  onStageTick(bot, game, round, stage, secondsRemaining) {
    let score = 0;
    game.players.forEach(player => {
      if (player === bot) {
        return;
      }
      const playerScore = player.get("score");
      if (playerScore > score) {
        score = playerScore
      }
    });
    bot.set("score", score+1);
  }
};)
``` -->

## Client

{% hint style="info" %}
See the [Special Empirica Component](../guides/special-empirica-components.md) page for more info.
{% endhint %}

## Shared

{% hint style="danger" %}
We are currently updating documentation for Empirica v2. _**This section's**_ information here is incorrect.
{% endhint %}

### `Game` object

| Property    | Type                                            | Description                                                                                                                           |
| ----------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `index`     | Number                                          | An auto-increment number assigned to each Game in order (1, 2, 3...)                                                                  |
| `treatment` | Object (key: String, value: String or Integer)  | An object representing the Factors set on this game, e.g. `{ "playerCount": 12 }`.                                                    |
| `players`   | Array of [Player objects](api.md#player-object) | Players participating in this Game.                                                                                                   |
| `rounds`    | Array of [Round objects](api.md#round-object)   | On the server side, this will show every round that makes up the game. But on the client side, this will only show the current round. |
| `createdAt` | Date                                            | Time at which the game was created which corresponds approximately to the time at which the Game started.                             |

### `Round` object

| Property | Type                                          | Description                                                                        |
| -------- | --------------------------------------------- | ---------------------------------------------------------------------------------- |
| `index`  | Object                                        | The 0 based position of the current round in the ordered list of rounds in a game. |
| `stages` | Array of [Stage objects](api.md#stage-object) | Stages composing this Round.                                                       |

### `Stage` object

| Property      | Type    | Description                                                                                               |
| ------------- | ------- | --------------------------------------------------------------------------------------------------------- |
| `index`       | Object  | The 0 based position of the current stage in the ordered list of a **all** of the game's stages.          |
| `name`        | String  | Programmatic name of stage (i.e. to be used in code, e.g `if (name === "outcome") ...`).                  |
| `displayName` | String  | Human name of stage (i.e. to be showed to the Player, e.g "Round Outcome").                               |
| `duration`    | Integer | The stage duration, in seconds.                                                                           |
| `startTimeAt` | Date    | Time at which the stage started. (only set if stage has already started, i.e. not set in `onStageStart`). |

### `Player` object

| Property              | Type                       | Description                                                                                                                                                                                                   |
| --------------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `index`               | Number                     | An auto-increment number assigned to each Player in order (1, 2, 3...)                                                                                                                                        |
| `id`                  | String                     | The ID the player used to register (e.g. MTurk ID).                                                                                                                                                           |
| `urlParams`           | Object (key/value: String) | Parameters that were set on the URL when the user registered.                                                                                                                                                 |
| `bot`                 | String                     | Name of the bot used for this player, if the player is a bot (e.g. `Alice`).                                                                                                                                  |
| `readyAt`             | Date                       | Time at witch the player became ready (done with intro steps).                                                                                                                                                |
| `exitAt`              | Date                       | Time when the player exited the Game (whether the game ended normally or not, see exitStatus).                                                                                                                |
| `exitStatus`          | String                     | <p>Status of the Player at Game exit. <br><br> Can be: "gameFull", "gameCancelled", "gameLobbyTimedOut", "playerEndedLobbyWait", "playerLobbyTimedOut", "finished". "finished" represent the normal exit.</p> |
| `online`              | Boolean                    | True if the player is currently online.                                                                                                                                                                       |
| `idle`                | Boolean                    | True if the player is currently online but idle. Idleness is defined as either the page not being active (on another tab/window) or not detecting any activity (mouse/keyboard) for more than 60s.            |
| `lastActivityAt`      | Date                       | Time when the player was last seen online and active (not idle). Server only (this is not accessible on the client at the moment).                                                                            |
| `lastLogin.at`        | Date                       | Time the player last come online (registered, reopened page and auto-login kicked in or re-entered player ID – if they were forgotten).                                                                       |
| `lastLogin.ip`        | String                     | [IP address](https://developer.mozilla.org/en-US/docs/Glossary/IP_Address) of player on last connection.                                                                                                      |
| `lastLogin.userAgent` | String                     | [User-Agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) of player on last connection.                                                                                                      |

### `GameLobby` object

| Property      | Type                                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------- | ---------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `treatment`   | Object (key: String, value: String or Integer) | An object representing the Factors set on this game, e.g. `{ "playerCount": 12 }`.                                                                                                                                                                                                                                                                                                                                                |
| `queuedCount` | Integer                                        | <p>Total number of players queued for this game, including ready players and players currently going through the intro steps. <br> <br> <strong>N.B.: There could be more players in queuedCount than specified by the <code>playerCount</code> Factor, as Empirica can sometimes overbook Games to shorten wait times.</strong> <br> Use <code>gameLobby.treatment.playerCount</code> to get the expected number of players.</p> |
| `readyCount`  | Integer                                        | Number of players ready to play. They have completed the intro steps, and they are on the lobby page.                                                                                                                                                                                                                                                                                                                             |
