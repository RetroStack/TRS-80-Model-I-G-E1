# TRS-80 Model 1 (Rev G) Replica - E1

This project is a faithful reimplementation of the mainboard of the iconic TRS-80 Model 1 (Revision G) computer. My own revision, the E1, is designed to replicate the original system's functionality by using a PCB design 1-to-1 to the original, including components, interfaces, and even traces. The entire project is available under the MIT license.

![E1 Replica](/Latest/TRS80_Model_I_G_E1_Photo.png)

## Project Details

### Latest Files

In the "Latest" folder, you'll find the most up-to-date design files, including:

- Gerber files suitable for popular online PCB manufacturers like [PCBWay](/Latest/TRS80_Model_I_G_E1_Gerber_PCBWAY.zip) and [JLCPCB](/Latest/TRS80_Model_I_G_E1_Gerber_JLCPCB.zip).
- A Bill of Materials (BOM) in both [CSV](/Latest/TRS80_Model_I_G_E1_BOM.csv) and [PDF](/Latest/TRS80_Model_I_G_E1_BOM.pdf) formats.
- Layers exported in PDF and SVG formats.
- The [full schematics](/Latest/TRS80_Model_I_G_E1_Schematics.pdf) of the E1 replica which is 1:1 to the original G board.

### Ordering Instructions

When ordering the board from a PCB manufacturer, you can select the following to get a more faithful version of the board:

```
Dimension: 407mm x 184mm
Layers: 2
Base Material: FR-4 TG 135-140 (and up)
PCB Thickness: 1.6mm
PCB Color: Green
Silkscreen Color: White
Via Covering: Untented
Surface Finish: Lead Free HASL
Outer Copper Weight: 1oz
Gold Fingers / Card Edge: yes (chamfer: 30 degrees)
Castellated Holes: no
```

Additionally, supply the following comment for the manufacturer:

> Card edge is only on the upper right. The bottom right is just a connector and does not need to be chamfered.
> 
> There are some missing pads on the top layer. That is correct. Please leave them as-is.

This addresses recurring questions from some of the interesting designs that were used on the original board which was replicated. See the "Curiosities" section below.

### Implementation

E1 has been implemented using KiCAD 7. The KiCAD project files are included in this repository.

![E1 Replica Front](/Latest/TRS80_Model_I_G_E1_3D_Front.png)
![E1 Replica Back](/Latest/TRS80_Model_I_G_E1_3D_Back.png)

### RetroStack Libraries

To work with this KiCAD project, you'll need the RetroStack libraries for KiCAD. Please [follow this link](https://www.github.com/RetroStack/KiCAD-Libraries) to access and install these libraries.

## Curiosities

The original board had multiple errors and strange implementations, often caused by the limited capabilities of the manufacturing process, but also to save money. The following sections discuss some of the stranger features on the original PCB board, which were replicated when possible.

### Small Holes

At the edges of the board, you can see two rather small holes. These were used during the manufacturing process to keep the board in a known position, enabling the machines to create and assemble the board.

### Unused Vias

There are a bunch of unused vias on the board. I am not entirely sure why that is.

### Additional Capacitor

Capacitor C58, located next to the ROMs, was never documented in the technical reference manual. My guess is that it was added later.

### Missing Capacitor

There is, however, a capacitor missing on the board. This capacitor is also called C58 (yes, there are two of them) and is located right next to the relay. It is missing on all the boards I've seen, but I have added it to the schematics and included a note that it is missing on the PCB. This capacitor is actually part of the Cassette Remote control circuit and seems out of place there.

### Wrong Resistor

Next to the two potentiometers for the H- and V-Sync, there is supposed to be a 100 Ohm 0.25 Watt resistor, according to the technical documentation. However, on all the boards I have seen, there is actually a 220 Ohm 0.5 Watt resistor instead.

### Undocumented 8k RAM support

The board actually supports two different kinds of 8k ICs for the dynamic RAM. This is not documented in the technical reference manual or the user documentation.

### Missing Pads (On the Top)

I’ve replicated the "missing pads" on the top of the board as they were on the original board. The pads are only connected at the bottom, so it's fine for them to be missing on the top.

But why was it done this way? At the time, the solder masks weren’t as precise and couldn't adequately cover the traces between pads. Bridging those pads and traces during soldering was (and still is) a common issue on these older boards. That isn’t the case with modern boards, but I still replicated this for the pads only (not the traces in between) to stay closer to the original without the risk of accidental bridging. I guess it's a good compromise.

Completely unconnected pins usually lacked pads on the top as well, but KiCAD doesn’t have an option for that, unfortunately. So, I kept them as they are, meaning they have pads on both the top and bottom.

### Missing Pads (On the Bottom)

I replicated three missing pads on the bottom of the board at Z69. While accurate to the original, it was a pain to solder the sockets to the pads while they rested on top of the board. I don’t use wave soldering as they did in the original, so that was just annoying. In the newest version of the board, I placed these pads back to make them easily solderable.

### Bumpy Traces and Zones

If you ever wonder what these "bumpy" traces and fill zones are, they are not dissolving or anything of that nature. This is how they are supposed to be. The boards were assembled in this way. The traces and zones were tinned, then solder mask was applied, covering nearly everything. When the board was wave soldered with the components in place, these tinned traces melted again due to the heat and solidified shortly after. The tension of the solder mask kept them in somewhat random shapes and caused these bumps. You can actually see this if you put your soldering iron to a pad close to these bumps; you will see that the tin beneath the solder mask liquifies and can even be sucked out by a desoldering iron or pump.

Since the method of tinning has changed (using HASL nowadays) and I don't wave solder, this isn't happening anymore, and it is difficult and probably costly to replicate.

## Main TRS-80 Model 1 Repository

For additional resources related to the TRS-80 Model 1, be sure to check out the central page for the TRS-80 Model 1 on RetroStack. You can find it [here](https://www.github.com/RetroStack/TRS-80-Model-I).

## Support this Project

RetroStack is passionate about exploring and preserving the legacy of older computer systems. Our work involves creating detailed documentation and videos to share our knowledge. We're also dedicated to reviving these classic systems by reimplementing them and offering replacement parts at no cost. If you're keen on supporting this unique project, we invite you to visit our [Patreon page](https://www.patreon.com/RetroStack). Your support would be immensely valuable and greatly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Thank you for your interest in the TRS-80 Model 1 (Board G) replica project - E1. We hope that it inspires retro computing enthusiasts and contributes to the preservation of classic computing history. If you have any questions or suggestions, feel free to reach out to us. Happy computing!
