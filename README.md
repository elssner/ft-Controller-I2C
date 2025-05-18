# ft-Controller-I2C



### Beispiele

Beispiel||0|1|2|3|4|5|6|7|8|9
---|---|---|---|---|---|---|---|---|---|---|--
---|**I²C Devices**| ||||
dipswitch|[Grove - 6-Position DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch)|0|x|||
keyboard|[M5Stack Card Keyboard](https://docs.m5stack.com/en/unit/cardkb_1.1)|0|0|0|0|0
lcd16x2|[Grove - LCD Display 16x2 Zeichen](https://wiki.seeedstudio.com/Grove-16x2_LCD_Series)
oled|[OLED Display 128x128 oder 128x64](https://wiki.seeedstudio.com/Grove-OLED-Display-1.12-SH1107_V3.0)
qwiiceeprom|[SparkFun Qwiic EEPROM - 512Kbit](https://www.sparkfun.com/products/18355)
qwiicgpio|[SparkFun Qwiic GPIO](https://www.sparkfun.com/products/17047)
qwiicjoystick|[SparkFun Qwiic Joystick](https://www.sparkfun.com/products/15168)
qwiickeypad|[SparkFun Qwiic Keypad 12 Tasten](https://www.sparkfun.com/products/15290)
qwiiclcd|Qwiic LCD Displays [20x4](https://www.sparkfun.com/products/16398) und [16x2](https://www.sparkfun.com/products/16396)
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


