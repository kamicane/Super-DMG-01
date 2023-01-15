# Super DMG JACK

Super DMG JACK is a replacement headphone/audio PCB for the original Game Boy. It can be used on a stock DMG or the Super DMG-01.

It uses a PAM8302 mono amplifier to power the speaker when no headphones are present, but it can also be built as a headphone jack replacement using the amplifier on the CPU board.

The amplifier schematic is based on [Adafruit's pam8302 amplifier PCB](https://github.com/adafruit/Adafruit-PAM8302-Mono-Amplifier-PCB).

The headphone output needs to be unamplified, and grabbed _after_ the DMG volume potentiometer.

<img src="../images/jack-top.png?raw=true" alt="sdmg jack top" width="48%"/> <img src="../images/jack-bottom.png?raw=true" alt="sdmg jack bottom" width="48%"/>

<img src="../images/sdmg_jack.jpg?raw=true" alt="sdmg jack" width="48%"/> <img src="../images/sdmg_jack_full.jpg?raw=true" alt="sdmg jack full" width="48%"/>

## BOM

| Designator | Package | Qty | Value / Description | Source |
|------------|---------|-----|---------------------|--------|
| CN1 | PJ-3043-B | 1 | Headphone connector | [LCSC](https://lcsc.com/product-detail/C2682182.html) |
| CN2 | 1.25 TH | 1 | CPU PCB Connector | [LCSC](https://lcsc.com/product-detail/C722595.html) |
| CN3 | 1.25 TH | 1 | Speaker Connector | [LCSC](https://lcsc.com/product-detail/C722604.html) |
| U1 | SOP-8 | 1 | PAM8302 | [LCSC](https://lcsc.com/product-detail/C112137.html) |
| U2 | SOT-23-5 | 1 | SN74AHC1G14 | [LCSC](https://lcsc.com/product-detail/C7469.html) |
| VR1 | Bourns TC33X-2-103E | 1 | 10kΩ SMD | [LCSC](https://lcsc.com/product-detail/C719176.html) |
| FB1, FB2 | 0805 | 2 | Ferrite Bead ||
| C1, C2, C5 | 0805 | 3 | 1µf ||
| C3, C4 | 0805 | 3 | 220pf ||
| R1, R2 | 0805 | 2 | 220Ω ||
| R3, R4 | 0805 | 2 | 100Ω ||
| R5 | 0805 | 1 | 10kΩ ||

I got premade wires from [AliExpress](https://www.aliexpress.com/item/1005002353691025.html) (1.25mm 2p and 5p), but you can also just use 28/30 awg without connectors.

I use "WSC" 8Ω 2W speakers from AliExpress.

## DMG Pinout

<img src="../images/dmg_pinout.png?raw=true" alt="dmg-pinout" width="100%"/>

## Full Installation

- Get the L/R signals from the volume potentiometer. On the stock DMG, grab the signals ** after pot, on Super DMG-01 grab from the bottom pins directly
- Solder the speaker to this board
- Get power from the 5v rail on the CPU board
- Do not solder ```U2``` and/or do not wire the (E)nable signal

## Jack-only Installation

The jack-only installation is meant to be used with the on-board DMG amplifier, however you still need to solder an extra wire for power as the ENABLE signal need to be inverted.

- Get the L/R signals from the volume potentiometer. On the stock DMG, grab the signals ** after pot, on Super DMG-01 grab from the bottom pins directly
- Keep the speaker in the LCD board
- Get power from 5V (Super DMG CPU) or SW (stock DMG) on the CPU board
- Solder only ```U2```, ```R5``` and the headphone jack

## Notes

3d print the [jack spacer](../3d_models/super_dmg_jack_spacer.stl) for correct alignment.
