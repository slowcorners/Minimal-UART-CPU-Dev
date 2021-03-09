************************************************************
*****                                                  *****
***** Slu4's Minimal UART CPU (FLASH Edition) Emulator *****
*****                                                  *****
************************************************************

1) Emulator Keyboard Shortcuts
------------------------------
ALT+TAB			Change focus to another application
END					Quits the emulator
F1					Toggles the emulator's HUD control screen
F2/F3				Changes the memory start address on HUD control screen by +/- 0x0100
SHIFT+F2/F3	Changes the memory start address on HUD control screen by +/- 0x1000
F9          Unlocks/locks write access to FLASH area 0x0000-0x7fff (indicated by red color in HUD)
F10         Generates .bin files for control word MSB, LSB and FLASH OS area 0x0000-0x0fff
Pos1				Resets the program counter to 0x0000
ESC e				Clears the RAM of the 8-Bit CPU
ESC c				Clears the terminal screen
ESC p<adr>	Sets the program counter to <adr>. Example: ESCp0800 sets the PC to 0x0800
ESC b<adr>  Sets a one-time break point. Example: ESCb8000 halts the clock when MAR = 0x8000
ESC r				Halts the clock and resets the CPU and all it's components
ESC l<prog>	Assembles the text file <prog> and uploads the corresponding machine code into RAM
ESC 0				Halts the clock
ESC 1..9		Sets clock speed to 10^1..9Hz but no larger than the current maximum supported by the hardware (1.8432MHz)
ESC s				Performs a full clock cycle (LOW, HIGH)
ESC h				Performs half a clock cycle
ESC x				Executes until next instruction fetch (control signal II) is hit
ESC #<hex>	Writes the specified hex data into RAM starting at PC (ESC#cafe writes 0xca 0xfe)

2) Loading, assembling and running the example program 'chars.txt'
------------------------------------------------------------------
- Launch the emulator
- type ESC l chars.txt ENTER
- type ESC 2
- Press F1 to see the program in memory and the blinkenlights control signals.
  Change the clock speed to your liking.

3) If you prefer, you can use the stand-alone assembler asm.exe to produce
'keystroke' output inside a console and cut & paste that into the emulator.
Just type asm <progname>. Works just as good ;-).

4) Some Assembler syntax (also take a look at the example programs)
-------------------------------------------------------------------
*=$xxxx			    sets the program counter address to hex xxxx
label:			    defines a label
JPA label		    uses a label
$xxxx				    16-bit hex word
$xx					    8-bit hex byte
123					    8-bit dec byte
'a'					    equivalent to 65 or $41
"hello"			    defines a byte string in memory
1, 2, 3			    defines a byte string in memory
<label			    least significant byte (LSB) of the 16-bit address 'label'
>label			    most significant byte (MSB) of the 16-bit address 'label'
#include <file> includes another source file prior to assembling
#begin          tells the assembler to output the following instruction (default)
#end            tells the assembler to ignore the following instructions until #begin is hit
#break          defines a one-time-only breakpoint

5) OpCodes / Instruction Set
----------------------------
See separate document.

I hope this gets you started. Let me know how things are going. Cheers!
Slu4
