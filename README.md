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
[keyboard](#keyboardpy)|<code>0x5F</code>|[M5Stack Card Keyboard](https://docs.m5stack.com/en/unit/cardkb_1.1)|2
[lcd16x2](#lcd16x2py)|<code>0x3E</code>|[Grove - LCD Display 16x2 Zeichen](https://wiki.seeedstudio.com/Grove-16x2_LCD_Series)|1, 2, 3
[oled](#oledpy)|<code>0x3C 0x3D</code>|OLED Displays [128x128](https://wiki.seeedstudio.com/Grove-OLED-Display-1.12-SH1107_V3.0), [128x64](https://wiki.seeedstudio.com/Grove-OLED-Yellow&Blue-Display-0.96-SSD1315_V1.0)|8, 9, 10, 11
[oled_geometrie](#oled_geometriepy)||Blöcke für Linien und Kreise|8, 10, 11
[qwiiceeprom](#qwiiceeprompy)|<code>0x50</code>|[SparkFun Qwiic EEPROM - 512Kbit](https://www.sparkfun.com/products/18355)|9, 10
[qwiicgpio](#qwiicgpiopy)|<code>0x27</code>|[SparkFun Qwiic GPIO](https://www.sparkfun.com/products/17047)|5
[qwiicjoystick](#qwiicjoystickpy)|<code>0x20</code>|[SparkFun Qwiic Joystick](https://www.sparkfun.com/products/15168)|6, 14, 15
[qwiickeypad](#qwiickeypadpy)|<code>0x4B</code>|[SparkFun Qwiic Keypad 12 Tasten](https://www.sparkfun.com/products/15290)|4, 5
[qwiiclcd](#qwiiclcdpy)|<code>0x72</code>|Qwiic LCD Displays [20x4](https://www.sparkfun.com/products/16398), [16x2](https://www.sparkfun.com/products/16396)|4, 5, 6
[qwiicmotor](#qwiicmotorpy)|<code>0x5D 0x5E</code>|[SparkFun Qwiic Motor Driver](https://www.sparkfun.com/products/15451)|14, 15
[qwiicrelay](#qwiicrelaypy)|<code>0x1E</code>|[SparkFun Qwiic Single Relay](https://www.sparkfun.com/products/15093)|Hauptprogramm
[rtc](#rtcpy)|<code>0x51</code>|[Grove - RTC (Real Time Clock)](https://wiki.seeedstudio.com/Grove_High_Precision_RTC)|1, 4, 10

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

Block **readKeyboard** () : Byte
* gibt zurück: 0 wenn keine Taste gedrückt, sonst ASCII-Code der gedrückten Taste

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

Block **initOLED** (select_oled:boolean optional)
* Parameter *select_oled*: Auswahl Display (I²C-Adresse) None oder False: 0x3C; True: 0x3D
* initialisiert die Matrix: Variablen zum Speichern der Pixel (1024 oder 2048 Byte)
* initialisiert das Display mit der angegebenen I²C-Adresse 0x3C oder 0x3D (Lötbrücke)

> Wenn zwei Displays angeschlossen sind, muss der Block **initOLED** zweimal aufgerufen werden, mit False und True.
> Es gibt nur eine Matrix, die mit dem folgenden Block an ein bestimmtes Display gesendet werden kann.

Block **displayMatrix** (fromPage, toPage, select_oled) → alle Parameter optional
* Immer aufrufen, um das in die Matrix gezeichnete Bild auf dem Display anzuzeigen.
* Ohne Parameter wird das komplette Display über den I²C-Bus neu geschrieben.
* Mit den optionalen Parametern *fromPage*, *toPage* ist es möglich, nur einen Teil des Displays zu aktualisieren. Eine 'Page' ist eine Zeile 8 Pixel hoch und 128 Pixel breit (gesamte Breite des Displays).
* Das 128x64 Display hat 8 Zeilen (0-7). Das 128x128 Display hat 16 Zeilen (0-15).
* Der Parameter *select_oled* bestimmt, an welches OLED Display die Matrix gesendet wird.

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
* Zeichnet eine Linie mit den angegebenen Koordinaten in die Matrix.
* Parameter wie oben **setPixel**.

Block **oled_rectangle** (x0, y0, x1, y1, pixel)
* Zeichnet ein Rechteck mit den angegebenen Koordinaten in die Matrix.

Block **oled_circle** (x0, y0, radius, pixel)
* Zeichnet einen Kreis um den Mittelpunkt *x0*, *y0* in die Matrix.

Block **oled_minute** (minute, x, y, l0, l1, pixel)
* zeichnet Uhrzeiger in die Matrix: 60 Positionen (Winkel vom Mittelpunkt)
* *minute*: 0..59 Winkel der Linie vom Mittelpunkt *x*, *y*
* *l0*, *l1* Länge des Zeigers (Anfang und Ende vom Mittelpunkt in Pixeln)
* Parameter *x*, *y*, *pixel* wie oben **setPixel**

Block **oled_hour** (hour, x, y, l0, l1, pixel)
* wie **oled_minute** mit *hour*: 0..23

Block **oled_clock** (x, y, radius, hour, minute)
* Zeichnet eine analoge Uhr. *hour* und *minute* geben die Stellung der Uhrzeiger an.

#### qwiiceeprom.py

Block **readEEPROM** (adr16Bit, read_length) : Liste der Bytes
* *adr16Bit*: 0x0000..0xFFFF
* *read_length*: Anzahl zu lesender Bytes (**nicht** auf 32 begrenzt)
* die zurück gegebene Liste kann mit `Datenstrukturen`**in der Liste** gelesen werden

Block **testEEPROM** ()
* Testet, ob der ASCII Zeichensatz im EEPROM programmiert ist.
* Schreibt Bytes in Konsole: ['0x3e', '0x51', '0x49', '0x45', '0x3e'].
* F900-FBFF (Speicherbereich der ASCII Zeichen) kann im Code geändert werden.

#### qwiicgpio.py

Block **setGPIO** (IO, INV)
* beide Parameter *IO*, *INV*: String mit 8 Binärziffern (0 oder 1)
* *IO*: CONFIGURATION 0=output 1=input
* *INV*: INVERSION 0=original polarity; 1=inverted (nur bei *IO*=1)
* *INV*=1: Pin an GND (0V) -> logische 1
* Beispiel:\
**setGPIO**('00000011', '00000000'): 6 output und 2 input\
**setGPIO**('11111111', '11111111'): alle 8 Pins input inverted
* für Taster als input Pull Up Widerstände (10 kOhm) an 3V3 erforderlich
* ACHTUNG: GPIO INPUT und OUTPUT hat 3,3 Volt Pegel!

Block **readGPIO** () : Byte
* gibt 1 Byte zurück, 1 Bit pro GPIO Pin
* an input Pins max. 3,3 Volt Spannung anschließen!

Block **writeGPIO** (byte)
* *byte*: schaltet GPIO Pins, die als 0=output konfiguriert sind
* Bit=0: 0Volt; Bit=1: 3,3Volt

#### qwiicjoystick.py

Block **readJoystick** ()
* Liest alle Joystick Register über den I²C-Bus in Variable JOYSTICK_BUFFER.
* Muss am Anfang jeder Schleife aufgerufen werden.

> Die folgenden Blöcke lesen nur die Variable JOYSTICK_BUFFER, nicht den I²C-Bus.

Block **getJoystickX** () : Byte

Block **getJoystickY** () : Byte
* gibt 1 Byte zurück mit der Stellung des Joystick in X bzw. Y Richtung
* Mittelstellung ist 128, geringe Abweichung durch Hardware Toleranz
* Endstellung unten bzw. links = 0; oben bzw. rechts = 255

Block **getJoystickButtonPosition** () : Boolean
* gibt True zurück, wenn der Joystick jetzt gerade gedrückt ist

Block **getJoystickButtonOnOff** () : Boolean
* wechselt False / True bei jedem Drücken des Joystick

#### qwiickeypad.py

Block **readKeypad** () : Byte
* gibt zurück: 0 wenn keine Taste gedrückt, sonst ASCII-Code der gedrückten Taste
* Keypad hat 12 Tasten: '0'=48 ... '9'=57 .. '#'=35 .. '*'=42
