# CH32V003-tiny-in-line-dev-board
A tiny CH32V003 32bit RISC-V prototype development board in an unusual form factor - 8 pins single in-line.
A CH32V003J4M6 SOP-8 IC is used. It has 6 IO pins one of which is used for flashing the ROM. It has 16kB of flash (large for an SOP-8 MCU) and 2kB of RAM and runs at 24MHz max with no crystal. It costs only £0.13 (+local tax) (20 off) on Aliexpress.

![CH32V003-dev-board-SIL8-front-300x250-](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/77a99866-9de3-43b4-8248-6c9a0305b63e)
![CH32V003-dev-board-SIL8-back-300x250](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/2ac84c71-436c-40ab-b0a8-dd1cfc0af197)
![CH32V003-dev-board-SIL8-top-300x200](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/e6b72381-6526-4f45-a96e-5b0269a48633)

I did the project as an exercise in minimalism.


## Notable design features
* Size 20x17x7mm
* LED/12k resistor to ground on PC4 (pin 7) and push button switch to ground on PA2 (pin3).
* 5V or 3.3V power.

**Construction**

Built on a 1.27mm pitch prototyping PCB. using SMD components, apart from the header. An 8x1 turned-pin male header carries all the IC pins. There's no separate flashing header. Just plug it into a standard 0.1in pitch breadboard and connect pins 2, 4 and 8 to a WCH-LinkE USB dongle.

![CH32V003-dev-board-SIL8-flashing-300x370](https://github.com/alunmorris/CH32V003-tiny-in-line-dev-board/assets/4630866/e9b46861-a6f1-4e76-8ba2-29351a3c48b2)

The push switch is 4.5x3mm. I tried a 2x3mm switch but it was too tricky to press.
Demo at https://www.youtube.com/watch?v=rPzlua1Xw1I
Demo code at https://github.com/alunmorris/Fast-primes-CH32V003-OLED-display

## C Programming
I used both Arduino and the CH32V003fun environment in PlatformIO (in Visual Studio). Demo code at https://github.com/alunmorris/Fast-primes-CH32V003-OLED-display/tree/main

**Arduino**
This was straighforward using the WCH official CH32V Boards Manager (https://github.com/openwch/board_manager_files/raw/main/package_ch32v_index.json ). However the Arduino Blink sketch uses a crazy 10368 bytes, leaving only ~6KB unused.

**PlatformIO / CH32V003fun**
I found this much more difficult to get working. I hadn't used PlatformIO for a while, and then only with imported Arduino sketches. 
https://github.com/cnlohr/ch32v003fun promised small code size. Blink is only 512B.
I could not get code to compile until I realised that I needed to set the top level ch32v003fun as the project folder. To build just _one_ of the examples, click the tiny folder icon at the bottom of PlatformIO (Switch PlatformIO Project Environment) and choose the project to build.

It looks like we will get a detailed guide for newbies to using CH32V003fun with PlatformIO: _Share the detailed steps to use ch32v003fun under vscode/platformio_ https://github.com/cnlohr/ch32v003fun/issues/339 

**Unbricking the CH32V003**
If you use pin 8 (PD1) as an IO pin you won't be able to re-flash it without using the WCH-LinkUtility
Run WCH-LinkUtility. Use manu Target->Clear All Code Flash By Power off. The CH32V003 must be powered from WCH-LinkE.
