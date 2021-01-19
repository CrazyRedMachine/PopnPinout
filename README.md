# PopnPinout

Pinout information for Pop'n Music Cabinets

# By System

## Firebeat

MIL30 1 (UPPER)

looking at connector on firebeat pcb, top row from right to left
x   x x x  x x x x x   x x L L   x x             ( L L = contact loop)
 cbl x x t1 2 3 4 5 bl5 6 7 8 12v x x


MIL30 2 (LOWER)

but1   2 3 4  5 6 7 8   9 c tst srv gnd   gnd x
    cct x x s1 2 3 4 bl9 1 2   3 4 x  +12v   x

## Python

Uses the 50+16 connector into the power distribution box.
Cannot interface the Jamma directly as the lights signals are decoded by the power distribution box 

Also the power distribution board generates a keepwarm voltage with 680ohms pullup resistors.

R61 bl3
R66 bl4
R63 bl9

R65 bl2
R70 bl5
R67 bl8

R69 bl1
R62 bl6
R71 bl7


## BemaniPC (SD)
p
(looking at the cable extremity, ie.
looking at connector on pwr distib board, top row from right to left :

MIL50

gnd  5  4  3  2  1 x gnd  6  7  8  9  x  x x x x x   c   gnd tst rst srv x x
    x s1 s2 s3 s4 x x +12v t1 t2 t3 t4 t5 x x x x cbl cct   x   x   x   x x x

MIL16 button lamps

b1  b3 b4  x b6  b8 b9 x
  b2  x  b5 x  b7  x  x 12

## BemaniPC (HD)

# By cabinet

# Bonus: Centronics dataswitch

![centronics](https://github.com/CrazyRedMachine/PopnPinout/blob/main/assets/cent36.gif?raw=true)

Looking at the male end (connector on the cable, which means red wire is pin 1)

1  GND
2  Button 5
3  Side lamp 1
4  Button 4
5  Side lamp 2
6  Button 3
7  Side lamp 3
8  Button 2
9  Side lamp 4
10 Button 1
11 +12V
12 Button 6
13 Top 1
14 Button 7
15 Top 2
16 Button 8
17 Top 3
18 Button 9
19 Top 4
20 Top 5
21 Coin Blocker
22 Coin
23 Coin Counter
24 Test
25 Reset
26 Service
27 Button lamp 1
28 Button lamp 2
29 Button lamp 3
30 Button lamp 4
31 Button lamp 5
32 Button lamp 6
33 Button lamp 7
34 Button lamp 8
35 Button lamp 9
36 +12V

DO NOT WIRE THE 12V PINS TO THE FIREBEAT, it already generates its own 12V signal for the lamps, you risk damaging the board.
