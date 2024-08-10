# TRS-80 Model 1 (Rev G) Replica - E1

This project is a faithful reimplementation of the mainboard of the iconic TRS-80 Model 1 (Revision G) computer. My own revision, the E1, is designed to replicate the original system's functionality by using a PCB design 1-to-1 to the original, including components, interfaces, and even traces. The entire project is available under the MIT license.

![E1 Replica](/Latest/TRS80_Model_I_G_E1_Photo.png)

## Project Details

### Latest Files

In the "Latest" folder, you'll find the most up-to-date design files, including:

- Gerber files suitable for popular online PCB manufacturers like [PCBWay](/Latest/TRS80_Model_I_G_E1_Gerber_PCBWAY.zip) and [JLCPCB](/Latest/TRS80_Model_I_G_E1_Gerber_JLCPCB.zip). Most manufacturers should be fine with either.
- A Bill of Materials (BOM) in both [CSV](/Latest/TRS80_Model_I_G_E1_BOM.csv) and [PDF](/Latest/TRS80_Model_I_G_E1_BOM.pdf) formats. (Also, see the list below.)
- Layers exported in PDF and SVG formats.
- If you have trouble identifying components, refer to the [labels SVG](/Latest/TRS80_Model_I_G_E1_Labels.svg).
- The [full schematics](/Latest/TRS80_Model_I_G_E1_Schematics.pdf) of the E1 replica which is 1:1 to the original G board.
- A simple [Assembly Guide](/Latest/TRS80_Model_I_G_E1_AssemblyGuide.pdf) in PDF format.

### Implementation

E1 has been implemented using KiCAD 7. The KiCAD project files are included in this repository.

![E1 Replica Front](/Latest/TRS80_Model_I_G_E1_3D_Front.png)
![E1 Replica Back](/Latest/TRS80_Model_I_G_E1_3D_Back.png)

### Assembly Instructions

For each step, check if there is a connection between pad 1, 8, 9, 16 on Z18 (all four corners of the dynamic RAM IC). That IC needs all 3 voltages with ground. If any of them are shorted, then you know what you did most recently. Finding the cause of the short should then be relatively easy.

