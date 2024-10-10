---
title: Gameplay Mechanics
description: An initial dive into gameplay mechanics using Unreal Engine
author: Jan
date: 2023-12-11
categories: [2. PROGRAMMING, GAMEPLAY MECHANICS]
tags: [coursework, abertay, c++, unreal engine, blueprints, conversion]
---
# Introduction
For my coursework, I chose to focus on a Final Fantasy styled turn based combat gameplay
mechanic with an action timer. I am an avid Final Fantasy player and loved the Active Time
Battle concept Square Enix had used for their combat mechanics in the past
(Evans-Thirlwell, 2021). I am also in the process of developing an idea for a game that will
include a turn based combat and so am looking at different combat systems. Therefore, I
wanted to put a personal spin on a turn based combat system and see what works and what
does not. This mechanic was referenced from a YouTube tutorial by Ryan Laley who makes
entire mechanics in Unreal Engine blueprints. The blueprints were afterward converted into
C++.

# Link to Gameplay Video Presentation
{% include embed/youtube.html id='DMTATTaozkw' %}

# Clarification
The term “character” will be used frequently throughout this documentation. This refers to
the models within the player and enemy parties.

# Resources
The Mechanic is based on a blueprint tutorial found on youtube and the models and
animations are sourced from Adobe’s Mixamo website.

# Summary
In this mechanic, the player is greeted by a scene containing 6 characters, 3 player
characters and 3 enemy characters. The player party names, health and action timer bars
are displayed in the bottom right corner. Once the action timers fill, a target window menu
will be displayed with the options for attacking, selecting items and running. The “Items” and
“Run” buttons are non functional but were part of my ambition of incorporating them into the
mechanic. My main focus for the project however, was the turn based system. Once the
player chooses the “Attack” option, the player is prompted with a second window to choose
which enemy character to target. The player party character will then perform an attack on
the enemy, triggering attack and hit animations for the characters. A series of stat
calculations determine how strong, fast and resilient a character is.

# The Game
The inspiration for this mechanic comes from many turn based combat systems, ranging
from Pokemon (Vintage is the New Old, 2023) to Golden Sun(Chinn, 2021) to Wargroove
(Wargroove, n.d.) and Advance Wars (Castle23clash, 2023). Although a lot of inspiration is
taken from these games, the Active Time Battle mechanic Square Enix had used in most of
their Final Fantasy games (RPG o Mania, 2019) has shown the most intrigue.
Active Time Battle is a mechanic that involves the player to wait until their action timer gauge
of a party member is filled before they can attack with them (RPG o Mania, 2019). Usually
this timer is based on a calculation which includes the speed statistic of a character. Enemy
characters will usually have their separate action timers and will attack whenever their timers
are ready. Weaker enemies might attack once in the time of the player attacking while boss
characters could land three attacks until the player’s character gauges are filled (Forestl,
2014).
This creates a whole new dynamic onto turn based combat. The player needs to strategize
more and plan ahead as the enemy could lash out with a devastating blow at any time.
The mechanic for this game is based on Active Time Battle and Turn Based Combat
systems.

# The Rules
The rules for the combat mechanic’s work in a sequential order:
1. A speed calculation, based on the character's speed stat determines all 6 character’s
initiative order. Starting from highest to lowest speed, the characters will be stored in
an array. The player party’s action timers will be displayed and increased.
2. Once the action timer fills, the player can attack by choosing a target enemy. If the
speed of the enemy is faster than the player, the enemy will go before the player.
3. When a character attacks, an attack animation will be triggered and the target
window will be removed until the action timers fill.
4. During an attack, a damage calculation based on the character's strength stat is
performed and contested with a resistance calculation based on the defending
character's endurance stat. These calculations are triggered at a certain timestamp in
the attack animation blueprint.
5. A character’s hit animation is also triggered at the timestamp of the attacking
character’s animation.
6. The damage calculation will be deducted from the defending characters health point
stat and the attack will be considered resolved.
7. The current character will then be removed from the initiative array and their turn
comes to an end. Thereafter, the character with the next fastest speed calculation in
the array resolves their attack.
8. Once all characters have had their turn, the array will be refilled and the next battle
round takes place.

# Mechanic Specifications
Although this mechanic is based on a blueprint tutorial, converting this mechanic into C++
was not an easy task. The project contains a multitude of base and inherited classes.
Therefore, for a sense of clarity the classes will be explained individually rather than what
would be triggered in succession.

