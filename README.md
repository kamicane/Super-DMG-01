# DMG-01-B

A KiCAD 6.0 recreation of the original Game Boy motherboard, with a few modern twists.

<img src="images/pcb-front.png?raw=true" alt="pcb-front" width="512"/>

The schematic is largely based on [the work done by bit 9](https://chipmusic.org/forums/post/215957/#p215957).

I used [Gekkio KiCAD libs](https://github.com/Gekkio/gekkio-kicad-libs) for a few symbols (cpu, ram, cart connector, link port). The specialized footprints were traced by me using fusion 360. I used these [scans by bit 9](https://imgur.com/a/X5qKI) as a reference.

## Warning

*This revision is not yet tested.* Revision 1.2 was operational but had a few issues. Instructions incoming after testing.

## Differences

### USB-Type-C

I got rid of the round power connector in favor of an USB-C port. The port is only connected to a pin on the motherboard, you need you add your charger of choice. The port is optional.

### ProSound

The headphone output does not pass through the amplifier, only the volume potentiometer.

### AMP Power

The audio amplifier is powered by regulated output.

### Configurable power switching

To seamlessly support more complex voltage regulators & battery chargers what goes into the power switch is configurable via solder jumpers.

### Power distribution switch

A power distribution switch makes sure the Game Boy is fully operational even with a dirty power switch. This circuit can potentially be bypassed with a jumper.

## Required components from an original DMG

- DMG CPU
- Power Switch (could not find a similar enough switch)
- Cart Connector
- Screen Connector (could not find a connector with the same number of pins and pitch)
- RAM & VRAM
- DMG AMP: optional if you plan to use an external amplifier
- Link port: optional if you don't care about multiplayer games

## Disclaimer

I am not an electronics expert. This board might fry your games, set your house on fire and kill your pets.

## License

This work is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License.](http://creativecommons.org/licenses/by-sa/4.0/)
