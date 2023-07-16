# Part 5.2: Turning the chat on and off

In the standard prisoner's dilemma experiment, participants are not able to communicate with one another. We've left the chat enabled from the template experiment up until this point, but now we should set up a flag to enable or disable it, so we can measure the effect of the chat on the outcomes of the game.

#### Create a factor and treatments&#x20;

Let's return to the file `.empirica/treatments.yaml`. As we did when we changed the number of rounds, we'll create a factor for the chat:

```yaml
  - desc: Can players chat with each other during the game?
    name: chatEnabled
    values:
      - value: true
      - value: false
```

We update our existing conditions, and create new ones with the chat in different states. This time, we'll set the default behavior of the chat to be disabled:

```yaml
treatments:
  - desc: Standard one-shot prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 1
      chatEnabled: false
    name: baseline
  - desc: A short iterated prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 3
      chatEnabled: false
    name: short_iterated
  - desc: A long iterated prisoner's dilemma
    factors:
      playerCount: 2
      numRounds: 7
      chatEnabled: false
    name: long_iterated
  - desc: Standard one-shot prisoner's dilemma with chat
    factors:
      playerCount: 2
      numRounds: 1
      chatEnabled: true
    name: baseline_chat
  - desc: A short iterated prisoner's dilemma with chat
    factors:
      playerCount: 2
      numRounds: 3
      chatEnabled: true
    name: short_iterated_chat
  - desc: A long iterated prisoner's dilemma with chat
    factors:
      playerCount: 2
      numRounds: 7
      chatEnabled: true
    name: long_iterated_chat
```

As we add additional manipulations to the game, the number of different treatments begins to grow rapidly. Managing this type of complexity is exactly what Empirica was built to accomplish. Imagine creating a separate setup for each of these different conditions, rather than being able to simply parameterize the factors!

#### Enable or disable chat in the player display

In order to make use of the chat feature, we'll make changes to `client/src/Game.jsx`. Notice in this file that the `<Chat...>` component is embedded in syntax that looks like this:

```
{playerCount > 1 && <div>...</div>}
```

This is a [short-circuit condition](https://dev.to/harlessmark/short-circuit-evaluation-with-react-3dn4) that works as follows. Before the `&&` sign we have an expression that will evaluate to either `true` or `false`,  depending on the number of players in the game. The double ampersand `&&` indicates a logical "and" statement, which means that it will try and find out if the values on both the left and right side of the `&&` will evaluate to true. If the left-hand side value is false, then it knows that the statement as a whole must evaluate to false, regardless of what is on the right-hand side. So for efficiency, it stops at that point and doesn't even bother to evaluate the right-hand side - that is, it "short circuits" the full expression.

On the other hand, when the left-hand side is true, it will process what is on the right-hand side of the `&&`. In this case, it will find our chat component, which it evaluates as a [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value, and displays it to the screen.

All we need to do at this point is replace the left-hand side condition with one that looks for `chatEnabled`. We have two changes to make - first to replace `playerCount` in the treatment object destructuring line with `chatEnabled`:

```javascript
const { chatEnabled } = game.get("treatment");
```

Then we need to use `chatEnabled` in the left-hand side of the short-circuit operation. As `chatEnabled` already returns a `true` or `false` value, we can just use it directly as the left-hand side expression:

```jsx
  {chatEnabled && (
    <div className="h-full w-128 border-l flex justify-center items-center">
      <Chat scope={game} attribute="chat" />
    </div>
  )}
```

Your full code for `Game.jsx` should now look like this:

{% code title="client/src/Game.jsx" lineNumbers="true" %}
```jsx
import { Chat, useGame } from "@empirica/core/player/classic/react";

import React from "react";
import { Profile } from "./Profile";
import { Stage } from "./Stage";

export function Game() {
  const game = useGame();
  const { chatEnabled } = game.get("treatment");

  return (
    <div className="h-full w-full flex">
      <div className="h-full w-full flex flex-col">
        <Profile />
        <div className="h-full flex items-center justify-center">
          <Stage />
        </div>
      </div>

      {chatEnabled && (
        <div className="h-full w-128 border-l flex justify-center items-center">
          <Chat scope={game} attribute="chat" />
        </div>
      )}
    </div>
  );
}
```
{% endcode %}

Now when you restart empirica and play through a game, you'll be able to turn the chat on or off by selecting the appropriate treatment condition.
