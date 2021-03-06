# OpenC64Cart16K
OpenC64Cart16K is an Open Hardware Cartridge for the Commodore 64. It only supports 16 KB ROMs and uses a single (E)EPROM chip. It is the 16 KB counterpart to [OpenC64Cart](https://github.com/SukkoPera/OpenC64Cart).

![Board](https://raw.githubusercontent.com/SukkoPera/OpenC64Cart16K/master/doc/render-top.png)

### Summary
OpenC64Cart16K is designed to accept a 64 KB (512 Kilobit) (E)EPROM with a 27512-style pinout:
![27512 Pinout by Peter Schepers](https://ist.uwaterloo.ca/~schepers/ROMS/PINOUTS/27512.png)

Such chips can hold up to 4 cartridge images, which can be selected by jumpers.

The recommended part is Winbond W27C512 (or W27E512, I don't understand what differences they have), which is widely available, cheap and electrically erasable, which avoids the need for a clunky UV-eraser. This is the only part that was thoroughly tested. Other parts, even smaller in size, will probably work, but will require an ad-hoc configuration.

Usage is straightforward: just insert the EEPROM in the socket making sure that the notch and all pins are aligned, set the jumpers as desired and plug the cartridge in your C64.

### Configuration
**IMPORTANT: ALWAYS TURN YOUR C64 OFF BEFORE MOVING THE CONFIGURATION JUMPERS.**

When flashing the contents, make sure that every file is exactly 16384 bytes long and just concatenate them. If your 16 KB ROM is split into two 8 KB files, concatenate them as well, with the "low" ROM before the "high" ROM.

Then use the following table to set the jumper configuration for your image of choice:

| ROM Image # | A14 | A15 |
|-------------|-----|-----|
| 1           |  L  |  L  |
| 2           |  H  |  L  |
| 3           |  L  |  H  |
| 4           |  H  |  H  |

### License
OpenC64Cart16K is Open Hardware.

### Thanks
The following links were useful during the development of this project:
- https://www.c64-wiki.com/wiki/Expansion_Port
- http://blog.worldofjani.com/?p=879
- https://ist.uwaterloo.ca/~schepers/roms.html
- http://smisioto.no-ip.org/elettronica/kicad/kicad.htm
