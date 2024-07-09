# CH32V003-tiny-in-line-dev-board
A tiny CH32V003 32bit RISC-V prototype development board in an unusual form factor - 8 pins single in-line.
A CH32V003J4M6 SOP-8 IC is used. It has 6 IO pins one of which is used for flashing the ROM. It has 16kB of flash (large for an SOP-16 MCU) and 2kB of RAM and runs at 24MHz max with no crystal. It costs only £0.13 (+local tax) (20 off) on Aliexpress.
![CH32V003-dev-board-SIL8-front-300x250-](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/c2b6819b-519c-4b03-8c60-0affc5fb05ed)
![CH32V003-dev-board-SIL8-back-300x250](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/2ac84c71-436c-40ab-b0a8-dd1cfc0af197)
![CH32V003-dev-board-SIL8-top-300x200](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/e6b72381-6526-4f45-a96e-5b0269a48633)

I did the project as an exercise in minimalism and aesthetics - and yes, the soldering could be neater.


## Notable design features
* Size 20x17x7mm
* LED/12k resistor to ground on PC4 (pin 7) and push button switch to ground on PA2 (pin3).
* 5V or 3.3V power.

**Construction**

Built on a 1.27mm pitch prototyping PCB. using SMD components, apart from the header. An 8x1 turned-pin male header carries all the IC pins. There's no separate flashing header. Just plug it into a standard 0.1in pitch breadboard and connect pins 2, 4 and 8 to a WCH-LinkE (or other) flasher.
![CH32V003-dev-board-SIL8-flashing-300x370](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/e9b46861-a6f1-4e76-8ba2-29351a3c48b2)

The push switch is 4.5x3mm. I tried a 2x3mm switch but it was too tricky to press.

## Programming
I used both Arduino and the CH32V003fun environment in PlatforIO (in Visual Studio). 

**Arduino**
This was straighforward using the WCH official CH32V Boards Manager (https://github.com/openwch/board_manager_files/raw/main/package_ch32v_index.json ). However the Arduino Blink sketch. Uses 10368 bytes, laeving only ~6KB unused.

**PlatformIO / CH32V003fun**
I fond this much more difficult to get working. I hadn't used PlatformIO for a while, and then only with imported Arduino sketches. 
https://github.com/cnlohr/ch32v003fun promised small code size. Blink is only xxx

