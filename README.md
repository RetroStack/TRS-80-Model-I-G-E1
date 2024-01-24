# TRS-80 Model 1 (Rev G) Replica - E1

This project is a faithful reimplementation of the mainboard of the iconic TRS-80 Model 1 (Revision G) computer. My own revision, the E1, is designed to replicate the original system's functionality by using a PCB design 1-to-1 to the original, including components, interfaces, and even traces. The entire project is available under the MIT license.

![E1 Replica](/Latest/TRS80_Model_I_G_E1_Photo.png)

## Project Details

### Latest Files

In the "Latest" folder, you'll find the most up-to-date design files, including:

- Gerber files suitable for popular online PCB manufacturers like [PCBWay](/Latest/TRS80_Model_I_G_E1_Gerber_PCBWAY.zip) and [JLCPCB](/Latest/TRS80_Model_I_G_E1_Gerber_JLCPCB.zip). Most manufacturers should be fine with either.
- A Bill of Materials (BOM) in both [CSV](/Latest/TRS80_Model_I_G_E1_BOM.csv) and [PDF](/Latest/TRS80_Model_I_G_E1_BOM.pdf) formats. (Also, see the list below.)
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

### Bill of Materials (BOM)

Below is a list of materials needed to assemble a complete system. Please note that the links and prices (as of January 22, 2024) will not be updated in the future and should only be used as a reference for locating the correct items.

Note: Links and alternatives are provided to assist you in finding the necessary components. I cannot guarantee the complete accuracy or reliability of all these links and alternatives. Please check it for yourself!

