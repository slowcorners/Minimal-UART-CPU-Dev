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
F9          Unlock/lock write access to FLASH area 0x0000-0x7fff (see red color in HUD)
F10         Writes .bin files for control word and FLASH OS area 0x0000-0x0fff
SHIFT+F2/F3	Changes the memory start address on HUD control screen by +/- 0x1000
Pos1				Resets the program counter to 0x0000
ESC e				Clears the RAM of the 8-Bit CPU
ESC c				Clears the terminal screen
ESC p<adr>	Sets the program counter to <adr>. Example: ESCp0800 sets the PC to 0x0800
ESC b<adr>  Sets a one time break point. Example: ESCb8000 halts the clock when MAR = 0x8000
ESC r				Resets the CPU and all it's components
ESC l<prog>	Assembles the text file <prog> and uploads the corresponding machine code to RAM
ESC 0				Halts the clock
ESC 1				Sets clock speed to 10Hz
ESC 2				Sets clock speed to 100Hz
ESC 3				Sets clock speed to 1kHz
ESC 4				Sets clock speed to 10kHz
ESC 5				Sets clock speed to 100kHZ
ESC 6				Sets clock speed to 1MHz
ESC 9       Sets clock speed to the current maximmum 1.8432MHz of the hardware
ESC s				Performs a single clock cycle
ESC h				Performs a half single clock cycle
ESC x				Executes instruction until next 'II' control signal (fetch) is hit
ESC #<hex>	Writes the specified hex data into RAM starting at PC (ESC#cafe writes 0xca 0xfe)

2) Loading, assembling and running the example program 'chars.txt' (or 'cursor.txt')
------------------------------------------------------------------------------------
- Launch the emulator
- type ESC l chars.txt ENTER
- type ESC 2
- Press F1 to see the program in memory and the blinkenlights control signals.
  Change the clock speed to your liking.

3) If you prefer, you can use the stand-alone assembler asm.exe to produce address
'keystroke' output in the console and cut&paste that into the emulator.
Works just as good ;-).

4) Some Assembler syntax (also take a look at the example programs)
-------------------------------------------------------------------
*=$xxxx			sets the program counter address to hex address xxxx
label:			defines a label
JPA label		uses that label
$xxxx				16-bit hex word
$xx					8-bit hex byte
123					8-bit dec byte
'a'					equivalent to 65 or $41
"hello"			defines a byte string in memory
1, 2, 3			defines a byte string in memory
<label			least significant byte (LSB) of the 16-bit address 'label'
>label			most significant byte (MSB) of the 16-bit address 'label'
#begin      tells the assembler to output the following instruction (default)
#end        tells the assembler to ignore the following instructions until #begin is hit
#break      defines a one-time-only breakpoint

5) OpCodes
----------
See separate document.

I hope this helps. Let me know how things are going. Cheers!
