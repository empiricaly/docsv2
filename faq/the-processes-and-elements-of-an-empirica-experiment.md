# The Processes and Elements of an Empirica Experiment

{% hint style="danger" %}
We are currently updating documentation for Empirica v2. Some information on this page is incorrect.
{% endhint %}

### What is a React.js component?

A React.js component is the main building block of the frontend of your Empirica App. There are many tutorials online to help with your understanding of React.js.

In Empirica, we assign certain components for the Intro Steps, the Round, the Exit Steps, and a few other elements of the Game.

A component is composed of:

* **states** that affect what is rendered for the user, but that can also be changed by the user interacting with the rendered elements of the app.
* **props** provided from other components that can be used to determine what is rendered for the user.
* **other components** that it imports and builds into what it renders for the user.
* a **render function** that determines what is shown to the user with a mix of HTML (with `<> tags`) and JavaScript (with `{}`).

Each component is generally made into one `.jsx` file. Components can be imported into each other to build more complex components. Usually, the type of components used in Empirica are **class-based**.

A major perk of React.js components is that whenever one of their states change (e.g., because of the action of user), it will **refresh every component** **affected** and update what is rendered depending on the new states. This makes for web apps that live update what they look like and do. This is particularly useful for Empirica because you want to update what you show to players depending on states such as which responses they have given, which stage of the Game they are at, what other players are doing, etc.

Hence, there are some elements of a component you might want to render differently depending on certain props and states. You can use syntax such as `{ condition ? true : false }`or `{ condition && true}` where _condition_ is a condition that is tested, _true_ is what is rendered if this condition tests true, and _false_ is what is rendered if this condition tests false.

A component might look like this:

```jsx
// Importing elements and other components
import React, { Component } from "react";
import GivingResponse from "./GivingResponse";

export default class Questionnaire extends Component {
  // The state of the questionnaire
  state = {
    showHint: false,
  };

  // Handling if the player clicks to show hint (toggles the hint on and off)
  handleShowHint = () => {
    this.setState({ showHint: !this.state.showHint });
  };

  render() {
    // Getting the props
    const { player } = this.props;

    return (
      <div>
        <p> What is the name of the first person to set foot on the moon?</p>

        {/* A button that affects the conditional that
                 determines whether to show the hint or not */}
        <button onClick={this.handleShowHint()}>Show hint</button>
        {this.state.showHint && <p className="hintcolour">He was American.</p>}

        {/* Importing another component for the player to give their answer.
                 We pass down the prop of the player */}
        <GivingResponse player={player} />
      </div>
    );
  }
}
```

### How can I redirect a player if I detect they are using a certain browser or a mobile device?

You might not want players to join your game from a mobile or tablet, nor from certain browsers. To do so you can use [react-device-detect](https://www.npmjs.com/package/react-device-detect) and modify the first page of your experiment (e.g., the consent page, the NewPlayer page, or the first page of your Intro Steps) to prevent them from continuing the experiment if you detect the device or browser that you do not want.

To install react-device-detect use:

```
meteor npm install react-device-detect
```

react-device-detect has different Booleans that you can import and use in one of your components to detect whether the player is using a certain browser.

* isMobile for whether they are using a mobile device
* isChrome for whether they are using Chrome
* isFirefox for whether they are using Firefox
* isSafari for whether they are using Safari
* ...

And others than you can find out about [here](https://www.npmjs.com/package/react-device-detect).

Import them into the component with:

```
import { isMobile, isFirefox, isSafari, isChrome } from 'react-device-detect';
```

For example, if you want to render a different consent form if the player is using a mobile device or is not using Chrome:

```jsx
return !isMobile && isChrome ? (
  <div>This is the consent form...</div>
) : (
  <div>Please use a computer and Chrome.</div>
);
```

### How can I show a different Exit Step to players depending on whether they have finished the game or if the game was cancelled/had a problem?

In the `client/src/App.jsx` you set which components form the **Exit Steps** with the `exitSteps` prop on `EmpiricaContext`. You can use the `player.get("exitStatus")` to separate out whether they have finished the game or if they were sent to the exit steps because the game was cancelled/had an issue and send them to different Exit Steps.

For example:

```jsx
export default function App() {
  // ...
  return (
    <EmpiricaParticipant>
      <EmpiricaContext
        exitSteps={({ game, player }) =>  player.get("ended") === "finished" ? [PostSurvey, Thanks] : [Sorry]}>
        <Game />
      </EmpiricaContext>
    </EmpiricaContext>
  )
}
```

### Can players navigate back and forth between the Exit Steps?

For now, players cannot navigate back and forth between the Exit Steps.

Players can only move from one Exit Step to the next if the component has an element (e.g., a button) that will call the `next` prop. For example:

```jsx
<button type="button" onClick={next}>
  Finish this experiment
</button>
```

If you wanted multiple pages within the Exit Steps that players can navigate through, you could create a component within one Exit Step that has different components to form "pages" and with a state that knows which page it is at and navigating to and from them.

### Can a manually sent a player to an exit step?

You can have a piece of code to manually send a player to an exit stage if they do something (e.g., you want to give them a quit button) by using:

```
player.set("ended", "reason")
```

where the string is the name of the exit stage you want to send them to.
