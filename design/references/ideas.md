# R001 : Royal bedroom (in bed)
- seize loincloth
- out
- regard mirror (examine self)
- : shriek from the throne room
- west (to throne room)
# R002 : Throne room
- seize sword (and smite demon)
##### game starts here
- seize axe (Alcaz enters the room)
- treat with Alcaz (Demon blood. I know of only one enemy capable of such a feat. We must take the fight to him.)
- : Alcaz : creates portal
- west (through portal)
# R003 : River Bank
- smite chest (coin)
- treat with Alcaz (rings bell)
- seize goat
- present coin (and enter boat)

R100 : At the Dark River
- get goat (and leave the wolf and cabbage behind)
- enter boat (the mage will float across the rover and therefore does not need to enter the boat)
- at the other side you release the goat (I am a warrior, not a farmer. I have no need of a goat.)
- A get healer (taking the goat would piss her off and refer to you as a horny farmer)
- A enter boat (the goat does not get eaten by the wolf, since they were there already when you arrived)
- room elements:
- broken bridge (so we need to get a ferry)
- bell (to call the ferryman)
- boat with hooded skeleton ferryman with space for two entities (player + goat) (player + healer)
- dried and cracked fountain (with a coin in the first round)
- treasure chest hidden behind the fountain (with a coin in the second round : its the ferryman's treasure chest)

solution sequence:
- LOOT FOUNTAIN/CHEST (gets coin)
- TALK MAGE/USE SWORD (on bell) (gets boat with ferryman)
- SEIZE GOAT/HEALER (gets payload)
- USE BOAT (enters boat with payload)
- USE COIN (pay the ferryman) (as you pass the coin into his hand, it disappears (and ends up in the chest))

dialogue:
- In the city, thieves are behanded.
- As for this thief, (pulling away the hood), all he has left is the hand. (only the hand receiving the coin is flesh and blood, everything else is a skeleton)

# R200 : At the entrance to the Maze of Order and Chaos
- use entrance
- A use wine (to drench the sword) : we need to have gained the wine at some point (from the mage? because he does not accompany you on this road?)
- A use flint (to set the sword aflame)
- A use sword / attack entrance (burn down the maze and walk across the burned maze directly to the other side)
# R21x : In the Maze of Order
- use sign (order)
You read "n n north". "Not quite my lord, there is more". You read "northwest". The mage pats you on the back. A nine-letter word! Congratulations! You can do it!
(make a reference that Inform by default only reads 9 letters : not even the gods of this realm could disambiguate longer words)
Exit used closes behind you, with fragrant flowers
You observe that the mage does not appear surprised by this (he knows this terrain well, since it is in his backyard close to the castle)
# R22x : In the Maze of Chaos
- use any exit (random)
Exit used closes behind you, with reeking flowers

# R300 : At the front gate of the evil castle
- talk to mage (to read the sign - it is a long text) (text will have an additional paragraph referring to the path of justice when carrying the sword and talking to the healer to read the sign, the mage omits this text on purpose we find out when the healer is reading the text)
- kill monster (guardian of chaos and lies)
- talk to monster (guardian of order and truth)
- enter gate
- A mention that you can know which guardian is order and which is chaos (the healer thinks that is impossible, you can only figure out the correct gate). then the Order guard confirms it and the Chaos guard denies it. You also do not need to choose a gate because you will tread the hidden path : the path of Justice.
- A talk to statue (guardian of justice) : the path of justice lies at your feet
- A go down

# R800 : At the Tomb of the Hermit (end of circular path)(in a dream)
- receive the blessing of the hermit (alone, the mage cannot go here)(the blessing will make the sword a holy object when applied to it which can defeat the evil mage)
- undo until you reach the first room and make the right choice (the mage will complain when you use undo, since he realizes he cannot reach his goal when you undo your path)
The healer will tell you that your accomplice (the mage) is deceiving you and you need to rewrite history / go back. You then wake up from your dream.

# Designer notes
- Undo makes little or no sense for a game offering a singe choice. I therefore have subverted the implementation of undo to allow the player to go beyond the beginning of the game in order to reach the location where he has to make his choice. This makes undo part of the correct path through the game. (no shortcut allowed, you need to reach the end of the first path before you receive the blessing and can reach the actual beginning of the game.) I also thought it funny if 'undo' actually shows what is happening when you undo an action.
- Based on ideas I had written down (the puzzles for the maze, the river, the gate of order/chaos) before this jam was announced.
