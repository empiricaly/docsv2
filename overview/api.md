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
  round.set("scoreToReach", round.currentGame.get("maxScore"));
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

### `Empirica.onStageEnded(callback)`

`onStageEnded` is triggered after each stage. It receives the current [game](api.md#game-object), the current [round](api.md#round-object), and [stage](api.md#stage-object) that just ended.

#### Example

```javascript
Empirica.onStageEnded(({ stage }) => {
  const expectedScore = stage.round.get("expectedScore");
  const group = stage.get("score") > expectedScore ? "great" : "not_great";
  stage.set("scoreGroup", group);
});
```

### `Empirica.onRoundEnded(callback)`

`onRoundEnded` is triggered after each round. It receives the current [game](api.md#game-object), and the [round](api.md#round-object) that just ended.

#### Example

```javascript
Empirica.onRoundEnded(({ round }) => {
  let maxScore = 0;
  round.currentGame.players.forEach((player) => {
    const playerScore = player.round.get("score") || 0;
    if (playerScore > maxScore) {
      maxScore = playerScore;
    }
  });
  round.set("maxScore", maxScore);
});
```

### `Empirica.onGameEnded(callback)`

`onGameEnded` is triggered when the game ends. It receives the `game` that just ended.

#### Example

```javascript
Empirica.onGameEnded(({ game }) => {
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

### Empirica.flush()

`Empirica.flush(): Promise<void>` adds the ability to manually flush changes outside of callback functions. This is useful when you want to make changes asynchronously without blocking the callback. For example, if you want to call an external API and update an attribute with the results, but your don't want to block the callback while waiting for the API to respond.

`Empirica.flush()` will return a promise that resolves when the changes have been flushed. You can use `await Empirica.flush()` to wait for the changes to be flushed. But you do not have to wait for the flush. It is only useful if you have multiple flushes in a single function, where you want to commit the changes in steps.

The simplest example:

```js
Empirica.on("stage", "myTrigger", (ctx, { stage, myTrigger }) => {
  callMyAPI.then((value) => {
    stage.set("value", value);
    Empirica.flush();
  });
});
```

An example with different use cases:

```js
Empirica.on("stage", "myTrigger", (ctx, { stage, myTrigger }) => {
  // Copying the stage to the global namespace so we can use it outside of the
  // callback function. See below this callback function.
  myStage = stage;

  // flush
  setTimeout(() => {
    stage.set("b", (stage.get("b") || 0) + 1);
    Empirica.flush();
  }, 2000);
});

// Note: copying a stage to the global namaspace like this is not recommended,
// this is just for illustration purposes. If you have multiple games running
// at the same time, stages will overwrite each other.
let myStage;
setInterval(() => {
  if (myStage) {
    myStage.set("c", (myStage.get("c") || 0) + 1);
    Empirica.flush();
  }
}, 1000);
```

Note: if you perform blocking operations between changes, the changes before the blocking operations **might** be flushed before flushing manually. The change log is global, so while you're blocking, other changes might happen in a callback elsewhere, and that could trigger a flush of all latent changes. If you want to make a set of changes atomic, you should not do any blocking operations between them (i.e. use `await` or Promises) or collect your changes in a local datastructure and apply them at once.

If you are starting an interval (`setInterval`), you should make sure to clear it properly. Here's an example with an interval per game:

```js
const timers = {};

// We use the game event to start the interval. this ensures that the interval
// is started on a server restart.
Empirica.on("game", (ctx, { game }) => {
  if (!game.isRunning) return;

  timers[game.id] ||= setInterval(() => {
    // do something
    Empirica.flush();
  }, 1000);
});

Empirica.onGameEnd(({ game }) => {
  clearInterval(timers[game.id]);
});
```

Or have a single interval that manages all games:

```js
const activeGames = new Set();

// We use the game event to start the interval. this ensures that the interval
// is started on a server restart.
Empirica.on("game", (ctx, { game }) => {
  if (game.isRunning) {
    activeGames.add(game);
  }
});

setInterval(() => {
  for (const game of activeGames) {
    // do something
  }
  Empirica.flush();
}, 1000);

Empirica.onGameEnd(({ game }) => {
  activeGames.delete(game.id);
});
```

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

<table><thead><tr><th>Property</th><th>Type</th><th>Description</th><th><select></select></th></tr></thead><tbody><tr><td><code>round</code></td><td><a href="api.md#round-object">Round object</a></td><td>Round this stage is a part of.</td><td></td></tr><tr><td><code>currentGame</code></td><td><a href="api.md#game-object">Game object</a></td><td>Game this stage is a part of.</td><td></td></tr></tbody></table>

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
