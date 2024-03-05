# TRS-80 Model 1 (Rev G) - Curiosities

The original board had multiple errors and strange implementations, often caused by the limited capabilities of the manufacturing process, but also to save money. The following sections discuss some of the stranger features on the original PCB board, which were replicated when possible.

## Additional Capacitor

![Additional Capacitor](/Images/Curiosities/AdditionalC58.png)

Capacitor C58, located next to the ROMs, was never documented in the technical reference manual. My guess is that it was added later.

## Missing Capacitor

![Missing Capacitor](/Images/Curiosities/MissingC58.png)
![From Original Schematics](/Images/Curiosities/MissingC58Schema.png)

There is, however, a capacitor missing on the board. This capacitor is also called C58 (yes, there are two of them) and is located right next to the relay. It is missing on all the boards I've seen, but I have added it to the schematics and included a note that it is missing on the PCB. This capacitor is actually part of the Cassette Remote control circuit and seems out of place there.

## Wrong Resistor

![Wrong Resistor](/Images/Curiosities/WrongResistor.png)
![From Original Schematics](/Images/Curiosities/WrongResistorSchema.png)

Next to the two potentiometers for the H- and V-Sync, there is supposed to be a 100 Ohm 0.25 Watt resistor, according to the technical documentation. However, on all the boards I have seen, there is actually a 220 Ohm 0.5 Watt resistor instead.

## Undocumented 8k RAM support

The board actually supports two different kinds of 8k ICs for the dynamic RAM. This is not documented in the technical reference manual or the user documentation. See Page 7 of the [new schematics](/Latest/TRS80_Model_I_G_E1_Schematics.pdf).

## Missing Pads (On the Top)

![Missing Pads on Original](/Images/Curiosities/MissingPadsTop.png)
![Missing Pads on Replica](/Images/Curiosities/MissingPadsTopE1.png)

I’ve replicated the "missing pads" on the top of the board as they were on the original board. The pads are only connected at the bottom, so it's fine for them to be missing on the top.

But why was it done this way? At the time, the solder masks weren’t as precise and couldn't adequately cover the traces between pads (see purple/magenta and blue arrow). Bridging those pads and traces during soldering was (and still is) a common issue on these older boards (especially the traces or purple/magenta arrow). That isn’t the case with modern boards, but I still replicated this for the pads only (not the traces in between) to stay closer to the original without the risk of accidental bridging. I guess it's a good compromise.

Completely unconnected pins usually lacked pads on the top as well, but KiCAD doesn’t have an option for that, unfortunately. So, I kept them as they are (see orange arrow), meaning they have pads on both the top and bottom.

The yellow arrow is unrelated to this topic, but you can see the cut trace of the original board which is needed for the lower-case mod.

## Missing Pads (On the Bottom)

![Missing Pads on Original](/Images/Curiosities/MissingPadsBottom.png)
![Missing Pads on Replica](/Images/Curiosities/MissingPadsBottomE1.png)

I replicated three missing pads on the bottom of the board at Z69. While accurate to the original, it was a pain to solder the sockets to the pads while they rested on top of the board. I don’t use wave soldering as they did in the original, so that was just annoying. In the newest version of the board, I placed these pads back to make them easily solderable.

## Unused Vias

![Unconnected Vias](/Images/Curiosities/UnconnectedVias.png)

There are a bunch of unused vias on the board. I am not entirely sure why that is.

## Small Holes

![Mounting Holes](/Images/Curiosities/MountingHoles.png)

At the edges of the board, you can see two rather small holes. These were used during the manufacturing process to keep the board in a known position, enabling the machines to create and assemble the board.

## Bumpy Traces and Zones

![Bumpy Traces and Zones](/Images/Curiosities/BumpyTracesZones.png)

If you ever wonder what these "bumpy" traces and fill zones are, they are not dissolving or anything of that nature. This is how they are supposed to be. The boards were assembled in this way. The traces and zones were tinned, then solder mask was applied, covering nearly everything. When the board was wave soldered with the components in place, these tinned traces melted again due to the heat and solidified shortly after. The tension of the solder mask kept them in somewhat random shapes and caused these bumps. You can actually see this if you put your soldering iron to a pad close to these bumps; you will see that the tin beneath the solder mask liquifies and can even be sucked out by a desoldering iron or pump.

Since the method of tinning has changed (using HASL nowadays) and I don't wave solder, this isn't happening anymore, and it is difficult and probably costly to replicate.
