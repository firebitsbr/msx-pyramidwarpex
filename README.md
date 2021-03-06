# msx-pyramidwarpex

Disassembly, reverse engineering, and possible enhancement of the MSX game cartridge "Pyramid Warp (1983)"

## Versions:

* `PyramidWarp.annotated.asm`:
	* The annotated disassembly of Pyramid Warp (1983).
	* Assembles to the original ROM, verbatim.

* `PyramidWarp.enhanced.asm`:
	* The original source code, once disassembled, was easy to understand and easy to improve because it used no compression, did no clever tricks, and underused some resources (e.g.: the game looked like SCREEN 1 despite being SCREEN2 already).
	* This is a patcheable version of the original source code that allows several of those enhancements.
	* This version keeps most of the original source code untouched and, actually, a pixel-perfect clone of the original game can be assembled from this!

* `PyramidWarp.enhanced+.asm`:
	* This version break ties with the original source code wherever necessary to accomodate not-so-easy-to-fit enhancements (such as a proper music replayer or a sprite flickering routine)
	* Work in progress

## Enhancements

### Original enhancements by theNestruo

* Moved RAM start from $C000 to $E000 (RAM requirement is now 8KB)
* Unused data removed. Data realigned to simplify routines and to free space (+512 bytes freed)
* Disabled keyboard click sound
* Player starts looking down instead of up (simply because it looks better)
* Numbers in scoreboard aligned right to improve readability
* Patcheable colors (symbolic constants in assembly code)
* Patcheable graphics (external binaries for font, charset and sprites)
* Patcheable room definitions (external assembly code)
* 5th and 6th enemy slots can be enabled

### Additional enhancements by Nenefranz

* Completely new graphic set
* Enemies can look in 4 directions
* Enemies sprites can be replaced by player sprites
* A floor tile can be used instead of transparent character
* Numbers in scoreboard in a different color (to improve readability)
* Fixes the first draw of the playground

### Future enhancements

* Proper music and sounds
* More room definitions! More randomness!
* Sprite flickering routine
* (bug) Improve the old "use 3D charset" enhancement to be compatible with "floor tile" enhancement (and with the new graphic set)
