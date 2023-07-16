# Part 4.1: Removing example code

When you create an experiment with the `empirica create` command, Empirica populates a template experiment with the jelly bean and minesweeper code that you saw in the previous step.  We won't use this example code in our experiment, so let's clean it out. There are a few steps:

* delete the entire `client/src/examples` folder
* In `client/src/Stage.jsx`:
  * remove the imports for `JellyBeans` and `MineSweeper` (2 lines)
  *   replace the `switch` statement and its three cases (8 lines, including brackets) with the code \`

      ```
      return (<p>Not yet implemented...</p>)
      ```

The file should look like this when you are done:

{% code title="Stage.jsx" lineNumbers="true" %}
```jsx
import {
  usePlayer,
  usePlayers,
  useRound,
} from "@empirica/core/player/classic/react";
import { Loading } from "@empirica/core/player/react";
import React from "react";

export function Stage() {
  const player = usePlayer();
  const players = usePlayers();
  const round = useRound();

  if (player.stage.get("submit")) {
    if (players.length === 1) {
      return <Loading />;
    }

    return (
      <div className="text-center text-gray-400 pointer-events-none">
        Please wait for other player(s).
      </div>
    );
  }

  return (<p>Not yet implemented...</p>)
}
```
{% endcode %}

* In the `server/src/callbacks.js` file:
  * empty the contents of the `onGameStart` and `onStageEnded` functions, keeping the function definitions
  * delete everything after the empty function definition for `Empirica.onGameEnded({})`.

When you are done, the file should look like this:

```javascript
import { ClassicListenersCollector } from "@empirica/core/admin/classic";
export const Empirica = new ClassicListenersCollector();

Empirica.onGameStart(({ game }) => {});

Empirica.onRoundStart(({ round }) => {});

Empirica.onStageStart(({ stage }) => {});

Empirica.onStageEnded(({ stage }) => {});

Empirica.onRoundEnded(({ round }) => {});

Empirica.onGameEnded(({ game }) => {});
```

> Note: In JavaScript, a callback function is a function that is passed as an argument to another function and is invoked or called at a specific point within that function's execution. The callback function is typically used to ensure that certain code is executed only after the completion of a specific task or operation. In our case, these callbacks are invoked when parts of the experiment start and end.

#### Restart empirica

Now we can restart Empirica to have it reflect our changes. The command below will remove our existing datafile and start the server.

```sh
rm .empirica/local/tajriba.json; empirica
```

At this point of the tutorial, you should be able to start a new game on the admin site ([http://localhost:3000/admin/](http://localhost:3000/admin/)). On participants' window ([http://localhost:3000/](http://localhost:3000/)), when you enter into the game, you'll see the message "Not yet implemented..."

