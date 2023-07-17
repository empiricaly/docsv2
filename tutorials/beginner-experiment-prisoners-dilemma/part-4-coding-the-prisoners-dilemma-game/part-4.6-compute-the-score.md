# Part 4.6: Compute the Score

The last major piece needed to complete this section of the demo is to compute the result that a player receives based on their and their partner's choices.

#### Identify the correct time to compute the score

The score should be computed once, at the end of the "choice" stage. To coordinate this computation, we do it on the server side, in the `onStageEnded` callback function in `server/src/callbacks.js`. This function gets triggered at the end of each stage, and receives the recently closed `stage` object as an argument.&#x20;

The first thing we need to do is make sure that our code only gets run at the end of the _Choice_ stage. We can do this by adding a [guard clause](https://blog.webdevsimplified.com/2020-01/guard-clauses/) at the beginning of the `onStageEnded` function that stops execution of the function by returning from the function early, if it detects that the newly-ended stage was not a Choice stage. To test this we can include a `console.log` statement that should only print after the choice stage.

```javascript
Empirica.onStageEnded(({ stage }) => {
  if (stage.get("name") !== "choice") return;
  console.log("End of choice stage");
});
```

{% hint style="warning" %}
Surprise! This `console.log()` statement doesn't print in the browser console. This code is running on the server, rather than in the participant's browser, and so instead it prints in the terminal window that you used to start Empirica.
{% endhint %}

#### Loop over all the players

We don't have access to Empirica's 'hooks' on the server side, but we can get access to the players from the `stage` argument. `stage.currentGame` will give us access to the game object, and `stage.currentGame.players` will return the list of players:

```javascript
const players = stage.currentGame.players;
```

Once we have the list of players, we can loop over them and compute the list of scores:

```javascript
for (const player of players) {
  console.log("computing score for player ", player.id)

}
```

For each player, we need to identify the partner, using the same strategy as before. We'll need to find the partner for each player as we compute the player's score, so this will be inside our `for` loop:

```javascript
  const partner = players.filter((p) => p.id !== player.id)[0];
```

Now we need to get the choices made by both the player and their partner. This code looks mostly familiar

```javascript
  const playerChoice = player.round.get("decision");
  const partnerChoice = partner.round.get("decision");
```

#### Compute the payoff for each player

Once we know the choice that the player and their partner each made, we can compute the payoff for the player. In this case, we define a variable called `score` that we will assign a value (in months) based on both the player's choice and their partner's choice:

```javascript
  let score;
  if (playerChoice === "testify" && partnerChoice === "testify") {
    score = 6;
  } else if (playerChoice === "testify" && partnerChoice === "silent") {
    score = 1;
  } else if (playerChoice === "silent" && partnerChoice === "testify") {
    score = 12;
  } else {
    score = 2;
  }
```

Now we need to save the score to the `player.round` object, so that is available for our Results component to display. This will be the last line inside our `for` loop:

```javascript
  player.round.set("score", score);
```

Your complete code should now look like this:

{% code title="server/src/callbacks.js" lineNumbers="true" %}
```javascript
import { ClassicListenersCollector } from "@empirica/core/admin/classic";
export const Empirica = new ClassicListenersCollector();

Empirica.onGameStart(({ game }) => {
  const round = game.addRound({
    name: `Round`,
  });
  round.addStage({ name: "choice", duration: 10000 });
  round.addStage({ name: "result", duration: 10000 });
});

Empirica.onRoundStart(({ round }) => {});

Empirica.onStageStart(({ stage }) => {});

Empirica.onStageEnded(({ stage }) => {
  if (stage.get("name") !== "choice") return;
  console.log("End of choice stage");

  const players = stage.currentGame.players;
  
  for (const player of players) {
    console.log("computing score for player ", player.id);
    const partner = players.filter((p) => p.id !== player.id)[0];
    const playerChoice = player.round.get("decision");
    const partnerChoice = partner.round.get("decision");

    let score;
    if (playerChoice === "testify" && partnerChoice === "testify") {
      score = 6;
    } else if (playerChoice === "testify" && partnerChoice === "silent") {
      score = 1;
    } else if (playerChoice === "silent" && partnerChoice === "testify") {
      score = 12;
    } else {
      score = 2;
    }
    player.round.set("score", score);
  }
});

Empirica.onRoundEnded(({ round }) => {});

Empirica.onGameEnded(({ game }) => {});
```
{% endcode %}

#### Restart and run through the experiment again

At this point, we have completed the coding for the basic prisoner's dilemma game. To restart your server and test the game, close the existing server by pressing `<ctrl>+c` in the terminal window, and then entering the following command:

```sh
rm .empirica/local/tajriba.json; empirica
```
