# Documentation – Manual APWorld for HFW

This is my documentation for the creation of a manual APWorld for Horizon Forbidden West. Well, it's not really a documentation, but more of a thought log. That's the reason why it's not well structured, because my thoughts weren't. I also mostly didn't go back to change things. There are some exceptions though (like this paragraph)

## Initial Ideas

Here are my initial Ideas for this like what are location checks etc.

- CHEAT MOD REQUIRED
- Each Quest has an Item associated with it, which unlocks that quest.
- Quests require having specific Equipment unlocked
- Finishing a quest sends a location check
- Equipment can be classified into the following categories:
  - Damage
  - Applies a specific Debuff (Freeze etc.)
  - Grouped by Rarity
  - Level of Quest translates to Rarity required
- There are different levels of equipment which can be unlocked
- This is because one weapon deals more damage than the other
- Upgrades could also be unlocked
  - Maybe as filler? Upgrade of your choice?
- As quests count the following things:
  - Main Quest, Side Quests, Errands
  - Tallnecks
  - Cauldrons
  - Rebel Camps/Outposts
  - Hunting Ground Trials
  - Salvage Contracts
  - Gauntlet Runs
  - Melee Pits
  - Relic Ruins
  - Arena
  - Black Boxes, Drones, Vista Points
- Buying Weapons also sends location checks
- Filler Items could be…
  - Shards
  - Ammo Crafting Resources

## What are Location Checks?