|Reference|Quantity|Value|Component Name|Description|Source Comment|Source Cost USD|Source Total Cost USD|Source|Source Link|
|-|-|-|-|-|-|-|-|-|-|
|C1|1|220uF 16V|C_Polarized|Polarized capacitor||1.48|1.48|Mouser|https://www.mouser.com/ProductDetail/598-227TTA050M|
|C2, C4, C5, C10, C11, C57|6|10uF 16V|C_Polarized|Polarized capacitor||0.29|1.74|Mouser|https://www.mouser.com/ProductDetail/598-106RMR050M|
|C3, C7, C14, C15|4|0.01uF 24V|C (103)|Unpolarized capacitor||0.23|0.92|Mouser|https://www.mouser.com/ProductDetail/594-D103Z25Z5VF63L6R|
|C6|1|100uF 16V|C_Polarized|Polarized capacitor||0.37|0.37|Mouser|https://www.mouser.com/ProductDetail/647-UVZ1J101MPD|
|C8|1|2200uF 35V|C_Polarized|Polarized capacitor||5.31|5.31|Mouser|https://www.mouser.com/ProductDetail/598-228TTA063M|
|C9|1|10000uF 16V|C_Polarized|Polarized capacitor||7.87|7.87|Mouser|https://www.mouser.com/ProductDetail/598-109TTA025M|
|C12, C13|2|470pF|C (471)|Unpolarized capacitor||0.23|0.46|Mouser|https://www.mouser.com/ProductDetail/594-D471K20Y5PH6UJ5R|
|C16, C17, C18, C19, C22, C23, C28, C29, C30, C31, C32, C33, C34, C35, C36, C37, C38, C39, C40, C41, C44, C45, C46, C47, C48, C49, C50, C51, C52, C53, C54, C55, C56, C58|34|0.1uF 25V|C (104)|Unpolarized capacitor||0.17|5.78|Mouser|https://www.mouser.com/ProductDetail/594-K104K10X7RF53L2|
|C20|1|330pF|C (331)|Unpolarized capacitor||0.3|0.3|Mouser|https://www.mouser.com/ProductDetail/594-F331K29Y5RP6UK5R|
|C21|1|750pF|C (750)|Unpolarized capacitor||0.37|0.37|Mouser|https://www.mouser.com/ProductDetail/80-C322C751K3G5TA|
|C24, C25|2|220pF|C (221)|Unpolarized capacitor||0.23|0.46|Mouser|https://www.mouser.com/ProductDetail/594-D221K20Y5PF63J5R|
|C26|1|0.047uF|C (47nF)|Unpolarized capacitor||1.9|1.9|Mouser|https://www.mouser.com/ProductDetail/594-222236755473|
|C27|1|0.022uF|C (22nF)|Unpolarized capacitor||1.34|1.34|Mouser|https://www.mouser.com/ProductDetail/594-2222-366-45223|
|C42|1|22uF 16V|C_Polarized|Polarized capacitor||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/710-860010372002|
|C43|1|47pF|C (47)|Unpolarized capacitor||0.4|0.4|Mouser|https://www.mouser.com/ProductDetail/594-S470K25SL0N63L6R|
|CR1|1|1N4735|D_Zener|Zener diode||0.25|0.25|Mouser|https://www.mouser.com/ProductDetail/512-1N4735A|
|CR2|1|1N5231|D_Zener|Zener diode||0.15|0.15|Mouser|https://www.mouser.com/ProductDetail/512-1N5231B|
|CR3, CR4, CR5, CR6, CR7|5|1N4148|D|Diode||0.1|0.5|Mouser|https://www.mouser.com/ProductDetail/512-1N4148|
|CR8|1|MDA202|D_Bridge_+AA-|Diode bridge, +ve/AC/AC/-ve|Replacement|0.61|0.61|Mouser|https://www.mouser.com/ProductDetail/621-KBP210G|
|CR9, CR10|2|1N982|D_Schottky|Schottky diode|Replacement, Lower (39V instead of 75V)|0.26|0.52|Mouser|https://www.mouser.com/ProductDetail/78-1N4754A-TAP|
|J1, J2, J3|3|Front View|DIN-5_180degree|5-pin DIN connector (5-pin DIN-5 stereo)||0.386|1.158|AliExpress|https://www.aliexpress.us/item/2255801077942335.html|
|J100|1|Connector|Conn_01x20|Generic connector, single row, 01x20||0.5|0.5|Mouser|https://www.mouser.com/ProductDetail/649-1012937992002BLF|
|K1|1|Relay_SPST-NO|TRS80_Model_I_Relay_NO|Relay SPST, Normally Open, EN50005|Slightly smaller than original|14.84|14.84|DigiKey|https://www.digikey.com/en/products/detail/sensata-cynergy3/S2-05P/4425813|
|Q1|1|2N3904|2N3904|0.2A Ic, 40V Vce, Small Signal NPN Transistor, TO-92||0.35|0.35|Mouser|https://www.mouser.com/ProductDetail/512-2N3904BU|
|Q2, Q5|2|2N3906|2N3906|-0.2A Ic, -40V Vce, Small Signal PNP Transistor, TO-92||0.28|0.56|Mouser|https://www.mouser.com/ProductDetail/512-2N3906BU|
|Q3|1|TIP29A|Q_NPN_BCE|NPN transistor, base/collector/emitter||1.01|1.01|Mouser|https://www.mouser.com/ProductDetail/863-TIP29AG|
|Q4|1|2N6594|Q_PNP_BEC|PNP transistor, base/emitter/collector|Replacement (Other: RS2040)|4.95|4.95|Jameco|https://www.jameco.com/z/2N6287-STMicroelectronics-Bipolar-Darlington-Transistor-PNP-BJT-100V-20A-160W-TO-3_2280119.html|
|Q6|1|MJE34|Q_PNP_BCE|PNP transistor, base/collector/emitter|Replacement|0.67|0.67|Mouser|https://www.mouser.com/ProductDetail/511-TIP32C|
|-|1|||Q4 Heatsink||1.01|1.01|Mouser|https://www.mouser.com/ProductDetail/532-506007B00|
|-|1|||Q6 Heatsink|Smaller than original|0.3|0.3|Mouser|https://www.mouser.com/ProductDetail/532-507302B00|
|R1|1|68|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-68R|
|R2|1|2.7k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JR-522K7|
|R3|1|750|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-750R|
|R4|1|0.33|R|Resistor 2W||0.45|0.45|Mouser|https://www.mouser.com/ProductDetail/603-CFR2WSJT-73-0R33|
|R5, R10|2|1k|R_Potentiometer|Potentiometer||0.57|1.14|Mouser|https://www.mouser.com/ProductDetail/531-PT10H-1K-S|
|R6, R7, R16, R53|4|1.2k|R|Resistor 0.25W||0.1|0.4|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-1K2|
|R8|1|100k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-100K|
|R9, R11, R12|3|3.3k|R|Resistor 0.25W||0.1|0.3|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-3K3|
|R13|1|2.2k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JT-52-2K2|
|R14|1|12k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-12K|
|R15|1|1.5k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JT-52-1K5|
|R17|1|2k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-2K|
|R18|1|5.6|R|Resistor 3W||0.57|0.57|Mouser|https://www.mouser.com/ProductDetail/279-EP3WSS5R6J|
|R19, C_R67|2|220|R|Resistor 0.5W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-50JB-52-220R|
|R20, R21|2|100k|R_Potentiometer|Potentiometer||0.57|1.14|Mouser|https://www.mouser.com/ProductDetail/531-PT10H-100K-S|
|R22|1|75|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-75R|
|R23|1|120|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-120R|
|R24|1|680k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-680K|
|R25|1|1.6M|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-1M6|
|R26, R42|2|1M|R|Resistor 0.25W||0.1|0.2|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JT-52-1M|
|R27, R64|2|330|R|Resistor 0.25W||0.1|0.2|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-330R|
|R28|1|270|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-270R|
|R29|1|1.8k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-1K8|
|R30|1|47|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-47R|
|R31|1|10|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JT-52-10R|
|R32, R43, R44, R47, R65|5|10k|R|Resistor 0.25W||0.1|0.5|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-10K|
|R33, R36|2|360k|R|Resistor 0.25W||0.1|0.2|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-360K|
|R34, R35, R38, R41, R45|5|470k|R|Resistor 0.25W||0.1|0.5|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-470K|
|R37|1|560k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-560K|
|R39, R40, R48, R49, R50, R51, R57, R58, R59, R60, R61, R62, R63, R66, R67, R68, R69|17|4.7k|R|Resistor 0.25W||0.1|1.7|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-4K7|
|R46, R52|2|910|R|Resistor 0.25W||0.1|0.2|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-910R|
|R54, R55|2|7.5k|R|Resistor 0.25W||0.1|0.2|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-7K5|
|R56|1|220k|R|Resistor 0.25W||0.1|0.1|Mouser|https://www.mouser.com/ProductDetail/603-CFR-25JB-52-220K|
|S1|1|Power|SW_4PST||No Cap|4.34|4.34|DigiKey|https://www.digikey.com/en/products/detail/c-k/F4UEE/417520|
|S2|1|Reset|SW_DPST||Red Cap|1.815|1.815|AliExpress|https://www.aliexpress.us/item/3256804467086494.html|
|Y1|1|10.6445 MHz|Crystal|Two pin crystal|Only 10.6MHz|0.73|0.73|Mouser|https://www.mouser.com/ProductDetail/449-LFXTAL028537BULK|
|Z1, Z2|2|LM723C|LM723C_1|Linear Regulator (adjustable)||1.04|2.08|Mouser|https://www.mouser.com/ProductDetail/595-UA723CN|
|Z3, Z71|2|Jumper|TRS80ModelIX71|8-Bit DIP Switch|Replacement|2.07|4.14|Mouser|https://www.mouser.com/ProductDetail/710-418117270908|
|Z4|1|LM3900|LM3900|Quad operational amplifier||0.6|0.6|Mouser|https://www.mouser.com/ProductDetail/595-LM3900NE4|
|Z5|1|74C00|74LS00|quad 2-input NAND gate||0.62|0.62|Mouser|https://www.mouser.com/ProductDetail/595-CD74HC00E|
|Z6, Z57|2|74C04|74LS04|Hex Inverter||0.47|0.94|Mouser|https://www.mouser.com/ProductDetail/595-SN74HC04AN|
|Z7, Z69, Z70|3|74LS74|74LS74|Dual D Flip-flop, Set & Reset||0.49|1.47|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS74AN|
|Z8|1|74LS153|74LS153|Dual Multiplexer 4 to 1||1.13|1.13|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS153N|
|Z9, Z42, Z52|3|74LS04|74LS04|Hex Inverter||0.67|2.01|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS04N|
|Z10, Z11|2|74LS166|74LS166|Shift Register 8-bit, parallel load||1.24|2.48|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS166AN|
|Z12, Z32, Z50, Z65|4|74LS93|74LS93|Divide by 2 & 8 counter||3.04|12.16|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS93N|
|Z13, Z14, Z15, Z16, Z17, Z18, Z19, Z20|8|MK4116|4116|16kBit x 1 Bit Dynamic RAM||3.95|31.6|Jameco|https://www.jameco.com/z/4116-15-Major-Brands-IC-4116-15-DRAM-16-384-Bit-16Kx1-150ns-5V_41339.html|
|Z21|1|74LS156|74LS156|Dual 2 to 4 lines Decoder/Demultiplexer, Open Collector||0.75|0.75|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS156N|
|Z22, Z38, Z39, Z44, Z55, Z60, Z67, Z68, Z72, Z75, Z76|11|74LS367|74LS367_Split|Hex buffer 3-State outputs||1.44|15.84|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS367AN|
|Z23, Z25, Z36, Z73|4|74LS32|74LS32|Quad 2-input OR||0.56|2.24|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS32N|
|Z24, Z53|2|74LS132|74LS132|Quad 2-input NAND Schmitt trigger||1.03|2.06|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS132N|
|Z26|1|74LS20|74LS20|Dual 4-input NAND||1.28|1.28|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS20N|
|Z27, Z59|2|74LS175|74LS175|4-bit D Flip-Flop, reset||1.02|2.04|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS175N|
|Z28|1|74LS174|74LS174|Hex D-type Flip-Flop, reset||1.12|1.12|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS174N|
|Z29|1|MCM6670|MCM6670P|128 x 7 x 5 Character Generator|Adapter needed||0|-|-|
|Z30, Z37|2|74LS02|74LS02|quad 2-input NOR gate||0.55|1.1|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS02N|
|Z31, Z35, Z43, Z49, Z51, Z64|6|74LS157|74LS157|Quad 2 to 1 line Multiplexer||0.88|5.28|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS157N|
|Z33|1|2364_20L|2364_20L|2364 64kBit (8kb x 8) PROM|Adapter needed||0|-|-|
|Z34|1|2332_20L_21L|2332_20L_21L|2332 32kBit (4kb x 8) PROM|Adapter needed||0|-|-|
|Z40|1|Z80CPU|Z80|Z80 CPU||9.62|9.62|Mouser|https://www.mouser.com/ProductDetail/692-Z84C0010PEG|
|Z41|1|75452|75452|Dual-Peripheral Drivers for High-Current, High-Speed Switching||0.9|0.9|Mouser|https://www.mouser.com/ProductDetail/595-SN75452BP|
|Z45, Z46, Z47, Z48, Z61, Z62, Z63|7|2102|2102_1|1K Static RAM (SRAM)||2.95|20.65|Jameco|https://www.jameco.com/z/MM2102AN-4-National-Semiconductor-IC-MM2102AN-4-NMOS-SRAM-1024-Bit-1024x1-250ns-DIP-16_2287991.html|
|Z54|1|74LS30|74LS30|8-input NAND||1.18|1.18|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS30N|
|Z56, Z58|2|74LS92|74LS92|Divide by 12 counter||3.27|6.54|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS92N|
|Z66|1|74LS11|74LS11|Triple 3-input AND||0.91|0.91|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS11N|
|Z74|1|74LS00|74LS00|quad 2-input NAND gate||0.57|0.57|Mouser|https://www.mouser.com/ProductDetail/595-SN74LS00N|
|-|30|DIP-14|DIP-14|DIP-14 Socket|Optional|0.75|22.5|Jameco|https://www.jameco.com/z/14MTLP-Jameco-ValuePro-Socket-IC-14-Pin-Machine-Tooled-Low-Profile-0-3-Inch-Wide_37197.html|
|-|39|DIP-16|DIP-16|DIP-16 Socket|Optional|0.85|33.15|Jameco|https://www.jameco.com/z/16MTLP-Jameco-ValuePro-Socket-IC-16-Pin-Machine-Tooled-Low-Profile-0-3-Inch-Wide_37402.html|
|-|1|DIP-18|DIP-18|DIP-18 Socket|Optional|0.99|0.99|Jameco|https://www.jameco.com/z/18MTLP-Jameco-ValuePro-18-Pin-Machine-Tooled-Low-Profile-IC-Socket-0-3-Inch-Wide_65585.html|
|-|1|DIP-40|DIP-40|DIP-40 Socket|Optional|1.69|1.69|Jameco|https://www.jameco.com/z/40MTLP-Jameco-ValuePro-40-Pin-Machine-Tooled-Low-Profile-IC-Socket-0-6-Inch-Wide_41136.html|
|-|1|DIP-8|DIP-8|DIP-8 Socket|Optional||0|-|-|
|-|2|DIP-24|DIP-24|DIP-24 Socket|Optional|1.49|2.98|Jameco|https://www.jameco.com/z/24MTLP-6-Jameco-ValuePro-24-Pin-Machine-Tooled-Low-Profile-IC-Socket-0-6-Inch-Wide_39351.html|

