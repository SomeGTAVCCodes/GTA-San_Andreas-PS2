//TITLE:		GTA:San Andreas ".pnach" Cheat, Codes & Mods.
//AUTHOR:		TKBS
//DATE:			04 04 2025
//INFO:			Cheat codes for GTA:SA (PS2) (PAL) (2004)
** This is all the notes, research, Unknown, broken, to do list etc that accompany the ".pnach" & ".ct" cheats.
** It may also include codes that work , but these present in the final file && are just an aid to the process that created them or the non-working stuf, which may help.

//Request:		Please Add, fix, or port any missing codes, devs can read the Notes & Junk for more info

//TODO LIST;-

//* 100% Complete - Unlocks ?? Hydra & Rhino outside CJ's
//* Jump varying heights. - gravity but no jump height adjustments.
//* No Cops AI 			- PARTIAL
* teleport to vh
* equip parachute, jetpack and save in garages, or spawn them.
* fix weapon equip when using jetpack.

//---- In-Game Cheats Addresses. ----
//** THESE ARE FOR REFERENCE ONLY, it will not activate all th cheats, but it shows the memory region where the button inputs happening and booleans set.

//--- Transferring this knowledge from San Andreas to Vice City ----
//* Used to find cheats in PAL
//*  In San andreas type cheat code for weapons here is the input:
//*  			44440000 4452554C 3431344C 00000033 00000000
//* 			00 00 44 44 4C 55 52 44 4C 34 31 34 33 00 00 00
//*  search for that in PAL VICE CITY
//*  this part was found
//*  			.....................44 4C 34 31 34 33 00 00 00
//** PAL VICE CITY 2003 MEMORY REGION FOR IN GAME CHEATS = "205C18F7"

//--------------------------------------------------------------------
// -------------- Me fixing the CJ's Garage Cheats --------------
//--------------------------------------------------------------------

//* This is the stuff related to CJ's Garge. I noticed the PAL ARMAX CD codes were very strange compared to vice city.
//* NTSC Codes online are the same, they just look weird even though they work.
//* there was no VH 2 in the garage code on ARMAx, nor was there ddamage proof, nor was their a colour setter.
//* So i corrected the PAL RMAX CD codes, and the pnach codes, and the ntsc codes, and added damage proof and colours based on mmy knowledge from Vice City.
//* I still have no idea why the others codes used these weirrd har daddress 0x, 1x. It makes more sense to use the corrected versions i posted.

The Final Version looks like this:
//Vehicles: CJ's Garage:  ----			FINAL VERSION: IGNORE EVERYTHING ELSE.		- by TKBS
//Line 1 = 	VH ID & DMG PROOF
//Line 2 = 	Colours		||				e.g - 0000|01|7E = Pink with White Stripes, See colors.dat.
//patch=1,EE,2080D9E0,extended,01A4001F
//patch=1,EE,2080DA02,extended,0000557E

Here is how i did it:

// [KEY] ---- Vehicles ---- Vehicles List: (use vehicles.ide)
//IDs: 400-611 || Hex: 190 - 263
//Mr Whoopee 	= 423	|| 000001A7
//BRAVURA 		= 401	|| 00000191
//Cop Car LA	= 596   || 00000254
//Fire-Truck	= 407   || 00000197
//Rhino-Tank	= 432   || 000001B0

// Old Notes:
//* I have No idea how or why this works, what the color address is, or why i cannot find garages like vice city.
//* Vehicle must exist in garage, maing it a bit pointless, other than dmg proof.

//CJ's Garage:
//Line 1 default = ???????? || - literally all ?'s  -Also - the first line doesn't even do anything (?).
//Line 2 default = 0D88D0DD || - My guess at damage proof, based on VC - this line does not exist on ARMax CD.
//Line 3 default = DDDD0D88 || - Vehicle ID 2?
//Line 4 default = DDDD0D88 || - My guess at Vehicle ID 1?
//Line 5 ?????????????????? || - My guess at colour ? - In vice city, Colour is +20 from VH id line.
//* i noticed the car change and not bike, the 4 bytes up crashed game, bytes before line 3 worked for VH 2

//[NTSC(2?) D080E472] - [PAL(black) D080D9E2] = A90 | (2,704)
//Possibly Add "1" or "2C" or "4 bytes" to one of the digits (the 8 or D?) for the next garage.
//TODO: TEST: 0000FFFF

