# Super DMG Jack

This board is a _work in progress_. _Do not order_.

Super DMG Jack can be used on any DMG or DMG compatible CPU board.

This is an upated version of my [DMG Prosound PAK](https://oshpark.com/shared_projects/IECpD72C).

It uses a PAM8302 mono amplifier to power the speaker when no headphones are present.

This can also be built as a simple headphone jack replacement using the DMG on-board amplifier.

The schematic is based on [Adafruit's pam8302 amplifier PCB](https://github.com/adafruit/Adafruit-PAM8302-Mono-Amplifier-PCB).

## AMP Installation

- If using an original DMG CPU board get the L/R signals from the volume potentiometer
- Solder the speaker to this board
- Get power from the 5v rail on the CPU board
- Do not solder ```U2```, do not wire the (E)nable signal

## Jack-only Installation

The jack-only installation is meant to be used with the on-board DMG amplifier, however you still need to solder an extra wire for power as the ENABLE signal need to be inverted due to how the new headphone jack works.

- (Recommended for prosound) If using an original DMG CPU board get the L/R signals from the volume potentiometer
- Keep the speaker in the LCD board
- Get power from the 5v rail on the CPU board
- Solder only ```U2```, ```R5``` and the headphone jack.
