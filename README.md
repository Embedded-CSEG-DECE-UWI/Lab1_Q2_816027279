# ECNG3006 Lab 1 Question 1

Registers an interrupt handler and triggers it from app_main.

## GPIO functions

 * GPIO0: output
 * GPIO2:  input, pulled up, interrupt from falling edge

## How to use example

### Hardware Required

 * Connect GPIO15 with GPIO4

### Configure the project

```
make menuconfig
```

* Set serial port and flash mode under Serial Flasher Options.


### Build and Flash

Build the project and flash it to the board, then run monitor tool to view serial output:

```
make -j4 flash monitor
```

(To exit the serial monitor, type ``Ctrl-]``.)


## Example Output  

Generate pulses on GPIO0, that triggers interrupt on GPIO2. See [output](output/lab1_q2_816027279.out).

```
I (243) gpio: GPIO[0]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0 
I (248) gpio: GPIO[2]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 1| Pulldown: 0| Intr:2 
I (259) main: cnt: 1
 
I (1254) main: cnt: 2
 
I (2254) main: cnt: 3

I (2256) main: GPIO[2] intr, val: 0, times called: 1

I (3254) main: cnt: 4

I (4254) main: cnt: 5

I (4256) main: GPIO[2] intr, val: 0, times called: 2

I (5254) main: cnt: 6

I (6254) main: cnt: 7

I (6256) main: GPIO[2] intr, val: 0, times called: 3
 ```
