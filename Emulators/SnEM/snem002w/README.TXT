SNem release 0.02
-----------------

Changes since last release :

- Rewritten graphics emulation. Now line-by-line changes and HDMA are emulated.
- Mode 7 works better
- Some 65816 bug fixes - more games work
- HiROM support (buggy)
- Improved SPU skipper
- Now runs at correct speed always (hopefully)

What is emulated :

65816  - about 75% of opcodes. A few major bugs.
SPC700 - about 50% of opcodes. Some games need it to do anything (Bomberman 3),
         some games need it disabled (KSFH).
PPU    - Modes 0,1,2 and 3 emulated, with full sprites, HDMA, and line-by-line
         changes.
DMA    - All channels. Might be some bugs though.
Joypad - Joypad 1 is emulated with the following keys :

        Button    Key
         Dpad    arrows
          A        S
          B        X
          X        A
          Y        Z
        Start      C
        Select     D


Other keys :

ESC     - quit
F1      - Soft reset
F3      - Toggle HDMA
F12     - screenshot to scrshot.pcx. Remember to trim file to 256x224

What's not emulated :

DSP  - well not properly at least... not much point, SPC never triggers note on.
Any special chips


Command line :

snes <file.smc> [-spc]

-spc enables the SPC700 emulation, which is incomplete at the moment.


Notes :

Most HiROM games don't work correctly.

Mode 7 is still very buggy. Only a handfull of mode 7 stuff works correctly.

The SPC never triggers any notes.

Still quite a few 65816 bugs.

There may be a problem with sprite clipping. I've been unable to determine
whether that's a 65816 or rendering bug yet.


Compatibility :

Demos :
SONIC.SMC    - Works
TWEET.SMC    - Works
CDI.SMC      - Works
DWARF.SMC    - Works
Infinity     - Works
First Drop   - Some graphics errors
Nesquik      - Needs more mode 7
M-DEMO.SMC   - Loads of graphics errors. Press F1 on the third part to get onto
               the fourth (demo needs reset)
Snes Wish    - Some graphics errors
ATX-DEM1.SMC - Some graphics errors
Lynchmob msc - Works, but pointless as there's no sound.

Games :
RTS Pacman          - Playable
Gradius 3           - Playable
KSFH                - Playable
TMNT 4              - Playable
Smash TV            - Playable, some pre-game gfx errors
Soccer Kid          - Screen a bit shaky at times
Mario World         - Various collision detection errors
Wario's Woods       - Disable BG 3. Playable
FF2                 - Sprite errors, bad mode 7 (hence overworld unusable), very
                      slow
Super Offroad       - Can't start game
Mystical Ninja      - Level data missing in platformy bits, sprite clipping
                      problems
Cameltry            - Bad mode 7 (rotation flipped or something)
Super B.C. Kid      - Sprite errors + BG3 absent.
Super Bomberman     - Huge errors + sprite errors (Hudson's sprite allocation
                      system doesn't work correctly).
Super Bomberman 3   - Hits BRK and dies.
Pin. Fantasies      - Playable.
Asterix             - Doesn't get past language select
The Humans          - Resets after first level.
Zelda 3             - Collision detection AWOL.
Mario Allstars      - SMB 2+3 broken. Need hacked version.
Columns             - Not very playable yet.
Mr. Do!             - Sprites are invisible for some reason.
Super Soccer        - Can't start game, but runs demo ad infinitum.
Smash Tennis        - Ignores input. Therefore can't start game.
Super Tennis        - Locks.
Some dbz game       - Intro guy spins round and round and round and round and round and... (don't think this is any great loss though)
Addams Family       - Squashed BG data.
Pushover            - Bad initial password. Later levels bugged.
Gods                - Big GFX errors
James Pond 2        - Bad level+sprites data
Super StarWars      - Crashes on starting new game
Lemmings            - Big GFX errors, can't make lemmings do anything.
Illusion of Time    - Ignores input/hangs on title.
Axelay              - Hangs on title
Beast               - No sprites
Wolfenstein 3D      - Corrupt display
Micro Machines 2    - Sprite errors, game never starts
Exhaust Heat        - Excessive flashing on title. Menu behaviour broken.
Donkey Kong Country - Totally fucked
Chrono Trigger      - Shows something. No, really.


Other stuff :

Thanks to TRAC for some bugfixes and misc help.
Also thanks to the developers of DJGPP, Allegro and MING/W.

I would appreciate any comments, constructive criticism, improvements etc on
this emu.

Tom Walker
tommowalker@hotmail.com