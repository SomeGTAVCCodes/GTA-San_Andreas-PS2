


** see .pnach file for the fix.

//----------The vortex pay and spray bug:----------
//Added: IIRC, version 1 for PS2 would crash or freeze when CJ exited a Vortex after using a pay'n'spray. Use a cheat to spawn a vortex and check it out. Spawns Vortex: Triangle, Triangle, Square, Circle, X, L1, L2, Down, Down
//spawn vortex: Triangle, Triangle, Square, Circle, X, L1, L2, Down, Down
//(EE pc:0033F140) TLB Miss, addr=0x0 [load]
//(EE pc:00290BD4) TLB Miss, addr=0x7a [load]
//(EE pc:00290BDC) TLB Miss, addr=0x7a [store]



Set break point : 0010ECE0


How to fix the bug using 2nd release:

In theory (but might not be possible if code is native to elf)

* compare a cheat code from thsi PAL version to the 2nd release
* use that offset and the break point or debug point or start of the stack at the event of the vortex bug
* once that address isfoudn in the new version which has the bug fixed, try to back port it to the versiuon 1 

briefly worked once as usal,
then didnt work agian

fuk it 
i already the completed the game, multiple times. berfore earnign about the bug


current colution i found is added to the.pnach - chaneg a 0  to a 4 fixed it, or at least, was a wrok-around