## BattleGameMode
When launching the application a main static camera is set to the scene and the player
controller is initialised. Both Player and Enemy characters are stored within PlayerUnits and
EnemyUnits arrays from the BattlePosition class in its initial scene setup.
Once the EnemyUnits have been stored, the UnitBattleHUD is set for each PlayerBase
stored within the PlayerUnits array and added to the PartyUnitHUD. This will display the
Name, Action Timer and HP of each player party member.
A Turn Request function stores all unique actors of type ABaseUnit, that is, all player and
enemy party characters, into a TurnOrder array. The StartTurn function will be called after a
character has been added to the TurnOrder array. This is to check if the next turn needs to
be prepared (i.e. if the TurnOrder array is for some reason empty) or if the unit's turn can
begin. If the TurnOrder array is indeed empty, the ReadyNextTurn function is called which
calls StartTurn and triggers a delegate to broadcast that the character's turn is completed
and removes the character. This will always be element zero within the TurnOrder array from
the battle round.
Once this check is complete a Sequence of type integer will be increased. If Sequence
reaches greater or equal to 2, Sequence will be set back to true and will retrigger the
StartTurn function check.

## BattlePosition
The functions SpawnPlayerUnit and SpawnEnemyUnit will check and set Player and Enemy
Placements. They will also add the characters to the aforementioned PlayerUnits and
EnemyUnits arrays respectively within the BattleGameMode class.

## BaseUnit
The BaseUnit class contains a BeginPlay functionality which calculates and sets the HP
current and max values of each character.
It also contains an AnyDamage function in which a defending character's true damage is
calculated and the “IsHit” montage of the defending character is triggered. The true damage,
which is the current HP minus the CalculateDamageResistance, is then subtracted from the
current HP value and set as an integer to avoid decimal values being displayed.

## PlayerBase & EnemyBase
Both Player and Enemy Base classes don’t have any C++ functionality and are only parent
classes of the BP_PlayerBase and BP_EnemyBase blueprints. The C++ classes were
necessary for being able to call the blueprints which are the parent blueprints of the player
and enemy characters.

## CameraTopDown
This class functions as a parent class to the BP_CameraTopDown blueprint. It is used to set
the camera to the BattleGameMode Class.

## CPlayerController
Just as the CameraTopDown class, this class functions as a parent class to the
BP_PlayerController blueprint. It is used to set the player controller input to the
BattleGameMode Class.

## UnitBattleHUD
Within this class, the names for the Enemy targets are populated to the HUD by calling the
PopulateTargetList function in the TargetWindow class. The animations for moving back and
forth between windows are also triggered depending on if the “Attack” or “Back” buttons are
clicked on.

## TargetWindow
The TargeWindow is a part of the HUD that displays all enemy targets. As mentioned above,
the PopulateTargetList function is called within the UnitBattleHUD class and will check if
there is a UPanel widget pointer. If there is, then it will clear all of its children. Then it will look
for the maximum size of the EnemyUnits array, which is three and add each enemy party
member of that array to the TargetWindow HUD.

## TargetWindowSlot
TargetWindowSlot inherits from targewindow and is the individual slot that displays each of
the enemy character’s name and the “Select Target” header. There were multiple attempts to
convert this widget however, due to setting the widget up in the blueprint designer the
conversion was more difficult than anticipated and therefore was reverted back to the
original blueprint.

## PartyWidget & PartyWidgetSlot
PartyWidgetSlot inherits from PartyWidget and is the individual slot that displays each of the
player character’s information (name, HP, action timer bar). As with the TargetWindow and
TargetWindowSlot blueprints, there were multiple attempts to convert these widgets and only
after a multitude of attempts, the decision was made to revert them back to their blueprint
states.

## BattleHeadsUpDisplay
This is another blueprint widget that calls the PartyWidget which then in succession displays
the individual player character names. On its own, the blueprint is the semi transparent box
displayed in the bottom right.

## StatTableStruct & StatModifier
These are two structs. The StatTableStruct contains the base stats for a base character
which are set as integers and are calculated in conjunction with the StatModifier struct.
The StatModifier struct is a struct containing the same struct names as the StatTableStruct
but are of type float and are set to 1.0f. Stats can be multiplied with the modifier to give each
character unique values (e.g. HPBase 100 * HPMod 0.8 = 80 HP). Both structs are called
from the CombatManager class and are made public in the editor for ease of change.