//CJ's Garage: Vehicle: DMG Proof.			- AR Max Converted to PAL 2004 || "+A90" from ntsc
//patch=1,EE,D080D9E2,extended,00100000
//patch=1,EE,1080D9E0,extended,0000001F
//patch=1,EE,1080D9E2,extended,000001A4
//patch=1,EE,1080D9DE,extended,000001A0
//patch=1,EE,2080DA02,extended,0000007E

//CJ's Garage colour : NTSC ? 				- "-100" from pal
//D080D8E2 00100000
//0080D902 00000000
//Pink: 0000007E

//CJ's Garage: NTSC ?						- "-A90" from pal
//D080E472 00100000
//1080E472 00000190

//Vehicles: CJs Garage || 0000007E = Pink || 0000223B = Firetruck 2 colours			- Corrected by TKBS
//Example Firetruck
//VH ID = 		2080D9E2 FFFF0197
//Colours = 	2080DA02 0000223B		- Stripes Colour Then Main Colour
//Colours | e.g 0000|01|7E = Pink with White Stripes

//Vehicles: CJ's Garage:  ----
//patch=1,EE,2080D9E2,extended,FFFF0197
//patch=1,EE,2080DA02,extended,0000223B
//patch=1,EE,1080D9E0,extended,0000001F

//--------------------------------------------------------------------
//-------------- TESTS Junk, Fails, Unknown, Not tested --------------
//--------------------------------------------------------------------

//Taxi Time: - I searched around the memory region, then NOP'd the address. It generated this value.	
patch=1,EE,206BA106,extended,FFFFFE00
patch=1,EE,206BA108,extended,FFFFFE00
patch=1,EE,206BA10C,extended,FFFFFE00

//patch=1,EE,206BA164,extended,1FFFFFDF

Unnamed Cheat
137787E9 627D3831

Unnamed Cheat
1059EC04 00000190

20802428 3B9AC9FF
206BA104 3B9AC9FF

//Vigilante: Instant Vigilante tests-

//Threat eliminated:
//* Copy paste this from the address ->...
[206F3C440]
00227CDC 00227CDC 00000F07 00002537 00001E43 00001F42 0000203F 00002140 00002B2D 00002241 0000233A 00002442 0000253E 00002C31 00002645 0000284D 00002947 00002A47 00002A47 0000000C 00000000 00251251 00001C20 00000000 00005DEB 00000000 00000000 00251251 00000021 00000018 00000001 0000003B 00000F3C 00000001 00253BC4 00000001

//Vigilante: Level Number
//patch=1,EE,206BA178,extended,00000000

//Vigilante: Instant Vigilante tests-- correct addresses, not sure of the values.
//patch=1,EE,206F3C440,extended,00000000
//patch=1,EE,206F3C444,extended,00000000
//patch=1,EE,206F3C448,extended,00000000
//patch=1,EE,206F3C44C,extended,00000000
//patch=1,EE,206F3C450,extended,00000000
//patch=1,EE,206F3C454,extended,00000000
//patch=1,EE,206F3C458,extended,00000000
//patch=1,EE,206F3C45C,extended,00000000
//patch=1,EE,206F3C460,extended,00000000

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
//Addresses change (dynamic): ** Use the Save State Provided! - then these cheat will work.

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

//parachute 		- (Press L1 + LEFT)		- Not Working
//patch=1,EE,A00C22B0,extended,2001344C
//patch=1,EE,A00C22B4,extended,51010006
//patch=1,EE,A00C22B8,extended,8C8200FC

// ---- Wanted Level ----

//Max Wanted Level (no line 2 +4 bytes ?)
//patch=1,EE,2027BFC8,extended,00000000

//Never Wanted Level ||Default Values =  27BDFFD0 || FFBF0020
//patch=1,EE,2027BF90,extended,03E00008
//patch=1,EE,2027BF94,extended,00000000

//Never get Busted
//patch=1,EE,2046B090,extended,03E00008
//patch=1,EE,2046B094,extended,00000000

//Wanted Level Always 0:				- *** does not work ***
//patch=1,EE,2027BFB4,extended,20040000

//Wanted Level Always 1://patch=1,EE,2027BFB4,extended,20040032

//Wanted Level Always 4://patch=1,EE,2027BFB4,extended,00000006

//water level - test 1 of these lines , nts pal plat.
//patch=1,EE,2017F800,extended,00000000
//patch=1,EE,2017F900,extended,00000000
//patch=1,EE,2017F700,extended,00000000

//cannot remember what this fukka is
//patch=1,EE,2024E42C,extended,00003D00
