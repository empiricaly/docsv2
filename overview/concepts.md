# Concepts

_Elements on this page might refer to the_ [_life cycle_](lifecycle/) _or the_ [_API_](api.md) _of an Empirica experiment._

## Game

A Game is a single run of the experiment. It is also used to describe the experiment that was developed. One or more _Players_ participate in a Game. A Game is divided into three main parts: Intro steps, Game, and Exit Steps.

The _Intro Steps_ are when Players arrive in the game. Before arriving at the Lobby, they can read instructions, answer quizzes, etc.. The Intro Steps are asynchronous (each player completes them at their own pace). Once all the Players have reached the Lobby stage, the _Game_ initializes. The Game is composed of r_ounds_ divided into _Stages_. Players must complete every stage of a round before moving on to the next Round. The Game is synchronous (every player has to finish a stage before they can all move on to the next stage). Once every Round is complete, the Players will reach the _Exit Steps_ where they can read a debrief, answer questionnaires, etc. The Exit Steps are asynchronous.

## Player

Players are users participating in a Game. A game must have a least 1 Player. Each Player entry in the database will contain information such as their last login, their unique ID, the ID of the Game they are participating in, which steps they have accomplished, and any other data you additionally assign to Players (e.g., an avatar to represent the Player).

## Batch

A Batch is a set of 1 or more Games that run in parallel. Batches allow the creation of different assignment methods for player distribution: simple and complete. Batches are run one at a time in order of creation time. If you start multiple batches at once in the admin, only the first will accept players. Once full, the next batch will automatically start receiving players.

## Round

A Game is made up of 1 or more ordered Rounds. A round contains one or more stages. Rounds are usually composed of the same stages that repeat throughout the game.

For example, in the guess the correlation experiment, we ask the player to guess the correlation between a graph and a numerical value on each round. In the first stage of each round, it's the guess. The second stage is the reveal of the result. And in the third stage, we show what other players have guessed. All in the same round. And in the next round, we repeat those stages.

All rounds are not required to contain the same stages or even the same number of stages.

## Stage

A Round may contain one or more stages. A stage has a `duration`.

The `duration` is a required field that sets the duration of the stage **in seconds**, with a minimum of 5 seconds and no maximum. You can also allow Players to _submit_ a stage, which marks it as done for the given player. When all players have submitted, the stage is considered done. If the stage timer runs out, the stage is also considered done, whichever happens first.

Usually, a `name` field is used to programmatic reference the stage. It can later be used in the UI code to differentiate stages.

If you do not want to have a timer and wait until players submit, you can set the timer to an unreasonable value (e.g. 30000000 \~= a year), and hide the timer in the UI.

The Rounds and Stages are **synchronous** (every player has to finish a stage before they can all move on to the next stage). The timer allows you to avoid one Player not responding and stopping the other Players from continuing because a new stage starts when the timer ends.

## Factors

Factors are variables that will affect how a game will play. One _Factor Type_ is mandatory for any Empirica game, the `playerCount` number.

Factors are assembled into Treatments, which are themselves assigned to Games.

To create _Factor Values_, you must first create Factor Types. A _Factor Type_ describes the Factor. A \_Factor Type) has a `name`, a `description`, a `type,` and a `required` marker.

*   The `name` must be a code-friendly name, such a `playerCount`, which does not

    contain spaces or odd characters and is written in

    [camelCase](https://en.wikipedia.org/wiki/Camel\_case).
*   The `description` is a human-readable description used in the admin UI to help

    other admins understand what this factor does.
*   Finally, the `type` is a computing type (integer, string, ...) to limit what

    \_Factor Values _can be created for this \_Factor Type_.
*   Factor Types can also be marked as `required`, meaning they are required in

    all treatments.

The Factors can then be accessed as a property of the Game. This can be used to represent different conditions. For example, say you want some Games to show information from the other Players' answers to each other and some Games not to. You can have a "socialInformation" factor set to "yes" and "no", and only show the information from other Players if `game.socialInformation == "yes"` .

## Treatment

A Treatment is a named _set of Factors_. Each Factor can appear at most once in a treatment, and required Factors must be present. The set of Factors in a treatment must be unique. No two treatments with the same set of factors can be created.

## Game Lobby

A Game Lobby is where the players wait for other players to arrive until the game starts.

### Lobby Config

Lobby configs configure the Game Lobby for common scenarios. It contains a timer duration for the lobby and handles the experiment's behavior in case of timeouts. Such as whether it start anyway or cancel the game once the timer runs out.

## Intro Steps

The Intro Steps are pages shown to the user after registering and before the game or game lobby. The game designer can configure these steps to contain whatever is needed: instructions, a quiz, forms, etc.

The steps can be altered depending on the treatment assigned to the current player or the treatments.

The Intro Steps are **asynchronous** (each player completes them at their own pace).

## Exit Steps

The Exit Steps are pages shown to the user after the game. They are configured by the experiment designer and may contain: results, reward instructions, quiz, thank-you note...

The steps shown may be altered depending on any parameter of the player or the game (treatment, results, etc.).

The Exit Steps are **asynchronous** (each player completes them at their own pace).
