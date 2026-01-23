
[what is this?;-]
* This content modifies & improves the default GTA San Andreas PS2 experience
* users can replicate the changes and create their own.
* Full readme in help folder

[The Aim] = i wanted a perfect main.scm.
* Including; Fixes, simple cheat menus users can replicate and modify provide commonly wanted stuff, all unused code stripped etc.
* For PCSX2 2.0+ I wanted to have all code intact just fixed and improved as needed, with all PS2_KB working and listed and a complete ".pnach cheat" file for the new non "20######" style 64bit addresses. 
* For PCSX2 1.6.0 i wanted all the ps2_kb removed (users cannot use it), and a perfect cleaned, fixed scm + cheat menus
* a perfect .scm with as much space as possible including templates for cheat menus, all commonly requested fixes & features
* importantly: have it so that users can simply copy paste examples into their own, so they can replicate, easily, fast & efficiently the whole process.

** Unfortunately there is no list + relevant fixces posted online, and those that are are often incorrect, unneccasary or cannot be replicated.
* mass focus on CLEO bullshit/ PC mods - neglecting PS2, whilst failing to provide the basic fundamentals correctly like a standardised perfect .scm comptible for all versions has caused a massive diference between PS2 & PC. Which has led to teh most basic expectations of users not being met, not met by rockstar to begin with, nor on any subsequent 1 of the 30+ re-releases, and variants, and not by any of the 20+ years of modding either.... if it had, i wouldn't be here.
 
TO DATE: 
* not 1 single post has ever been made showing someone playing SAN ANDREAS with a PS2 keyboard, 
* there is no list of the keys used --> the functions for quick easy reference
* afaik, no-one has ever played PCSX, any version, with san andreas and a keyboard, the 1.60 plugins do not work, and i didn;t even think of it myself until 2026, having already completed my san andreas stuff last year
TODO 
	a perfect scm is needed ... it doesnt exist
	a ps2 kb comptible perfect version is also needed - it doesnt exist 
	snippets for all changes are needed - these do not exist
	port pnach to new 64bit format for pcsx2 2.0 -- ummm yhe, wow - theres 6,00+ PS2 titles that users spent years making codes for.. abosultely shocking move to break cheats.

[quick instructions]
* Replace original files with modded files, rebuild iso, enjoy!
* if you want to modify yourself or maybe learn something new just go through the full read me, docs, files, examples & information provided.

[How to Replicate - Quick]
1. ** implement fixes  
2. * modify other stuff how you want to -e.g some pickup placment tweaks etc
3. take simple example like a 12 options cheat menu make 3 or 4 of them and start making cheats and stuff. 

[make space for new code]
* strip out any PS2_ KB related code BUT keep the press "22" mission skip stuff, + replace it with PAD 2 Select 
	-  one or 2 other PS2_ things can be kept like level up taix, amb, fireturck etc with start button
* with code space create your basic 12 options cheat menus as placeholders to test stuff.
* there are approx 5,000 lines (1%) that can be removed, all related to unused ps2_kb input debugging satuff.

[notes]
* i recommend creating the perfect clean scm file before making any other changes, even changing coords of pickups, unless they are for fixing e.g. stuff in walls.
* testing and iterating is a pain in the ass on PS2, but with 5,000 extras free lines and a bunch of cheat menus you can test alot of stuff in each build ,
	- using an ethernet cable to the ps2 is the best option for testing on the hardware.

[fixes] - do these;-
1. basketball & jetpack (cannot play with...)
2. basketball radius check (save bug fix)
3. incorrect terminate/return ordering
4. missed phone calls
5. visuals (pcsx2)
6. ...
	
---------------------------------------------------------
---- [Cheats & Debug - New input Options] ----
---------------------------------------------------------
* Cheats & Debug options have been created the same as i did for vice city hybrid ("VCH").
* Check final main.scm/ main.txt or the cheats & debug readme IF inputs have changed.
* use a second control to execute the following;-

* Open Teleport Menu	- PAD 1 SELECT + CIRCLE.	|| destinations
* Open Cheats Menu	- PAD 1 SELECT + X.			|| various options
* Open Weather Menu	- PAD 1 CIRCLE + X.			|| optional: not in final, because i use ".pnach" to set weather
* Close Menu			- PAD 1 SELECT + SQUARE.
* Spawn Explosions 	- PAD 1 CIRCLE (in vehicle).|| pseudo projectile, same as ("VCH") || you may want to change this to SQUARE, or another button./
* Skip Missions:		- PAD 2 SELECT, sometimes START has a function.
					* other options depend on the mission.
* Users can skip the entire game (1hour+ of pressing select) but game progression may break unless the following is done;-
DO NOT SKIP;- 
		important phone calls.
		maddog jump out of plane parachute misison. wait until you jump out the plane.
		the "end of the line" final mission when your indoors can be alittle buggy even withotu skipping.
		there is no cop car vigilante skip. Rockstar did not add it and i could not get it working.