1) (optional) Install sockets for all ICs. You probably want to skip Z3 and Z71, if you want to use DIP switches instead.
2) Install all diodes. These diodes are hard to read and if you accidentally mix them up, you might end up with incorrect voltages on the rails. Also, make sure to orient them correctly. There should be a black band on one side of the glass diode. Match this with the "thicker" side of the diode on the PCB. Installing first the shorter components will make sure you still can flip the board around and solder things easily.
3) Install all resistors. Resistors do not have an orientation. Skip the potentiometers for now. When installing the C_R67 (yes, there is a "C_"), this is an unmarked resistor between relay and the R21 potentiometer. This should be a 220 ohm 0.5W resistor (a bit larger than the others). There is another R67 which is next to Z42, which is a 4.7k Ohm resistor 0.25W (same size as most of the others).
4) Install all disc-like capacitors. Do not install the electrolytic capacitors yet! All other capacitors are rather small and orientation isn't important. The C58 next to the relay stays empty. Do not install it there. Instead, there is another (!!!) C58 next to the ROMs in the middle of the PCB.
5) Install all transistors, including the ones with the heatsinks. The TIP29 should go into Q3 (metal side away from board towards the Q3 label) while the TIP32C should go into Q6 (lay flat with heatsink; bend legs wit needle-nose pliers to fit). Don't forget to add thermal paste between heatsink and transistors. Make sure to add the screws and nuts and that it fits tightly as the screws themself connect traces. Not having them properly installed will result in a non-functioning system. The smaller black transistors have one flat side. These should all face towards the bottom of the board towards all the ICs (the middle leg needs to be bend slightly out to fit). 
6) Install the crystal (no orientation), relay (match orientation on PCB; three legs towards the bottom), full-bridge rectifier (CR8; match "+" marking on component with PCB marking), all DIN connectors, both switches, keyboard connector (if bend, bend it upwards - towards the CPU to fit in the case), and potentiometers (only goes in one way). You can also install the DIP switches, if you go with that (numbers on the left side and "ON" label on the right).
7) Install all electrolytic capacitors. Make sure the orientation is correct! Modern capacitors mark the "-" side. On the PCB, the positive side is marked. All electrolytic capacitors on the PCB are oriented the same way EXCEPT C42 (!!!). Incorrect orientation may result in a small explosion (loud and smokey, but probably not dangerous).
8) Only install Z1 & Z2 to calibrate the power supply. Don't install any of the other ICs yet!!!
9) Get Multimeter ready in voltage mode. Connect power, turn on S1. If something starts to smell burned, turn S1 off and disconnect power.
10) Check voltage between pad 1 (-5V) and pad 16 (GND) on Z18. It should be around -5.1V to -5.2V. Since this is clamped with a zener diode, this should be pretty accurate. There is nothing that needs to be calibrated here. If the voltage goes beyond -5.3V, check R19 (may be really hot! careful!). If R19 is hot to the touch, your power supply is probably broken. (I've seen this on one power supply while another one didn't have that problem.) 
11) Check voltage between pad 8 (+12V) and pad 16 (GND) on Z18. It should be around +12.0V. If it isn't, change the R10 potentiometer. If it is +/-0.5V off, then this is fine. But, try to get it as close to the desired voltage as possible.
12) (You need to calibrate +12V first before going to this next step!!!) Check voltage between pad 9 (+5V) and pad 16 (GND) on Z18. It should be around +5.0V. If it isn't, change the R5 potentiometer. If it is +/-0.5V off, then this is fine. But, also here, try to get it close to the desired voltage.
13) Re-check all the voltages after calibration, just to be sure.
14) Turn off S1 and disconnect power. Do this for each of the following steps. After each change, re-check the voltages at Z18 to find shorts quickly.
15) Start inserting the ICs. Focus on the 74LSxx ICs first. They are cheap and are easily recoverable in case there is a short somewhere and you start frying ICs. May be do 2-4 chips at a time and re-check the voltages at Z18. Do this systematically from left to right and top to bottom, so you know which you inserted most recently. If one of the voltages changes significantly at Z18 (+/- 2V and more), then you probably have a short with the most recent ICs. Do not insert the CPU, ROMs, character generator, and RAMs (static (2102) and dynamic ones (4116)) for now. They are expensive to replace if they fry.
16) Insert the 74Cxx ICs. These ICs are also cheap, but they are very sensitive. If all voltages are good, then they are good to install. 
17) Connect to a monitor. Use a CRT, if possible, as video calibration is easier. LCD works too, but the reaction time is slow and requires a longer wait time after each change.
18) After turning on monitor and S1, you should see white blocks on a black background. If you don't see it, try changing R20 (vertical sync) and R21 (horizontal sync). If all fails, try to center both potentiometer. This usually results in a non-optimal picture, but a picture non-the-less. You can then calibrate.
19) (Don't forget to turn off system!) Insert the static video RAM (2102). These ICs only require +5V.
20) Now you need to configure the memory addresses and the memory configuration. With DIP switches, configure as follows:
  - (memory location configuration) Z3: Switch 1 to the left, while all others are to the right. This is the configuration for 12k ROM and 16k RAM.
  - (memory type configuration) Z71: Switch 1, 3, 5 to the right while all others are to the left. This is the configuration for 16k RAM modules.
21) Insert the dynamic RAM (4116). These ICs require all three voltages.
22) Insert CPU. Not much should have changed from the video calibration up until now. The next step will change that.
23) Insert character generator. Instead of white blocks, you should see (random) characters. The system doesn't clear the video memory yet since no ROM is installed.
24) Install ROM. This should be a Level II v1.3. If you don't have this, you probably need additional circuity to make these work. You can also burn the [diag ROM](https://github.com/misterblack1/trs80-diagnosticrom/blob/main/trs80m13diag.bin) on a 2k ROM to test the system. The diag ROM should work for all revisions of the TRS-80 Model 1.
25) At this point, you should see a prompt showing "Memory Size?" that keeps blinking (if it is the normal system ROM). The reason for the blinking is that the keyboard is not yet connected and the system recognizes keypresses. Install the keyboard with the IDC cable (if you installed a header).
26) Now, you should be able to use the system. Try to hold the left SHIFT key and press the right arrow key and the text size should increase, switching the video modes. (It is OK when some characters are skipped. That is normal.) The CLEAR key should reset it to the original video mode and clear the screen.
27) Try running a "Hello World!" program: 10 PRINT "Hello World!" (Return) 20 GOTO 10 (Return) RUN (Return). You can stop with the BREAK key.

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

