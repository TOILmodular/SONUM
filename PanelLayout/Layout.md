## Panel Layout for PCB

The panel dimensions provided in the section "Original Design" below are based on my own module build, since I am not following the standard HP (1HP eq. 5.08mm) size.
An alternative by building an HP-standard size panel can be found in the section "HP Standard Design" further below.

### Original Design
Coordinates given in the table fit to the layout of components given in the PCBc in folder GerberFiles.
The layout is the same for both versions.

Panel size: 144mm x 128.5mm

The numbers in the table are refering to the numbers in the picture below.
Coordinates origin is the lower left corner of the panel.


| No. | X-coord. [mm] | Y-coord. [mm] | Comment |
| --- | --- | --- | --- |
| 1 | 14.5 | 105 | Low-Pass Pot |
| 2 | 37.5 | 105 | 125Hz Pot |
| 3 | 60.5 | 105 | 390Hz Pot |
| 4 | 83.5 | 105 | 1200Hz Pot |
| 5 | 106.5 | 105 | 3800Hz Pot |
| 6 | 129.5 | 105 | High-Pass Pot |
| 7 | 14.5 | 82 | IN1 Pot |
| 8 | 37.5 | 82 | 185Hz Pot |
| 9 | 60.5 | 82 | 570Hz Pot |
| 10 | 83.5 | 82 | 1750Hz Pot |
| 11 | 106.5 | 82 | 5500Hz Pot |
| 12 | 14.5 | 59 | IN2 Pot |
| 13 | 37.5 | 59 | 265Hz Pot |
| 14 | 60.5 | 59 | 830Hz Pot |
| 15 | 83.5 | 59 | 2600Hz Pot |
| 16 | 106.5 | 59 | 8050Hz Pot |
| 17 | 129.5 | 59 | Feedback Pot |
| 18 | 14.5 | 39 | Feedback Path Switch |
| 19 | 37.5 | 39 | 125Hz Jack |
| 20 | 60.5 | 39 | 390Hz Jack |
| 21 | 83.5 | 39 | 1200Hz Jack |
| 22 | 106.5 | 39 | 3800Hz Jack |
| 23 | 129.5 | 39 | ODD OUT Jack |
| 24 | 14.5 | 27 | IN1 Jack |
| 25 | 37.5 | 27 | 185Hz Jack |
| 26 | 60.5 | 27 | 570Hz Jack |
| 27 | 83.5 | 27 | 1750Hz Jack |
| 28 | 106.5 | 27 | 5500Hz Jack |
| 29 | 129.5 | 27 | EVEN OUT Jack |
| 30 | 14.5 | 15 | IN2 Jack |
| 31 | 37.5 | 15 | 265Hz Jack |
| 32 | 60.5 | 15 | 830Hz Jack |
| 33 | 83.5 | 15 | 2600Hz Jack |
| 34 | 106.5 | 15 | 8050Hz Jack |
| 35 | 129.5 | 15 | ALL OUT Jack |

<img height="800" src="https://github.com/user-attachments/assets/04f60cb6-ce3b-4465-acba-6e752f927170">

### HP Standard Design
For building the panel with a size following the HP standard, you can use the panel Gerber files provided in the folder "GerberFiles".

I ordered my own panel via such gerber file built out of PCB material.

Here are a few parameters of the panel.
| Parameter | Value |
| --- | --- |
| Width | 28HP |
| Pot hole diameter | 8mm |
| Jack hole diameter | 6.1mm |
| Switch hole diameter | 5.1mm |
| Mounting hole diameter | 3.2mm|
