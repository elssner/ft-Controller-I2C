> Diese Seite bei [elssner.github.io/ft-Controller-I2C](https://elssner.github.io/ft-Controller-I2C/) öffnen.

### Robo Pro Coding Blöcke für fischertechnik RX und TXT 4.0 Controller zur Programmierung beliebiger I²C Module

Robo Pro Coding Projekt von [fischertechnik GitLab](https://git.fischertechnik-cloud.com/i2c) laden: im Suchfeld **i2c** eingeben

#### Quellcodedateien und I²C Module in Programmierbeispielen verwendet:

* für die angeschlossenen I²C Module nicht benötigte Quellcodedateien können gelöscht werden
* Quellcodedatei i2cCode darf nicht gelöscht werden

Quellcodedatei|I²C Adr|I²C Module|Beispiel n
---|---|---|---
[advanced](#advancedpy)||Blöcke für fehlende Funktionen|11
i2cCode||Python I²C für [RX](https://github.com/fischertechnik/RX-Controller-I2C) und [TXT 4.0](https://github.com/fischertechnik/TXT40-Controller-I2C)|alle
dipswitch|<code>0x03</code>|[6-DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch), [5-Way Switch](https://wiki.seeedstudio.com/Grove-5-Way_Switch)|3
keyboard|<code>0x5F</code>|[M5Stack Card Keyboard](https://docs.m5stack.com/en/unit/cardkb_1.1)|2
lcd16x2|<code>0x3E</code>|[Grove - LCD Display 16x2 Zeichen](https://wiki.seeedstudio.com/Grove-16x2_LCD_Series)|1, 2, 3
oled|<code>0x3C 0x3D</code>|OLED Displays [128x128](https://wiki.seeedstudio.com/Grove-OLED-Display-1.12-SH1107_V3.0), [128x64](https://wiki.seeedstudio.com/Grove-OLED-Yellow&Blue-Display-0.96-SSD1315_V1.0)|8, 9, 10, 11
oled_geometrie||Blöcke für Linien und Kreise|8, 10, 11
qwiiceeprom|<code>0x50</code>|[SparkFun Qwiic EEPROM - 512Kbit](https://www.sparkfun.com/products/18355)|9, 10
qwiicgpio|<code>0x27</code>|[SparkFun Qwiic GPIO](https://www.sparkfun.com/products/17047)|5
qwiicjoystick|<code>0x20</code>|[SparkFun Qwiic Joystick](https://www.sparkfun.com/products/15168)|6, 14, 15
qwiickeypad|<code>0x4B</code>|[SparkFun Qwiic Keypad 12 Tasten](https://www.sparkfun.com/products/15290)|4, 5
qwiiclcd|<code>0x72</code>|Qwiic LCD Displays [20x4](https://www.sparkfun.com/products/16398), [16x2](https://www.sparkfun.com/products/16396)|4, 5, 6
qwiicmotor|<code>0x5D 0x5E</code>|[SparkFun Qwiic Motor Driver](https://www.sparkfun.com/products/15451)|14, 15
qwiicrelay|<code>0x1E</code>|[SparkFun Qwiic Single Relay](https://www.sparkfun.com/products/15093)|Hauptprogramm
rtc|<code>0x51</code>|[Grove - RTC (Real Time Clock)](https://wiki.seeedstudio.com/Grove_High_Precision_RTC)|1, 4, 10

#### Programmierbeispiel wird bei geschlossenem `Input I5..I8` gestartet:

* Quellcodedatei i2cCode wird in allen Programmierbeispielen verwendet

n|`I8`|`I7`|`I6`|`I5`|Beispiel|Quellcodedateien, I²C Module
---|---|---|---|---|---|---
0|`0`|`0`|`0`|`0`|i2cScan
1|`0`|`0`|`0`|`1`|grovelcd_rtc|lcd16x2, rtc
2|`0`|`0`|`1`|`0`|grovcelcd_keyboard|lcd16x2, keyboard
3|`0`|`0`|`1`|`1`|grovelcd_dipswitch|lcd16x2, dipswitch
4|`0`|`1`|`0`|`0`|qlcr_rtc_keypad|qwiiclcd, rtc, qwiickeypad
5|`0`|`1`|`0`|`1`|qlcd_gpio_keypad|qwiiclcd, qwiicgpio, qwiickeypad
6|`0`|`1`|`1`|`0`|qlcd_joystick|qwiiclcd, qwiicjoystick
7|`0`|`1`|`1`|`1`||
8|`1`|`0`|`0`|`0`|oled_zeichnen|oled, oled_geometrie
9|`1`|`0`|`0`|`1`|oled_eeprom_copy|oled, eeprom
10|`1`|`0`|`1`|`0`|oled_eeprom_rtc|oled, oled_geometrie, eeprom, rtc
11|`1`|`0`|`1`|`1`|oled2_systemtime|2*oled, oled_geometrie, advanced
12|`1`|`1`|`0`|`0`||
13|`1`|`1`|`0`|`1`||
14|`1`|`1`|`1`|`0`|joy_2motoren|qwiicjoystick, qwiicmotor
15|`1`|`1`|`1`|`1`|joy_4motoren|qwiicjoystick, 2*qwiicmotor

### Beschreibung der I²C Funktionen

> RX Controller nutzt CircuitPython, TXT 4.0 Controller nutzt Python3. Beide unterstützen I²C, aber völlig verschieden.
> Die I²C Blöcke hier sind plattformunabhängig programmiert. Die Python Implementation wird erkannt und dann der entsprechende Code ausgeführt.\
<ins>I²C kennt nur 2 Funktionen:</ins>\
*an eine I²C-Adresse Bytes senden* oder *von einer I²C-Adresse Bytes empfangen*.\
Es gibt noch eine Kombination aus beiden und i2cScan soll alle Module am Bus finden.

#### i2cCode.py

Block **i2cWriteBuffer** (i2cAdr, write_buffer)

* sendet Bytes aus der Liste *write_buffer* an die *i2cAdr*
* *i2cAdr*: 7 Bit (0x00..0x7F bzw. 0..127)
* *write_buffer*: Liste darf nur 8-Bit Elemente (0x00..0xFF bzw. 0..255) enthalten
* Parameter *write_buffer* kann z.B. mit Block *erzeuge Liste* (aus Datenstrukturen) übergeben werden

Block **i2cReadBuffer** (i2cAdr, length) : Liste der Bytes

* empfängt Bytes von der *i2cAdr*, *length* ist die Anzahl der Bytes
* aus der zurück gegebenen Liste können die Bytes mit 'in der Liste' Blöcken (aus Datenstrukturen) gelesen werden



### Beschreibung der Quellcodedateien (alphabetisch geordnet)

#### advanced.py

> allgemeine Blöcke, die Python-Funktionen bereit stellen (ohne I²C Bezug)\
Kommentar, Chr, Int, list_hex, Ord, print_bin, string_decode, string_list, system_time

Block **system_time** () : Liste mit 9 Elementen

* TXT 4.0: RTC Systemuhr (year, mon, mday, hour, min, sec, wday, yday, isdst)\
Uhr wird bei Internetverbindung gestellt
* RX: Zeitstempel umgerechnet in (0, 0, 0, hour, min, sec, 0, 0, 0)

#### dipswitch.py

Block **readSwitch** () : Byte(0..63)