Below is a list of materials needed to assemble a complete system. Please note that the links and prices (scroll to the right to see them; as of January 22, 2024) will not be updated in the future and should only be used as a reference for locating the correct items.

Note: Links and alternatives are provided to assist you in finding the necessary components. I cannot guarantee the complete accuracy or reliability of all these links and alternatives. Please check it for yourself!

|Reference|Qty|Description|Source Comment|Source Cost USD|Source Total Cost USD|Source|
|-|-|-|-|-|-|-|
|C1|1|220uF 16V polarized capacitor||1.48|1.48|[Mouser](https://www.mouser.com/ProductDetail/598-227TTA050M)|
|C2, C4, C5, C10, C11, C57|6|10uF 16V polarized capacitor||0.29|1.74|[Mouser](https://www.mouser.com/ProductDetail/598-106RMR050M)|
|C3, C7, C14, C15|4|0.01uF 24V (103) capacitor||0.23|0.92|[Mouser](https://www.mouser.com/ProductDetail/594-D103Z25Z5VF63L6R)|
|C6|1|100uF 16V polarized capacitor||0.37|0.37|[Mouser](https://www.mouser.com/ProductDetail/647-UVZ1J101MPD)|
|C8|1|2200uF 35V polarized capacitor||5.31|5.31|[Mouser](https://www.mouser.com/ProductDetail/598-228TTA063M)|
|C9|1|10000uF 16V polarized capacitor||7.87|7.87|[Mouser](https://www.mouser.com/ProductDetail/598-109TTA025M)|
|C12, C13|2|470pF (471) capacitor||0.23|0.46|[Mouser](https://www.mouser.com/ProductDetail/594-D471K20Y5PH6UJ5R)|
|C16, C17, C18, C19, C22, C23, C28, C29, C30, C31, C32, C33, C34, C35, C36, C37, C38, C39, C40, C41, C44, C45, C46, C47, C48, C49, C50, C51, C52, C53, C54, C55, C56, C58|34|0.1uF 25V (104) capacitor||0.17|5.78|[Mouser](https://www.mouser.com/ProductDetail/594-K104K10X7RF53L2)|
|C20|1|330pF (331) capacitor||0.3|0.3|[Mouser](https://www.mouser.com/ProductDetail/594-F331K29Y5RP6UK5R)|
|C21|1|750pF (750) capacitor||0.37|0.37|[Mouser](https://www.mouser.com/ProductDetail/80-C322C751K3G5TA)|
|C24, C25|2|220pF (221) capacitor||0.23|0.46|[Mouser](https://www.mouser.com/ProductDetail/594-D221K20Y5PF63J5R)|
|C26|1|0.047uF (47nF) capacitor||1.9|1.9|[Mouser](https://www.mouser.com/ProductDetail/594-222236755473)|
|C27|1|0.022uF (22nF) capacitor||1.34|1.34|[Mouser](https://www.mouser.com/ProductDetail/594-2222-366-45223)|
|C42|1|22uF 16V polarized capacitor||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/710-860010372002)|
|C43|1|47pF (47) capacitor||0.4|0.4|[Mouser](https://www.mouser.com/ProductDetail/594-S470K25SL0N63L6R)|
|CR1|1|1N4735 Zener diode||0.25|0.25|[Mouser](https://www.mouser.com/ProductDetail/512-1N4735A)|
|CR2|1|1N5231 Zener diode||0.15|0.15|[Mouser](https://www.mouser.com/ProductDetail/512-1N5231B)|
|CR3, CR4, CR5, CR6, CR7|5|1N4148|Diode|0.1|0.5|[Mouser](https://www.mouser.com/ProductDetail/512-1N4148)|
|CR8|1|MDA202 Diode bridge, +ve/AC/AC/-ve|Replacement|0.61|0.61|[Mouser](https://www.mouser.com/ProductDetail/621-KBP210G)|
|CR9, CR10|2|1N982 Schottky diode|Replacement, Lower (39V instead of 75V)|0.26|0.52|[Mouser](https://www.mouser.com/ProductDetail/78-1N4754A-TAP)|
|J1, J2, J3|3|5-pin DIN connector (5-pin DIN-5 stereo)|For metal connector only. The plastic plugs don't fit in it.|0.386|1.158|[AliExpress](https://www.aliexpress.us/item/2255801077942335.html)|
|J100|1|01x20 Generic connector, single row, 01x20||0.5|0.5|[Mouser](https://www.mouser.com/ProductDetail/649-1012937992002BLF)|
|K1|1|Relay SPST, Normally Open|Slightly smaller than original|14.84|14.84|[DigiKey](https://www.digikey.com/en/products/detail/sensata-cynergy3/S2-05P/4425813)|
|Q1|1|2N3904 0.2A Ic, 40V Vce, Small Signal NPN Transistor, TO-92||0.35|0.35|[Mouser](https://www.mouser.com/ProductDetail/512-2N3904BU)|
|Q2, Q5|2|2N3906 -0.2A Ic, -40V Vce, Small Signal PNP Transistor, TO-92||0.28|0.56|[Mouser](https://www.mouser.com/ProductDetail/512-2N3906BU)|
|Q3|1|TIP29A (BCE) NPN transistor||1.01|1.01|[Mouser](https://www.mouser.com/ProductDetail/863-TIP29AG)|
|Q4|1|2N6594 (BEC) PNP transistor|Replacement (Other: RS2040, MJ2955G)|4.73|4.73|[Mouser](https://www.mouser.com/ProductDetail/863-MJ2955G)|
|Q6|1|MJE34 (BCE) PNP transistor|Replacement|0.67|0.67|[Mouser](https://www.mouser.com/ProductDetail/511-TIP32C)|
|-|1|Q4 Heatsink||1.01|1.01|[Mouser](https://www.mouser.com/ProductDetail/532-506007B00)|
|-|1|Q6 Heatsink|Smaller than original|0.3|0.3|[Mouser](https://www.mouser.com/ProductDetail/532-507302B00)|
|R1|1|68 Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-68R)|
|R2|1|2.7k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JR-522K7)|
|R3|1|750 Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-750R)|
|R4|1|0.33 Resistor 2W||0.45|0.45|[Mouser](https://www.mouser.com/ProductDetail/603-CFR2WSJT-73-0R33)|
|R5, R10|2|1k Potentiometer||0.57|1.14|[Mouser](https://www.mouser.com/ProductDetail/531-PT10H-1K-S)|
|R6, R7, R16, R53|4|1.2k Resistor 0.25W||0.1|0.4|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-1K2)|
|R8|1|100k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-100K)|
|R9, R11, R12|3|3.3k Resistor 0.25W||0.1|0.3|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-3K3)|
|R13|1|2.2k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JT-52-2K2)|
|R14|1|12k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-12K)|
|R15|1|1.5k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JT-52-1K5)|
|R17|1|2k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-2K)|
|R18|1|5.6 Resistor 3W||0.57|0.57|[Mouser](https://www.mouser.com/ProductDetail/279-EP3WSS5R6J)|
|R19, C_R67|2|220 Resistor 0.5W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-50JB-52-220R)|
|R20, R21|2|100k Potentiometer||0.57|1.14|[Mouser](https://www.mouser.com/ProductDetail/531-PT10H-100K-S)|
|R22|1|75 Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-75R)|
|R23|1|120 Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-120R)|
|R24|1|680k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-680K)|
|R25|1|1.6M Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-1M6)|
|R26, R42|2|1M Resistor 0.25W||0.1|0.2|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JT-52-1M)|
|R27, R64|2|330 Resistor 0.25W||0.1|0.2|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-330R)|
|R28|1|270 Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-270R)|
|R29|1|1.8k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-1K8)|
|R30|1|47 Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-47R)|
|R31|1|10 Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JT-52-10R)|
|R32, R43, R44, R47, R65|5|10k Resistor 0.25W||0.1|0.5|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-10K)|
|R33, R36|2|360k Resistor 0.25W||0.1|0.2|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-360K)|
|R34, R35, R38, R41, R45|5|470k Resistor 0.25W||0.1|0.5|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-470K)|
|R37|1|560k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-560K)|
|R39, R40, R48, R49, R50, R51, R57, R58, R59, R60, R61, R62, R63, R66, R67, R68, R69|17|4.7k Resistor 0.25W||0.1|1.7|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-4K7)|
|R46, R52|2|910 Resistor 0.25W||0.1|0.2|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-910R)|
|R54, R55|2|7.5k Resistor 0.25W||0.1|0.2|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-7K5)|
|R56|1|220k Resistor 0.25W||0.1|0.1|[Mouser](https://www.mouser.com/ProductDetail/603-CFR-25JB-52-220K)|
|S1|1|Power 4PST|No Cap|4.34|4.34|[DigiKey](https://www.digikey.com/en/products/detail/c-k/F4UEE/417520)|
|S2|1|Reset DPST|Red Cap|1.815|1.815|[AliExpress](https://www.aliexpress.us/item/3256804467086494.html)|
|Y1|1|10.6445 MHz Two pin crystal|Only 10.6MHz|0.73|0.73|[Mouser](https://www.mouser.com/ProductDetail/449-LFXTAL028537BULK)|
|Z1, Z2|2|LM723C Linear Regulator (adjustable)||1.04|2.08|[Mouser](https://www.mouser.com/ProductDetail/595-UA723CN)|
|Z3, Z71|2|8-Bit DIP Switch|Replacement|2.07|4.14|[Mouser](https://www.mouser.com/ProductDetail/710-418117270908)|
|Z4|1|LM3900 Quad operational amplifier||0.6|0.6|[Mouser](https://www.mouser.com/ProductDetail/595-LM3900NE4)|
|Z5|1|74C00 quad 2-input NAND gate|74HC00 works in a pinch, but suboptimal video.|~2.50|~2.50|eBay/Jameco|
|Z6, Z57|2|74C04 Hex Inverter|74HC00 works in a pinch, but suboptimal video.|2.49|4.98|[Jameco](https://www.jameco.com/webapp/wcs/stores/servlet/ProductDisplay?storeId=10001&langId=-1&catalogId=10001&productId=44231)|
|Z7, Z69, Z70|3|74LS74 Dual D Flip-flop, Set & Reset||0.49|1.47|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS74AN)|
|Z8|1|74LS153 Dual Multiplexer 4 to 1||1.13|1.13|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS153N)|
|Z9, Z42, Z52|3|74LS04 Hex Inverter||0.67|2.01|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS04N)|
|Z10, Z11|2|74LS166 Shift Register 8-bit, parallel load||1.24|2.48|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS166AN)|
|Z12, Z32, Z50, Z65|4|74LS93 Divide by 2 & 8 counter||3.04|12.16|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS93N)|
|Z13, Z14, Z15, Z16, Z17, Z18, Z19, Z20|8|4116 16kBit x 1 Bit Dynamic RAM||3.95|31.6|[Jameco](https://www.jameco.com/z/4116-15-Major-Brands-IC-4116-15-DRAM-16-384-Bit-16Kx1-150ns-5V_41339.html)|
|Z21|1|74LS156 Dual 2 to 4 lines Decoder/Demultiplexer, Open Collector||0.75|0.75|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS156N)|
|Z22, Z38, Z39, Z44, Z55, Z60, Z67, Z68, Z72, Z75, Z76|11|74LS367 Hex buffer 3-State outputs||1.44|15.84|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS367AN)|
|Z23, Z25, Z36, Z73|4|74LS32 Quad 2-input OR||0.56|2.24|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS32N)|
|Z24, Z53|2|74LS132 Quad 2-input NAND Schmitt trigger||1.03|2.06|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS132N)|
|Z26|1|74LS20 Dual 4-input NAND||1.28|1.28|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS20N)|
|Z27, Z59|2|74LS175 4-bit D Flip-Flop, reset||1.02|2.04|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS175N)|
|Z28|1|74LS174 Hex D-type Flip-Flop, reset||1.12|1.12|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS174N)|
|Z29|1|MCM6670 128 x 7 x 5 Character Generator|Adapter needed||0|[GitHub](https://github.com/RetroStack/MCM776x_CharGen_Adapter)|
|Z30, Z37|2|74LS02 quad 2-input NOR gate||0.55|1.1|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS02N)|
|Z31, Z35, Z43, Z49, Z51, Z64|6|74LS157 Quad 2 to 1 line Multiplexer||0.88|5.28|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS157N)|
|Z33|1|2364 (20-pin Low) 2364 64kBit (8kb x 8) PROM|Adapter needed||0|-|
|Z34|1|2332 (20- & 21-pin Low) 2332 32kBit (4kb x 8) PROM|Adapter needed||0|-|
|Z40|1|Z80 CPU||9.62|9.62|[Mouser](https://www.mouser.com/ProductDetail/692-Z84C0010PEG)|
|Z41|1|75452 Dual-Peripheral Drivers for High-Current, High-Speed Switching||0.9|0.9|[Mouser](https://www.mouser.com/ProductDetail/595-SN75452BP)|
|Z45, Z46, Z47, Z48, Z61, Z62, Z63|7|2102 1K Static RAM (SRAM)|7th IC needed for lowercase mod|2.95|20.65|[Jameco](https://www.jameco.com/z/MM2102AN-4-National-Semiconductor-IC-MM2102AN-4-NMOS-SRAM-1024-Bit-1024x1-250ns-DIP-16_2287991.html)|
|Z54|1|74LS30 8-input NAND||1.18|1.18|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS30N)|
|Z56, Z58|2|74LS92 Divide by 12 counter||3.27|6.54|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS92N)|
|Z66|1|74LS11 Triple 3-input AND||0.91|0.91|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS11N)|
|Z74|1|74LS00 quad 2-input NAND gate||0.57|0.57|[Mouser](https://www.mouser.com/ProductDetail/595-SN74LS00N)|
||1|DIP-8 Socket|Optional|0.49|0.49|[Jameco](https://www.jameco.com/z/6100-8-R-Jameco-ValuePro-IC-Socket-8-Pin-Machine-Tooled-Low-Profile-0-3-Inch-Wide_51626.html)|
||30|DIP-14 Socket|Optional|0.75|22.5|[Jameco](https://www.jameco.com/z/14MTLP-Jameco-ValuePro-Socket-IC-14-Pin-Machine-Tooled-Low-Profile-0-3-Inch-Wide_37197.html)|
||39|DIP-16 Socket|Optional|0.85|33.15|[Jameco](https://www.jameco.com/z/16MTLP-Jameco-ValuePro-Socket-IC-16-Pin-Machine-Tooled-Low-Profile-0-3-Inch-Wide_37402.html)|
||1|DIP-18 Socket|Optional|0.99|0.99|[Jameco](https://www.jameco.com/z/18MTLP-Jameco-ValuePro-18-Pin-Machine-Tooled-Low-Profile-IC-Socket-0-3-Inch-Wide_65585.html)|
||2|DIP-24 Socket|Optional|1.49|2.98|[Jameco](https://www.jameco.com/z/24MTLP-6-Jameco-ValuePro-24-Pin-Machine-Tooled-Low-Profile-IC-Socket-0-6-Inch-Wide_39351.html)|
||1|DIP-40 Socket|Optional|1.69|1.69|[Jameco](https://www.jameco.com/z/40MTLP-Jameco-ValuePro-40-Pin-Machine-Tooled-Low-Profile-IC-Socket-0-6-Inch-Wide_41136.html)|

### RetroStack Libraries

To work with this KiCAD project, you'll need the RetroStack libraries for KiCAD. Please [follow this link](https://www.github.com/RetroStack/KiCAD-Libraries) to access and install these libraries.

## Main TRS-80 Model 1 Repository

For additional resources related to the TRS-80 Model 1, be sure to check out the [central page for the TRS-80 Model 1](https://www.github.com/RetroStack/TRS-80-Model-I) on [RetroStack](https://www.github.com/RetroStack).

## Support this Project

RetroStack is passionate about exploring and preserving the legacy of older computer systems. My work involves creating detailed documentation and videos to share the knowledge. I am also dedicated to reviving these classic systems by reimplementing them and offering replacement parts at no cost. If you're keen on supporting this unique project, I invite you to visit my [Patreon page](https://www.patreon.com/RetroStack). Your support would be immensely valuable and greatly appreciated!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
