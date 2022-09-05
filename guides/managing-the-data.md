# Managing the Data

## Recording the data

There are multiple places where you can record data in an Empirica experiment.

### To the player

One way of recording the data of players' responses is to set them to the
`player` prop itself. You can do so with this command:

```
player.set("name_of_property", value)
```

You can retrieve what you have set as a specific property/answer for the player
with:

```
player.get("name_of_property")
```

### To the game, round or stage

If you want to save general data (not specific to one player), you can save it
to the `game`, `round` or `stage` with:

```
game.set("name_of_property", value)
round.set("name_of_property", value)
stage.set("name_of_property", value)
```

You can retrieve what you have set as a specific property/answer with:

```
game.get("name_of_property")
round.get("name_of_property")
stage.get("name_of_property")
```

### To the player.game, player.round or player.stage

One way of recording the data of players' responses is to set them to the
`player.game`, `player.round` or `player.stage` prop to identify a particular
data/response of a _particular player_ to a _particular game, round or stage_.
You can do so with this command:

```
player.game.set("name_of_property", value)
player.round.set("name_of_property", value)
player.stage.set("name_of_property", value)
```

You can retrieve what you have set as a specific property/answer with:

```
player.game.get("name_of_property")
player.round.get("name_of_property")
player.stage.get("name_of_property")
```
