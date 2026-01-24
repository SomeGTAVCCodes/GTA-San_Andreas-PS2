-----------------------------------------------------------------
--- The .scm ----
-----------------------------------------------------------------
* The previous version has comments "/* // */". This can be used to see primarily where my notes are and for users to replicate if they want
*   - Search "//" or "TKBS" & use common text edit features like compare, and jump to next compare for fast comparisons. 

* The latest version labelled "ZAZ_FIX" is a compiled-> decompiled version (stripped of comments),
*   - this makes it very dificult (impossible) to compare to original - or continue working on e.g. ps2_kb removals (becuase we have lost the comments that direct use to what i needed to add or remove next and now don;t know which block was from a ps2_kb request and which was not.

* "CustomVariables.ini" are required for Sanny Builder 4.1. recommended, using option - "PS2 v1". Although i recommend users use this file for reference and start with a clkean decompiled main.scm NOT using custom variables at all.

-----------------------------------------------------------------
 --- i wanted this to be a perfect scm (Vanilla+) ----
 -----------------------------------------------------------------
[1]
* it should have all PS2_KB removed except mission skip - and not break anything i.e. perfect changes

[2]
fix pickups, add missing adrenaline, fix any issues with coords items, icons, placements etc.

[3]
fix any issues like jetpack bball, bball save etc.

[4]
add template sections that are just "noname: terminate_this scripts" - they do nothing
users can copy/ paste templates into those sections e.g cheat menus.

[5]
with a perfect cleaned and fixed scm, and all the templates provided separately users can creat their own be-spoke main.scm, hassle free!

-----------------------------------------------------------------
[What i achieved vs what i wanted]
-----------------------------------------------------------------
* The only thing i could NOT achieve was the MAGIC CAR -e.e. spawn any vehicle mod, which i had working for vice city 
* i wanted this to not be a cheat menu - but to be like VICE_CITY-Hyrbid Version 
** infact i am sure it can be done in less than 50 lines of code. It doesn't require an extensive menu or even the same as vice city hyrbid or liberty city stories 
* it should be Simply press pad 2 select + l1, or r1 to increase or decrease the model ID and spawn that vehicle and thats it!

[this main.scm is]
** (i HOPE) OK! - but i cannot gurantee it.
* I was unable to remove all the PS2_KB depsite seevral attemtps, once last year in january, once in june, and again this january.
- It is simply to complicated - especially when files you are working with is nothing like the original nor is it anything like it looks after compile.
- it is too confusing to do for any 1 person - and this is why after 22years it has never been done and people rely on CLEO... which is pointless if you cant get the main.scm correct to begin with.

After tests - i am completely convinced fixes and removal of junk code actually results in a much better running game. 
Although my code is not perfect, currently it is believed to work, just not tested on a full p,ay-through.
it is simple, easy to udnerstand, easy to edit, and literally does everything you ever wanted **except MAGIC_CAR**

[Credits]
Zaz provided an informative overview and check of the custom scripts, resulting in a 1 word removal that basically fixed everything lol!
Orion appears to aid and support users through their, often noobie, situations. Big thanks for constant support and detailed explanations.
Credits to respective authors for apps used or additional files/ info, unfortunately it is difficult to always ascertain whom the original ares of files that are constantly re-posted without original docvs.



