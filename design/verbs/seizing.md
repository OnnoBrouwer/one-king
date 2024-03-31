# Purpose

Seizing is the Barbarian equivalent of taking something.

# Commands

```
Seizing is an action applying to one visible thing.
Understand "seize [something]" as seizing.
Understand "take [something]" as seizing.
Understand the commands "get" as "seize".
```

# Help text

forcefully take.

# Effect

We remember the holder of the noun (for UNDO), and transfer it to the player.

If we reached the end of the Choice table, we need to switch to another table depending on which weapon we seized (the original Single Choice):

Weapon seized | Table chosen   | Companion NPC
--------------|----------------|--------------
Sword         | Order vs Chaos | Alcaz
Axe           | Good vs Evil   | Lydia

# Instances

T.N | Location    | Noun  | Effect
----|-------------|-------|-------
O01 | Throne Room | Sword | Player wields the sword.
O09 | Throne Room | Axe   | Player wields the axe. Portal disappears. Alcaz enters.
O22 | North Bank  | Goat  | Player carries the goat.
G01 | Throne Room | Axe   | Player wields the axe.
G07 | Throne Room | Sword | Player wields the sword.
G15 | North Bank  | Lydia | Player carries Lydia.
