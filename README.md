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




