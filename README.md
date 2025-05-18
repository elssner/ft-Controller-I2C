> Diese Seite bei [elssner.github.io/ft-Controller-I2C](https://elssner.github.io/ft-Controller-I2C/) öffnen.

* Robo Pro Coding Blöcke für fischertechnik RX und TXT 4.0 Controller
* zur Programmierung beliebiger I²C Module

Robo Pro Coding Projekt von [fischertechnik GitLab](https://git.fischertechnik-cloud.com/i2c) laden: im Suchfeld **i2c** eingeben

#### Quellcodedateien und I²C Devices werden von den angekreuzten Programmierbeispielen verwendet:

Beispiel|||0|1|2|3|4|5|6|7|8|9
---|---|---|---|---|---|---|---|---|---|---|---|---
Quellcodedatei|I²C Adr|I²C Devices| ||||
advanced||Blöcke für fehlende Funktionen
i2cCode||Python I²C für RX und TXT 4.0| 
dipswitch|<code>0x03</code>|[6-DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch), [5-Way Switch](https://wiki.seeedstudio.com/Grove-5-Way_Switch)|0|x|||
keyboard|<code>0x5F</code>|[M5Stack Card Keyboard](https://docs.m5stack.com/en/unit/cardkb_1.1)|0|0|0|0|0
lcd16x2|<code>0x3E</code>|[Grove - LCD Display 16x2 Zeichen](https://wiki.seeedstudio.com/Grove-16x2_LCD_Series)
oled|<code>0x3C 0x3D</code>|OLED Displays [128x128](https://wiki.seeedstudio.com/Grove-OLED-Display-1.12-SH1107_V3.0), [128x64](https://wiki.seeedstudio.com/Grove-OLED-Yellow&Blue-Display-0.96-SSD1315_V1.0)
oled_geometrie||Blöcke für Linien und Kreise
qwiiceeprom|<code>0x50</code>|[SparkFun Qwiic EEPROM - 512Kbit](https://www.sparkfun.com/products/18355)
qwiicgpio|<code>0x27</code>|[SparkFun Qwiic GPIO](https://www.sparkfun.com/products/17047)
qwiicjoystick|<code>0x20</code>|[SparkFun Qwiic Joystick](https://www.sparkfun.com/products/15168)
qwiickeypad|<code>0x4B</code>|[SparkFun Qwiic Keypad 12 Tasten](https://www.sparkfun.com/products/15290)
qwiiclcd|<code>0x72</code>|Qwiic LCD Displays [20x4](https://www.sparkfun.com/products/16398), [16x2](https://www.sparkfun.com/products/16396)
qwiicmotor|<code>0x5D 0x5E</code>|[SparkFun Qwiic Motor Driver](https://www.sparkfun.com/products/15451)
qwiicrelay|<code>0x1E</code>|[SparkFun Qwiic Single Relay](https://www.sparkfun.com/products/15093)
rtc|<code>0x51</code>|[Grove - RTC (Real Time Clock)](https://wiki.seeedstudio.com/Grove_High_Precision_RTC)


#### Steuer Byte 0 <code>..xx....</code> (2 Bit) Betriebsart

hex|bit|Funktion|bei Ereignis von einem Sensor
---|---|---|---
0x00|<code>..00....</code>|Fernsteuerung 6 Motoren|Stop bei Hindernis
0x10|<code>..01....</code>|Fernsteuerung ein Motor M0|wechselt zum *Programm Sensoren*
0x20|<code>..10....</code>|Programm 5 Strecken|Stop bei Hindernis
0x30|<code>..11....</code>|Programm Sensoren|wechselt zum Ereignis-Block


