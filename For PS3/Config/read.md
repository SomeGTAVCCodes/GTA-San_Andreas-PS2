title 		POSSIBLE_CONFIG_OPTIONS_GTSA
author:		TKBS
info:		A custom config for GTA SAN_ANDREAS
			i just tested what works and what crashes and documented it. No idea how beneficial it is.
Links:
https://www.psdevwiki.com/ps3/PS2_Emulation/PS2_Config_Commands
https://www.psdevwiki.com/ps3/PS2_Classics_Configuration_Files_(Official)#G
https://ps3classics.github.io/ps2/config-guide.html
https://ps3.aldostools.org/ps2config.html
https://www.psx-place.com/threads/compatibility-list-ps2-on-ps3.1306/page-88

[Example]
0x21 		|| is used in VC & GTA 3, but causes No Signal Output in SA.
add  "00 00 00"
becomes "21 00 00 00" || FMV Stutter ?instruction cache skip
if has parameter add extra 00 00 00 00 with appropriate ##

[FINAL]
1.|`| Custom.
2.|`| Net.
3.|`| GX & soft. - recommended.
3D 00 00 00 60 40 00 00 0F 00 00 00 B0 45 1E 00 08 51 1E 00 19 00 00 00 45 00 00 00 50 00 00 00 40 00 00 00 00 00 00 00 53 4C 45 53 2D 35 32 35 34 31
3D 00 00 00 89 3D 00 00 0F 00 00 00 B0 45 1E 00 08 51 1E 00 19 00 00 00 45 00 00 00 50 00 00 00 40 00 00 00 00 00 00 00 53 4C 45 53 2D 35 32 35 34 31
3D 00 00 00 57 44 00 00 0F 00 00 00 B0 45 1E 00 08 51 1E 00 19 00 00 00 45 00 00 00 50 00 00 00 40 00 00 00 00 00 00 00 53 4C 45 53 2D 35 32 35 34 31
#.ntsc -							DC 46 1E 00 E8 4A 1E 00

----------------------------------------------------------
---- tests & notes ----
----------------------------------------------------------
ps2_gxemu.self and/or ps2_softemu.self

			|cus,net,soft|			  | ntsc or pal            |			|			 |							|| TITLE ID + NUMBER e.g.  SLES52541 ...
|`| Custom: 
3D 00 00 00 |60 40 00 00 |0F 00 00 00 |B0 45 1E 00 08 51 1E 00 |40 00 00 00 |50 00 00 00 |00 00 00 00
|`| Net: Extracted from PS2 Classic
3D 00 00 00 |89 3D 00 00 |0F 00 00 00 |B0 45 1E 00 08 51 1E 00 |40 00 00 00 |			 |00 00 00 00 				||53 4C 45 53 2D 35 32 35 34 31
|`| GX & soft
3D 00 00 00 |57 44 00 00 |0F 00 00 00 |B0 45 1E 00 08 51 1E 00 |			|			 |00 00 00 00 				||53 4C 45 53 2D 35 32 35 34 31
|`| SLES-52927 - Extracted from PS2 Classic (NPED-00070) - (rev. 16480). Requires PS2 Emulator from firmware 4.20 or newer
3D 00 00 00 |60 40 00 00 |0F 00 00 00 |B0 45 1E 00 08 51 1E 00 |40 00 00 00 |			 |00 00 00 00 				||53 4C 45 53 2D 35 32 39 32 37			
|`| NTSC- SLUS_209.46.CONFIG
3D 00 00 00 |60 40 00 00 |0F 00 00 00 |DC 46 1E 00 E8 4A 1E 00 |40 00 00 00 |50 00 00 00 |00 00 00 00

|`| test: With bytes from ntsc version:
* 57 44 00 00 should probably be removed here, its in the wrong place but it does laod.
3D 00 00 00 60 40 00 00 0F 00 00 00 DC 46 1E 00 E8 4A 1E 00 57 44 00 00 19 00 00 00 45 00 00 00 50 00 00 00 40 00 00 00 00 00 00 00 53 4C 45 53 2D 35 32 35 34 31
...OR...
|`| test: With bytes from pal version:
3D 00 00 00 60 40 00 00 0F 00 00 00 B0 45 1E 00 08 51 1E 00 19 00 00 00 45 00 00 00 50 00 00 00 40 00 00 00 00 00 00 00 53 4C 45 53 2D 35 32 35 34 31

[Possible Options based on info on the wiki & known confs]
19 00 00 00 || Disable DEV9. Disables net/ps2hdd capabilities including Network Adapter detection.
21 00 00 00 || is used in VC & GTA 3, SA = NO SIGNAL! - do not use  instruction cache skip
40 00 00 00 || SA || Command change GIF behavior by setting value to 1 at address 0x2F0 LS in SPU4
45 00 00 00 || Sets something 1 (|| Does somethign with resolution (tv settings switch) but still does not fix pal iso patched with adrenaline 60hz ypos issue..)
50 00 00 00 || Enable pressure sensitive controls
46 00 00 00 || L2H Improvement
1C 00 00 00 01 00 00 00 1D 00 00 00 01 00 00 00 || multitap on pad port 1 ||  0x1C toggles multitap emulation, enabled in both ports by default || 0x1D sets which port to use. 
1C 00 00 00 02 00 00 00 1D 00 00 00 02 00 00 00 || multitap on pad port 2
46000000 <---------------- Enable L2H Improvement
41000000 <---------------- Disable lwsync 

Optional: // not tested - possibly the headers?
* Replace "60 40 00 00" with ;-
60 40 00 00 custom  - function unknown
89 3D 00 00 net   	- function unknown  - also ntsc platinum not sure if compat with pal
57 44 00 00 soft  	- function unknown
...

00 00 00 00 soft 	- unknown whether attached to other command/ parameter or is 0x00

DC 46 1E 00 E8 4A 1E 00 - in ntsc - function unknown + also loads in pal but not sure if has an effect
B0 45 1E 00 08 51 1E 00 - in pal  - function unknown + also loads in ntsc but not sure if has an effect

53 4C 45 53 			|| Version 1 "SLES-52541"
2D 35 32 35 34 31 		|| ...
- (2D 35 32 39 32 37)	|| Version 2 platinum "...."

*** So all would be:
3D 00 00 00 || header & file version 
60 40 00 00 || custom, net , or soft values.
0F 00 00 00 
B0 45 1E 00 
08 51 1E 00 
17 00 00 00 || Force analog controller mode 0x17 	0x19
19 00 00 00 || Force analog controller mode 0x17 	0x19
21 00 00 00	|| "NO SIGNAL!"  -- Do not use effects display
40 00 00 00	|| Works 
44 00 00 00	|| Disable smoothing filter  
45 00 00 00	|| Works
0x46 00 00 00	|| Enable L2H Improvement 

50 00 00 00	|| Works
00 00 00 00 //... not sure if enable pressure sensitive above ^^ requires additional 01,02, etc for pads.
57 44 00 00 || "WD.."(hex~text)
00 00 00 00 //... not sure if part of above. looks independant
				00000000 = SLPS-25606 <---- Config terminator or TitleID enforcer
53 4C 45 53  || sles title and number e.g.  SLES52541 ...
2D 35 32 35 34 31 || ...


tod do 
test 0x21 followed by 0x22 but assume they both have parametrs for stuff - coz it switches resoutioln.
