# Purpose

Regarding is the Barbarian equivalent of examining something.

# Commands

We use the regarding command for several different scenarios:

## Regarding the player inventory

We implement taking inventory as looking at ourselves (which also shows the player's inventory).

```
Regarding-self is an action applying to nothing.
Understand "inventory" as regarding-self.
Understand "take inventory" as regarding-self.

Carry out regarding-self:
	try regarding Conan.
```

## Regarding the room

We implement regarding without a noun as looking at the room.

```
Regarding-room is an action applying to nothing.
Understand "regard" as regarding-room.
Understand "look" as regarding-room.

Carry out regarding-room:
	try looking.
```

## Regarding something or someone

We treat looking, examining, and reading identically.

```
Regarding is an action applying to one visible thing.
Understand "regard [something]" as regarding.
Understand "look [something]" as regarding.
Understand "examine [something]" as regarding.
Understand "read [something]" as regarding.
```

# Help text

scrutinize with suspicion or interest.

# Effect

Increment the regard counter of the noun.

# Instances

We only progress the story if the regarding action is listed as an allowed action.

Note that some regarding actions are listed as optional, i.e. the player can skip them.

T.N | Location          | Noun           | Optional | Effect
----|-------------------|----------------|----------|---------------------------------
C02 | Royal Bedroom     | Mirror         | YES      | 'as good-looking as ever' pales in comparison to this one.
O28 | Dark River        | River          | NO       | Releases the serpent.
O47 | Path of Order (1) | Marker         | YES      | Points the player east.
O49 | Path of Order (2) | Marker         | YES      | Points the player south.
O51 | Path of Order (3) | Marker         | YES      | Points the player south.
O52 | Path of Order (3) | Marker         | YES      | Points the player southwest.
O60 | Guard Room        | Tablet         | NO       | Tells the player about the Guard Riddle.
G20 | Dark River        | River          | NO       | Boat enters South Bank side of the river.
G37 | Path of Order (1) | Marker         | YES      | Player gets warned by Lydia about the tainted runes.
G50 | Guard Room        | Tablet         | NO       | Tells the player about the Path of Justice.