### Implementation

E1 has been implemented using KiCAD 7. The KiCAD project files are included in this repository.

![E1 Replica Front](/Latest/TRS80_Model_I_G_E1_3D_Front.png)
![E1 Replica Back](/Latest/TRS80_Model_I_G_E1_3D_Back.png)

### RetroStack Libraries

To work with this KiCAD project, you'll need the RetroStack libraries for KiCAD. Please [follow this link](https://www.github.com/RetroStack/KiCAD-Libraries) to access and install these libraries.

## Curiosities

The original board had multiple errors and strange implementations, often caused by the limited capabilities of the manufacturing process, but also to save money. The following sections discuss some of the stranger features on the original PCB board, which were replicated when possible.

### Additional Capacitor

![Additional Capacitor](/Images/Curiosities/AdditionalC58.png)

Capacitor C58, located next to the ROMs, was never documented in the technical reference manual. My guess is that it was added later.

### Missing Capacitor

![Missing Capacitor](/Images/Curiosities/MissingC58.png)
![From Original Schematics](/Images/Curiosities/MissingC58Schema.png)

There is, however, a capacitor missing on the board. This capacitor is also called C58 (yes, there are two of them) and is located right next to the relay. It is missing on all the boards I've seen, but I have added it to the schematics and included a note that it is missing on the PCB. This capacitor is actually part of the Cassette Remote control circuit and seems out of place there.

