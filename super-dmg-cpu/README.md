# Super DMG CPU

Super DMG CPU works with both IPS and DOT MATRIX LCD boards.

<img src="../images/cpu-top.svg?raw=true" alt="top" width="48%"/> <img src="../images/cpu-bottom.svg?raw=true" alt="bottom" width="48%"/>

## Credits

The schematic is largely based on [the work done by bit 9](https://imgur.com/a/X5qKI).

I used [Gekkio KiCAD libs](https://github.com/Gekkio/gekkio-kicad-libs) for a few symbols (cpu, ram, cart connector, link port). The specialized footprints were traced by me using fusion 360, using these [scans by bit 9](https://chipmusic.org/forums/topic/13608/dmg-main-board-schematic-circuit-arduinoboy/) as a reference.

## Warning

v1.8 and below have an error with the Link Port, where the footprint was flipped (sigh). If you have a v1.8 or below please don't use the link port, as it might damage the other Game Boy! This was fixed in later versions.

## Features

### Compatibility

Super DMG CPU can be built using new components, except for the CPU, power switch and link connector. It is also possible to use some components harvested from a DMG.

### USB Type-C

The round power connector is replaced with an USB Type-C port. The port is only connected to a pad on the motherboard, you need to add your own battery charger and/or power regulator if you want to make use of it. This port is optional.

### Power distribution IC

A power distribution IC takes the system load away from the power switch, so the game boy remains fully operational even if the switch is not in an optimal condition. This circuit can be bypassed with a jumper.

### Internal ProSound

The headphone output does not pass through the amplifier, only the volume potentiometer.

## BOM

| Designator | Package | Qty | Value / Description | Source |
|------------|---------|-----|---------------------|--------|
| U1 | QFP-80 14x20 p0.8 | 1 | CPU | DMG, SGB
| U2 | SOP-28 17.5x8.4 p1.27 | 1 | VRAM | DMG, SGB, [LCSC](https://lcsc.com/product-detail/C1351073.html)
| U3 | SOP-28 17.5x8.4 p1.27 | 1 | RAM | DMG, SGB, [LCSC](https://lcsc.com/product-detail/C1351073.html)
| U4 | SSOP-18 6x7.4 p0.8 | 1 | Audio Amplifier | DMG
| EXT1 | | 1 | Link Connector | DMG
| DA1, DA2, DA3, DA4 | SOT-23-3 | 4 | BAV99-7-F | [LCSC](https://www.lcsc.com/product-detail/C106919.html)
| C1, C23 | 3528 | 2 | 100µf tantalum | [LCSC](https://lcsc.com/product-detail/C122271.html)
| SW1 | | 1 | Power Switch | DMG
| U5 | SOT-23-5 | 1 | Power Distribution | [LCSC](https://lcsc.com/product-detail/C517266.html)
| D2 | SOD-123 | 1 | 1N414 | [LCSC](https://lcsc.com/product-detail/C83528.html)
| X1 | HC-49S | 1 | 4.194304 MHz | DMG, [LCSC (TH)](https://lcsc.com/product-detail/C718646.html), [LCSC (SMD)](https://lcsc.com/product-detail/C2149317.html)
| USB1 | USB_C_16p | 1 | Charge Connector | [LCSC](https://lcsc.com/product-detail/C2931472.html)
| VR1 | | 1 | Volume Pot | DMG, [AliExpress](https://www.aliexpress.com/item/32840044311.html)
| CN1 | 1.25 x 21 SMD | 1 | LCD Board Connector | DMG, [AliExpress](https://www.aliexpress.com/item/1005004824507106.html)
| CN2 |  | 1 | Cart Connector | DMG, [AliExpress](https://www.aliexpress.com/item/1005002719771295.html)
| CN3 | | 1 | AA Battery Contacts | DMG, [AliExpress](https://www.aliexpress.com/item/32801068366.html)
| CN4 | 1.25 TH | 1 | Lipo Battery Connector | [LCSC](https://www.lcsc.com/product-detail/C722595.html)
| C3, C4 | 0805 | 2 | 1µF |
| C5, C6 | 0805 | 2 | 10µF |
| C7, C8, C9 | 0805 | 3 | 47nF |
| C10, C24, C25 | 0805 | 3 | 100nF |
| C12, C13, C14 | 0805 | 3 | 10nF |
| C16, C17, C18, C19 | 0805| 4 | 100pF |
| C21, C22 | 0805 | 2 | 27pF |
| R1, R2, R3, R4 | 0805 | 4 | 220Ω|
| R5, R6 | 0805 | 2 | 510Ω |
| R7 | 0805 | 1 | 180kΩ |
| R8 | 0805 | 1 | 1MΩ |
| R9 | 0805 | 1 | 10kΩ |
| R10, R11 | 0805 | 2 | 5.1kΩ |

## Assembly

- Solder all SMD components on the front side
- If using a power board with integrated power distribution close ```J5``` and do not install ```U5```, ```C24```, ```C25```, ```R9```
- If using an external amplifier, such as [Super DMG JACK](../super-dmg-jack) do not install ```U4```, ```C5-C9```, ```C23```
- If you do not need link functionality you can omit ```EXT1```, ```DA1-DA4```, ```R1-R4```, ```C16-C19```, ```D2```
- Solder the through hole components and the LCD board connector
- (Optional) solder the usb connector and cut an opening for the usb port in the front shell using the provided [rudimentary jig](../3d_models/dmg_usbc_jig.stl)
- The original DC jack hole can be covered with this simple [3d printed plug](../3d_models/dmg_dc_plug.stl)

## Notes

If using an original LCD board you need an original *DMG DC CONV* voltage regulator, as acceptable modern replacements that also include the -18v rail *do not exist yet*.

This pcb cannot be easily biverted yet.

## Ordering

[<img src="../images/pcbway-cpu.png?raw=true" alt="pcbway" width="256px"/>](https://www.pcbway.com/QuickOrderOnline.aspx?projectid=13266&issmt=0)
[<img src="../images/pcbway-referral.png?raw=true" alt="pcbway" width="256px"/>](https://pcbway.com/g/Gw03Yt)

Make sure you order with 1.0mm thickness.

## License

This work is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License.](http://creativecommons.org/licenses/by-sa/4.0/)
