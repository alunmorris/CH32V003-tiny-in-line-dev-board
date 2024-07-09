# CH32V003-tiny-in-line-dev-board
A tiny 



I did the project as an exercise in minimalism as well as being actually useful. Demo at 


## Notable design features
* Size 18x21x11mm
* Autoranges six levels for optimal accuracy
* OLED unplugs, allowing the MPU to be programmed via the same header

![multi-channel-voltmeter-5-smaller](https://github.com/alunmorris/Multi-channel-autorange-OLED-voltmeter/assets/4630866/3fbe69d8-d6f0-4e4b-b7f5-889d0f148057)


## Function Overview
The MPU ADC (10-bit) reads voltage data from 4 channels and shows them on an OLED display.

Features:
* 0-27V range. 1mV resolution for V<1V.
* 3.3-12V supply. Reverse polarity protection.
* Accuracy c.1% (can be improved by calibration). May deteriorate - depends on resistor quality.
* Temperature variation is mostly dependent on the resistors. The MPU ADC is +/-0.1% over 0 to 40C. 
* Positive voltage only. Over voltage indication. +/-100V input tolerant.
* 1.1Mohm input impedance (or 1.1Mohm in series with 30pF when V<2.5V).
* Sample rate c.10/s, configurable

### Circuit diagrams
In eeschema/Kicad .sch format.


**Construction**

uilt on a 1.27mm pitch prototyping PCB. using SMD components, apart from the two headers. I removed the 4 pin 2.54mm header from a standard 72x40 0.42in OLED module and replaced with a 7 pin 1.27mm male header with pins 2, 3 and 5 removed so that it goes through the same holes.
