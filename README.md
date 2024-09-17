# heatpump
Project trying to reverse engineer Bosh air to air heat pump 


Just started

The device is using a baud rate of 2400 bits per second, 8 data bits, no parity, and 1 stop bit MAYBE :)

Typical message format 

```
dd 0b fb 60 03 11 21 16 18 80 00 f0 c1 06
1  2  3  4  5  6  7  8  9  10 11 12 13 14
|  |  |  |  |  |  |  |  |  |   |  |  |  |- 13 CRC
|  |  |  |  |  |  |  |  |  |   |  |  | --- 12 CRC
|  |  |  |  |  |  |  |  |  |   |  |------- 11 ION setting
|  |  |  |  |  |  |  |  |  |   |---------- 10
|  |  |  |  |  |  |  |  |  |-------------- 9
|  |  |  |  |  |  |  |  |----------------- 8 swing vertical & horizontal
|  |  |  |  |  |  |  |-------------------- 7
|  |  |  |  |  |  |----------------------- 6 fan speed& operation mode
|  |  |  |  |  |-------------------------- 5 start stop
|  |  |  |  |----------------------------- 4 temperature setpoint
|  |  |  |-------------------------------- 3 always same
|  |  |----------------------------------- 2 always same
|  |-------------------------------------- 1 always same
|----------------------------------------- 0 always same

```
Setpoint to 20c

dd 0b fb 60 03 11 21 16 18 80 00 f0 c1 06

setpoint to 21c

dd 0b fb 60 04 11 21 16 18 80 00 f0 c1 05         
