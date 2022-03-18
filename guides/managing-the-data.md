# Managing the Data

## Recording the data

There are multiple places where you can record data in an Empirica experiment.

### To the player

One way of recording the data of players' responses is to set them to the `player` prop itself. You can do so with this command:

```
player.set("name of property", value)
```

You can retrieve what you have set as a specific property/answer for the player with:

```
player.get("name of property")
```

### To the player.stage

One way of recording the data of players' responses is to set them to the `player.stage` prop to identify a particular data/response of a particular player to a particular stage. You can do so with this command:

```
player.stage.set("name of property", value)
```

You can retrieve what you have set as a specific property/answer with:

```
player.stage.get("name of property")
```

### To the player.round

One way of recording the data of players' responses is to set them to the `player.round` prop to identify a particular data/response of a particular player to a particular round. You can do so with this command:

```
player.round.set("name of property", value)
```

You can retrieve what you have set as a specific property/answer with:

```
player.round.get("name of property")
```

### To the round

If you want to save general data (not specific to one player), you can save it to the `round` with:

```
round.set("name of property", value)
```

You can retrieve what you have set as a specific property/answer with:

```
round.get("name of property")
```

### To the game

If you want to save general data (not specific to one player), you can save it to the `game` with:

```
game.set("name of property", value)
```

You can retrieve what you have set as a specific property/answer with:

```
game.get("name of property")
```
