# The Admin Panel

## Structure

The Admin Panel can be accessed at `/admin`. It is made of two parts:

* The **monitoring** section
* The **configuration** section

### The Monitoring section

Here you can create and run batches of games and monitor player statuses.

### The Configuring section

Here you can create factors and treatments before creating batches.

## Clearing Players: How players can play again, even if they were led to the exit steps.

Players can only play once. If there is a problem (e.g., the lobby timed out or the game was full), or if you want players to play again, you can _clear_ them, which allows them to play again.

In the **monitoring section**, in the **players tab**, you can see the status of every Player. A button called `Clear`, to the right of each player line, allows you to clear them one by one.

Once _retired_, players can refresh their page/return to the link of your game, and they will be randomly allocated to a game with the same treatment as before. They are allocated to a game with the same treatment, so they don't discover a game with different conditions or instructions.

## Treatments and factors settings

The treatments and factors are saved in a `.empirica/treatments.yaml`. It is often shared by simply committing it to your code versioning system (e.g., Git).

You can edit treatments and factors manually in that file (make sure to reload the admin page after edits).

Alternatively, you can edit these directly in the admin UI, which will update the `.empirica/treatment.yaml` file.
