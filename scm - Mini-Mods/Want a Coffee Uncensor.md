
1. unsensor
2. remove unused censored code - save space.

---- Want a coffee?  / censorship mod ----

$GF_Censore_Flag = 0
$GF_Censore_Flag = 1

// -- this code will never run when uncensored -- 

:GFDATE_10909
goto @GFDATE_10969
/*if 
  $GF_Censore_Flag == 1
goto_if_false @GFDATE_10969
set_local_var_bit_const 3@ bit 30
clear_local_var_bit_const 3@ bit 1
1@ = 4
2@ = 0
goto @GFDATE_12139
goto @GFDATE_11221*/

//gosub @GFSEX_257

/*:GFSEX_257
if 
  not is_local_var_bit_set_const 9@ bit 1
goto_if_false @GFSEX_512
if 
  $GF_Censore_Flag == 1
goto_if_false @GFSEX_316
set_local_var_bit_const 9@ bit 1
7@ = 9
8@ = 0
return*/ 


Note: this can be done using .pnach or hex edit
//Uncensor (0) - Censor (1)
//patch=1,EE,206B33FC,extended,00000000

Note: online i alsao foudn this code a repost from a reposdt froma post that is gone.
// IF STUCK Press R1 R2 L1 L2
//E003F0FF 00700A42
//2088D860 4C333132
//2088D864 3244334C
//2088D868 32000052

Note: Users can also teleport CJ to escape using a cheat menu or fix the missions code by editing the scm.



[original code]
:GFDATE_10909
if
  $GF_Censore_Flag == 1					// || Will never occur when Mod is enabled
goto_if_false @GFDATE_10969
set_local_var_bit_const 3@ bit 30		// || Will never occur
clear_local_var_bit_const 3@ bit 1		// || Will never occur
1@ = 4									// || Will never occur
2@ = 0									// || Will never occur
goto @GFDATE_12139						// || Will never occur unless called elsewhere
goto @GFDATE_11221						// || Will never occur unless called elsewhere

[new code]
:GFDATE_10909							// || new code, just jump straight to wherever...
goto @GFDATE_10969

[original code]
:GFSEX_257
if
  not is_local_var_bit_set_const 9@ bit 1
goto_if_false @GFSEX_512
if
  $GF_Censore_Flag == 1					// || Will never occur
goto_if_false @GFSEX_316				// || Will never occur
set_local_var_bit_const 9@ bit 1		// || Will never occur
7@ = 9									// || Will never occur
8@ = 0									// || Will never occur
return 									// || Will never occur and rant: i dont understand return anyway, where fuck do they return to - the last operation before this :GFSEX_257 that called it  or the start of this stack :GFSEX_257, coz that would be a loop?? - i dont fuckign udnerstand code.never will.

[new code]
:GFSEX_257								// || new code, just jump straight to wherever...
goto @GFSEX_512
