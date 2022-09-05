# Game Life Cycle

_Elements on this page refer to the [concepts](../concepts.md), and [API](../api.md) of an Empirica experiment._

Empirica experiments are event driven. The image below summarizes the lifecycle from the beginning of a game through exit steps.

![](<../../.gitbook/assets/Picture3 (2).png>)

### Beginning and intro steps

In the admin panel, you would create a Batch of games for players to join. Players enter the game where they go through a consent form (optional), they provide an identifier (which can be set via URL queries), and they do the intro steps (the instructions and other components you have set in the intro steps. All of these are set by you in the `./client` . During these steps, players are **asynchronous**; namely, they complete these steps at their own pace until they have finished them, independent from the pace of other players.

### gameStart

Once players finish the intro steps they are sent to a lobby where they wait until every player has joined. When every player has joined, the Game object is created based on what is set in `./server/src/callbacks.js` in the `Empirica.onGameStart()`. This is where certain parameters are set, and where the Rounds and their Stages are created.

### Rounds and Stages

Then players go through each Stage of each Round. Once a Stage is finished, they move on to the next. If this was the last Stage of a Round, they move on to the next Round. If this was the last Round, they move on to the Exit Steps.

During these steps, players are **synchronous**; namely, every player has to finish each stage before they can all move on to the next.

In the `./server/src/callbacks.js`, a series of callbacks are triggered during this process:

- Before a round starts, [`onRoundStart`](../api#empiricaonroundstartcallback) is called.
- Before a stages starts, [`onStageStart`](../api#empiricaonstagestartcallback)is called.
- When a Stage ends, [`onStageEnd`](../api#empiricaonstageendcallback) is called.
- When a Round ends, [`onRoundEnd`](../api#empiricaonroundendcallback)is called.

See our guide on customising when player submit a stage:

{% content-ref url="customising-when-players-submit-stages.md" %}
[customising-when-players-submit-stages.md](customising-when-players-submit-stages.md)
{% endcontent-ref %}

### Game end and exit steps

Finally, when the last Round ends, after the end of Stage and Round callbacks are triggered, the [`onGameEnd`](../api#empiricaongameendcallback) callback is called in the `./server/src/callbacks.js`.

After which, the players goes through the exit steps. During these steps, players are **asynchronous**; namely, they complete these steps at their own pace until they have finished them, independent from the pace of other players.

### List of callbacks

The list of callbacks goes as follows in order:

- `onGameStart` Required
- `onRoundStart` Repeated for each Round
- `onStageStart` Repeated for each Stage
- `onStageEnd` Repeated for each Stage
- `onRoundEnd` Repeated for each Round
- `onGameEnd`
