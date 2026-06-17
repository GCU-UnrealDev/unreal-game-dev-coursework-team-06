NPC Features:<br/>
There are 2 types of NPCs in the game: a Melee and Ranged enemy, children of the Enemy<br/>
An Enemy has 4 States, and the higher one takes priority over the lower ones:<br/>

<pre><ol>
<li value="1">Dead<br/>
  o&nbsp;&nbsp;Upon reaching 0 hit points an enemy is considered dead<br/>
  o&nbsp;&nbsp;Ragdoll<br/>
  o&nbsp;&nbsp;Disable brain
</li>

<li value="2">Attacking (Melee):<br/>
  o&nbsp;&nbsp;Focus on the target<br/>
  o&nbsp;&nbsp;If has no weapons – equip them<br/>
  o&nbsp;&nbsp;Follow and attack the player once every 5 seconds:<br/>
    -&nbsp;Set movement speed (MS)<br/>
    -&nbsp;Clear focus<br/>
    -&nbsp;Move to the ideal range (attack range)<br/>
    -&nbsp;Focus on the target<br/>
    -&nbsp;Attack<br/>
    -&nbsp;Wait a set amount of time<br/>
  o&nbsp;&nbsp;Strafe around the player in a defensive position:<br/>
    -&nbsp;If not within the distance to strafe<br/>
      •&nbsp;Clear focus<br/>
      •&nbsp;Set MS<br/>
      •&nbsp;Move to the ideal range<br/>
    -&nbsp;Focus on the target<br/>
    -&nbsp;Set MS<br/>
    -&nbsp;Run EQS to find the perfect point to strafe to<br/>
    -&nbsp;Move to that point<br/>
    -&nbsp;Wait with a semi random interval
</li>

<li value="2">Attacking (Ranged):<br/>
  o&nbsp;&nbsp;If health is below a certain threshold:<br/>
    -&nbsp;Find cover:<br/>
      •&nbsp;Clear focus<br/>
      •&nbsp;Set MS<br/>
      •&nbsp;Run EQS to find the closest point where the player cannot see the enemy<br/>
      •&nbsp;Move to that point<br/>
    -&nbsp;Focus on the target<br/>
    -&nbsp;Heal by a set percentage<br/>
    -&nbsp;Wait for a set amount of time<br/>
  o&nbsp;&nbsp;If can see the target:<br/>
    -&nbsp;Attack the target every 5 seconds:<br/>
      •&nbsp;Set MS<br/>
      •&nbsp;Focus on the target<br/>
      •&nbsp;Wait a semi random interval<br/>
      •&nbsp;Attack<br/>
    -&nbsp;Move Around the player, strafing:<br/>
      •&nbsp;Run EQS to find the perfect ranged position<br/>
      •&nbsp;Move to that position<br/>
  o&nbsp;&nbsp;Move to the line of sight:<br/>
    -&nbsp;Clear focus<br/>
    -&nbsp;Set MS<br/>
    -&nbsp;Run EQS to find the closest position with a line of site to the player with a set parameters<br/>
    -&nbsp;Move to the position
</li>

<li value="3">Investigating<br/>
  o&nbsp;&nbsp;Focus on the target<br/>
  o&nbsp;&nbsp;(Melee Only) If no weapons equipped, equip them<br/>
  o&nbsp;&nbsp;Investigate:<br/>
    -&nbsp;Set MS<br/>
    -&nbsp;Move to the place where the sound was made<br/>
    -&nbsp;Wait<br/>
    -&nbsp;Go to the passive state if nothing found
</li>

<li value="4">Passive (default state)<br/>
  o&nbsp;&nbsp;(Melee Only) If weapons equipped, unequip them<br/>
  o&nbsp;&nbsp;If patrol route set – patrol:<br/>
    -&nbsp;Clear focus<br/>
    -&nbsp;Set MS<br/>
    -&nbsp;Move along the patrol route<br/>
  o&nbsp;&nbsp;If no patrol route set – wander around<br/>
    -&nbsp;Clear focus<br/>
    -&nbsp;If can find wander location (random available position on the map within a set distance:<br/>
      •&nbsp;Set MS<br/>
      •&nbsp;Move to the wander location<br/>
    -&nbsp;If can't find wander location:<br/>
      •&nbsp;Idle<br/>
      •&nbsp;Wait
</li>
</ol></pre>

To decide what state the enemy is in, they use their 3 senses:<br/>
-	Sight: On seeing a player an enemy goes into an attacking state<br/>
-	Hearing: On hearing a sound an enemy goes into investigating state<br/>
-	Damage: On getting damaged an enemy goes into an attacking state<br/>

Testing<br/>
To test the features:<br/>
-	Utilise the WASD and Space controls to move around and jump<br/>
-	Press N to make a noise<br/>
-	Press X to damage the Ranged Enemy (Orange)<br/>
