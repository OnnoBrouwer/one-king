# Purpose

Marching is the Barbarian equivalent of going somewhere.

# Commands

There are three ways our Barbarian can go to another location.

## Entering

The game allows the player to enter gates, portals, and vehicles.

```
Marching-in is an action applying to one visible thing.
Understand "enter [something]" as marching-in.
Understand "enter" as marching-in.
```

Location          | Enterable       | Mapping | Destination
------------------|-----------------|---------|------------
Throne Room       | Portal          | west    | North Bank
North Bank        | Boat            | south   | Dark River
South Bank        | Gate            | south   | Path of Order
South bank        | Boat            | north   | Dark River
Hall of Justice   | Circle of light | down    | Cavern of Bones
Cavern of Bones   | Sigil           | down    | Crypt of the Sage
Crypt of the Sage | (Sigil)         | north   | Royal Bedroom

*BUG* The Sigil leading north from the Crypt of the Sage to the Royal Bedroom is accidentally defined as a scenery door and thus never shown in the room description.
Inform never complained when I defined the same thing twice. The code at lines 4283-4285 should have been removed:

```
The bedroom door is a closed unopenable not apparent scenery door.
The bedroom door is north of r-crypt.
The bedroom door is south of r-bedroom.
```

## Leaving

The game allows the player to leave vehicles and rooms with an 'exit' direction (The game can still refuse the action if the player cowardly tries to walk back).

```
Marching-out is an action applying to nothing.
Understand "leave" as marching-out.
```

Location          | Mapping | Destination
------------------|---------|------------
Royal Bedroom     | west    | Dining Room
Dining Room       | west    | Throne Room
Throne Room       | west    | North Bank (portal open)
Throne Room       | south   | (diverted) (portal closed)
Dark River        | north   | (cowardly action) (if at North Bank)
Dark River        | south   | South Bank (if at South Bank)
Guard Room        | up      | (cowardly action)
Pit of Darkness   | up      | (unreachable)
Dark Corridor     | west    | (cowardly action)
Crypt of the Sage | south   | (cowardly action)
Hall of Justice   | west    | (cowardly action)
Cavern of Bones   | down    | Crypt of the Sage

## Marching

```
Marching is an action applying to one visible thing.
Understand "march" as marching.
Understand "march [direction]" as marching.
Understand "march [text]" as a mistake ("[xyzzy]").
Understand the commands "go", "walk", "run" as "march".
```

We do need a 'hack' for handling directions entered without a corresponding verb, since this is handled by an implicit going action:

```
The convert going to marching rule is listed first in the check going rules.
Check going (this is the convert going to marching rule):
	convert to the marching action on the noun.
```

# Help text

Type a direction (NORTH, NORTHEAST, EAST, SOUTHEAST, SOUTH, SOUTHWEST, WEST, NORTHWEST, UP, or DOWN) to travel. The proper command is MARCH, but direction alone will suffice.

# Effect

We remember which direction we marched so we can refer back to it.

We also remember the original location and store it in the table.

We then move the player and any NPCs travelling with the player (Alcaz and/or Lydia) to the destination.

# Instances

T.N | Location          | Direction | Destination
----|-------------------|-----------|------------
C03 | Royal Bedroom     | west      | Dining Room
C05 | Dining Room       | west      | Throne Room
O16 | Throne Room       | west      | North Bank
O23 | North Bank        | south     | Dark River
O35 | Dark River        | south     | South Bank
O46 | South Bank        | south     | Path of Order 1
O48 | Path of Order 1   | east      | Path of Order 2
O50 | Path of Order 2   | south     | Path of Order 3
O53 | Path of Order 3   | southwest | Path of Chaos 1
O55 | Path of Chaos 1   | inside    | Path of Chaos 2
O56 | Path of Chaos 2   | inside    | Path of Chaos 3
O57 | Path of Chaos 3   | inside    | --> Guard Room
O63 | Guard Room        | south     | Pit of Darkness
O70 | Dark Corridor     | east      | Crypt of the Sage
G08 | Throne Room       | west      | North Bank
G16 | North Bank        | south     | Dark River
G24 | Dark River        | south     | South Bank
G36 | South Bank        | south     | Path of Order 1
G38 | Path of Order 1   | east      | Path of Order 2
G39 | Path of Order 2   | south     | Path of Order 3
G40 | Path of Order 3   | southwest | Path of Chaos 1
G42 | Path of Chaos 1   | inside    | Path of Chaos 2
G43 | Path of Chaos 2   | inside    | --> Path of Chaos 4
G49 | Path of Chaos 4   | down      | Guard Room
G54 | Guard Room        | east      | Hall of Justice
G63 | Hall of Justice   | down      | Cavern of Bones 1
G65 | Cavern of Bones 1 | northeast | Cavern of Bones 2
G66 | Cavern of Bones 2 | west      | Cavern of Bones 3
G72 | Cavern of Bones 3 | southeast | Cavern of Bones 4
G73 | Cavern of Bones 4 | north     | Cavern of Bones 5
G87 | Cavern of Bones 5 | down      | Crypt of the Sage
G95 | Crypt of the Sage | north     | Royal Bedroom

NOTE: The 'inside' direction is interpreted here as 'any valid direction' and is used for the 'Path of Chaos'.
