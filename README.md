NPC Features:<br/>
There are 2 types of NPCs in the game: a Melee and Ranged enemy, children of the Enemy<br/>

An Enemy has 5 States, and the higher one takes priority over the lower ones:<br/>
1. Dead:<br/>
  o	Upon reaching 0 hit points an enemy is considered dead<br/>
  o	Ragdoll<br/>
  o	Disable brain<br/>
2. Attacking (Melee):<br/>
  o	Focus on the target<br/>
  o	If has no weapons – equip them<br/>
  o	Follow and attack the player once every 5 seconds:<br/>
    -	Set movement speed (MS)<br/>
    -	Clear focus<br/>
    -	Move to the ideal range (attack range)<br/>
    -	Focus on the target<br/>
    -	Attack<br/>
    -	Wait a set amount of time<br/>
  o	Strafe around the player in a defensive position:<br/>
    -	If not within the distance to strafe<br/>
      •	Clear focus<br/>
      •	Set MS<br/>
      •	Move to the ideal range<br/>
    -	Focus on the target<br/>
    -	Set MS<br/>
    -	Run EQS to find the perfect point to strafe to<br/>
    -	Move to that point<br/>
    -	Wait with a semi random interval<br/>
3. Attacking (Ranged):<br/>
  o	If health is below a certain threshold:<br/>
    - Find cover:<br/>
      •	Clear focus<br/>
      •	Set MS<br/>
      •	Run EQS to find the closest point where the player cannot see the enemy<br/>
      •	Move to that point<br/>
    -	Focus on the target<br/>
    -	Heal by a set percentage<br/>
    -	Wait for a set amount of time<br/>
  o	If can see the target:<br/>
    -	Attack the target every 5 seconds:<br/>
      •	Set MS<br/>
      •	Focus on the target<br/>
      •	Wait a semi random interval<br/>
      •	Attack<br/>
    -	Move Around the player, strafing:<br/>
      •	Run EQS to find the perfect ranged position<br/>
      •	Move to that position<br/>
  o	Move to the line of sight:<br/>
    -	Clear focus<br/>
    -	Set MS<br/>
    -	Run EQS to find the closest position with a line of site to the player with a set parameters<br/>
    -	Move to the position<br/>
4. Investigating<br/>
  o	Focus on the target<br/>
  o	(Melee Only) If no weapons equipped, equip them<br/>
  o	Investigate:<br/>
    -	Set MS<br/>
    -	Move to the place where the sound was made<br/>
    -	Wait<br/>
    -	Go to the passive state if nothing found<br/>
5. Passive (default state)<br/>
  o	(Melee Only) If weapons equipped, unequip them<br/>
  o	If patrol route set – patrol:<br/>
    -	Clear focus<br/>
    -	Set MS<br/>
    -	Move along the patrol route<br/>
  o	If no patrol route set – wander around<br/>
    -	Clear focus<br/>
    -	If can find wander location (random available position on the map within a set distance:<br/>
      •	Set MS<br/>
      •	Move to the wander location<br/>
    -	If can’t find wander location:<br/>
      •	Idle<br/>
      •	Wait<br/>

To decide what state the enemy is in, they use their 3 senses:<br/>
-	Sight: On seeing a player an enemy goes into an attacking state<br/>
-	Hearing: On hearing a sound an enemy goes into investigating state<br/>
-	Damage: On getting damaged an enemy goes into an attacking state<br/>


Testing<br/>
To test the features:<br/>
-	Utilise the WASD and Space controls to move around and jump<br/>
-	Press N to make a noise<br/>
-	Press X to damage the Ranged Enemy (Orange)<br/>
