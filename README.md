# SONUM - A CV-Controlled Fixed Filter Bank Eurorack Module
This Eurorack module SONUM is a fixed filter bank with a low-pass, a high-pass, and 12 band-pass filters.
The core part of the module is based on the [Fixed Filter Bank FFB from Yusynth](http://yusynth.net/Modular/EN/BANK/index.html), inspired by the Moog 914 module.
But there are a few crucial differences.

While the frequencies in the Yusynth module are basically multiples (octaves) of two notes, there is a "retuned" version published by Rich Holmes with alternative frequencies avoiding octave separations. 
Rich explained the intention of these different frequencies in a [YouTube video on his channel "Analog Output"](https://www.youtube.com/watch?v=-yv34qV_Hrs).
My module makes use of the Analog Output design for the 14 fixed filters.
I only changed the frequency of the high-pass filter from 11.5MHz to around 8.5MHz, because otherwise the filter output was just not audible anymore (at least for me).

There are two additional features, which are not present in the Yusynth and Analog Output designs.
The SONUM module provides CV inputs for the volume of the 12 band-pass filters.
There is also a feedback loop of the output signal back into the module input for some more experimental sounds.

<img height="500" src="https://github.com/user-attachments/assets/438ddd89-018c-434c-a00f-d454fff9138c">
<img height="500" src="https://github.com/user-attachments/assets/46c02fbc-1b9a-439b-852e-b2ce435d4b3f">
<img height="500" src="https://github.com/user-attachments/assets/8f4c4356-e21e-413a-98c4-b3123be40619">
<img height="500" src="https://github.com/user-attachments/assets/a682b9f1-d026-4ffc-96bf-0b91c53a6fa0">

## Features:
- 14 filter bands - 12 band-pass, a low-pass, and a high-pass - with attenuators
- 2 input channels - one into the even filters, one into the odd filters - with attenuators, normalled to each other
- Volume CV inputs for each of the 12 band-pass filters - attenuators serve as VCA bias
- A feedback loop with attenuator into both input channels with the feedback source selectable via a switch either from the odd or the even filter outputs
- 3 outputs - odd, even, and all filter channels

A demo of the module with a more detailed instruction for the usage is available on YouTube.

[<img width="500" src="https://github.com/user-attachments/assets/20c96704-a720-4ac5-8767-ff32d0bc53dc">](https://youtu.be/sHNB9UdjJjo)

## Signal Flow
The graph below describes the rough signal flow inside the module.

<img height="500" src="https://github.com/user-attachments/assets/80e67ade-8529-48ab-a43d-b9e9e8266a87">

The two inputs feed audio signals to different paths.
A signal coming in to input 1 is processed via an attenuator and sent to the high-pass filter and all odd filters from no.1 to no.11 in parallel.
The outputs from those filters are summed into the outputs ODD OUT and ALL OUT.

A signal coming in to input 2 is processed via an attenuator and sent to the low-pass filter and all even filters from no.1 to no.11 in parallel.
The outputs from those filters are summed into the outputs EVEN OUT and ALL OUT.

Another set of outputs from both odd and even processing blocks is sent into a feedback loop.
A switch on the front panel decides which of those two options is actually further processed.
The feedback signal is then going through another attenuator and mixed with both input signals.

The output volume of all 12 band-pass filters can be controlled via CV.

## Filter Band Frequencies
| Filter Band Number | Frequency [Hz]| Type | Signal Path |
| --- | --- | --- | --- |
| | 85.5 | Low-Pass | Even |
| 1 | 125 | Band-Pass | Odd |
| 2 | 185 | Band-Pass | Even |
| 3 | 265 | Band-Pass | Odd |
| 4 | 390 | Band-Pass | Even |
| 5 | 570 | Band-Pass | Odd |
| 6 | 830 | Band-Pass | Even |
| 7 | 1200 | Band-Pass | Odd |
| 8 | 1750 | Band-Pass | Even |
| 9 | 2600 | Band-Pass | Odd |
| 10 | 3800 | Band-Pass | Even |
| 11 | 5500 | Band-Pass | Odd |
| 12 | 8050 | Band-Pass | Even |
| | 8500 | High-Pass | Odd |

## Front Panel Labeling
The labels of all inputs, outputs, and knobs at the front panel indicate if they are relevant for the odd or even signal path. Elements for the odd path are boxed, while those for the even path are not.

<img height="500" src="https://github.com/user-attachments/assets/f68ab6cc-1dd4-4979-a9d6-da6853ab95dc">

## Module Build and PCBs
I added two different versions for the control board in the folder GerberFiles, an "original", and a "Thonk" version.
Reason is that for my own module, I am using specific potentiometers - 16K4 series from Supertech Electronics - and 3.5mm jack sockets - MJ-355 from Marushin - available at my local electronics shop.

<img width="500" alt="CtrlPCB Orig" src="https://github.com/user-attachments/assets/dcea06fe-0c9f-405c-b04a-e31d39cfe052">

However, since most DIY projects for Eurorack modules out there are using potentiometers from ALPHA and so-called THONKICONN jacks, as they are provided by Thonk in the UK, I also created another control board PCB for the "Thonk" version with footprints for those components.

<img width="500" alt="CtrlPCB Thonk" src="https://github.com/user-attachments/assets/48e87a1d-0c91-47f2-bf1a-662384c755de">

The main PCB is the same for both versions.

<img width="500" alt="MainPCB" src="https://github.com/user-attachments/assets/33049696-c70d-47c7-95bd-43289a57eca3">

I created the Gerber files with the online tool EasyEDA and ordered the PCBs at JLCPCB.

## Additional Information about specific Components
#### SMD Components
Due to the high number of components for all of the filter bands and VCAs, I decided to use the SMD version for all of the op amps on the boards.
In addition, there are a number of SMD bypass capacitors with the package size 1608 (imperial 0603).
Other components - resistors, other capacitors, diodes, quad VCA ICs - are through-hole.
That enabled me to keep the module size within 28HP.
#### Resistor Size
Concerning the resistor size, I am usually using small-size resistors, about half the length of the usual size, so they need less space on the PCB. If you want to use my Gerber files, you have to consider that fact. You might still use normal size resistors and put them in a standing position on the boards. Should also work fine.
#### Electrolytic Capacitors
On the control board, you will find 2 electrolytic capacitors with a rectangle next to them. Since these capacitors are too tall for standing upright on the board with the main board on top of it, those capacitors need to be mounted in a rectangular position. The rectangle shows the position for each bent-over capacitor.

<img width="300" src="https://github.com/user-attachments/assets/9747f9fc-4650-455d-8ddf-239dec878a60">

#### Resistor Arrays
There are four resistor arrays on the control board, each with eight 100K resistors.
Those are of the bussed type, so there are nine legs, and the orientation is crucial.
Make sure that the dot on the array and the dot on the board are lined up!
Another orientation is the squared hole for the component in the board, where the component side with the dot mark needs to be positioned.

<img width="300" src="https://github.com/user-attachments/assets/2adf1e37-27c3-4596-a13b-ff7bdcd9cb5d">

## Component Labeling on PCBs
Usually, I prefer labeling components with their values on the PCBs. So I do not have to switch between BOM, schematic, and PCB while selecting parts in the soldering process.

However, due to the huge number of components  for this module (235 resistors, 187 capacitors, 29 op amps...), the space on the main PCB is not sufficient to print all capacitor and resistor values.
So I decided to label them with the component numbers given in the schematic.
Those numbers are also listed in the BOM and separated between those on the main board and those on the control board. The resistor numbers in the BOM and schematic have the prefix R, while there is just the number printed on the PCBs.
