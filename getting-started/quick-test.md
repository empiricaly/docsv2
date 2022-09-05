---
description: >-
  Once you have created an experiment using empirica create.
---

# Running your experiment

## Running the app locally

Run the app on your local machine with one command:

```
empirica
```

This can take a few minutes.

This will start the app that you can access as a participant: [http://localhost:3000](http://localhost:3000)

You can access the `admin panel` here: [http://localhost:3000/admin/](http://localhost:3000/admin/)

## Loading the factors and treatments

Treatments and factors can be entered via the admin panel.

Empirica also enables "experiment as code" by which experimental treatments and
factors can edited directly in [YAML](https://learnxinyminutes.com/docs/yaml/)
at `.empirica/treatments.yaml`.

## Testing the app

To run a game, create a new `batch` with the games of treatments you want to use and click start on the batch.

Open a player tab by going to [http://localhost:3000](http://localhost:3000).

The player that you open with [http://localhost:3000](http://localhost:3000) is
cached on your browser. Whenever you start a game with this player, your local
app will keep that information. To play again there are multiple things you can
do:

- Click on the **Reset current session** button in the bottom right menu to
  reset this player, and create a new game for this player to join.
- Click on the **New Player** button in the bottom right menu to open a new tab
  with a different player (you will see tab with an id).

**The app will automatically ("hot") reload when save changes to the code.**