## CombatManager
The CombatManager class is the hub for the entire turn-based combat system. For this
class, certain functionality mentioned above, might be mentioned again to tie the strings
together.
The BeginPlay function sets variables. The BeginBattle function will set the action timer into
play and the Player will not be able to attack until the timer bar in the HUD is filled. The
action timer is also dependent on the SpeedCalculation function which calculates the
initiative order for each character.
The speed calculation is a result of normalised base unit speed stats subtracted by 1.0f
multiplied by the maximum action time minus the minimum action time which is then added
to the minimum action time (Laley, 2021).
Once the timer for a character is complete, the RequestTurn function is called which calls the
TurnRequest function in the BattleGameMode class, passing through a Character pointer of
the class ABaseUnit. The TurnRequest function adds this Character to a TurnOrder array
and calls StartTurn which is also within the BattleGameMode class. If the TurnOrder is not
empty then a function StartUnitTurn within the CombatManager is called.
The UnitBattleHUD is then called for the current player character’s turn and can choose
which target to attack. Once chosen, the index for that target will be set and the
AttackCommand function with the Character passed through as a parameter is called.
The AttackCommand function determines if a character's attack is a ranged or a melee
attack. Both the melee and ranged attack functions have the same functionality, however,
the option for further development after the deadline for this coursework is put in place.
If either type of attack is chosen, the widget is removed from the screen and the player’s
attack animation montage is triggered. Another timer is set which then successively calls the
EndUnitTurn function. This will broadcast a delegate with the name OnTurnEnded to notify
any classes who are listening for this delegate. The first character in the TurnOrder array will
be removed. Lastly, the BeginBattle function will be called once again and the character next
in line of the TurnOrder array will execute their turn.
There are two further foundational functions in the CombatManager class.
CalculateBaseDamage calculates the damage using the strength stats of the attacking
character before the resistance is calculated. The calculation is as follows:
Damage = ((BaseStat.Str * Mod.Str) * 5) * Random Number between 0.9 and 1.1)
(Laley, 2021)
CalculateDamageResistance calculates the CalculateBaseDamage result from above in
conjunction with the Endurance stat of a character.
The calculation is as follows:
Resistance = (baseDamage)^2 / (baseDamage + (BaseStat.end * Mod.end))
(Laley, 2021)
This is the true damage that will be deducted from the defending characters current HP
value


# Technical Discussion & Development
I have only opened Unreal Engine a handful of times in the past. Therefore, I was very much
going into the project blind. As Unreal Engine 5 can be daunting beyond description, I
approached the development by first researching how convoluted blueprints can be if one is
somewhat knowledgeable in programming. Once I had done my research, I made the
decision to create my project in blueprint and convert them afterwards into C++. This
decision is partially based on what has been mentioned frequently in the module's lectures in
which many developers work in blueprint first and then convert it into C++ after. My
conclusion to this was that if I am capable of converting blueprints then my chances for
employability are heavily increased.
I followed a tutorial to develop the blueprint project and downloaded the models from
Adobe’s Mixamo. The best way to get my head wrapped around the concept was to replace
the variables throughout the project first. Once the variables had been converted, I started
replacing the functions, which made the project more difficult to maintain and ensure that
everything was still fully functional. The reason being that the blueprints of the tutorial I was
following were not designed to be independent from another. And due to time constraints it
was not possible to look into optimisation. However, with the time that I had and overcoming
many situations of breaking the game, the project was converted successfully.

# UML Diagram
![UML](/assets/img/UMLs/GamePlayMechanics-UML.png)

The UML diagram is also in the submission folder due to its size

# Conclusion
To conclude, I found this project incredibly insightful. I created my first mechanic in Unreal
Engine by converting blueprints into code. A task I now appreciate much more. I also feel I
have become more accurate when researching specific nodes in blueprints and code in C++.
In terms of time management, I felt that I bit off more than I could chew. The original plan
was to set up turn based combat with melee and ranged attacks plus item features such as
healing, buffs and debuffs. I also had a tool in mind that would allow me to toggle stats
based on a level slider to check if the stats were well balanced.
However, these are all things that I will visit over the summer when there is more time to look
into turn based combat mechanics. I never considered approaching turn based combat with
a queue system and this project gave me far more insight than I could have imagined.
Understanding blueprints is definitely a learning curve and there are many things to consider.
Personally speaking, I would have preferred to programme the entire project in C++ from the
beginning as initially understanding the blueprints were the cause for me putting an
extension on this module. However, I am happy that I went out of my comfort zone and
started on the blueprints as this has given me an incredible understanding of how the
concept works. Converting from blueprints has also prepared me for the DES310 module
next term. I do hope that the DES310 project will be in C++ from the beginning, however,
knowing blueprints can also help artists include assets into the project more efficiently which
we can then easily convert to make the project run better.
