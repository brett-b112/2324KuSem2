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

## Example
![image](exADC.png)

## Step Size
![image](stepSize.png)

## Example ADC Circuit
![image](exCircuit.png)

## Example: TI ADC080x 8-bit
* The ADC0801, ADC0802, ADC0803, ADC0804 etc. (all 8 bit input).
* Operates With Processors or as a Stand-Alone Device
* Interface to Temp Sensors, Voltage Sources, and Transducers
![image](TIADC.png)

## Pin Functions
* *VREF*
* reference voltage for IC is either 1/2 of the voltage applied to VCC supply pin
or is euqal ot hte voltage that is externally forced at the VREF/2
![image](pinFunc.png)

## Timing
![image](DACTiming.png)
* 1.
    * When we decide we need to read from the ADC, we use the processor to assert CS (make CS =0)
    * CS: Chip select processor enables the ADC (active low)
    * At the same time WR (write) must be asserted (WR=0)
* 2.
    * After receiving the signal from the processor (CS and WR asserted), ADC starts conversions
    * Once conversion is done, ADC sends a signal via INTR pin
    * This means data can be read now from ADC
    * This is called a handshaking protocol
* 3.
    * Once INTR is asserted (INTR=0), the processor starts reading data from D0-D7
    * To do that, the processor asserts the read data signal (RD=0)
    * Keep asserted as long as data must be read

## Quiz on Canvas Quiz 6 I believe
![image](QuizDAC.png)
1. Convert 0xF1 to binary
2. Map binary onto equation
3. Calculate the whole thing and multiply it by the 10V on the outside
* The answer is 9.4V
![DAC Quiz An](QuizDACans.JPG)


----------
# Interrupt
------------
# Thu Mar 21st
------------

## Interrupt-Driven vs. Polling
![image](idvp.png)
![image](idvp2.png)

## Polling Example with Keyboard
* Two I/O are needed to facilitaet pollign for device like keyboard
    * **Status register** : indicates a key struck
    * **Data register** : stroes the input date from keyboard
* CPU regulary checks status register
* If the specific bit of the status registe is set:
    * CPU reads from data regsiter

## Polling
![image](Polling.png)
* Problem
    *  CPU can't do nay useful things in the meantime
* Improvements
    * Check multiple I/O devices rather than one
    * Instead of keep checking the status (busy waiting), do some other useful work and then check again
    * Q. when to check again?
    * Q. what if the I/O is latency critical?
    * The CPU may miss the I/O when its ready and check when its not ready
* Can we do I/O immediately when tis is read ?
    * soluion: interrupt


## Interrupt
• What is an interrupt?
    • Notifications for the processor!
• Hardware interrupts
    • Devices (timer, disk, keyboard, ...) to CPU
• Software interrupts
    • Used for inter-process communication in a multi-core micro-controller
• Exceptions
    • Divide by zero, segmentation fault, ...
    • an unexpected event from within the process


## Interrupt Operation
* I/O device that may or may not have anything to do with the program that is running can
1. force the running program to stop,
2. have the processor execute a program that carries out the needs of the I/O device, and then
3. have the stopped program resume execution as if nothing had happened.

## Example
* Let us asume program A is running on teh CPU
* what happens when an interupt occur safter instruction n+2 occurs
![inter1](inter1.png)
![inter2](inter2.png)

## Two parts to Interrupt Driven I/O
1. Causign the interrupt to occur
2. Handlign the interrupt request

# Part 1: Causing the Interrput to Occur

## Conditions for Having an intterupt
* Several things must be true for an I/O device to actually interrupt the program that is running:
1. The I/O device must want service.
2. The device must have the right to request the service.
3. The device request must be more urgent than what the processor is currently doing.
* If all three elements are present, the processor stops executing the program that is running and takes care of the interrupt.

## I/O device must watn service
![want.png](want.png)
## I/O device has teh rigth to request the service
![able.png](able.png)

## Urgency of the Interrupt
* There may be many devices that want to interrupt the processor at a specific time.
* Each program runs at a specific priority level
* For an interrupt to go through, the interrupt should have a priority level higher that the program running on the processor
* We do not want a radio volume control to interrupt an image processing application in an autonomous vehicle! 17

## Generation of an INterrupt Signal
![genInterrupt.png](genInterrupt.png)
