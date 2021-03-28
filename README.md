# PopnPinout

Pinout information for Pop'n Music Cabinets

# By System

## Firebeat

There are two MIL30 connectors taking care of the I/O

![firebeat](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/pinout_firebeat.PNG?raw=true)

- CN-Check has to be wired to GND for the system to accept I/O (games won't boot otherwise)
- +12V on that PCB is an OUTPUT, do NOT wire a power source to it 
- All outputs are normally 0V and active +12V (with a daisychain to +12V, then each named pin is for the negative side)
- All inputs are normally +12V and active 0V (with a daisychain to GND)
- Using these connectors bypass the power distribution box and thus the keepwarm voltage meant for incandescent lightbulbs (which means you can and should use 12V LEDs inside the buttons).

### Volume pot

![firebeat_vol](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/firebeat_vol.PNG?raw=true)

Firebeat cabs have a volume pot controlling the sound output level. This only applies to the Line Out, not the Line Out AUX.

The pot is plugged to the CN48 connector (vertical 9-pin connector under the line out RCA sockets).
If you don't have such volume pot you can either solder one or just bridge pins 2 and 4, as well as pins 3 and 5 together (with pin 1 on top and pin 9 on bottom)

### Power connector

If you don't have the original power connector, you can use regular 4.8mm spade connectors (same kind as used with arcade buttons) which fit nicely on 2 pin each.

![python_power](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/python_power.PNG?raw=true)

Black wires are for GND, Red wires are for +5V, Orange wires are for +12V

## Python

There are two MIL connectors on the power distribution box, one MIL50 and one MIL16, taking care of the I/O

![python](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/pinout_python_pc.PNG?raw=true)

- While buttons could be wired to the jamma connector directly, power button lamps are using a shift register inside the power distribution box to decode light data.

### Power connector

If you don't have the original power connector, you can use regular 4.8mm spade connectors (same kind as used with arcade buttons) which fit nicely on 2 pin each.

![python_power](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/python_power.PNG?raw=true)

Black wires are for GND, Red wires are for +5V, Orange wires are for +12V

### Using 12V LEDs instead of incandescent lightbulbs

The power distribution board generates a keepwarm voltage with 680ohms pullup resistors labeled R69 R65 R61 R66 R70 R62 R71 R67 R63.

![python_ledmod](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/python_ledmod.PNG?raw=true)

By cutting traces on the GND side of each of these resistors (along the orange lines on the above photo) you can then use 12V LEDs in the buttons instead of incandescent lightbulbs. This is recommended to preserve the board as LEDs will draw much less current.

## BemaniPC (SD)

There are two MIL connectors on the power distribution box, one MIL50 and one MIL16, taking care of the I/O

![pc](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/pinout_python_pc.PNG?raw=true)

The power distribution board is different and not compatible with python, but the interface towards the cabinet buttons and lamp remains the same.

## BemaniPC (HD)

The HD cab doesn't use the MIL50+MIL16 connector anymore but it retains the same connectors towards the BemaniPC itself.

# Bonus: Centronics dataswitch

![centronics2](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/centronics2.PNG?raw=true)

I've been using these pinouts to make custom centronics cables. This way I can plug the cabinet IO to male IDC connectors (pictured above on the left),
go into a centronics dataswitch (the kind used for old printer sharing), and from there go back into a female MIL50+MIL16 connector (pictured above on the right, to plug on the bemaniPC or python power distribution board), or a dual female MIL30+30 connector (to plug on the firebeat). 

![centronics_switch](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/centronics_switch.PNG?raw=true)

## Centronics custom pinout

Of course the pinout is entirely up to you, but just for the record I'm including the one I picked (I followed the MIL50+MIL16 connectors with the IDC, pretty much).

### Important notes on the SD cab CN7 and CN8 connectors

You can deduce the cables pinout by mirroring the MIL50 and MIL16 connectors from the power distribution board. However please note that on the cabinet side, each GND is wired to only a subset of buttons rather than daisychaining all of them

- GND A only applies to buttons 1 to 5
- GND B only applies to buttons 6 to 9
- GND C only applies to Coin Test Reset Service
- The lamps +12v line is not sourced from these connectors but rather from the 2-pin CN63 connector

This is not an issue when making cables which go on a power distribution board as it will take care of putting the grounds together, but might become an issue if you attempt to interface directly with the dual MIL30 from a firebeat (in which case you should wire GND together on your cable, and also make sure to wire the CN63 GND with the firebeat GND so that the +12V reference point can work).

- DO NOT wire power onto the firebeat +12V connector. The firebeat generates its own.

### pinout

![centronics](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/cent36.gif?raw=true)

Looking at the male end (connector on the cable, which means red wire is pin 1)

| Centronics | Cabinet |
|---|---|
| 1  | GND |
| 2  | Button 5 |
| 3  | Side lamp 1 |
| 4  | Button 4 |
| 5  | Side lamp 2 |
| 6  | Button 3 |
| 7  | Side lamp 3 |
| 8  | Button 2 |
| 9  | Side lamp 4 |
| 10 | Button 1 |
| 11 | +12V |
| 12 | Button 6 |
| 13 | Top 1 |
| 14 | Button 7 |
| 15 | Top 2 |
| 16 | Button 8 |
| 17 | Top 3 |
| 18 | Button 9 |
| 19 | Top 4 |
| 20 | Top 5 |
| 21 | Coin Blocker |
| 22 | Coin |
| 23 | Coin Counter |
| 24 | Test |
| 25 | Reset |
| 26 | Service |
| 27 | Button lamp 1 |
| 28 | Button lamp 2 |
| 29 | Button lamp 3 |
| 30 | Button lamp 4 |
| 31 | Button lamp 5 |
| 32 | Button lamp 6 |
| 33 | Button lamp 7 |
| 34 | Button lamp 8 |
| 35 | Button lamp 9 |
| 36 | +12V |

DO NOT WIRE THE 12V PINS TO THE FIREBEAT, it already generates its own 12V signal for the lamps, you risk damaging the board.
