# API

This document describes Empirica's [server](api.md#server), [client](api.md#client) and [shared ](api.md#shared)APIs.

## Server

### `Empirica.onGameStart(callback)`

The `onGameStart` callback is called just before a game starts, when all players are ready, and it must create rounds and stages for the game.

One (and one only) onGameStart callback is required for Empirica to work.

The callback receives one argument, the [`game` object](api.md#game-object), which gives access to the `players` and the treatment for this game.

It also offers the `addRound()` method, which allows to add a round to the `game`. The returned Round object will implement the `addStage(stageArgs)` method, which allows to add a Stage to the Round. The `stageArgs` object to be passed to the stage creation method must contain:

* `duration`: the stage duration, in seconds

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

\`\`

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

<pre class="language-javascript"><code class="lang-javascript"><strong>Empirica.onGameEnd(({ game }) => {
</strong>  let maxScore = 0;
  game.rounds.forEach((round) => {
    const roundMaxScore = round.get("maxScore") || 0;
    if (roundMaxScore > maxScore) {
      maxScore = roundMaxScore;
    }
  });
  game.set("maxScore", maxScore);
});
</code></pre>

### Empirica.on(model, callback)

`on(model, callback)` listens to the creation of new mode objects. Model objects are the "game", "round", "stage", "player" and "batch". The callback receives a `ctx` object, and the model object listened to. In the example below, we're listening to new games, so we receive the `game` as argument.

```jsx
Empirica.on("game", (ctx, { game }) => {
  if (game.get("initCalc")) return;
  
  game.set("initCalc", initCalcs());
});
```

{% hint style="warning" %}
Beware, `Empirica.on(model, callback)`is called on new objects **and** when the server restarts (when you run `empirica` or the server restarts after a code change in development mode). You should add a check such as the one in the example above, where we check if `initCalc` was already set at the top of the callback.
{% endhint %}

### Empirica.on(model, attributeName, callback)

`on(model, attributeName, callback)` listens on changes to the attribute of `attributeName` on `model`. Model objects are the "game", "round", "stage", "player" and "batch". The callback receives a `ctx` object, the model object, and the attribute value. In the example below, we're listening on changes to `choice` on the `player` model.

```jsx
Empirica.on("player", "choice", (ctx, { player, choice }) => {
  if (choice === "yes") {
    // ...
  }
});
```

{% hint style="info" %}
We recommend using the value of the attribute given on the callback argument instead of doing `.get(attributeName)` on the model object as the value could have changed changed asynchronously.
{% endhint %}

## Server Objects

### `Game` object

| Property       | Type                                            | Description                                          |
| -------------- | ----------------------------------------------- | ---------------------------------------------------- |
| `players`      | Array of [Player objects](api.md#player-object) | Players participating in this Game.                  |
| `rounds`       | Array of [Round objects](api.md#round-object)   | This will return every round that makes up the game. |
| `stages`       | Array of [Stage objects](api.md#stage-object)   | This will return every stage that makes up the game. |
| `currentRound` | [Round object](api.md#round-object)             | The current Round.                                   |
| `currentStage` | [Stage object](api.md#stage-object)             | The current Stage.                                   |

### `Round` object

| Property      | Type                                          | Description                   |
| ------------- | --------------------------------------------- | ----------------------------- |
| `stages`      | Array of [Stage objects](api.md#stage-object) | Stages composing this Round.  |
| `currentGame` | [Game object](api.md#game-object)             | Game this round is a part of. |

### `Stage` object

<table><thead><tr><th>Property</th><th>Type</th><th>Description</th><th data-type="select"></th></tr></thead><tbody><tr><td><code>round</code></td><td><a href="api.md#round-object">Round object</a></td><td>Round this stage is a part of.</td><td></td></tr><tr><td><code>currentGame</code></td><td><a href="api.md#game-object">Game object</a></td><td>Game this stage is a part of.</td><td></td></tr></tbody></table>

### `Player` object

| Property       | Type                                | Description                                         |
| -------------- | ----------------------------------- | --------------------------------------------------- |
| `id`           | String                              | The ID the player used to register (e.g. MTurk ID). |
| `currentRound` | [Round object](api.md#round-object) | Round the player is currently in.                   |
| `currentStage` | [Stage object](api.md#stage-object) | Stage the player is currently in.                   |
| `currentGame`  | [Game object](api.md#game-object)   | Game the player is currently in.                    |

## Client

{% hint style="info" %}
See the [Special Empirica Component](../guides/special-empirica-components.md) page for more info.
{% endhint %}

##
