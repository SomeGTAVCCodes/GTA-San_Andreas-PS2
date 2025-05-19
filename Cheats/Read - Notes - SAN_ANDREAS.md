//TITLE:		GTA:San Andreas ".pnach" Cheat, Codes & Mods.
//AUTHOR:		TKBS
//DATE:			04 04 2025
//INFO:			Cheat codes for GTA:SA (PS2) (PAL) (2004)
** This is all the notes, research, Unknown, broken, to do list etc that accompany the ".pnach" & ".ct" cheats.
//Request:		Please Add, fix, or port any missing codes, devs can read the Notes & Junk for more info

//** Addresses Change, to make life easier, start a new game with the save state provide, so that the addresses stay the same.

// ---- Cheats we want at start ----
//** To create a Clean Starter Save Game & Save State compatible with all our cheats we want these cheats in ".pnach" form.
//* Jump				- varying heights.
//* Infinite Ammo 		- - Done + Individual Weapons & Clips when using save state
//* Infinite Sprint		- Done
//* Infinite Air		- Done
//* Infinite Health		- Done
//* Infinite Armour		- Done
//* Money				- Done
//* dmg proof ER VH's in CJ's garage - for side quests.	- Done		
//* Clean Streets - NO peds, traffic.
//* No Cops AI
//** All of these must also allow the upgrade system to work 
//** && All must have the original values logged so they can be reset to default.

// ---- Cheats Notes: ----

//--------------------------------------------------------------------
//-------------- TESTS Junk, Fails, Unknown, Not tested --------------
//--------------------------------------------------------------------

//Vigilante Unlock Not working - cannot find address.
//Vigilante: Set to 0 For ppl left to kill - to add to kills.
//patch=1,EE,206F3CD4,extended,00000000
//Vigilante: Level 12 = B
//patch=1,EE,206BA178,extended,0000000D
//Vigilante: These 3 addresses all values change together
//206BA178
//2066C0F8
//2066B524

// ---- Weapons: Infinite Ammo ----
//Weapons: AMMO
//Default Value = 2442FFFF ||
//Weapons: Infinite AMMO					- ARMAX CD
patch=1,EE,20134340,extended,00000000
//Weapons: Infinite CLIP AMMO				- ARMAX CD
//patch=1,EE,201343A4,extended,24420000

//Weapons: Extra AMMO						- ARMAX CD
//patch=1,EE,20134340,extended,24420001
//Weapons: Extra CLIP AMMO					- ARMAX CD
//patch=1,EE,201343A4,extended,24420001

// ---- Weapons: Individual gun Infinite Ammo ----
//Addresses change: ** Use the Save State Provided! - then these cheat will work.

//Weapons: Machine Pistol Ammo
//patch=1,EE,210B2308,extended,00000032
//patch=1,EE,210B230C,extended,0000012C

//Weapons: Handgun Ammo
//Weapons: Rifle Ammo
//Weapons: Shotgun 1 Ammo
//Weapons: Shotgun 2 Ammo
//Weapons: Uzi Ammo
//Weapons: Rocket Ammo
//Weapons: Molotovs Ammo
//Weapons: Spray Paint Ammo

//Infinite Health PAL 1 Notes:
//* Converted from NTSC using "-A90", Then searching above, below that memory region for the values.
//* Needs Max (upgraded) Health Support.
//Line 1 Default Value = C4600580
//Line 2 Default Value = 44030000
//Line 3 Default Value = 00000000

//Infinite Health PAL 1 Notes:
//* Converted from NTSC using "-A90", Then searching above, below that memory region for the values.
//* Needs Max (upgraded) Health Support.
//Line 1 Default Value = C4600580
//Line 2 Default Value = 44030000
//Line 3 Default Value = 00000000

//Infinite Health PAL 1: (default health sizee)
//patch=1,EE,202A9C20,extended,3C0142C8
//patch=1,EE,202A9C28,extended,AC610580
//patch=1,EE,202A9C2C,extended,24030064

//MAX Health PAL							- Converted from NTSC using "-A90" by TKBS
//patch=1,EE,208022C0,extended,44B00000

//MAX Health NTSC 1: 20802D50 44B00000	|| 20802D50 -A90 = 208022C0
//MAX Health NTSC 2: 208021C0 44B00000	|| 208021C0 -A90 = 20801730

//Infinite Health NTSC 1: (These lines are not in the correct order.)
//patch=1,EE,202A9B38,extended,AC610580
//patch=1,EE,202A9B30,extended,3C0142C8
//patch=1,EE,202A9B3C,extended,24030064

//Infinite Health NTSC 2:	20261824 E4400580

//Infinite o2:								- Not Tested
//patch=1,EE,202A9AC0,extended,E6400044

//Infinite o2								- Not Tested
//patch=1,EE,202A99D0,extended,E6400044

//Infinite Sprint:							- Not Working
//patch=1,EE,00709748,extended,00000001

//20802530 Number of rockets fired?

//Disable Cop AI	- Not Working
//patch=1,EE,2027C208,extended,00000000

//jetpack 		- (Press R2 + DOWN)			- Not Working
//patch=1,EE,A00C20A4,extended,20013444
//patch=1,EE,A00C20A8,extended,51010009
//patch=1,EE,A00C20AC,extended,8C820100

//parachute 		- (Press L1 + LEFT)		- Not Tested
//patch=1,EE,A00C22B0,extended,2001344C
//patch=1,EE,A00C22B4,extended,51010006
//patch=1,EE,A00C22B8,extended,8C8200FC

// ---- Wanted Level ----

//Max Wanted Level (no line 2 +4 bytes ?)
//patch=1,EE,2027BFC8,extended,00000000

//Never Wanted Level ||Default Values =  27BDFFD0 || FFBF0020
patch=1,EE,2027BF90,extended,03E00008
patch=1,EE,2027BF94,extended,00000000

//Never get Busted
//patch=1,EE,2046B090,extended,03E00008
//patch=1,EE,2046B094,extended,00000000

//Wanted Level Always 0:				- *** does not work ***
//patch=1,EE,2027BFB4,extended,20040000

//Wanted Level Always 1://patch=1,EE,2027BFB4,extended,20040032

//Wanted Level Always 4://patch=1,EE,2027BFB4,extended,00000006

//water level - test 1 of these lines , nts pal palt.
//patch=1,EE,2017F800,extended,00000000
//patch=1,EE,2017F900,extended,00000000
//patch=1,EE,2017F700,extended,00000000

