> Diese Seite bei [elssner.github.io/ft-Controller-I2C](https://elssner.github.io/ft-Controller-I2C/) öffnen.

### Robo Pro Coding Blöcke für fischertechnik RX und TXT 4.0 Controller zur Programmierung beliebiger I²C Module

Robo Pro Coding Projekt von [fischertechnik GitLab](https://git.fischertechnik-cloud.com/i2c) laden: im Suchfeld **i2c** eingeben

#### Quellcodedateien und I²C Module in Programmierbeispielen verwendet:

* für die angeschlossenen I²C Module nicht benötigte Quellcodedateien können gelöscht werden
* Quellcodedatei i2cCode wird immer benötigt und darf nicht gelöscht werden

Quellcodedatei|I²C Adr|I²C Module|Beispiel n
---|---|---|---
[i2cCode](#i2ccodepy)||Python I²C für [RX](https://github.com/fischertechnik/RX-Controller-I2C) und [TXT 4.0](https://github.com/fischertechnik/TXT40-Controller-I2C)|alle
[advanced](#advancedpy)||Blöcke für fehlende Funktionen|11
[dipswitch](#dipswitchpy)|<code>0x03</code>|[6-DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch), [5-Way Switch](https://wiki.seeedstudio.com/Grove-5-Way_Switch)|3
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

I²C: Inter-Integrated Circuit → [de.wikipedia.org/wiki/I²C](https://de.wikipedia.org/wiki/I%C2%B2C)

Hardware

* an einen I²C-Bus mit 4 Leitungen `SDA, SCL, -, +` (hier 3,3V) können mehrere I²C Module gleichzeitig angeschlossen werden (hintereinander gesteckt oder mit I²C Hub)
* die I²C Module müssen verschiedene 7-Bit I²C Adressen haben
* die Anzahl gleichzeitig angeschlossener Module ist aus elektrischen Gründen begrenzt

Software

* I²C kennt nur 2 Funktionen:\
**an eine I²C-Adresse Bytes senden** oder **von einer I²C-Adresse Bytes empfangen**
* es gibt noch eine Kombination aus beiden und i2cScan soll alle Module am Bus finden
* die Anzahl über den I²C-Bus übertragener Bytes ist **nicht** auf 32 Byte begrenzt

> RX Controller nutzt CircuitPython, TXT 4.0 Controller nutzt Python3. Beide unterstützen I²C, aber völlig verschieden.
> Die I²C Blöcke hier sind **plattformunabhängig** programmiert. Die Python Implementation wird erkannt und dann der entsprechende Code ausgeführt.

#### i2cCode.py

Block **i2cWriteBuffer** (i2cAdr, write_buffer)

* sendet Bytes aus der Liste *write_buffer* an die *i2cAdr*
* *i2cAdr*: 7 Bit (0x00..0x7F bzw. 0..127)
* *write_buffer*: Liste darf nur 8-Bit Elemente (0x00..0xFF bzw. 0..255) enthalten
* Parameter *write_buffer* kann mit `Datenstrukturen`**erzeuge Liste** übergeben werden

Block **i2cReadBuffer** (i2cAdr, length) : Liste der Bytes

* empfängt Bytes von der *i2cAdr*, *length* ist die Anzahl der Bytes
* die zurück gegebene Liste kann mit `Datenstrukturen`**in der Liste** gelesen werden

Block **i2cWriteReadBuffer** (i2cAdr, write_buffer, read_length) : Liste der Bytes

* sendet und empfängt Bytes, ohne dazwischen den I²C-Bus frei zu geben
* erlaubt I²C Register adressieren und lesen mit nur einer Funktion

Block **i2cScan** () : Liste der 7-Bit I²C-Adressen

* versucht alle möglichen I²C-Adressen in einer Schleife zu erreichen
* wenn read oder write erfolgreich ist, wird die gültige I²C Adresse in einer Liste gesammelt
* die zurück gegebene Liste kann mit `Text` **gib aus** in der Konsole angezeigt werden

Block **isRX** () : boolean

* gibt True zurück, wenn `sys.implementation.name == 'circuitpython'`


### Beschreibung der Quellcodedateien (alphabetisch geordnet)

#### advanced.py

> allgemeine Blöcke, die Python-Funktionen bereit stellen (ohne I²C Bezug)\
Kommentar, Chr, Int, list_hex, Ord, print_bin, string_decode, string_list, system_time

Block **system_time** () : Liste mit 9 Elementen
* TXT 4.0: RTC Systemuhr (year, mon, mday, hour, min, sec, wday, yday, isdst)\
Uhr wird bei Internetverbindung gestellt, Zeitzone am Controller einstellen
* RX: Zeitstempel umgerechnet in (0, 0, 0, hour, min, sec, 0, 0, 0)

#### dipswitch.py

Block **readSwitch** () : Byte → 6 Bit (0..63), 1 Bit pro DIP Schalter

#### keyboard.py

Block **readKeyboard** () : Byte → ASCII-Code der gedrückten Taste

#### lcd16x2.py

Block **initLCD** ()

Block **writeText** (row, col, end, text, right)
* *row*: Zeile 0 oder 1; *col*: Spalte 0..15; *end*: Spalte 0..15 (letztes Zeichen)
* *text*: Text, alle Datentypen werden mit str() konvertiert
* *right*: None oder False:linksbündig; True:rechtsbündig\
Text wird mit Leerzeichen auf die Länge (end-col)+1 aufgefüllt
* Parameter außer *text* können weg gelassen werden (None)\
default: row=0; col=0; end=15; right=False

Block **clearScreen** ()

Block **setCursor** (row, col)
* *row*: Zeile 0 oder 1; *col*: Spalte 0..15
* Parameter optional, default: row=0; col=0

Block **writeLCD** (text)
* schreibt an aktuelle Cursorposition
* *text*: Text, alle Datentypen werden mit str() konvertiert

Block **setDisplay** (displayOn:boolean, cursorOn:boolean, blinkOn:boolean)

#### oled.py

> OLED Displays zeigen 128x64 oder 128x128 Pixel an. Alle Pixel werden zuerst in Variablen gespeichert. Dieser Speicher wird 'Matrix' genannt.
> Um die 'Matrix' auf dem OLED Display anzuzeigen, muss immer der Block **displayMatrix** aufgerufen werden.

Block **initOLED** (display:boolean optional)
* Parameter *display*: Auswahl Display (I²C-Adresse) None oder False: 0x3C; True: 0x3D
* initialisiert die Matrix: Variablen zum Speichern der Pixel (1024 oder 2048 Byte)
* initialisiert das Display mit der angegebenen I²C-Adresse 0x3C oder 0x3D (Lötbrücke)

> Wenn zwei Displays angeschlossen sind, muss der Block **initOLED** zweimal aufgerufen werden, mit False und True.
> Es gibt nur eine Matrix, die mit dem folgenden Block an ein bestimmtes Display gesendet werden kann.

Block **displayMatrix** (fromPage, toPage, display) → alle Parameter optional
* Ist immer aufzurufen, wenn das in die Matrix gezeichnete Bild auf dem Display angezeigt werden soll. Fehlen die Parameter, wird das komplette Display über den I²C-Bus neu geschrieben (1KB oder 2KB Pixel).
* Mit den optionalen Parametern *fromPage*, *toPage* ist es möglich, nur einen Teil des Displays zu aktualisieren. Eine 'Page' ist eine Zeile 8 Pixel hoch, 128 Pixel breit, füllt also die gesamte Breite des Displays. Das 128x64 Display hat 8 Zeilen (0-7), das 128x128 Display hat 16 Zeilen (0-15).
* Der Parameter *display* bestimmt, an welches OLED Display die Matrix gesendet wird.

> Die folgenden Blöcke ändern nur die Pixel in der Matrix, nicht das Display.

Block **clearMatrix** (fromPage, toPage) → alle Parameter optional
* *fromPage*: 0..7, default: 0
* *toPage*: 0..7 bzw. 0..15, default 7 bzw. 15

Block **setPixel** (x, y, pixel)
* *pixel*: schaltet ein Pixel (in der Matrix) True:EIN oder False:AUS. 
* Für die Koordinate *x* sind Werte von 0 (links) bis 127 (rechts) möglich.
* Für die Koordinate *y* sind Werte von 0 (oben) bis 63 bzw. 127 (unten) möglich.

Block **writeMatrix** (row, col, text)

> Um Text mit Pixeln zu zeichnen, muss der EEPROM angeschlossen und der Zeichensatz programmiert sein. Pro Zeichen werden 8 Byte vom EEPROM in die Matrix kopiert.

* *row*: Zeile 0..7 bzw. 0..15; *col*: Spalte 0..15
* *text*: Text, alle Datentypen werden mit str() konvertiert
* Parameter optional, default: row=0; col=0

Block **paintEEPROM** (eepromStartadresse, fromPage, toPage) → alle Parameter optional
* *eepromStartadresse*: 0x0000..0xFFFF; default 0xF800 (Anfang vom Zeichensatz)
* *fromPage*: 0..7, default: 0; *toPage*: 0..7 bzw. 0..15, default 7 bzw. 15
* Kopiert aus dem EEPROM pro 'Page' 128 Byte in die Matrix.
* Ohne Parameter wird der gesamte Zeichensatz vom EEPROM in die Matrix kopiert.
* Im EEPROM können Bilder, die das ganze Display füllen, gespeichert werden.

#### oled_geometrie.py

Block **oled_line** (x0, y0, x1, y1, pixel)
* Zeichnet eine Linie mit den angegebenen Koordinaten. Mit *pixel* False werden die Pixel gelöscht.

Block **oled_rectangle** (x0, y0, x1, y1, pixel)
* Zeichnet ein Rechteck mit den angegebenen Koordinaten. Mit *pixel* False werden die Pixel gelöscht.

Block **oled_circle** (x0, y0, radius, pixel)
* Zeichnet einen Kreis um den Mittelpunkt *x0*, *y0*. Mit *pixel* False werden die Pixel gelöscht.

Block **oled_minute** (minute, x, y, l0, l1, pixel)
* Der Parameter *minute* bestimmt die Richtung (den Winkel) der Linie vom Mittelpunkt *x*, *y* (auf dem Zifferblatt einer Uhr).
* Der Zeiger muss nicht im Mittelpunkt beginnen. Die Parameter Linie *l1*, *l2* bestimmen Anfang und Ende des Zeigers (vom Mittelpunkt in Pixeln).
* Mit *pixel* False kann der Zeiger auch wieder gelöscht werden.

Block **oled_hour** (hour, x, y, l0, l1, pixel)
* Funktioniert wie **oled_minute**, allerdings sind hier nicht 60, sondern 12 Positionen des Zeigers möglich.

Block **oled_clock** (x, y, radius, hour, minute)
* Zeichnet eine analoge Uhr. *hour* und *minute* geben die Stellung der Uhrzeiger an.
