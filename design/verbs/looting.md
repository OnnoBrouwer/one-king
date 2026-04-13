# Purpose

Looting is the Barbarian equivalent of opening and removing all from a container.

# Commands

```
Looting is an action applying to one visible thing.
Understand "loot [something]" as looting.
Understand the commands "search" and "pilfer" as "loot".
```

# Help text

forcefully take the contents of.

# Effect

We remember the contents of the noun (for UNDO), and transfer it to the player.

# Instances

T.N | Location        | Container          | Looted item        | Effect
----|-----------------|--------------------|--------------------|-------
C01 | Royal Bedroom   | Bed                | Loincloth          | Player wears loincloth.
C04 | Dining Room     | Table              | Bottle of wine     | Player carries bottle of wine.
O44 | South Bank      | Altar              | Goat               | Goat escapes.
O65 | Pit of Darkness | Bottle of wine     | Wine               | Wine removed. Player ends up in Dark Corridor.
G22 | Dark River      | Ferryman           | Gold necklace      | Returns necklace to Lydia.
G34 | South Bank      | Altar              | Lydia              | Lydia ends up in the location.
G55 | Hall of Justice | Reliquary          | Vial of holy water | Alcaz enters the location.
G75 | Cavern of Bones | Vial of holy water | Holy water         | Holy water removed.
