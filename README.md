# Super DMG-01

A [KiCad](https://www.kicad.org/) 6.0 recreation of the original Game Boy, with a few modern twists.

One of the main goals of this project is to build an entire DMG using only a DMG CPU or a SGB CPU.

<img src="images/photo-cpu-top-v1.7-alpha2.jpg?raw=true" alt="pcb-v1.3" width="48%"/> <img src="images/photo-cpu-bottom-v1.7-alpha2.jpg?raw=true" alt="usb-v1.3" width="48%"/>

[<img src="images/pcbway-cpu.png?raw=true" alt="pcbw" width="256px"/>](https://www.pcbway.com/QuickOrderOnline.aspx?projectid=13266&issmt=0)
[<img src="images/pcbway-referral.png?raw=true" alt="pcbway" width="256px"/>](https://pcbway.com/g/Gw03Yt)

## Credits

- bit9 for the [DMG schematics](https://imgur.com/a/X5qKI) and [board scans](https://chipmusic.org/forums/post/215957/#p215957)
- [Gekkio](https://github.com/Gekkio) for the CPU, RAM, CART symbols from [Gekkio KiCad libs](https://github.com/Gekkio/gekkio-kicad-libs)

## Separate Boards

Like an original DMG, the Super DMG-01 is made out of separate boards. Doumentation for each board can be found in the relative sub-folders:

- CPU Board: [Super DMG CPU](super-dmg-cpu)
- JACK Board: [Super DMG JACK](super-dmg-jack) (experimental)

## 3rd party boards

To complete the build additional boards are required:

- JACK board: while Super DMG JACK is under development you can use [DMG Prosound PAK](https://oshpark.com/shared_projects/IECpD72C), or use one from a DMG
- DC CONV Board: use [MouseBiteLabs](https://github.com/MouseBiteLabs)' [DMGC-PWR-01](https://github.com/MouseBiteLabs/Game-Boy-DMG-Color/tree/main/DMGC-PWR-01) or use one from a DMG
- LCD Board: Use any of the available IPS kits or use one from a DMG

## Disclaimer

I am not an electronics expert. Super DMG-01 might fry your games, set your house on fire and kill your pets.

<img src="images/photo-usb.jpg?raw=true" alt="bottom" width="100%"/>

## License

This work is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License.](http://creativecommons.org/licenses/by-sa/4.0/)
