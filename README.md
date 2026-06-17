NPC Features:
There are 2 types of NPCs in the game: a Melee and Ranged enemy, children of the Enemy

An Enemy has 5 States, and the higher one takes priority over the lower ones:
1. Dead:
  o	Upon reaching 0 hit points an enemy is considered dead
  o	Ragdoll
  o	Disable brain
2. Attacking (Melee):
  o	Focus on the target
  o	If has no weapons – equip them
  o	Follow and attack the player once every 5 seconds:
    -	Set movement speed (MS)
    -	Clear focus
    -	Move to the ideal range (attack range)
    -	Focus on the target
    -	Attack
    -	Wait a set amount of time
  o	Strafe around the player in a defensive position:
    -	If not within the distance to strafe
      •	Clear focus
      •	Set MS
      •	Move to the ideal range
    -	Focus on the target
    -	Set MS
    -	Run EQS to find the perfect point to strafe to
    -	Move to that point
    -	Wait with a semi random interval
3. Attacking (Ranged):
  o	If health is below a certain threshold:
    - Find cover:
      •	Clear focus
      •	Set MS
      •	Run EQS to find the closest point where the player cannot see the enemy
      •	Move to that point
    -	Focus on the target
    -	Heal by a set percentage
    -	Wait for a set amount of time
  o	If can see the target:
    -	Attack the target every 5 seconds:
      •	Set MS
      •	Focus on the target
      •	Wait a semi random interval
      •	Attack
    -	Move Around the player, strafing:
      •	Run EQS to find the perfect ranged position
      •	Move to that position
  o	Move to the line of site:
    -	Clear focus
    -	Set MS
    -	Run EQS to find the closest position with a line of site to the player with a set parameters
    -	Move to the position
4. Investigating
  o	Focus on the target
  o	(Melee Only) If no weapons equipped, equip them
  o	Investigate:
    -	Set MS
    -	Move to the place where the sound was made
    -	Wait
    -	Go to the passive state if nothing found
5. Passive (default state)
  o	(Melee Only) If weapons equipped, unequip them
  o	If patrol route set – patrol:
    -	Clear focus
    -	Set MS
    -	Move along the patrol route
  o	If no patrol route set – wander around
    -	Clear focus
    -	If can find wander location (random available position on the map within a set distance:
      •	Set MS
      •	Move to the wander location
    -	If can’t find wander location:
      •	Idle
      •	Wait

To decide what state the enemy is in, they use their 3 senses:
-	Sight: On seeing a player an enemy goes into an attacking state
-	Hearing: On hearing a sound an enemy goes into investigating state
-	Damage: On getting damaged an enemy goes into an attacking state


Testing
To test the features:
-	Utilise the WASD and Space controls to move around and jump
-	Press N to make a noise
-	Press X to damage the Ranged Enemy (Orange)
