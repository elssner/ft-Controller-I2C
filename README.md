# ft-Controller-I2C



### Beispiele

Beispiel||0|1|2|3|4|5|6|7|8|9
---|---|---|---|---|---|---|---|---|---|---|--
**I²C Devices**| ||||
dipswitch|[Grove - 6-Position DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch)|0|x|||
keyboard|0|0|0|0|0
lcd16x2
oled
qwiiceeprom
qwiicgpio
qwiicjoystick
qwiickeypad
qwiiclcd
qwiicmotor
qwiicrelay
rtc


#### Steuer Byte 0 <code>..xx....</code> (2 Bit) Betriebsart

hex|bit|Funktion|bei Ereignis von einem Sensor
---|---|---|---
0x00|<code>..00....</code>|Fernsteuerung 6 Motoren|Stop bei Hindernis
0x10|<code>..01....</code>|Fernsteuerung ein Motor M0|wechselt zum *Programm Sensoren*
0x20|<code>..10....</code>|Programm 5 Strecken|Stop bei Hindernis
0x30|<code>..11....</code>|Programm Sensoren|wechselt zum Ereignis-Block


