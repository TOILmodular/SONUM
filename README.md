# SONUM - A CV-Controlled Fixed Filter Bank Eurorack Module
This Eurorack module SONUM is a fixed filter bank with a low-pass, a high-pass, and 12 band-pass filters.
The core part of the module is based on the [Fixed Filter Bank FFB from Yusynth](http://yusynth.net/Modular/EN/BANK/index.html), inspired by the Moog 914 module.
But there are a few crucial differences.

While the frequencies in the Yusynth module are basically multiples (octaves) of two notes, there is a "retuned" version published by Rich Holmes with alternative frequencies avoiding octave separations. 
Rich explained the intention of these different frequencies in a [YouTube video on his channel "Analog Output"](https://www.youtube.com/watch?v=-yv34qV_Hrs).
My module makes use of the Analog Output design for the 14 fixed filters.

There are two additional features, which are not present in the Yusynth and Analog Output designs.
The SONUM module provides CV inputs for the volume of the 12 band-pass filters, as well as a feedback loop of the output signal back into the module input.

Features:
- 14 filter bands - 12 band-pass, a low-pass, and a high-pass - with attenuators
- 2 input channels with attenuators, normalled to each other
- Volume CV inputs for each of the 12 band-pass filters - attenuators serve as VCA bias
- A feedback loop with attenuator into both input channels with the feedback source selectable via a switch either from the odd or the even filter outputs
- 3 outputs - odd, even, or all filter channels

A demo of the module is available on YouTube.

[<img width="500" src="https://github.com/user-attachments/assets/514c045f-fd39-4608-8385-e16976552af9">](xxx)

## Module Build and PCBs
I added two different versions for the control board in the folder GerberFiles, an "original", and a "Thonk" version.
Reason is that for my own module, I am using specific potentiometers - 16K4 series from Supertech Electronics - and 3.5mm jack sockets - MJ-355 from Marushin - available at my local electronics shop.

<img width="500" alt="CtrlPCB Orig" src="https://github.com/user-attachments/assets/dcea06fe-0c9f-405c-b04a-e31d39cfe052">

However, since most DIY projects for Eurorack modules out there are using potentiometers from ALPHA and so-called THONKICONN jacks, as they are provided by Thonk in the UK, I also created another control board PCB for the "Thonk" version with footprints for those components.

<img width="500" alt="CtrlPCB Thonk" src="https://github.com/user-attachments/assets/6eac2def-754e-417b-9de5-e9c6fca10dd0">

The main PCB is the same for both versions.

<img width="500" alt="MainPCB" src="https://github.com/user-attachments/assets/33049696-c70d-47c7-95bd-43289a57eca3">

I created the Gerber files with the online tool EasyEDA and ordered the PCBs at JLCPCB.

## Additional Information about specific Components
Due to the high number of components for all of the filter bands and VCAs, I decided to use the SMD version for all of the op amps on the boards.
In addition, there are a number of SMD bypass capacitors with the package size 1608 (imperial 0603).
Other components - resistors, other capacitors, diodes, quad VCA ICs - are through-hole.
That enabled me to keep the module size within 28HP.

Concerning the resistor size, I am usually using small-size resistors, about half the length of the usual size, so they need less space on the PCB. If you want to use my Gerber files, you have to consider that fact. You might still use normal size resistors and put them in a standing position on the boards. Should also work fine.

On the control board, you will find 2 electrolytic capacitors with a rectangle next to them. Since these capacitors are too tall for standing upright on the board with the main board on top of it, those capacitors need to be mounted in a rectangular position. The rectangle shows the position for each bent-over capacitor.

## Component Labeling on PCBs
Usually, I prefer labeling components with their values on the PCBs. So I do not have to switch between BOM, schematic, and PCB while selecting parts in the soldering process.

However, due to the huge number of components  for this module (235 resistors, 187 capacitors, 29 op amps...), the space on the main PCB is not sufficient to print all capacitor and resistor values.
So I decided to label them with the component numbers given in the schematic.
Those numbers are also listed in the BOM. The resistor numbers in the BOM and schematic have the prefix R, while there is just the number printed on the PCBs.

My suggestion is to have the BOM displayed or printed out, when soldering the boards. So you can process all components for a specific value by checking the component numbers and searching the locations on the board.
