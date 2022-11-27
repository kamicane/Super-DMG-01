# DMG-01-B

A KiCAD 6.0 recreation of the original Game Boy motherboard, with a few modern twists.

This board works with both modern IPS and original dot matrix LCDs.

<img src="images/pcb-front.png?raw=true" alt="pcb-front" width="512"/>

The schematic is largely based on [the work done by bit 9](https://chipmusic.org/forums/post/215957/#p215957).

I used [Gekkio KiCAD libs](https://github.com/Gekkio/gekkio-kicad-libs) for a few symbols (cpu, ram, cart connector, link port). The specialized footprints were traced by me using fusion 360, using these [scans by bit 9](https://imgur.com/a/X5qKI) as a reference.

## Differences

### USB Type-C

I got rid of the round power connector in favor of an USB-C port. The port is only connected to a pad on the motherboard, you need to add a battery charger. The port is optional.

### Internal ProSound

The headphone output does not pass through the amplifier, only the volume potentiometer.

### AMP Power

The audio amplifier is powered by regulated output.

### Configurable power paths

To support more complex voltage regulators & battery chargers you can configure the power paths via solder jumpers.

### Power distribution switch

A power distribution IC takes the system load away from the power switch, so the game boy remains fully operational even if the switch is not in an optimal condition. This circuit can potentially be bypassed with a jumper.

## Required specialized components

- DMG CPU || SGB CPU
- DMG Power Switch
- 2x DMG S-RAM || 2x SGB S-RAM || [replacement](https://lcsc.com/product-detail/SRAM_Alliance-Memory-AS6C6264-55SCN_C1351073.html) (untested)
- DMG Cart Connector || [replacement](https://www.aliexpress.com/item/1005002719771295.html)
- DMG Screen Connector || [replacement](https://www.aliexpress.com/item/1005004824507106.html)
- DMG Crystal || [TH replacement](https://lcsc.com/product-detail/Crystals_Suzhou-Liming-Elec-49SS-4-194304-20-10-10-B_C718646.html) (untested) || [SMD replacement](https://lcsc.com/product-detail/Crystals_JYJE-S1T41943ZWJAC_C2149317.html) (untested)
- DMG AMP (optional if you plan to use an external amplifier)
- DMG Link connector
- DMG Volume Potentiometer || [replacement](https://www.aliexpress.com/item/32840044311.html)

## Disclaimer

I am not an electronics expert. This board might fry your games, set your house on fire and kill your pets.

## WIP Instructions

### Ordering

Order in 1.0 thickness. The provided gerbers are made to be ordered on JLCPCB. Make sure you select "specify a location" on the "remove order number" option.

Alternatively feel free to generate your own gerbers for your fab house of choice using the provided KiCAD files.

### Assembly

- Solder all SMD components on the front side. Refer to the [BOM](KiCad/dmg-01-b.csv).
- Solder the through hole components and the screen connector.
- If using a stock (or similar) voltage regulator close JP1 and JP2.
- (Optional) solder the usb connector and cut an opening for the usb port in the front shell using the provided [rudimentary jig](3d_models/dmg_usbc_jig.stl).
- The original DC jack hole can be plugged with this simple [3d printed plug](3d_models/dmg_dc_plug.stl).

## License

This work is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License.](http://creativecommons.org/licenses/by-sa/4.0/)
