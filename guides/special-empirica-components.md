# Special Empirica Components

## No Games

The "No experiments available" page can be overriden in the `App.jsx` file with the `noGames` prop on `<EmpiricaContext>` like so (file simplified for clarity):

```jsx
import { MyNoGames } from "./MyNoGames.jsx";
// ...
export default function App() {
  // ...
  return (
    <EmpiricaParticipant>
      <EmpiricaContext noGames={MyNoGames}>
        <Game />
      </EmpiricaContext>
    </EmpiricaContext>
  )
}
```

The "no games" component does not receive any special props.

## Consent

The consent page can be overriden in the `App.jsx` file with the `consent` prop on `<EmpiricaContext>` like so (file simplified for clarity):

```jsx
import { MyConsent } from "./MyConsent.jsx";
// ...
export default function App() {
  // ...
  return (
    <EmpiricaParticipant>
      <EmpiricaContext consent={MyConsent}>
        <Game />
      </EmpiricaContext>
    </EmpiricaContext>
  )
}
```

The Consent component will receive one prop:

* `onConsent`: this is a function that should be called if the player consents. If they do not consent, you can either modify something on the page (e.g. hide the consent form) or redirect them away from the experiment.

Here's a simplistic Consent component example:

```jsx
export function MyConsent({ onConsent }) {
  return (
    <div>
      <div>Do you consent?</div>
      <div>
        <button type="button" onClick={onConsent}>
          Yes!
        </button>
      </div>
    </div>
  );
}
```

If you don't want to fundamentaly change the Consent, and only want to change the text of the default consent, you can use the Consent component provided with the Empirica package:

```jsx
import { Consent } from "@empirica/core/player/react";

export function MyConsent({ onConsent }) {
  return (
    <Consent
      title="Do you consent?"
      text="It's all good, mate."
      buttonText="OK"
      onConsent={onConsent}
    />
  );
}
```

## PlayerCreate (where players set their id)

Players have to set their id at a **PlayerCreate page** just after the consent page. This could be a name, an MTurk/Prolific id, a student id, an email, etc.

You might want to change its design, format, or instructions. For example, if you want participants to provide a student id but no other personal information, you would want to make your own clear instructions.

The default PlayerCreate.jsx page looks like this:

```jsx
import React, { useState } from "react";

export function MyPlayerForm({ onPlayerID, connecting }) {
  // For the text input field.
  const [playerID, setPlayerID] = useState("");

  // Handling the player submitting their ID.
  const handleSubmit = (evt) => {
    evt.preventDefault();
    if (!playerID || playerID.trim() === "") {
      return;
    }

    onPlayerID(playerID);
  };

  return (
    <div>
      <div>Enter your Player Identifier</div>

      <form action="#" method="POST" onSubmit={handleSubmit}>
        <fieldset disabled={connecting}>
          <label htmlFor="playerID">Identifier</label>
          <input
            id="playerID"
            name="playerID"
            type="text"
            autoComplete="off"
            required
            autoFocus
            value={playerID}
            onChange={(e) => setPlayerID(e.target.value)}
          />

          <button type="submit">Enter</button>
        </fieldset>
      </form>
    </div>
  );
}
```

There are 2 props passed to the PlayerCreate component:

* `onPlayerID`: the callback you must call with the player identifier you collected from the Player.
* `connecting`: this will be true while the player create being identified (after you have submitted with `onPlayerID`), until the player is "logged in". This field allows you to disable or hide the form while sending the login data to the server.

Once you've made your version of the PlayerCreate component, you can import it into the `App.jsx` file, and set the `playerCreate` prop on `<EmpiricaContext>` like so (file simplified for clarity):

```jsx
import { MyPlayerForm } from "./MyPlayerForm.jsx";
// ...
export default function App() {
  // ...
  return (
    <EmpiricaParticipant>
      <EmpiricaContext playerCreate={MyPlayerForm}>
        <Game />
      </EmpiricaContext>
    </EmpiricaContext>
  )
}
```

## Lobby

The lobby page can be overriden in the `App.jsx` file with the `lobby` prop on `<EmpiricaContext>` like so (file simplified for clarity):

```jsx
import { MyLobby } from "./MyLobby.jsx";
// ...
export default function App() {
  // ...
  return (
    <EmpiricaParticipant>
      <EmpiricaContext lobby={MyLobby}>
        <Game />
      </EmpiricaContext>
    </EmpiricaContext>
  )
}
```

At the moment, the Lobby does not have any special fields, but you do have access the current Player (`const player = usePlayer()`) and the current treatment (`player.get("treatment")`).

## Timer

There is a `Timer.jsx` component in the default game template that represents the stage timer and shows players how much time is left at that stage.

The time remaining on the current stage (in milliseconds) can be accessed with the `useStageTimer()` React Hook.

Note that the timer might not exist if there is no current stage (before the Game starts, or in between Stages)

Here is the code for a basic Timer component:

```jsx
import { useStageTimer } from "@empirica/core/player/classic/react";
import React from "react";

export function MyTimer() {
  const timer = useStageTimer();

  return (
    <div>
      {timer?.remaining ? Math.round(timer?.remaining / 1000) : 0} seconds
    </div>
  );
}
```

## Finished, Loading and Connecting

The Finished, Loading and Connecting pages can be overriden in the `App.jsx` file with the `finished`, `loading`, and `connecting` props on `<EmpiricaContext>` like so (file simplified for clarity):

```jsx
import { Myloading } from "./Myloading.jsx";
import { Finished } from "./Finished.jsx";
// ...
export default function App() {
  // ...
  return (
    <EmpiricaParticipant>
      <EmpiricaContext
        loading={Loading}
        connecting={Loading}
        finished={Finished}
      >
        <Game />
      </EmpiricaContext>
    </EmpiricaContext>
  )
}
```

These components do not receive any special props.

Function of these components:

* `loading`: is shown any time the experiment is loading, including between stages.
* `connecting`: us shown while the experiment is connecting to the server. This will happen on the initial page start, or if the server disconnects at any point. By default, the connecting page is the same as the loading page.
* `finished`: is the last page shown to the player after they have finished the Game and all the exit steps.

## Empirica Chat

{% hint style="warning" %}
This chat documentation has not been update for Empirica v2 yet and is likely incorrect!
{% endhint %}

To add a chat in Empirica, you can use our simple solution by using the **Empirica Chat**. For detailed information about Empirica Chat, see [here](https://github.com/empiricaly/chat).

### Installing

First, install Empirica Chat with:

```
npm install --save @empirica/chat
```

### Import and Usage

In the components you want to use the chat, import this:

```
import { Chat } from "@empirica/chat";
```

Then you can create the chat component with:

```jsx
<Chat player={player} scope={game} />
```

`chat` expects 2 required props:

* `player`: the current player
* `scope`: object that the chat will be attached to, can be game, round, or stage objects.

### Scoping

The scope is important because it determines where the chat data (the messages) will be stored. You can access them again afterwards based on the scope. For example, if the scope is set to the Round:

```javascript
const chat = round.get("chat") ?? [];
```

### Multiple chat instances within the same scope

You can pass an optional `customKey` string prop to differentiate different chats within the same scope. This changes which get/set key on the given scope the chat will be recorded.

```jsx
<Chat player={player} scope={game} customKey="casual_chat" />
```

### Display names

`Chat` also displays a name for each participant, which you need to set in the experiment independently of the `playerId`: `player.set('name', "myPseudonym")`

### Other functionalities

There are many other functionalities with Empirica chat that you can see [here](https://github.com/empiricaly/chat).
