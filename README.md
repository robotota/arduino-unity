arduino-unity
=============

#General description

Arduino-Unity firmware converts Arduino board to interface board to control multiple simple external devices like servos, dc motors and leds. It allows to change pin configurations on the fly via simple text commands.

Arduino-unity contains drivers for several simple devices:
  * servos
  * leds and switches
  * DC motors
  * Analog inputs
  * i2c controlled devices

With i2c driver one Unity-flashed Arduino may control similar devices. 

#Usage

1. Flash Arduino with arduino-unity firmware
2. Connect your external devices to Arduino board
3. Open serial comm with Arduino (Serial monitor might be used)
4. Set up pin configuration with def commands 
5. Issue save command
6. Command the devices.

#Example

def servo hor 10       ; Servo motor named hor on pin 10
def servo vert 11      : Servo motor named vert on pin 11
def led led 13         ; LED on pin 13 named led
def led switch 3       ; Custom switch or latch on pin 3. We use led driver for it.
save                   ; store device definitions in EEPROM
                       ; 
hor 170                ; rotate first servo to the left
vert 90                ; set second servo to its central position
led on                 ; turn on the led
led off                ; turn off the led

