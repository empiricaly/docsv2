---
description: >-
  Once you have created an experiment using either create-empirica-app or a git
  clone.
---

# Running your experiment

## Installing the node modules

Whenever you _first_ pull or clone an app from a repository, you need to run this command to install all the Node packages in both client and server directories:

```
cd client
npm install
cd ../server
npm install
```

## Running the app locally

Run the app on your local machine with one command:

```
empirica
```

This can take a few minutes.

This will start the app that you can access as a participant: [http://localhost:8882](http://localhost:8882)

You can access the `admin panel` here: [http://localhost:8882/admin/](http://localhost:8882/admin/)

Log in with the _username_ and _password_ found in `.empirica/empirica.toml`.

## Loading the factors and treatments

Treatments and factors can also be entered manually via the admin panel.

Empirica also enables "experiment as code" by which experimental treatments and factors can edited directly in [YAML](https://learnxinyminutes.com/docs/yaml/) at `.empirica/treatments.yaml`.&#x20;

## Testing the app

To run a game, create a new `batch` with the games of treatments you want to use and click start on the batch.

Open a player tab by going to [http://localhost:8882](http://localhost:8882).

The player that you open with [http://localhost:8882](http://localhost:8882) is cached on your browser. Whenever you start a game with this player, your local app will keep that information. To play again there are multiple things you can do:

* Click on the **Reset current session** button in the bottom right menu to reset this player, and create a new game for this player to join.
* Click on the **New Player** button in the bottom right menu to open a new tab with a different player (you will see tab with an id).

**The app will automatically ("hot") reload when save changes to the code.**
