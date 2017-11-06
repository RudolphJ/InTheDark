# In the Dark
Scenario for Valkyrie and Mansions of Madness, 2 edition

CHANGES DONE 1

1. Asking about the Ritual
Made slightly more random.
The order now goes:
	Not Role 1 decided by pre-shuffle of the roles
	Not Role 3 decided by pre-shuffle of the roles
	Not Role 4 decided by pre-shuffle of the roles
	Then random of
		Two thirds chance of Not Role 1 again
		One third chance of Not Role 4 again

2. Giving Sigil to Role 1
Calls up EventEliminated so will use the same image

3. Initialisation for 5 Investigators
Added for game balance.

4. Close Friend Text added for asking about Role 3
If an Ally is asked about Ally Role 3 they will reveal the Ally was a close friend of Martha.  For roles 1 and 2, this may be a lie.  Once done, a flag is raised so that the text is not repeated.

5. Darkness Tokens
Darkness Tokens cover all spaces of a tile.
Text added to Scenario and to the placement of tiles.

6. Cellar Crate
Added test for the searching of the crate

7. Ghost of Bettina
Fixed reference to husband and step-sister.


CHANGES DONE 2

1. Painting
Incremented countSigil for all events triggered by solving the painting.

2. Give Sigil to Role 2
Redid the text so the Druid grabs the sigil and drops it.

3. EventPlaceRitualSite
Added a repeat of WhoHasDagger,=,#rand3 as currently the randomizer seems to favour the number 1 when Valkyrie is run for the first time.

4. Camp Fire
The camp fire goes out at the end of the MajorMythosRound.
This can have a significant effect on the finale.

5. Spawned Dark Young at Graveyard
Monster spawned in the rightmost space.

6. Simplified the Dark Young Retreat
[EventDarkYoungRetreat]
Text is simplified and the question reversed.


CHANGES DONE 3


1.  Grave Stone Added
Text about Bettina moved from Grave to Grave Stone.

2.  Grave Search
Body of the Druid Matt Barker replaces unknown hiker.

3.  Matt Barker added as a Druid
The question 'When did you last see Matt Barker' added to each ally.

4.  Zombie Druid Added
If there are more than 3 investigators, Zombie Druid added with very low health.  Now, players who like combat have something extra to kill.

5. Fire
Yet more hints added about the Beltane ritual. 

6. Dark Young Retreat made faster
EventDarkYoungRetreat text changed to following to speed up it getting to the Forest from the Shack.
	The monster moves 1 space East.
	If it cannot move to an adjacent space East, it will 	instead move to an adjacent space South.
	Then, after the first move, the monster moves 1 space 	East.
	It cannot move across a dashed yellow line.
	Did the monster move at least one space?
		Yes, the Monster moved at least one space
		No, it did not move even one space

7.Added check for Dagger Found to spawning at the Shack\Graves
EventSpawnDarkYoungOther added check DaggerFound,==,0.
Once the dagger is found the monster gets to the ritual site for the big finale.


CHANGES DONE 4

1) Question 'Who owns this cabin?' (Question improved)
Replace with 'Can you tell me about this place?'
The original question sounds like the investigator wants to buy the cabin.

2) Attack Ally instructs removal of wrong Ally Token (Bug Fix)
[SpawnWizard1] move text 'Remove the <X> Ally Token' to the event [EventAttackConfirmedX]
Otherwise the wrong Ally Token is removed.

3) [EventTokenAllyD3] (Bug Fix)
add=TokenAllyB3 should be add=TokenAllyD3

4) [EventAllyE1Monologue2] The term wizard implies male (Response made clearer)
'one of them is a Dark Druid and a powerful wizard!'
Replace the term 'wizard' with 'spell caster'.

5) Renamed Matt Barker to Pete Barker
The name Matt Barker sounds too similar to the British TV presenter Matt Baker

6) Sylvia Marsh now gives info about Barker 
[EventAllyE1Monologue2] 
e.g. 'Barker agreed to meet us tonight with proof of who is a Dark Druid'

7) [TokenDrownedBody] 
Text 'Push the 'Body' replaced with the 'Push the woman'

8) Typos fixed
Replace holy bush with holly bush
Replace short out this mess with sort out this mess

9) Message that the Camp Fire Burns Out is shown on repeated turns (Significant Bug)
[EventCampFireGoesOut] 
The event for the fire burning out may occur repeatably
In conditions=#round,>=,MajorMythosStart replace >= with =

10) The investigators must now find the Old Journal before the door to the Shack can be opened
Both Steve and Fran thought Corrina (like Ammi) would only open the door if the investigator had the Sigil.
The test now requires finding the Old Journal (and learning about the history of the Beck family).
[ShackDoorLocked1]  'You are outsiders who know nothing about the history of  the Beck family and this place!'
[ShackDoorLocked2]  Corrina refuses to open the door if JournalFound == 1
[ShackDoorLocked3]  Influence test (3 successes needed) if JournalFound == 0

11) The Retreat of the Dark Young now is split into two questions
With the retreat of the Dark Young, Steve read the question to mean the Dark Young is removed if it cannot make the final (second) move east.
So the question is now split into two questions.
	[EventDarkYoungRetreat] 
	The monster moves 1 space East.
	If it cannot move to an adjacent space East, it will instead move 1 space South.
		Did the monster move at least one space (either East or South)?
			Yes, the Monster moved at least one space [Calls EventDarkYoungRetreatSecondStep]
			No, it did not move even one space

	[EventDarkYoungRetreatSecondStep]
	The monster moves 1 additional space East.	

12) Torch card now placed on camp fire space
This makes it more of a challenge to get the Torch card.
Added the existing RemoveDarknessCamp event to the events triggered by igniting camp fire.

13) Redid the answers to the question 'When did you last see Pete Barker?'



CHANGES DONE 5

1) Various Typos fixed

2) Sylvia Marsh
Added new option 'Tell her what you know about the Ritual'
Add new monster spawn 'Child of Dagon'
The effect of attacking Marsh is now different and more dramatic!

3) UI Image
Used the images of the stones for the UI Introduction

4) Place Investigators
Modified so 1 Clue is given to a random investigator
All investigators gain the Dazed Condition

5) Added hints that being dazed was caused by the Dark Druid

6) Added humming noise to stones

7) Split music into 2 parts - introduction and chanting

8) Added general hints to EventSpoilers



CHANGES DONE 6

1) Major bug in Valkyrie prevents Mythos Events for 5 players
Workaround until bug in Valkyrie fixed
If two StartRound or EndRound events run in same round sometimes only one is resolved.
[EventInitHeroes5]
Changed MinorMythosStart,=,1 to MinorMythosStart,=,2

2) Goat Spawn 1 not triggered
This bug was because the check for the saving of the drowned woman which has been removed.
conditions=#round,==,GoatSpawn1Start DrownedSaved,=,0

3) Cult Sigil
Inspecting the item now allows defeating of Child of the Goat and Goat Spawn

4) Numerous typos fixed

5) Old Journal
Text rephrased as it implied all the children were daughters.
Added text about pages missing.




