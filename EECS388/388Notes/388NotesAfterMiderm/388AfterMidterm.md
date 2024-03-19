# 388 Notes After Midterm

----------
# Tuesday March 19th Lecture 12
--------
# I/O Interface
-------

## How does CPU talk to Devices?
* **Port Mapped I/O**
    * Use a seperate address space for I/O devices and use specia linstructions to access the I/O memory
* **Memory mapped I/O**
    * I/O memory is mapped into the CPU address space
    * Use load/stroe instruction to communicate with I/O devices
    *![](memMapIO.png)
## Memory Map of SiFive FE310
![](memMapSi.png)

## General Purpose I/O (GPIO)
* Programmable digital I/O pins
*Use voltage levels to represent signals
    * 5V = logic 1
    * 0V = logic 0
* can be configured as input or output
* Useful to interact witih external devices

## Example; Turn on an LED
![](redLED.png)

## Memory MAP of GPIO
    This is based on the c code for the blinking LED first lab. We are looking at lib.h file for GPIO names
![](memMapGPIO1.png)
![](memMapGPIO2.png)

## Lib.C example
    Again using C code here
![](libC.png)
![](libH.png)

## Volatile in C
* Using volatile compiler generates code to re-load variable each time it is reference in your program
* Wihout volatile the compiler may generate code that reuses value loaded in register
![](volatileC.png)

## I/O register paths
![](IOPath.ong)

----------
# I/O Devices ADC/DAC
-------

## Voacb
* ADC (analog to digital converter)
* DAC (digital to analog converter)
![iimage](ADCAD.png)

## Examples
* microphone converts to 1010101
* 01010101 converts to sound from speakers


## DAC0808: 8-bit D/A Converter
![image](8bitConv.png)

## Using the DAC
![image](usingDAC.png)
![image](usingDAC2.png)

## Inside DAC 0808
![image](insideDAC.png)

## DAC Resolution
* number of data inputs decides the resolution of DAC
* So if there are n digital inpit pin -> 2^n analog levels
* 8 input DAC -> 256 Discrete voltage levels
![image](dacRes.png)

# QUESTION ON THE FINAL
![fequestion](question1.png)
![fequestion](question1Ans.JPG)