- Buying a Weapon/Outfit (excluding NG+ Weapons/Outfits, as they can't be bought in NG)
- Completing an Activity
- Killing the first Machine of a Kind (not including Variants)

## What are Item Unlocks?

- Unlocking a Weapon (including NG+ Weapons)
- Unlocking a Quest (Main Quest, Side Quest, Errand)
- You may now kill Machine X

## What are Fillers?

- 100/250/500/1000 Shards
- Cheat yourself a Machine Component (Heart or others)
- Upgrade a Weapon/Outfit for free
- Upgrade a Pouch for free
- Free Potion, Food and Medicine Restock
- I put the 250 Shards in the big Filler slot so it appears more often and put Gildun Hugs in the limited slot, because I foresee Shards being a major bottleneck

## Development of the APWorld

1. Let's make a list of all weapons and what tier they are
   1. Process: I go into the game, cheat spawn an enemy and test if it works well enough
   2. Or: Assign Values that fit
   3. Change of Plans: Rarities. That's more fun
      1. Warrior Bows as Tear Weapon seems like pain tho. Let's not let them have tear
      2. It's also only a tear weapon if it has tear in the name or if there is more tear than damage
      3. Also, Knockdown Arrows don't count
      4. NG+ and BS Weapons are included, BS is red, NG+ is yellow
2. List is done. Change of Plans: Difficulty = Hard, not Normal
3. Also, I will include NG+ and BS Weapons, the final Quest is "Epilouge" in Burning Shores. NG+ Weapons can only be unlocked (Item), not bought (Location). Tripwires are not included, they will be added as useful Items
4. The Game is split into four stages: Early Game, Mid Game, Late Game and Burning Shores
   1. Early Game = "Reach for the Stars" to "The Eye of the Earth"
   2. Mid Game = "The Broken Sky" to "Seeds of the Past" – basically all subroutines
   3. Late Game = "Faro's Tomb" to "Singularity"
   4. Burning Shores = "To the Burning Shores" to "Epilogue"

These Stages classify the Quest Levels for Weapons. This means the following:

- 1. Level 1-16: Uncommon Weapons and Outfits
  2. Level 17-25: Rare Weapons and Outfits
  3. Level 26-37: Very Rare Weapons and Outfits
  4. Level 37+: Legendary Weapons and Outfits

1. Outfits will be Progression Items too, but since you only need one, this is broader and I will not make a list
2. I will now start with the apworld by making all the items you can unlock
   1. Weapons  
      WEAPON CATEGORY WEIRD THINGS EXPLANATION:
      1. CanDetonate: Can Detonate Canisters. Sometimes (for example for Ronda's Bellowback), the tier of the weapon is irrelevant, only whether it can detonate canisters or not
      2. NeedDetonate: This Weapon only counts as a Weapon for that category if another Weapon with CanDetonate is present.
   2. Outfits
      1. These get Rarity, Outfit and Outfit_Rarity
      2. Sobecks Rainment is a Very Rare Outfit, since it has the stats of one. It originally was very rare but got ranked down to rare without changing the stats. The same goes for Tenakth Marshal, which got the reverse treatment. Also, it is fine to wear Sobecks Rainment during Faros Tomb if it isn't unlocked yet.
   3. Ability to damage Machines
      1. They get the Damage_Prefix. Didn't do that for the outfits and weapons (usable_ prefix). We'll see if it matters later
      2. The Defense Drone in "To the Burning Shores" is not an unlock and not a location check
   4. Quests
      1. These get the \_Unlocked suffix.
      2. They get a Category based on the kind of Quest
      3. "Reach for the Stars" and "The Point of the Lance" are not Items, they are unlocked from the beginning
      4. Cauldrons, "Opening the Arena", "First Forge" also require Unlocks
      5. The Quests/Interludes "The Dying Lands" and "The Eye of the Earth", "GEMINI" and "All that remains" are grouped. You can only unlock the former and that automatically means you may do the ladder. This is because you are forced to do the ladder quest right after the former. "His Final Act" and "Epilogue" are not grouped, since you are not forced to do "Epilogue" right after "His Final Act". Even though some Quests are grouped, you still get a location check for both.
      6. Similarly, Cradle of Echoes does not require unlocks, since you are forced to do it after acquiring one sub-function
   5. Filler
      1. There is a total of 8000 extra shards in Fillers, which is probably necessary due to the fact that every weapon is a check and costs shards
      2. Free = Cheat yourself the Items to do the upgrade or cheat them directly
   6. Quest Items
      1. For easier Coding, I will set up special Items that you get after completing a specific quest. You will still get a location check from the quest though because I will give that quest two location checks: One will be random an the other will be the quest item. Those will skip balancing!
      2. To the Brink, because it unlocks Merchants
      3. Embassy, because it unlocks No Mans Land and Plainsong
      4. Death's Door, because it unlocks the Igniter
      5. Eye of the Earth, because it unlocks the Tenakth Region
      6. All Subordinate Functions, because it unlocks San Francisco
      7. Singularity, because it unlocks Los Angeles
      8. Every Arena Group
      9. Completed a Salvage Contractor
3. Next, I will set up the regions
   1. I will define different Areas of the Game as Regions
      1. The Daunt
      2. No Man's Land
      3. Plainsong
      4. The Base
      5. Tenakth Desert/Las Vegas
      6. Tenakth Mountains
      7. Tenakth Jungle
      8. Tenakth Green ("Ninmah Research Lab" to "Salt Bite" to "The Maw of the Arena")
      9. San Francisco
      10. Los Angeles
      11. Tutorial
   2. About when I did GEMINI in Step 8, I realized how you are supposed to use regions. But I'm not redoing the beginning right now because I'm lazy. That's the reason why the Post-Regions AND the Quest-Items exist. Could've done Quest-Items via Regions. Oh well.
   3. Stopped being lazy and fixed the regions. Therefore, the regions from above are outdated and only kept there for historical purposes
4. This is where it gets difficult: Locations. Those will be set up next
   1. To get some structure down, I will start with the main quests
      1. To the Brink doesn't need anything other the quest unlock since merchants are locked until after it's completed
      2. I don't want the player to just get OP Weapons in the early game. Therefore, in for example "The Embassy", I will not allow a legendary Damage weapon as a damage dealer for that quest. You can still get OP Weapons early game, because maybe the legendary weapon required for a late game quest is hidden in early game, but I want to reduce the odds. Also, the Canister-Detonate-Category doesn't have a rarity, so you can get OP weapons that way too
      3. For Main Quests, I will not strictly adhere to the Level, but will assign Rarities as they fit
      4. Cradle of Echoes does not get requirements, since you are forced to do it at a specific time. The Requirements here are just for the logic: Complete either Sub-Function. Also, you may damage Specters here without the Item.
      5. "The Stars in their Eyes" only gets the Unlock condition, because the only enemy is a Bilegut, the equipment for which you have to acquire to get through a "region" to get to this quest
      6. Forgot about "All that remains", so it's after all the collectibles. Also, it is in Post-GEMINI so that I don't have to copy the requirements over
   2. Next up are the side quests. I can use the regions from the Main Quests for easier conditions
      1. Side Quests with multiple Conditions get the old quest item treatment. For Example, "Need to know" requires having "The Burning Blooms" and "GEMINI" completed (because you need to wait until Talanah is on the other side, which is definitely the case after "GEMINI". Might also be earlier, but better safe than sorry)
      2. "The Roots that Bind" doesn't need the ability to damage Widemaws since you are intended to sneak behind them
      3. "Thirst for the Hunt" and the follow-up Quests are not dependent on other quests, you can do them back to back. Therefore, they get their own regions
      4. The Ally Quests "The Second Verse" and "What was Lost" are set after Singularity, since I don't know when the second part of the quest unlocks. In previous playthroughs, sometimes, the second part was available right after doing the first part of the quest. This should be the case guaranteed after Singularity. The other Quests "Lost Legacy" and "First Forge" don't behave like that and have a set trigger ("GEMINI" and all Rebel Camps respectively), so I will not put them after Singularity in the Region logic
      5. "Valley of the Fallen" is different depending on whether you did Singularity or not. Since it's not possible to have a condition be Has Not Done XY, I will require the Equipment for both fights. Also, one of the fights is incredibly hard without either the Tremortusk or Thunderjaw Override, so completing Cauldron Kappa is one of the Requirements for completing this Side Quest.
      6. Sometimes when looking at the APWorld, you might think "Oh, he forgot a damage Weapon." In most cases, this Damage Weapon is hidden in the Region conditions. Same goes for the Ability to damage certain Machines etc.
      7. If you need to defeat a difficult machine like a Stormbird, I will use Elemental Damage as a Requirement with the Elements being the Elements the Machine is weak to. You need to have either the one or the other weak element to defeat the machine in logic. Usually, this looks like this: (Element A or Element B). In the case that there are two machines, with one being weak to Element A and the other being weak to Element A and Element B, I will only have Element A as a requirement since that already fulfills the OR part of the Requirement.
   3. Next up are Errand Quests
      1. Sometimes, Damage_Machine is missing because it's partly intended to sneak past and not fight the Machines. This is the case (amongst other) in "The Roots that Bind" (Widemaws) and "The Taste of Victory" (Glinthawk, Widemaw). If you don't have the machine unlocked yet, well, you'll have to sneak past
      2. Since the Requirements for "The Roots that Bind" are so low, the Errand "In Bloom" will not use a Quest Item as a requirement and instead just copy over the requirements. The Clawstrider does not need to be copied since it is required in "The Dying Lands"
      3. "The Souvenir" gets a Quest Item in case I need it because Jomar offers some item. Could do a region here, but if another merchant you need to unlock has that item too, this will become difficult
      4. After "Shining Example", I realized a possible mistake with my categories. I may need to fix a bunch later. Edit: Fixed it
      5. The Delvers Trinkets and Pangea Figurines don't count as errands. They should count, but I forgot
   4. Ok, the next thing on the list are Salvage Contracts
      1. Finishing a Contractor will give a quest item for simplicity with the Oseram Artificer Outfit
      2. In Logic, you are supposed to defeat Runda's bellowback by triggering the shock canisters on its belly
   5. Contracts are done, Hunting Grounds are up next
      1. You only get a Logic check if you got full stripes
      2. The Level is determined by the level of the hunting ground
      3. For the Weapon Checks for the Medals, you are expected to buy the items from the top to the bottom, alphabetically sorted, skipping the Coils in Logic. This is the reason why every hunting ground and arena challenge has at least two checks: One for the general location check and one for the currency
      4. That doesn't work well, so HG and Arena Weapons aren't checks.
      5. "The Raintrace" needs the Clawstrider Override from "Cauldron IOTA", so that will get it's own region later
   6. Next up are the Tallnecks
      1. The Story Tallneck in the middle of the desert is an exception, for obvious reasons
      2. The Tallneck "Salt Bite" will not be completed until I'm done with Cauldrons because you unlock it through "Cauldron IOTA"
   7. Next up are the Cauldrons
      1. Cauldron IOTA gets a Region, because the things that need IOTA (Tallneck Salt Bite and Hunting Grounds Raintrace) don't have a second quest requirement
      2. Cauldron KAPPA gets an Item because the thing that needs Kappa (Valley of the Fallen) has a second Quest Requirement (The Kulrut)
   8. Backtracking the Quest that need Cauldrons is up next
      1. "The Valley of the Fallen" has a LOT of checks because it has many different Machines in it
   9. Done, next are all the activities you can do
      1. Arena
         1. I will make a region for completing each Arena challenge. To make coding easier, I will make the region for finishing the challenge and put the location check in that region. That will lead to less copy pasting between locations and regions
         2. Equipment Requirements are Rare for the first two Categories, Very Rare for the middle two and Legendary for the last two
         3. "Apex Predators" does not connect to "Apex Waterwings" directly because "Apex Waterwings" requires the completion of the burning shores. It is connected via quest item.
      2. Devotee Outposts
         1. Two of the outposts are allowed to do without the quest "In His Wake". Which ones they are I will figure out in playtesting. The other two are accessible after "The Stars in their eyes"
      3. Gauntlet Runs
         1. All things that are towards the Tenakth Mountains are considered post-Broken-Sky, because I don't know if you can do them before
      4. Melee Pits
         1. There is one location check for each completed challenge. Every Pit has 3 of these. You may need to reset skills to get the skills required for those melee pits.
         2. Tutorials and free fight don't give checks
         3. The Enduring is after GEMINI to allow for level-ups for a bigger health buffer in the fight since the fight is hard
         4. I'm not the one to stop you from utilizing the trap exploit
      5. Rebel Outposts
         1. "The Deadfalls" may not be completed without the quest "The Bristlebacks". It also doesn't give location checks. This is because it has another icon on the map
         2. Since you only need to kill the outpost leader, the Damage_Machine is not required for any outpost. Similarly, elemental Damage for the machines is also not required
         3. Shining Wastes South may be done without Blood for Blood and has a Location Check, since it appears just like the other camps on the map
      6. Rebel Camps
         1. First Forge requires a quest unlock
      7. Relic Ruins
         1. Night of Lights doesn't unlock a location check since it's part of the Errand with the same name. Similarly, this Ruin may not be done until Night of Lights has been unlocked. Edit: For consistency with other edge cases, it should be a location check, but since I use the website, I can't change it now.
         2. No Man's Land is after Death's Door because it requires the igniter. Same goes for Restless Weald.
         3. Dry Yearn is after Seeds of the Past because there are vines in the way
         4. Stillsand is after Sea of Sands because I think you need the diving mask?
         5. Murmuring Hollows is before Friend in the Dark, so it can be done freely
      8. Vista Points
         1. For these, you might not be able to kill the machines at the vista. You'll need to sneak past instead
         2. Vistas in SF are Post-Wings of the ten because I'm unsure if they require the sunwing
      9. Black Boxes
         1. Bonewhite Tear is after Wings of the Ten because the shelter might only be accessible with a Sunwing. Same for Isle of Spires
      10. Survey Drones
          1. For Logic, Drones don't need to be plugged in in order to get a check. However, if you want to change that, do it. You'll just need the region in everything before "Eye of the Earth" to "Eye of the Earth"
          2. Plainsong requires the Igniter
          3. I will put the Module Number in the check title
          4. You might need to sneak past machines again
      11. God of War Totems
      12. Delvers Trinkets
      13. Aerial Captures
          1. One AC has to be done after For His Amusement
          2. One AC requires killing an Apex Stormbird first, so it gets the requirements for killing it
          3. One AC requires doing all other AC's first, so it gets For His Amusement as the region and the Stormbird as the Requirement
      14. Signal Lenses
          1. Lens of Afternoon is only accessible during "The Twilight Path", so it has the same requirements
          2. Lens of Evening is only accessible during "Signals of the Sun", so it has the same requirements
      15. Pangea Figurines
   10. Backtrack: Region Categories.
       1. I will add Categories to everything done so far, named after the geographic region, so it's easier to find in the client. I probably forgot some regions. Here's the list of regions I added:
          1. The_Daunt
          2. No_Mans_Land
          3. Plainsong
          4. Plainsong_Mountains
          5. Dry_Yearn
          6. The_Stillsands
          7. Shining_Wastes
          8. Runners_Wild
          9. The_Raintrace
          10. The_Long_Coast
          11. Stand_of_the_Sentinels
          12. Sheerside_Mountains
          13. San_Francisco
          14. Burning_Shores
       2. The Arena will not get Region Categories. Just Opening the Arena will, so if the Player is like "What can I still do here", they will see Arena and get reminded AND they will not get overwhelmed by all the arena stuff there they can't do. To further strengthen the reminder aspect, I put the first and the last one in the region category
       3. I'd rather put things in more categories then they belong to than fewer. This results in maybe some useless results when browsing the category, but no missing results
   11. Done, those definitely were some two three hours I just spent. Next up is adding the first kills of machines
       1. Most Machines will go in the region they spawn in
       2. Some Machines are found earlier in quests, so those will go there
       3. The Machines will also get a category depending on their class
          1. Chariot_Machine
          2. Acquisition_Class
          3. Combat_Class
          4. Recon_Class
          5. Transport_Class
       4. You encounter corruptors in three places: The main quests "Faros Tomb" and "His Final Act" as well as the arena challenge "Ancient Corruption". Since "His Final Act" is after "Faros Tomb", you can get the first corruptor kill in "Faros Tomb" or "Ancient Corruption". Therefore, I made a new region for the first kill so that I don't have to copy over the conditions for both of them and put an or between them. This means you need to complete "Faros Tomb" or "Ancient Corruption" to get the Location Check, which is my goal.
       5. The first Bristleback Kill is either in "To the Brink" or in the first part of "The Bristlebacks", so I'll put the first kill there
       6. Machines come in 4 Classes. Depending on the Class, I will require specific equipment for the kill
          1. Lightweight: Uncommon/Rare
          2. Midweight: Rare/Very Rare
          3. Heavyweight: Very Rare/Legendary
          4. Bilegut: Legendary
          5. Apex kill increase the weight class by one level for this calculation
       7. Scrap the weight class calculation, I will assign Equipment based on vibes and geographical region
       8. For Plowhorns, I didn't calculate the machine weight class because you have to defeat the harder version, Grimhorns, on your way there
       9. For Snapmaws, you can encounter them in No Mans Land, although there is no machine site there. You should be able to find them in the sea by the horus where "Death's Door" takes place
       10. Machines that get introduced in quests (like Tiderippers) will have their completion set to the region after the quest, since you get the first kill during the quest. Slaughterspines are an Exception, since you can encounter them earlier (at the long coast close to the boat to San Francisco for example)
       11. Ravagers can get the first kill after "Eye of the Earth" or during "Shadow in the West". Therefore, I'll make a region for the "Shadow in the West"-Kill and another for the Ravager-Kill, both of which connect to the Region in which the kill happens. That should allow for both ways to be possible. Same Procedure for the Shellsnapper
       12. The Stormbird First Kill will never be done on the unmarked site in the Sheerside Mountains, since it's not feasible to do that early with the Dreadwing there. It will always be done in SF because there's no Dreadwing there.
       13. Shell-Walkers can be killed at any point after the Embassy because of Lorends Contracts
   12. Now, the Weapons
       1. NG+, Arena and HG-Weapons don't send location checks as they can't be bought
       2. Weapons acquired in quests still give location checks
       3. If the cost include machine components, the weapon will only be available when a machine site is available since you need to be able to farm that machine until the correct component drops/might have already spent the component on another weapon/upgrade
       4. Weapons requiring large machine cores are considered Farmable after Faros Tomb
       5. Slaughterspines are considered Farmable after GEMINI
       6. In "The Wings of the Ten", you have to decide whether you want to kill Regalla or let her live to die in glory. Depending on your choice, you either get "Regalla's Wrath" (kill Regalla) or "Tenakth High Marshal" (let her live to die in glory). Since you can only ever get one, these two Items will only send one location check: Regalla's Equipment. This is not an Issue for the weapon you receive after "The Gate of the Vanquished", since that's the same no matter your choice
   13. Outfits
   14. Strike
   15. Sunken Caverns
5. I haven't done Strike and Sunken Caverns yet, but I will start the testing without these. The Reason is that I don't know which enemies are in the sunken caverns and I don't know if all pieces can be bought from the strike master in the arena
   1. Killed the Run after Eye of the Earth, checked spoiler, seemed mostly fine
   2. Ok, I found some major bugs and logic issues:
      1. Deaths Door was missing its unlock
      2. You don't need a quest to kill the first bristleback since there is one chilling outside the relic ruin in the Daunt
      3. Giving Shards to yourself sucks with the cheat mod I'm using, so I changed it to gold ingots
      4. Longlegs are only farmable in No Mans Land after completing Burning Blooms
      5. Changed the 8 Gold Ingots to a specific filler and Gildun Hugs to the general filler. The reason is that I want to make an option later to disable weaponsanity and outfitsanity and disabling those two should also delete the shards. I upped the Quantity on the 8 Gold Ingots to 55 so it should be the same amount. I did my math wrong though, but testing shows it's fine (added later, after first test with 1.0.4).
6. Found a big logic issue which I will fix in 1.0.3: Weapon Balancing. I earlier said that I excluded good weapons from early quests in order to force bad weapons in the early game. Well, the logic put good weapons in Early Game because according to logic, you can't make progress with them. Because I did conditions inconsistently, updating all location checks and regions to include higher rarities would be a pain. Therefore, all good weapons/outfits will get the worse categories too. That's easier to fix and should give the same results.
   1. Did that with search and replace
   2. I am not updating these for the canister ropecasters since that would mean I need to add the NeedDetonate-CanDetonate-stuff for like all locations and regions and that's too much work rn for these couple of edge cases, so you might get a very rare canister ropecaster a bit earlier
7. For the 1.0.5, we're going to want machine strike. For this, I want two different options on the machine strike difficulty. "Accessible" expects you to do Machine Strike after the Arena has been opened. And "Fast" expects you to do Machine Strike as soon as that strike player becomes available.
8. 1.0.6 is a bugfix patch
   1. Before I implemented the second change, the requirements for the examples looked like this: {Conditions for Aether} OR {Conditions for Poseidon} OR {Conditions for Demeter}, which I streamlined to one singular line
   2. The reason for 3. is that Erend only arrives at the base after 1 Subordinate Function has been completed
   3. The reason for 4 is that no black box requires the sunwing
   4. It is pretty trivial to avoid damaging snapmaws during "For His Amusement", so the requirements were removed (see 6)
   5. The reason for 7 and 8 is that the merchant at Camp Nowhere is only available after Breaking Even
   6. The last Gauntlet Run can only be completed after aquiring Poseidon, therefore 9
   7. Purgewater Ammo is required to put Tremortusks into the Shocked State, hence 10
   8. Both of the Weapons in 12 require a large machine core, that's why I changed their region
   9. The Reason for 13 is the difficulty of the trial
   10. Erends Game becomes available after 2 Sub-Functions have been collected. Because of my subordinate function event streamlining at the top, this is now easily possible.
   11. I know that most things in the Sheerside Mountains are accessible before "The Broken Sky", but that's a lot of work and it reduces the size of the sphere after "The Eye of the Earth", so I'm leaving it as is
   12. The reason for 17 through 19 is the fact that that weapon requires a Rockbreaker circulator. You are only able to farm large machines in logic after Faros Tomb, so the same should apply for the circulators of large machines.
   13. The snapmaw you'd want to kill can be ropecasted for the duration. Also, you can easily sneak past the Shellsnapper at the entrance. That's the reason for 21.
   14. I put Sons_of_Prometheus_Data after Wings of the ten to allow the player to decide if they want to do it early or late. Doing it early instantly completes the errand when inspecting the focus. Doing it late (after Wings of the Ten) instead gives you the coordinates to a supply cache, guarded by the Sons of Prometheus. Collecting it finishes the errand (24)
   15. The Sunwing is not required for the Vista at Shrouded Heights (25)
   16. You are incapable of fighting the Snapmaws during "Underwater Salvage", so the damage item is not required anymore. (26)
   17. You need to defeat the Stormbird at the Aerial Capture to unlock the Delvers Trinket (28)
   18. Waterwings only appear after "For his Amusement" on the map, they're sunwing sites before. But they do appear during "The Splinter Within" (30)
   19. The Relic Ruin "The Stillsands" does not need the diving mask (31)
   20. If Burning Shores gets disabled, the legendary ropecaster won't be available and I plan on making an option to disable BS in case you are on console and don't have it (33)
9. V 1.0.7 is a big content update with many new features.
   1. I decided to add 10 Jokers to the fillers. A Joker is basically a "I could do this, but I don't want to do this, so I will just check it off on manual"-Thing. This is optional though, you can change enable jokers in the YAML. I realized in testing that the sphere after Eye of the Earth is huge when you have all sanities enabled (guessing around 50 items and a lot of required travel) and Jokers can help a bit. You can also use them if you, for example, want to do melee pits, but not the pit master challenges and just use the jokers for those. But as I said, they are optional
   2. Ok, now for the biggest feature: I want the player to be able to disable the Burning Shores DLC (in case they don't have it)
      1. First, I need to put all the weapons and outfits you get in the burning shores in their category so I can disable them. And add the hook for that
      2. Now, I need to change the victory location to after Singularity. I don't know how to do that. So, Epilogue will still be the victory condition, but it's available right after Singularity. But for that, I need to change the region of Epilogue_Completed. I also don't know how to do that. But I do know how to dynamically change requirements. So, I will change the region to Post_Singularity and add Comp_His_Final_Act_leted as a requirement. Did that and…it actually worked? Didn't expect it to be that easy. Well, I did miss some things, let me fix those. Still works…wow
   3. Next, I want to add some free coils into the mix of filler Items. Also stopped being an idiot and use the windows editor for all this, using VS Code now.
   4. Next, I want the player to be able to disable the arena and melee pits. I'm going to implement these the same way machinesanity is implemented: You can enable them. Unlike Burning Shores, checking the condition enables these things instead of disabling it. Also, "Opening the Arena" will remain a valid location check, because it's more of a quest than an actual arena challenge
   5. Since the game against Varl and Erend are missable (if you complete Singularity before), they can now only contain useful Items and filler Items
   6. Unearthing the Delvers Trove and completing the Dino Digits Quiz will also give location checks now
   7. Now, I want some options to disable helpful filler items.
      1. I already have Jokers
      2. One option should disable all helpers (free upgrades and machine components, free restocks and free coils)
      3. Another option should disable the free shards you get when playing with Weaponsanity
   8. I also want this to be playable without a cheat mod. If you don't have one, just check this box and it should work fine. I realized that only weaponsanity and the free items and so on actually require a cheat mod, so you can play it without too.

## Version History and Patch Notes

These are not a thought log, but the actual patch notes. The reasons for these changes can be found in the Thought log above.

### 1.0

- Starting Version

### 1.0.1

- Added the starter items in the game.json as starter items

### 1.0.2

- Fixed the issues presented in 9.b:
  - "Deaths_Door_Completed" was missing "Deaths_Door_Unlocked" as a requirement
  - "Bristleback_First_Kill" was changed to not have any requirements since they can be found in the wilds without progressing a quest.
  - Changed the filler Items "X Shards" to "\[~X/64\] Gold Ingots"
  - Changed the requirements for "Longleg_First_Kill" to either during "Burning Blooms" or after "Eye of the Earth"
  - "Eight_Gold_Ingots" now no longer is the general filler, but rather a specific filler with an amount of 55
  - "Gildun_Hug" now is the general filler

### 1.0.3

- Fixed Weapon issues
  - Legendary Outfits/Weapons now are also classified as Very Rare, Rare and Uncommon.
  - Very Rare Outfits/Weapons now are also classified as Rare and Uncommon
  - Etc.

### 1.0.4

- Added some YAML options (don't remember which)
- Replaced Quest Items with Events, I didn't know about their existence earlier

### 1.0.5

- Added Machine Strike

### 1.0.6

My first tests revealed many flaws in my logic. You sometimes are expected to do things that are not possible in-game. For example, in some seeds POSEIDON could be hidden behind the last gauntlet race/the weapon you get from it, but you can't complete this race before acquiring POSEIDON. I didn't know about these things before my playtest. So, this is a bugfix patch.

1. Added an event for acquiring each subordinate function and put them in one category.
2. Streamlined some complicated requirements using the last change. For Example, both "Cradle_of_Echoes_Completed" and "Specter_First_Kill" now require "|@Sub_Function_Aquired:1|" instead of the condition there was before.
3. "First_Forge_Completed" now also requires "|@Sub_Function_Aquired:1|". Same goes for "The_Sun_Scourge_Aquired"
4. Moved "Black_Box_Isle_of_Spires" and "Wings_of_the_Ten_Aquired" to the region "San_Francisco" and "Black_Box_Bonewhite_Tear" to the region "Post_The_Broken_Sky"
5. Some items that are acquired by collecting all of a certain collectible are now also in that category: "Wings of the Ten", "Signals of the Sun"
6. Removed "Damage_Snapmaw" and "@Purgewater_Legendary:1" from the requirements of "For_His_Amusement_Completed" and "Post_For_His_Amusement"
7. "Cloudburst_Blastling_Aquired" now has one Subordinate Function or Breaking Even as a requirement
8. "Scalding_Spike_Thrower_Aquired" now has Breaking Even or Aether as a requirement
9. "Carjas_Bane_Aquired" and "Gauntlet_Run_The_Stillsands_Completed" now have "Poseidon_Aquired" as a condition
10. "Shock_and_Remove_Trial_Completed" now also has Purgewater as a requirement
11. All HG Trials are also Events now and "Tinkers_Pride_Aquired" now requires having completed all 12 Trials to streamline conditions
12. Moved "Icestorm_Boltblaster_Aquired" and "Ripsteel_Shredder_Gauntlet_Aquired" to the region "Post_Faros_Tomb"
13. "Heavy_Weapons_Trial_Full_Stripes" now requires legendary Tear, a Very Rare Outfit and Very Rare/Legendary Damage
14. "Won_against_Erend" now is in "Post_Eye_of_the_Earth" instead of "San_Francisco" and requires 2 Sub-Functions
15. Added "Relic_Ruin_Dunehollow_Gizmo_Completed" with the requirement "|Night_of_Lights_Unlocked|" and the region "Post_The_Sea_of_Sands"
16. "Ancestors_Return_Aquired" now requires Night of Lights
17. Moved "Adhesive_Warrior_Bow_Aquired" from "Post_Eye_of_the_Earth" to "Post_Faros_Tomb"
18. Moved the "Thunderbolt_Shredder_Gauntlet_BuyPass" to after Faros Tomb
19. Moved "Glowblast_Tripcaster_Aquired" and "Beamwire_Tripcaster_Aquired" to after Faros Tomb
20. Increased the amount of free machine components from 10 to 20
21. "Cauldron_KAPPA_Completed now requires the Diving Mask. It no longer requires "Damage_Shellsnapper" and "Damage_Snapmaw" can be replaced with a ropecaster
22. "Drowned_Hopes_Completed" and "Guardian_Tripcaster_Aquired" are now both in "Post_Eye_of_the_Earth" and require the diving mask
23. Changed the name of the item "Tenakth_Dragon" to "Tenakth_Dragoon" because I spelt it wrong initially
24. Added the location "Sons_of_Prometheus_Data_Completed" and the item "Sons_of_Prometheus_Data_Unlocked". The Region for the location is "Post_Wings_of_the_Ten"
25. Moved "Vista_Point_Shrouded_Heights_Completed" to "San_Francisco"
26. "Underwater_Salvage_Completed" now no longer requires "Damage_Snapmaw" and instead requires "Diving_Mask_Aquired"
27. Aerial Capture West and South now require "Damage_Stormbird"
28. Mighty Pint now has the same requirements as Aerial Capture West
29. Added a third Devotee Outpost and renamed the Devotee Outposts to North, West and South
30. Added "Comp_For_his_Amusement_leted" or "The_Splinter_Within_Unlocked" to "Waterwing_First_Kill"
31. Moved "Relic_Ruin_The_Stillsands_Completed" to "Post_Eye_of_the_Earth"
32. Moved "Black_Box_Jagged_Deep_Collected" to "Post_Eye_of_the_Earth" and added the diving mask as a condition
33. Moved the legendary Ropecaster Requirement to the burning shores arena
