# CH32V003-tiny-in-line-dev-board
A tiny CH32V003 32bit RISC-V prototype development board in an unusual form factor - 8 pins single in-line.
A CH32V003J4M6 SOP-8 IC is used. It has 6 IO pins one of which is used for flashing the ROM. It runs at 24MHz max with no crystal.
![CH32V003-dev-board-SIL8-front-](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/1d263515-e0fd-4fe5-92dd-b592708f6eec)

I did the project as an exercise in minimalism and aesthetics.


## Notable design features
* Size 20x17x7mm
* LED on PC4 (pin 7) and push button switch on PA2 (pin3).
* 5V or 3.3V power.


**Construction**

Built on a 1.27mm pitch prototyping PCB. using SMD components, apart from the header. An 8x1 turned-pin male header carries all the IC pins. There's no separate programming header. Just plug it into a standard 0.1in pitch breadboard and connect pins 2, 4 and 8 to a WCH-LinkE (or other) programmer.
The push switch is 4.5x3mm. I tried a 2x3mm switch but it was too tricky to press.

