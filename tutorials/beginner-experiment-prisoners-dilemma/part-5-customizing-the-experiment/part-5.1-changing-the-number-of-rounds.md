# Part 5.1: Changing the number of rounds

When participants play multiple rounds of the prisoner's dilemma, knowing that they will have repeated opportunities to coordinate, we may expect them to behave more prosocially, in the hope that their partner will cooperate as well. We can test this by varying the number of rounds in our game.

The first thing we'll do is modify the "Treatments" file, found in `.empirica/treatments.yaml`. When we create a new empirica experiment from the template, the treatments file looks like this:

{% code title="treatments.yaml" lineNumbers="true" %}
```yaml
factors:
  - desc: playerCount determines the number of Players are in a Game.
    name: playerCount
    values:
      - value: 1
      - value: 2
      - value: 3
      - value: 5
      - value: 8
      - value: 13
treatments:
  - desc: "Single-player Game"
    factors:
      playerCount: 1
    name: Solo
  - desc: "Two-player Game"
    factors:
      playerCount: 2
    name: Two Players
```
{% endcode %}

The file is broken down into two sections: `factors`, and `treatments`. The factors section defines all of the ways that an experiment could vary - in the template experiment, there is only one dimension listed, the playerCount. The treatments section defines how different factors combine to create a particular treatment condition that a player will experience. This will become clearer as we go along.

#### Add a factor for the number of rounds

The first change we want to make is to simplify the factors and treatments that currently exist. Our current prisoner's dilemma experiment only makes sense with two players, so we can simplify the treatment file by cutting out the other options. (We still need to include `playerCount` to be in the file, however, or empirica won't know what our default should be.) We can also adjust the name and description of our baseline two-player game:

{% code title="treatments.yaml" lineNumbers="true" %}
```yaml
factors:
  - desc: playerCount determines the number of Players are in a Game.
    name: playerCount
    values:
      - value: 2
      
treatments:
  - desc: Standard one-shot prisoner's dilemma
    factors:
      playerCount: 2
    name: baseline
```
{% endcode %}

We can now add a factor for the number of rounds we want players to play. Indentation matters in yaml syntax, so this addition should be included directly beneath the `playerCount` factor, and parallel it exactly:

```yaml
  - desc: How many times participants will make a choice
    name: numRounds
    values:
      - value: 1
      - value: 3
      - value: 7
```

#### Create treatments that vary the numRounds factor

Now we need to add this factor to the existing baseline treatment, by adding the new factor specification to the treatment:

```yaml
treatments:
  - desc: Standard one-shot prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 1
    name: baseline
    
```

Now we can add an additional treatment underneath the baseline treatment for a short or long iterated game:

```yaml
  - desc: A short iterated prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 3
    name: short_iterated
  - desc: A long iterated prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 7
    name: long_iterated
```

At this point, your treatment file should look like the following:

{% code title="treatments.yaml" lineNumbers="true" %}
```yaml
factors:
  - desc: playerCount determines the number of Players are in a Game.
    name: playerCount
    values:
      - value: 2
  - desc: How many times participants will make a choice
    name: numRounds
    values:
      - value: 1
      - value: 3
      - value: 7
      
treatments:
  - desc: Standard one-shot prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 1
    name: baseline
  - desc: A short iterated prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 3
    name: short_iterated
  - desc: A long iterated prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 7
    name: long_iterated
```
{% endcode %}

#### Access the new treatments variable inside the code

Our changes to the treatments file tell Empirica that we'd like to vary the number of rounds, but Empirica still doesn't know what to do with this information yet. We need to update our code to use this information in how it creates games.

As we're using the new variable to set the number of rounds, we'll want to get access to it in the `onGameStart` callback where we set up the round and stages of the game, in the file `server/src/callbacks.js`.&#x20;

We'll add a line at the very top of the `onGameStart` callback that will give us access to the treatment object for this particular game:

```javascript
  const treatment = game.get("treatment");
```

This object contains both the `numRounds` and the `playerCount` variable, and will contain any other variables we set in the treatments file down the road. We can pull out just the variable of interest using [Javascript object destructuring](https://www.javascripttutorial.net/es6/javascript-object-destructuring/). This syntax essentially takes the variable from inside the treatment object and sets it to a constant also called `numRounds`, accessible anywhere within this function. This line can sit immediately after we get the treatment variable:

<pre class="language-javascript"><code class="lang-javascript"><strong>  const { numRounds } = treatment;
</strong></code></pre>

#### Create multiple rounds

Now that we have the numRounds variable, we can use it to set up multiple rounds of the game. We'll take our existing round and stage creation code and wrap it in a for loop. At the same time, we'll make sure each round gets a unique name:

```javascript
  for (let i = 0; i < numRounds; i++) {
    const round = game.addRound({
      name: `Round ${i}`,
    });
    round.addStage({ name: "choice", duration: 10000 });
    round.addStage({ name: "result", duration: 10000 });
  }
```

Now, if you play through the game, when you press "continue" after the Result stage, you'll be taken to another round of the Choice stage.

#### Compute a cumulative score

As this is a multi-round game, we can compute a cumulative score that changes after each round. We'll set this cumulative score on the player object, as we want its value to persist across rounds in the game.

In the `onStageEnded` callback, after we set the player's score for the round, we can first get the current cumulative score as below:

<pre class="language-javascript"><code class="lang-javascript"><strong>  const currentScore = player.get("score") || 0;
</strong></code></pre>

Notice that here we're using the "or" operator `||` as before to provide a default value for currentScore. This is because in the first round of the game, there will be no existing value for score, and so the `player.get(...)` command will return `undefined`. Using the "or" operator means we can recognize this as the start-of-game state, and handle it appropriately.

We can now update the player's score to be the previous `currentScore`, plus the score for the round:

```javascript
  player.set("score", score + currentScore);
```

Your complete code for `server/src/callbacks.js` should now look like this:

{% code title="server/src/callbacks.js" lineNumbers="true" %}
```javascript
import { ClassicListenersCollector } from "@empirica/core/admin/classic";
export const Empirica = new ClassicListenersCollector();

Empirica.onGameStart(({ game }) => {
  const treatment = game.get("treatment");
  const { numRounds } = treatment;
  for (let i = 0; i < numRounds; i++) {
    const round = game.addRound({
      name: `Round ${i}`,
    });
    round.addStage({ name: "choice", duration: 10000 });
    round.addStage({ name: "result", duration: 10000 });
  }
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
    const currentScore = player.get("score") || 0;
    player.set("score", score + currentScore);
  }
});

Empirica.onRoundEnded(({ round }) => {});

Empirica.onGameEnded(({ game }) => {});

```
{% endcode %}

Remember to restart the server to incorporate server-side code changes by pressing `<ctrl>+c` within the terminal window, and then using the command below to clear the database and restart the server:

```bash
rm .empirica/local/tajriba.json; empirica
```

When you go to the Empirca admin interface to create a batch, you have the option to select between the baseline and the short and long iterated prisoner's dilemma games. You can add multiple games to a batch, and as participants arrive they will be randomly assigned to a treatment within the batch. This helps you know that there are no systematic differences between the groups assigned to each condition. For more information, see:

{% content-ref url="../../../overview/randomization-and-batches.md" %}
[randomization-and-batches.md](../../../overview/randomization-and-batches.md)
{% endcontent-ref %}

Notice now that when you play through the game, the score listed in the upper corner of the timer bar updates with your cumulative score. This is because the default empirica experiment uses `player.get("score")` as its data source for this display. You can update how these components are visualized in `client/src/Profile.jsx`.
