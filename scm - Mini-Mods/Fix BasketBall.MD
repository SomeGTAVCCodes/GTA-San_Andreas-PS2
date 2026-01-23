

---- BasketBall Bugs & Glitches ----
* there are 2 basketball/ related bugs i noticed when playing 
* shit online doesn't actually explain fuck all. (how and why the value locks & what variable? 
* the "fixes" online for the save icon are not good use these instead.
* there is no mention of the jetpack + bball glitch. so that's 2 more examples of internet being shit, well done people, 22 years...

---- Issue 1 ----
* saving at maddogs prevents re-loading/ loading of basketball object & thus mini-game is Unavailable

[The correct Solution]
* The correct solution is to reduce the 1st radius check "50.0 50.0" to "5.0 5.0" that initiates the basketball game loading ":BBall" 
	locate_char_any_means_object_2d $PLAYER_ACTOR near_object_in_rectangle 0@ radius 5.0 5.0 sphere 0 // Dist In Check (Load in ball) || this must be less than the save icon radius.

* Then reduce radius on the other 2 radius checks to "15.0 15.0" & add a few jumps to destroy in various places - See File
	locate_char_any_means_object_2d $PLAYER_ACTOR near_object_in_rectangle 0@ radius 15.0 15.0 sphere 0 // Dist Out Check (Load )  || these must be the same
	locate_char_any_means_object_2d $PLAYER_ACTOR near_object_in_rectangle 0@ radius 15.0 15.0 sphere 0 // the 3rd one same as 2nd || these must be the same

---- Issue 2 ----
* Using a jetpack with a basketball breaks / freezes.

[CODE]
:FIXES
script_name 'FIXES'
set_text_colour 255 100 100 255
display_text_with_number 500.0 1.0 GXT 'NUMBER' number $Issue

:FIXES_47
wait 0
if 
	is_player_using_jetpack $PLAYER_CHAR
goto_if_false @FIXES_105
set_player_control $PLAYER_CHAR can_move True
set_player_enter_car_button $PLAYER_CHAR can_enter_exit_vehicles 1

:FIXES_105
goto @FIXES_47
[/CODE]







--------------------------------------------------------------------------------
// most of the following is just rants
--------------------------------------------------------------------------------

[test notes] - before solution.
** so the expected behaviour is;--
1. walk towards bball court.
2. at radius check 15.0 the ball will be destroyed, but it doesn't exist yet so no problem
3. at radius check 10.0 the ability to play bball goes from 1, to 0. it's already at 0 because we have not even entered the radius yet - so no problem
4. at 5.0 the bball loads in and the game can be played, we should then be able to leave, at 10.0 not play but be able to return to 5.0 or go to 15.0 and unload the ball entirely.

** this does not happen ^^^

What happens;-
1. 50.0 for all 3 we established is wrong. it gives a save bug, not sure if any other fucky behaviour happens.
2. 5.0 for the 1st check only circumvents the save bug but does not fix the overall issue. - user can still play bball at mdogs then teleport to cause to save bug.
3. setting all 3 checks to make logical sense as explained above, 5, 10, 15, causes the ball to either load in and be unplayable or simply breaks the game entirely.
4. if you set all 3 radius checks to 5.0 then for some reason the ball spawns in once, cannot be used, then spawns in again and then its locked,  breaks the game entirely.. 

* This shows issue is way bigger than just the radius encompassing the save point. or 1 $19## variable being 0 or 1 there is clearly some other fucked-ness happening.
 
* modifying variable $1928 to either 0, 1 depending on what it should be (if for whatever reason it is incorrectly set) does not fix the issue 

^^ so we cannot do that way instead Must have 2nd call greater than 3rd 
instance 1 - 5.0
instance 2 - 15.0 15.0 // Must be less that maddogs crib save icon TO bball radius (2. axis)
instance 3 - 15.0 15.0 // Must be == instance 2.0
&& extra jumps to destroy model // must add extra checks to destroy, to ensure it can reload.


-----------------------------------------------------------------
------------------ file Changes  ------------------
-----------------------------------------------------------------

change     $1928 <> 0 			// coz it will never be less than.
 to		   $1928 > 0
	
5.0 5.0 sphere 0 				// Dist In Check (Load in ball)
15.0 15.0 sphere 0 				// Dist Out Check (Load )
15.0 15.0 sphere 0				// destroy

[code]
:BBALL_1177
Object.RemoveReferences(1@)
16@ = 0
$1928 = 0
gosub @BBALL_3441				// ADD "gosub @BBALL_3441" -> Object.Destroy(1@)

:BBALL_1698
set_player_enter_car_button $PLAYER_CHAR can_enter_exit_vehicles 1
Object.RemoveReferences(1@)
$1928 = 0
16@ = 0
gosub @BBALL_3441				// ADD "gosub @BBALL_3441" -> Object.Destroy(1@)

:BBALL_2162
Object.RemoveReferences(1@)
gosub @BBALL_3441				// ADD "gosub @BBALL_3441" -> Object.Destroy(1@)
if
    Player.Defined($PLAYER_CHAR)
goto_if_false @BBALL_2208
if
    $ONMISSION == 0
goto_if_false @BBALL_2208
set_player_enter_car_button $PLAYER_CHAR can_enter_exit_vehicles 1

:BBALL_3441
Object.Destroy(1@)
[/code]


[code - original ]
	locate_char_any_means_object_2d $PLAYER_ACTOR near_object_in_rectangle 0@ radius 50.0 50.0 sphere 0
[/code]

[code - new ]
	locate_char_any_means_object_2d $PLAYER_ACTOR near_object_in_rectangle 0@ radius 5.0 5.0 sphere 0

	"gosub @BBALL_3441" -> Object.Destroy(1@)
[/code]

[notes]			
When 			$1928 = 0 -> BBall Unavailable near CJs
				$1928 = 1 -> BBall available 

^^ the 1st script is;-
[code - original ]
:BBALL
script_name 'BBALL'
if
    $1928 <> 0					// less than should never occur  we only have 0,1 
goto_if_false @BBALL_31
terminate_this_script
[/code]		

* so to clean that shit before we do anything we can just delete it or force it to 0 or 1.

[ALSO remove all the debug shit code - it is not needed]
:BBALL_4206 // & other examples.

// -------------------------------------------
[moving the save icon: - not recommended]
* moving the save icon not recommended - not required
// -------------------------------------------