### Wrong Resistor

![Wrong Resistor](/Images/Curiosities/WrongResistor.png)
![From Original Schematics](/Images/Curiosities/WrongResistorSchema.png)

Next to the two potentiometers for the H- and V-Sync, there is supposed to be a 100 Ohm 0.25 Watt resistor, according to the technical documentation. However, on all the boards I have seen, there is actually a 220 Ohm 0.5 Watt resistor instead.

### Undocumented 8k RAM support

The board actually supports two different kinds of 8k ICs for the dynamic RAM. This is not documented in the technical reference manual or the user documentation. See Page 7 of the [new schematics](/Latest/TRS80_Model_I_G_E1_Schematics.pdf).

### Missing Pads (On the Top)

![Missing Pads on Original](/Images/Curiosities/MissingPadsTop.png)
![Missing Pads on Replica](/Images/Curiosities/MissingPadsTopE1.png)

I’ve replicated the "missing pads" on the top of the board as they were on the original board. The pads are only connected at the bottom, so it's fine for them to be missing on the top.

But why was it done this way? At the time, the solder masks weren’t as precise and couldn't adequately cover the traces between pads (see purple/magenta and blue arrow). Bridging those pads and traces during soldering was (and still is) a common issue on these older boards (especially the traces or purple/magenta arrow). That isn’t the case with modern boards, but I still replicated this for the pads only (not the traces in between) to stay closer to the original without the risk of accidental bridging. I guess it's a good compromise.

