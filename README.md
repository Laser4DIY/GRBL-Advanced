This is a fork of https://github.com/Schildkroet/GRBL-Advanced. It is meant to drive a Laser4DIY XY Table, see https://github.com/Laser4DIY/XY-Table

Changes made:
* laser mode on by default
* modified setting for homing/direction/end stops to match Laser4DIY configuration
* set table size to 160x160mm
* reduced travel speeds
* changed SpindlePwm config, so it acts a laser on/off signal (no PWM)

When used with a CNC shield on a Nucleo STM32 board, Laser4DIY hardware need to be attached like this:

Function  | CNC Shield Label 
---       | --- 
Stepper X | X 
Stepper Y | Y 
Endstop X | X+ 
Endstop Y | Y+
Laser Enable | Z+

This is the mapping of signals to pins:

Signal | Arduino Pin | Nucleo Pin
---    | ---         | --- 
x step     | 2  | a10
y step     | 3  | b3
x dir      | 5  | b4
y dir      | 6  | b10
x endstop  | 9  | c7
y endstop  | 10 | b6
spin pwm   | 11 | a7
