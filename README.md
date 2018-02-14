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


CHANGES DONE 7

1) Added warning to start of scenario that the scenario is a real murder mystery.

2) Added additional clue about the painter to the painting.

3) Changed response of the Novice Druid given the dagger to make it clearer that the White Druid really does exist.


CHANGES DONE 8

1) French Translation by Indoy
2) Added mention of 2 wall tokens for cave
3) Fixed text of AllyD2.  Corrina (if she is given the dagger) refers to the wrong Druids.
4) Text for climbing oak tree makes it clear one success enought to pass.


CHANGES DONE 9 (v1.6)

1) Scenario intro Typo
Mansion(s) of Madness ('s' added)
2) Made 5 players easier by starting with a free evidence
[EventInitHeroes5]
countSigil,+,1
3) Made 2 players easier by delaying start of Dark Young 
DarkYoungStart,=,6
4) Starting Equipment Bug
Pendant turned up as is equipment
Added to [QItemStartingEquipment]
ItemCommonElderSignPendant ItemCommonRitualDagger ItemCommonTorch
5) Clarified Dark Young Movement
For every space it moves onto, all Investigators (and all Monsters that cannot Phase or Fly) on the space take 2 Damage. {agility} Negates
6) John have you come back to me at last! 
[EventPlaceOak} Changed to a question mark and removed mention of John.
[EventSummonGhostFail] Removed reference to John
7) Explicityly turned off Mythos Events for Indoor spaces
Explicitly set $mythosIndoors,=,0
Raised issue #761 to add check for indoors
8) Clue trail added to go south if stone inspected
[EventStone1Search2Done]
"Once the humming sound has died done, you briefly hear shouting coming from the south."
10) Replaced flavor mythos event with custom event
[EventMythosFirstRound]
'From the East comes the sound of a whippoorwill bird crying out as something huge moves through woods.\nNo Effect.'
Added bird sound.
11) Added Custom mythos event trigered by start of Deadly
[EventMythosTransformText]
'You feel your body start to transform.
You feel compelled to run deep into the dark forest.\n\nAll Investigators suffer 1 Damage ({strength} negates)\n\nAll Investigators on an Outdoor space move 1 space East.\n'
12) Added new hint to look south when searching stone
[EventStone1SearchDone]
'Once the humming sound has died done, you briefly hear shouting coming from the south.'
13) French Translation
[EventMythosFirstRound]
[EventMythosTransformText.text]
[EventStone1SearchDone.text]
14) Incrimented Version Number
Now 1.6
15) Renamed [EventSpawnGhost] to [EventGhost]
16) Renamed [EventSpawnGhostMore] to [EventGhostMore]
Added
[EventSpawnGhostDaggerVar1]
[EventSpawnGhostDaggerVar2]
[EventSpawnGhostDaggerVar3]

17) For < 4 players Dark Druid has dagger
[EventInitHeroes2]
[EventInitHeroes3]
[EventWhereIsDagger]

18) Telling Sylvia about Ritual
Gains 2 clues if dagger not obtained
Reduced successes needed on influence test by 1.
[EventAllyE2TellCursedA] Added Text
'Only a Druid of great power and lore can wield the power of the sigil and dagger!'


CHANGES DONE 10 (v1.6)

1) Picture Puzzle
Added easier puzzle for 2 players
Made it clearer only a powerful Druid could paint the picture

2) Added info to Sylvia's monologue about Ritual
[EventAllyE2AboutRitualA] + [EventAllyE2AboutRitualB]

3) Changed Sylvia's monologue about Cult
[EventAllyE2AboutCultA] + [EventAllyE2AboutCultB]


CHANGES DONE 10 (v1.7)

1) Turn off search Token for Beneath Bridge
Turned off for 2 Players as final plot twist turned off

2) Change text about restoring the painting
[EventPaintingB]
Redid text as it implied Corrina is a fraud and so a liar.

4) If not a Druid and role is 3
[AllyCloseFriendFemale]
Her limited understanding of Druidic lore annoyed the others.

[AllyCloseFriendMale]
His forgetfulness and lapses in concentration was getting worse.

5) Added new text for Dark Druid killed
[EventWizardDefeated] renamed [EventDarkDruidDefeated]
Added 
[EventWizardDefeatedA] Find dagger
[EventWizardDefeatedB] Find note about Bettina
[EventWizardDefeatedC] Find note that Pete Barker is a spy

6) [AllyE2AboutCult1] Text added
'Pete told me both of these Druids always told the truth.'

7) Added Elder Ward Item for search under the bridge
Under the bridge you find an Elder Ward

CHANGES DONE 11 (v2.0)

1) Renamed to v2.0
2) When placing AllyA check if role3
[PlaceAllyAMore]
3) [OakPass2B]
Fix RoleAllyD != 3 should be RoleAllyB != 3