Completely unconnected pins usually lacked pads on the top as well, but KiCAD doesn’t have an option for that, unfortunately. So, I kept them as they are (see orange arrow), meaning they have pads on both the top and bottom.

The yellow arrow is unrelated to this topic, but you can see the cut trace of the original board which is needed for the lower-case mod.

### Missing Pads (On the Bottom)

![Missing Pads on Original](/Images/Curiosities/MissingPadsBottom.png)
![Missing Pads on Replica](/Images/Curiosities/MissingPadsBottomE1.png)

I replicated three missing pads on the bottom of the board at Z69. While accurate to the original, it was a pain to solder the sockets to the pads while they rested on top of the board. I don’t use wave soldering as they did in the original, so that was just annoying. In the newest version of the board, I placed these pads back to make them easily solderable.

### Unused Vias

![Unconnected Vias](/Images/Curiosities/UnconnectedVias.png)

There are a bunch of unused vias on the board. I am not entirely sure why that is.

### Small Holes

![Mounting Holes](/Images/Curiosities/MountingHoles.png)

At the edges of the board, you can see two rather small holes. These were used during the manufacturing process to keep the board in a known position, enabling the machines to create and assemble the board.

### Bumpy Traces and Zones

![Bumpy Traces and Zones](/Images/Curiosities/BumpyTracesZones.png)

If you ever wonder what these "bumpy" traces and fill zones are, they are not dissolving or anything of that nature. This is how they are supposed to be. The boards were assembled in this way. The traces and zones were tinned, then solder mask was applied, covering nearly everything. When the board was wave soldered with the components in place, these tinned traces melted again due to the heat and solidified shortly after. The tension of the solder mask kept them in somewhat random shapes and caused these bumps. You can actually see this if you put your soldering iron to a pad close to these bumps; you will see that the tin beneath the solder mask liquifies and can even be sucked out by a desoldering iron or pump.

Since the method of tinning has changed (using HASL nowadays) and I don't wave solder, this isn't happening anymore, and it is difficult and probably costly to replicate.

## Main TRS-80 Model 1 Repository

For additional resources related to the TRS-80 Model 1, be sure to check out the [central page for the TRS-80 Model 1](https://www.github.com/RetroStack/TRS-80-Model-I) on RetroStack.

## Support this Project

RetroStack is passionate about exploring and preserving the legacy of older computer systems. My work involves creating detailed documentation and videos to share the knowledge. I am also dedicated to reviving these classic systems by reimplementing them and offering replacement parts at no cost. If you're keen on supporting this unique project, I invite you to visit my [Patreon page](https://www.patreon.com/RetroStack). Your support would be immensely valuable and greatly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
