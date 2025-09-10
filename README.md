# EXPERIMENT-01-INTERFACTING-DIGITAL-OUTPUT-WITH-EDGE-DEVICE---(RASPBERRYPI-PICO)
### NAME : Yogesh rao S D
### ROLL NO :212222110055
 

### AIM
To interface a digital output device (LED) with the Raspberry Pi Pico and control it using MicroPython.

## APPARATUS REQUIRED
Raspberry Pi Pico
LED (Light Emitting Diode)
330Ω Resistor
Breadboard
Jumper Wires
USB Cable
 ## THEORY

 ![image](https://github.com/user-attachments/assets/abeabf63-f321-471e-a991-3adaa9043a8b)

 
 
 
 
 ### FIGURE-01 RASPI PICO PINOUT DIAGRAM 



 Raspberry Pi Pico is a microcontroller board based on the RP2040 chip. It supports MicroPython, making it suitable for IoT and embedded applications.
The Raspberry Pi Pico is a compact microcontroller board featuring a 40-pin layout, including power, ground, GPIO, and communication interface pins. It operates with a dual-core ARM Cortex-M0+ processor and supports MicroPython and C/C++ programming. The power pins include VBUS (5V from USB), VSYS (1.8V to 5.5V input), 3V3(OUT) (regulated 3.3V output), and multiple ground (GND) connections. The board offers 26 multi-purpose GPIO pins (GP0 to GP28), which can be used for digital input, output, PWM, and communication interfaces such as I2C, SPI, and UART. It also features three analog-to-digital converter (ADC) pins (GP26, GP27, GP28), used for reading analog sensor values, along with an ADC_VREF pin to set the reference voltage. For communication, I2C (SDA, SCL), SPI (MOSI, MISO, SCK), and UART (TX, RX) interfaces are mapped across different GPIO pins, allowing seamless connectivity with sensors and peripherals. All GPIO pins support PWM (Pulse Width Modulation), making it useful for motor control, LED brightness adjustment, and sound applications. The BOOTSEL button enables USB mass storage mode for firmware flashing, while the DEBUG pins (SWD interface) provide debugging capabilities. With its low power consumption, flexible GPIO options, and rich interface support, the Raspberry Pi Pico is widely used for IoT, embedded systems, robotics, and automation projects.


## Working Principle:

The LED is connected to one of the GPIO pins of the Pico.
The MicroPython script sets the GPIO pin HIGH to turn the LED ON and LOW to turn it OFF.
CIRCUIT DIAGRAM
Connect the anode (longer leg) of the LED to GP15 via a 330Ω resistor.
Connect the cathode (shorter leg) of the LED to GND (ground).


## PROGRAM (MicroPython)

# FIGURE -02 LED WITH TIME DELAY:
```
from machine import Pin
import time
led = Pin(15, Pin.OUT)
while True:
    led.on()
    print("LED is ON")
    time.sleep(1)
    led.off()
    print("LED is OFF")
    time.sleep(1)
 
````
#  FIGURE -03 THREE LED IN SERIES WITH TIME DELAY:
```
from machine import Pin
import time
red_led = Pin(15, Pin.OUT)
green_led = Pin(14, Pin.OUT)
blue_led = Pin(13, Pin.OUT)
blink_delay = 0.5

while True:

    print("Red LED ON")
    red_led.on()
    time.sleep(blink_delay)
    red_led.off()
    time.sleep(blink_delay)

    print("Green LED ON")
    green_led.on()
    time.sleep(blink_delay)
    green_led.off()
    time.sleep(blink_delay)

    print("Blue LED ON")
    blue_led.on()
    time.sleep(blink_delay)
    blue_led.off()
    time.sleep(blink_delay)

    print("All LEDs ON")
    red_led.on()
    green_led.on()
    blue_led.on()
    time.sleep(1) 
    red_led.off()
    green_led.off()
    blue_led.off()
    time.sleep(1) 

```
# FIGURE -04 LED AND BUZZER IN SERIES WITH TIME DELAY:
```
from machine import Pin
import time

led1 = Pin(15, Pin.OUT)
led2 = Pin(14, Pin.OUT)
led3 = Pin(13, Pin.OUT)
buzzer = Pin(12, Pin.OUT)

delay = 0.5 

led1.off()
led2.off()
led3.off()
buzzer.off()

while True:
    led2.on()
    print("LED 2 is ON")
    time.sleep(delay)
    led2.off()
    print("LED 2 is OFF")
    time.sleep(delay)

    led3.on()
    buzzer.on()
    print("LED 3 is ON, Buzzer is ON")
    time.sleep(delay)
    led3.off()
    buzzer.off()
    print("LED 3 is OFF, Buzzer is OFF")
    time.sleep(delay)

    led1.on()
    print("LED 1 is ON")
    time.sleep(delay)
    led1.off()
    print("LED 1 is OFF")
    time.sleep(delay)
```
### OUPUT  


# FIGURE -02 LED WITH TIME DELAY:
<img width="943" height="663" alt="Screenshot 2025-08-09 155310" src="https://github.com/user-attachments/assets/b7f2cbb1-618b-4c05-9d25-5cbb6a7ab311" />

#  FIGURE -03 THREE LED IN SERIES WITH TIME DELAY:
<img width="791" height="489" alt="Screenshot 2025-08-09 160250" src="https://github.com/user-attachments/assets/a04aea9a-3b40-4fbc-988e-e20d99949d2a" />

# FIGURE -04 LED AND BUZZER IN SERIES WITH TIME DELAY:
<img width="955" height="886" alt="Screenshot 2025-08-09 161514" src="https://github.com/user-attachments/assets/2f5624b9-9e5a-4a5b-8891-8fab8129670b" />


 
## RESULTS
The LED connected to the Raspberry Pi Pico successfully turns ON and OFF at  user defined time  confirming the proper interfacing of a digital output.
