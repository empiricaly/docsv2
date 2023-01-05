# V2 Migration

V2 is a rewrite and, therefore, introduces a lot of changes. But we have worked hard to keep the core experience similar to v1. This guide explains the differences with v1, what you need to know to start a new experiment, and how you might migrate your existing experiments.

## Differences with v1

The significant difference is the backing technology: Empirica is no longer built on top of Meteor. It is a bespoke framework focused on experiment development. Day to day, this only changes things a little.

### The _empirica_ command

The command we use is now called `empirica` instead of `meteor`, but you still have an `empirica create` command to create a new project. And you start your development server by running the command without argument: `empirica`.

### Code organization

We still have `server/` and `client/` directories. They are separate npm projects now. We used to have one `package.json` at the root of the project. Now both the client and server have their `package.json`, meaning they have their own npm dependencies. This is cleaner and easier in the long run. Also, in both directories, you will now see a subdirectory called `src/`, where all your code will reside. The base directory for the server and client is now only used for the configuration of each project.

### Server-side

On the server, we have the same callbacks except one: `onGameInit` is not called `onGameStart` (we already had an `onGameStart` that was not very used, and we have now merged them).

The arguments for each callback have changed a bit. We only pass the main object for the callback. For example, `onGameStart` passes a Game object, and `onStageEnd` passes a Stage object. You can walk through the objects if you need to reach related objects. For example, if you need the Game object in a Stage callback (say `onStageStart`), you can do: `stage.round.game`. It follows the logical structure of the objects: batches > games > rounds > stages. Players for a game are on the Game object.

### Client-side

On the client side, we are using a recent version of React, so you must learn about [React Hooks](https://reactjs.org/docs/hooks-intro.html).

The main objects (game, round, stage...) are no longer passed down between Components. Instead, you use the custom React Hooks provided by the empirica package. The main hooks are `useGame`, `usePlayer` (current player), `usePlayers` (all players in the current Game), `useRound,` and `useStage`. The initial template demonstrates how to use these.

Configuration for intro and exit steps, as well as Consent, NewPlayerForm, Loading, and NoBatches components, are now all done in the `App.jsx`. See the [special-empirica-components.md](special-empirica-components.md "mention") page for details.

### Data&#x20;

The database is no longer MongoDB. It is a single JSON file that resides in the `.empirica/local` directory, called `tajriba.json` (Tajriba is the name of our API Server). To back up or clear the database, it is simply a matter of copying or deleting that file.

We do not recommend reading that file directly, as the format for that file might change over time. also, if you upgrade empirica, any previous `tajriba.json` file will be invalid with the newer version. Using the export command, you can still export the data from that file, even on a different version, though we recommend exporting data before upgrading, then clearing the Tajriba file after the upgrade.

The `empirica export` is the preferred way to access the data. See [#exporting-the-data](managing-the-data.md#exporting-the-data "mention") for details about the export command.

### Deployment

Deployment is no longer done in Meteor Galaxy. Deployment is much easier done manually than it used to be, but it is still very much manual at the moment. See the [deploying-my-experiment](deploying-my-experiment/ "mention") page for an example deployment. We are working on further simplifying deployment.

## Migrating an existing experiment

The process of migrating an existing experiment is not automatic. If you do not need the new features of v2 and are done with developing your experiment, we recommend keeping it on v1. If you have just started or are about to start, moving to v2 is a good idea.

If you wish to convert your existing experiment, we recommend you start by creating a new v2 experiment from scratch (see [quick-start.md](../getting-started/quick-start.md "mention")).

Then, move over your callbacks, making sure to change the reference to your objects (see the[#server-side](v2-migration.md#server-side "mention") section above).

On the client side, you will need to move over your configuration manually (intro/exit steps, component overrides... – see the [#client-side](v2-migration.md#client-side "mention") section above). For Components, we recommend starting by migrating everything over as is and simply using the React Hooks on the very top Components and letting your existing Components pass down the main object (game, round...) as they used to in v1. Later you can migrate your components one by one to the new Hooks model for added clarity/simplicity (as well as improved performance). However, it is not a mandatory change!

## Missing features compared to v1

There are a few known missing features compared to v1:

* **Bot** There is currently no bot system in v2. We have everything we need to implement a great bot system, we it's not there yet. We will release this as soon as possible. Let us know your use case in a ticket.
* **Improved Admin** There is, of course, an admin UI already in v2, but it could be more feature rich. We are working on improvements there. Again, if you have particular features you want to see, create a ticket with your experience, so to help us prioritize what to work on first.
* **Automated Deployment** Deployment currently requires setting up a server manually. We want to make this experience much easier. We're working on it.
