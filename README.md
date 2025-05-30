
[I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[Programmierbeispiele](https://elssner.github.io/ft-Controller-I2C/#beispielepy) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Programmierung, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)

### Robo Pro Coding Blöcke für fischertechnik RX und TXT 4.0 Controller zur Programmierung eigener I²C Module.

Das Beispiel Projekt mit Blöcken für TXT 4.0 Controller ist im [fischertechnik GitLab](https://git.fischertechnik-cloud.com/i2c) veröffentlicht. <ins>Es kann für RX Controller konvertiert werden.</ins>
Alle I²C-Module und Programmierbeispiele auf dieser Seite wurden mit dem TXT 4.0 Controller und auch mit dem RX Controller getestet.

Mit der [App Robo Pro Coding](https://www.fischertechnik.de/de-de/apps-und-software#apps) kann das Projekt ohne Anmeldung von fischertechnik GitLab geladen werden. Dazu bleibt das Zugriffstoken leer und auf der nächsten Seite im Suchfeld kann `i2c` eingegeben werden. Der Name `ft_Controller_I2C` kann noch Versionsinformationen enthalten. Das Projekt kann dann lokal als .ft-Datei gespeichert werden.

#### Im Projekt enthaltene Quellcodedateien (Blöcke) für I²C Module.

Für eigene Projekte können aus der lokal gespeicherten .ft-Datei die Quellcodedateien für die angeschlossenen I²C Module importiert werden. Die Datei [i2cCode](#i2ccodepy) muss immer mit importiert werden. Die Datei [advanced](#advancedpy) enthält keine I²C spezifischen Blöcke, ist aber zu empfehlen. Aus der Datei [Beispiele](#beispielepy) könnte nur ein einzelner Block [Tabelle 2](#tabelle-2) übernommen werden. Alle anderen Quellcodedateien [Tabelle 1](#tabelle-1) sind bestimmten I²C Modulen zugeordnet.

###### Tabelle 1:
* Quellcodedateien mit Link zur Beschreibung der Blöcke (auf dieser Seite unten).
* I²C Module mit Link zur Hersteller Webseite mit Bild und Dokumentation.
* Nummern der Programmierbeispiele in [Tabelle 3](#tabelle-3), welche diese Module verwenden.

Quellcodedatei|I²C-Adresse|I²C Module|Beispiel Tabelle 3
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

#### Hauptprogramm
* Mit Drahtbrücken an den Eingängen `I8 I7 I6 I5` kann der Start eines bestimmten Programmierbeispiels codiert werden. [Tabelle 2](#tabelle-2) zeigt die Codierung der Eingänge.
* Beispiel 0 ruft **i2cScan** auf und zeigt die gefundenen I²C-Adressen in der Konsole an.
* Alle anderen Beispiele können nach Übertragung des Programms auf dem Controller (ohne Verbindung zur App) gestartet werden. Nur Module und Drahtbrücken umstecken.

###### Tabelle 2:
* Codierung der Eingänge, um ein Beispiel von Hauptprogramm zu starten.
* Name des Beispiel-Blocks und aufgerufende I²C Quellcodedateien aus [Tabelle 1](#tabelle-1).

`I8`|`I7`|`I6`|`I5`|Beispiel (Block)|Quellcodedateien, I²C Module
---|---|---|---|---|---
`0`|`0`|`0`|`0`|**i2cScan**|[i2cCode](#i2ccodepy) (immer erforderlich)
`0`|`0`|`0`|`1`|**grovelcd_rtc**|[lcd16x2](#lcd16x2py), [rtc](#rtcpy)
`0`|`0`|`1`|`0`|**grovelcd_keyboard**|[lcd16x2](#lcd16x2py), [keyboard](#keyboardpy)
`0`|`0`|`1`|`1`|**grovelcd_dipswitch**|[lcd16x2](#lcd16x2py), [dipswitch](#dipswitchpy)
`0`|`1`|`0`|`0`|**qlcd_rtc_keypad**|[qwiiclcd](#qwiiclcdpy), [rtc](#rtcpy), [qwiickeypad](#qwiickeypadpy)
`0`|`1`|`0`|`1`|**qlcd_gpio_keypad**|[qwiiclcd](#qwiiclcdpy), [qwiicgpio](#qwiicgpiopy), [qwiickeypad](#qwiickeypadpy)
`0`|`1`|`1`|`0`|**qlcd_joystick**|[qwiiclcd](#qwiiclcdpy), [qwiicjoystick](#qwiicjoystickpy)
`0`|`1`|`1`|`1`||
`1`|`0`|`0`|`0`|**oled_zeichnen**|[oled](#oledpy), [oled_geometrie](#oled_geometriepy)
`1`|`0`|`0`|`1`|**oled_eeprom_copy**|[oled](#oledpy), [qwiiceeprom](#qwiiceeprompy)
`1`|`0`|`1`|`0`|**oled_eeprom_rtc**|[oled](#oledpy), [oled_geometrie](#oled_geometriepy), [qwiiceeprom](#qwiiceeprompy), [rtc](#rtcpy)
`1`|`0`|`1`|`1`|**oled2_systemtime**|[oled](#oledpy), [oled_geometrie](#oled_geometriepy), [advanced](#advancedpy)
`1`|`1`|`0`|`0`||
`1`|`1`|`0`|`1`||
`1`|`1`|`1`|`0`|**joy_2motoren**|[qwiicjoystick](#qwiicjoystickpy), [qwiicmotor](#qwiicmotorpy)
`1`|`1`|`1`|`1`|**joy_4motoren**|[qwiicjoystick](#qwiicjoystickpy), [qwiicmotor](#qwiicmotorpy)

#### Beispiele.py
* Programmierbeispiele für die Nutzung mehrerer I²C Module gleichzeitig.

###### Tabelle 3:

n|Beispiel (Block)|Beschreibung
---|---|---
0|**i2cScan**
1|**grovelcd_rtc**|Grove LCD 16x2 zeigt Uhrzeit und Datum an.
2|**grovelcd_keyboard**|Grove LCD 16x2 schreiben mit Card Keyboard (50 Tasten).
3|**grovelcd_dipswitch**|Grove LCD 16x2 mit 6 DIP Schaltern oder 5-Way Switch.
4|**qlcd_rtc_keypad**|Qwiic LCD 16x2 oder 20x4 Uhr stellen und anzeigen.
5|**qlcd_gpio_keypad**|Qwiic LCD 16x2 oder 20x4 8 Bit Zeichencode Eingabe mit GPIO.
6|**qlcd_joystick**|Qwiic LCD 16x2 oder 20x4 zeigt Joystick Positionen an.
7||
8|**oled_zeichnen**|OLED 128x64 oder 128x128 Linien und Kreise anzeigen.
9|**oled_eeprom_copy**|OLED 128x64 oder 128x128 Zeichensatz aus EEPROM anzeigen.
10|**oled_eeprom_rtc**|OLED 128x64 oder 128x128 Datum, Uhrzeit digital und analog.
11|**oled2_systemtime**|2 OLED Displays, verschiedener Inhalt, Analoguhr System-Zeit.
12||
13||
14|**joy_2motoren**|2 Motoren (1 Modul) mit Joystick steuern.
15|**joy_4motoren**|4 Motoren (2 Module) mit Joystick umschalten und steuern.


### I²C

I²C: Inter-Integrated Circuit → [de.wikipedia.org/wiki/I²C](https://de.wikipedia.org/wiki/I%C2%B2C)

###### I²C Hardware

* An einen I²C-Bus mit 4 Leitungen `SDA, SCL, -, +` (hier 3,3V) können mehrere I²C Module gleichzeitig angeschlossen werden (hintereinander gesteckt oder mit I²C Hub).
* Die I²C Module müssen verschiedene 7-Bit I²C Adressen haben.
* Die Anzahl gleichzeitig angeschlossener Module ist aus elektrischen Gründen begrenzt.
* Qwiic Module haben immer 3,3V Logik und sind hervorragend geeignet.
* Grove Module mit 3,3V/5V verabschieden sich zuerst, wenn mehrere am I²C-Bus sind.
* M5Stack und andere Module mit 5V und müssen getestet werden.
* TXT 4.0 Controller verträgt am I²C-Bus mehr Module gleichzeitig als der RX Controller.

[6-pin Steckverbinder](https://www.conrad.de/de/p/fci-75867-131lf-pfosten-steckverbinder-rastermass-2-54-mm-polzahl-gesamt-6-anzahl-reihen-2-1-st-1401777.html) | [Qwiic Adapter](https://www.sparkfun.com/sparkfun-qwiic-adapter.html) | [Qwiic Cable - Grove Adapter](https://www.sparkfun.com/qwiic-cable-grove-adapter-100mm.html) | [Qwiic Cable Kit](https://www.sparkfun.com/sparkfun-qwiic-cable-kit.html)

###### I²C Software

* I²C kennt nur 2 Funktionen:\
**an eine I²C-Adresse Bytes senden** oder **von einer I²C-Adresse Bytes empfangen**
* Es gibt noch eine Kombination aus beiden und i2cScan soll alle Module am Bus finden.
* Die Anzahl über den I²C-Bus übertragener Bytes ist **nicht** auf 32 Byte begrenzt.

> [RX Controller nutzt CircuitPython](https://github.com/fischertechnik/RX-Controller-I2C), [TXT 4.0 Controller nutzt Python3](https://github.com/fischertechnik/TXT40-Controller-I2C). Beide unterstützen I²C, aber völlig verschieden.
> Die I²C Blöcke hier sind **plattformunabhängig** programmiert. Die Python Implementation wird erkannt und dann der entsprechende Code ausgeführt.

#### i2cCode.py

Block **i2cWriteBuffer** (i2cAdr, write_buffer)

* Sendet alle Bytes aus der Liste *write_buffer* an die *i2cAdr*.
* *i2cAdr*: 7 Bit (0x00..0x7F bzw. 0..127)
* *write_buffer*: Liste darf nur 8-Bit Elemente (0x00..0xFF bzw. 0..255) enthalten.
* Parameter *write_buffer* kann mit `Datenstrukturen`**erzeuge Liste** übergeben werden.

Block **i2cReadBuffer** (i2cAdr, length) : Liste der Bytes

* Empfängt Bytes von der *i2cAdr*, *length* ist die Anzahl der Bytes.
* Die zurück gegebene Liste kann mit `Datenstrukturen`**in der Liste** gelesen werden.

Block **i2cWriteReadBuffer** (i2cAdr, write_buffer, read_length) : Liste der Bytes

* Sendet und empfängt Bytes, ohne dazwischen den I²C-Bus frei zu geben.
* Erlaubt I²C Register adressieren und lesen mit nur einer Funktion.

Block **i2cScan** () : Liste der 7-Bit I²C-Adressen

* Versucht alle möglichen I²C-Adressen in einer Schleife zu erreichen.
* Wenn read oder write erfolgreich ist, wird die gültige I²C Adresse in einer Liste gesammelt.
* Die zurück gegebene Liste kann mit `Text` **gib aus** in der Konsole angezeigt werden.
* Es können Fehler auftreten, die Aus- und Einschalten des Controllers erfordern.

Block **isRX** () : boolean

* Gibt True zurück, wenn `sys.implementation.name == 'circuitpython'`.
* True: circuitpython import board, busio, (adafruit) I2CDevice
* False: Python3 from smbus2 import SMBus, i2c_msg


### Beschreibung der Quellcodedateien (alphabetisch geordnet)
Inhaltsverzeichnis: [Tabelle 1](#tabelle-1)

#### advanced.py

> Allgemeine Blöcke, die Python-Funktionen bereit stellen (ohne I²C Bezug).\
**Kommentar**, **Int**, **Ord**, **Chr**, **print_bin**, **encode_string**, **decode_string**, **list_string**, **list_hex**, **system_time**

Block **system_time** () : Liste mit 9 Elementen
* TXT 4.0: RTC Systemuhr (year, mon, mday, hour, min, sec, wday, yday, isdst)\
Uhr wird bei Internetverbindung gestellt, Zeitzone Germany am Controller einstellen.
* RX: Zeitstempel umgerechnet in (0, 0, 0, hour, min, sec, 0, 0, 0)

#### dipswitch.py
###### [Grove - 6-Position DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch) | [Grove - 5-Way Switch](https://wiki.seeedstudio.com/Grove-5-Way_Switch)
Block **readSwitch** () : Byte
* Gibt 1 Byte zurück: 6 Bit (0..63), 1 Bit pro DIP Schalter.

#### keyboard.py
###### [M5Stack Card Keyboard QWERTY 50-key](https://docs.m5stack.com/en/unit/cardkb_1.1)
Block **readKeyboard** () : Byte
* Gibt 0 zurück wenn keine Taste gedrückt, sonst ASCII-Code der gedrückten Taste.

#### lcd16x2.py
###### [Grove - LCD Display 16x2 Zeichen](https://wiki.seeedstudio.com/Grove-16x2_LCD_Series) | Black on Yellow | Black on Red | White on Blue
Block **initLCD** ()
* Muss einmal beim Start aufgerufen werden.

Block **writeText** (row, col, end, text, right)
* Schreibt an eine bestimmte Position Text mit fester Länge.
* *row*: Zeile 0 oder 1; *col*: Spalte 0..15; *end*: Spalte 0..15 (letztes Zeichen)
* *text*: Text, alle Datentypen werden mit str() konvertiert.
* *right*: None oder False=linksbündig; True=rechtsbündig\
Text wird mit Leerzeichen auf die Länge (end-col)+1 aufgefüllt.
* Parameter außer *text* können weg gelassen werden (None)\
default: *row*=0; *col*=0; *end*=15; right=False

Block **clearScreen** ()
* Löscht das LCD Display.

Block **setCursor** (row, col)
* Set Cursor für writeLCD oder wenn Cursor sichtbar ist oder blinkt.
* *row*: Zeile 0 oder 1; *col*: Spalte 0..15
* Parameter optional, default: *row*=0; *col*=0

Block **writeLCD** (text)
* Schreibt *text* an aktuelle Cursorposition.
* Alle Datentypen werden mit str() konvertiert.

Block **setDisplay** (displayOn, cursorOn, blinkOn)
* Alle Parameter boolean: False oder True
* Schaltet das Display, Cursor und blinkenden Cursor an und aus.

#### oled.py
###### [Grove - OLED Display 1.12 (128x128)](https://wiki.seeedstudio.com/Grove-OLED-Display-1.12-SH1107_V3.0) | [OLED Yellow&Blue Display 0.96 (128x64)](https://wiki.seeedstudio.com/Grove-OLED-Yellow&Blue-Display-0.96-SSD1315_V1.0) | [OLED Display 0.96](https://wiki.seeedstudio.com/Grove-OLED_Display_0.96inch)
> OLED Displays zeigen 128x64 oder 128x128 Pixel an. Alle Pixel werden zuerst in Variablen gespeichert. Dieser Speicher wird 'Matrix' genannt.
> Um die 'Matrix' auf dem OLED Display anzuzeigen, muss immer der Block **displayMatrix** aufgerufen werden.

Block **initOLED** (select_oled:Boolean) → Parameter optional
* Muss einmal beim Start aufgerufen werden.
* *select_oled*: Auswahl Display (I²C-Adresse) None oder False: 0x3C; True: 0x3D.
* Initialisiert die Matrix: Variablen zum Speichern der Pixel (1024 oder 2048 Byte).
* Initialisiert das Display mit der angegebenen I²C-Adresse 0x3C oder 0x3D (Lötbrücke).

> Wenn zwei Displays angeschlossen sind, muss der Block **initOLED** zweimal aufgerufen werden, mit False und True.
> Es gibt nur eine Matrix, die mit dem folgenden Block auf einem bestimmten Display angezeigt werden kann.

Block **displayMatrix** (fromPage, toPage, select_oled) → alle Parameter optional
* Immer aufrufen, um das in die Matrix gezeichnete Bild auf dem Display anzuzeigen.
* Ohne Parameter wird das komplette Display über den I²C-Bus neu geschrieben.
* Mit den optionalen Parametern *fromPage*, *toPage* ist es möglich, nur einen Teil des Displays zu aktualisieren. Eine 'Page' ist eine Zeile 8 Pixel hoch und 128 Pixel breit (gesamte Breite des Displays).
* Das 128x64 Display hat 8 Zeilen (0-7). Das 128x128 Display hat 16 Zeilen (0-15).
* Der Parameter *select_oled* bestimmt, an welches OLED Display die Matrix gesendet wird.

> <ins>Die folgenden Blöcke ändern nur die Pixel in der Matrix, nicht das Display.</ins>

Block **clearMatrix** (fromPage, toPage) → alle Parameter optional
* *fromPage*: 0..7, default: 0
* *toPage*: 0..7 bzw. 0..15, default 7 bzw. 15

Block **setPixel** (x, y, pixel)
* *pixel*: schaltet ein Pixel (in der Matrix) True:EIN oder False:AUS. 
* Für die Koordinate *x* sind Werte von 0 (links) bis 127 (rechts) möglich.
* Für die Koordinate *y* sind Werte von 0 (oben) bis 63 bzw. 127 (unten) möglich.

Block **writeMatrix** (row, col, text)
###### erforderlich: [qwiiceeprom](#qwiiceprompy)
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
###### erforderlich: [oled](#oledpy)
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
###### [SparkFun Qwiic EEPROM Breakout - 512Kbit](https://www.sparkfun.com/products/18355)
Block **readEEPROM** (adr16Bit, read_length) : Liste der Bytes
* *adr16Bit*: 0x0000..0xFFFF
* *read_length*: Anzahl zu lesender Bytes (**nicht** auf 32 begrenzt)
* die zurück gegebene Liste kann mit `Datenstrukturen`**in der Liste** gelesen werden

Block **testEEPROM** ()
* Testet, ob der ASCII Zeichensatz im EEPROM programmiert ist.
* Speicherbereich der ASCII Zeichen F900-FBFF kann im Code geändert werden.
* Schreibt Bytes in Konsole: ['0x3e', '0x51', '0x49', '0x45', '0x3e'].

#### qwiicgpio.py
###### [SparkFun Qwiic GPIO](https://www.sparkfun.com/products/17047)
Block **setGPIO** (IO, INV)
* Muss einmal beim Start aufgerufen werden.
* Beide Parameter *IO*, *INV*: String mit 8 Binärziffern (0 oder 1).
* Jede Binärziffer (Bit) ist einem von 8 Pins zugeordnet.
* *IO* CONFIGURATION Bit: 0=output Pin; 1=input Pin
* *INV* INVERSION Bit: 0=original polarity; 1=inverted
* INVERSION wirkt nur auf input Pins → Pin an GND → logische 1
* Beispiel:\
**setGPIO**('00000011', '00000000'): 6 output und 2 input\
**setGPIO**('11111111', '11111111'): alle 8 Pins input inverted
* ACHTUNG! GPIO INPUT und OUTPUT hat 3,3 Volt Pegel!

Block **readGPIO** () : Byte
* Gibt 1 Byte zurück, 1 Bit pro GPIO Pin.
* An input Pins max. 3,3 Volt Spannung anschließen!
* Taster schalten Pin an GND; Pull Up Widerstände (10 kOhm) an 3V3 erforderlich.

Block **writeGPIO** (byte)
* *byte*: Schaltet 8 GPIO Pins, die als 0=output konfiguriert sind.
* Bit=0: aus (0 Volt); Bit=1: an (3,3 Volt)

#### qwiicjoystick.py
###### [SparkFun Qwiic Joystick](https://www.sparkfun.com/products/15168)
Block **readJoystick** ()
* <ins>Muss am Anfang jeder Schleife aufgerufen werden.</ins>
* Liest alle Joystick Register über den I²C-Bus in Variable JOYSTICK_BUFFER.

> <ins>Die folgenden Blöcke **get** lesen nur die Variable, nicht den I²C-Bus.</ins>

Block **getJoystickX** () : Byte\
Block **getJoystickY** () : Byte
* Gibt 1 Byte zurück mit der Stellung des Joystick in X bzw. Y Richtung.
* Mittelstellung ist 128, geringe Abweichung durch Hardware Toleranz.
* Endstellung unten bzw. links = 0; oben bzw. rechts = 255.

Block **getJoystickButtonPosition** () : Boolean
* Gibt True zurück, wenn der Joystick jetzt gerade gedrückt ist.

Block **getJoystickButtonOnOff** () : Boolean
* Wechselt False / True bei jedem Drücken des Joystick.

#### qwiickeypad.py
###### [SparkFun Qwiic Keypad - 12 Tasten](https://www.sparkfun.com/products/15290)
Block **readKeypad** () : Byte
* Gibt 0 zurück wenn keine Taste gedrückt, sonst ASCII-Code der gedrückten Taste.
* Keypad hat 12 Tasten: '0'=48 ... '9'=57 .. '#'=35 .. '*'=42

#### qwiiclcd.py
###### [SparkFun Qwiic 20x4 SerLCD - RGB Backlight](https://www.sparkfun.com/products/16398) | [SparkFun Qwiic 16x2 SerLCD - RGB Backlight](https://www.sparkfun.com/products/16396)
Block **initQLCD** ()
* Muss einmal beim Start aufgerufen werden.
* Im Code kann die Größe des Display 16x2 oder 20x4 (COLS x ROWS) konfiguriert werden.

Block **writeQText** (row, col, end, text, right)
* Schreibt an eine bestimmte Position Text mit fester Länge.
* *row*: Zeile 0..3; *col*: Spalte 0..19; *end*: Spalte 0..19 (letztes Zeichen)
* *text*: Text, alle Datentypen werden mit str() konvertiert.
* *right*: None oder False=linksbündig; True=rechtsbündig\
Text wird mit Leerzeichen auf die Länge (end-col)+1 aufgefüllt.
* Parameter außer *text* können weg gelassen werden (None).\
default: *row*=0; *col*=0; *end*=COLS-1; right=False

Block **clearQScreen** ()
* Löscht das LCD Display.

Block **setQCursor** (row, col)
* Set Cursor für writeQLCD oder wenn Cursor sichtbar ist oder blinkt.
* *row*: Zeile 0..3; *col*: Spalte 0..19
* Parameter optional, default: *row*=0; *col*=0

Block **writeQLCD** (text)
* Schreibt *text* an aktuelle Cursorposition.
* Alle Datentypen werden mit str() konvertiert.
* Schreibt auf nächster Zeile weiter, max. Länge 32 Zeichen.

Block **setQDisplay** (displayOn, cursorOn, blinkOn)
* Alle Parameter boolean: False oder True.
* Schaltet das Display, Cursor und blinkenden Cursor an und aus.

#### qwiicmotor.py
###### [SparkFun Qwiic Motor Driver](https://www.sparkfun.com/products/15451)
Block **initMotor** (i2cAdr)
* Für jedes Motor-Modul einmal beim Start aufrufen (mit entsprechender *i2cAdr*).
* Parameter *i2cAdr* kann weg gelassen werden, default: 0x5D.
* 1 Modul steuert 2 Motoren, mehrere Module können gleichzeitig angeschlossen werden.
* 10 I²C-Adressen mit Lötbrücken einstellbar: 0x58..0x61.

Block **setMotorI2C** (i2cAdr)
* Ändert die I²C-Adresse für die folgenden Funktionen auf ein bestimmtes Motor-Modul.
* Wird nur bei mehreren angeschlossenen Qwiic Motor-Modulen benötigt.

Block **enableMotor** (on:Boolean)
* *on* schaltet Motor Power: True=an; False=aus (für 1 Modul = 2 Motoren).
* Power für H-Bridge soll bei längerem Stillstand aus geschaltet werden, um Energie zu sparen.

Block **driveMotorA** (speed:Byte)\
Block **driveMotorB** (speed:Byte)
* *speed* 0..128..255 Motor Drehzahl und Richtung.
* *speed* ist optional, default=128 (Stillstand).
* 0 max. rückwärts | ← 128 Stop → | 255 max. vorwärts

#### qwiicrelay.py
###### [SparkFun Qwiic Single Relay](https://www.sparkfun.com/products/15093)
Block **writeRelay** (on:Boolean)
* *on* schaltet Relais: True=an; False=aus.
* I2C_ADDRESS kann im Code geändert werden.

#### rtc.py
###### [Grove - High Precision RTC (Real Time Clock)](https://wiki.seeedstudio.com/Grove_High_Precision_RTC)

##### Uhr stellen

Block **writeRTC** (index, int8)
* Stellt die Uhr. Ändert ein bestimmtes Register *index*.
* `0`Seconds, `1`Minutes, `2`Hours, `3`Days, `4`Weekdays, `5`Months, `6`Years
* *int8*: 0..59 Byte wird in BCD konvertiert und im RTC-Modul gespeichert. 

Block **setRTC** (keyCode) : keyString
* Stellt die Uhr mit 5 ASCII Zeichen-Codes von Keypad oder Keyboard.
* Muss 5 mal mit ASCII Code aufgerufen werden, gibt den zusammengesetzten String zurück.\
  *1. Zeichen:* `*` neu, *2. Zeichen:* Register `0..6`,\
  *3. und 4. Zeichen:* 2 Ziffern dezimal `00..59`, *5. Zeichen:* `#` speichern
* Wenn 5 Zeichen gültig sind, wird mit **writeRTC** das Register geändert.
* Beispiel: `*120#`setzt Minute auf 20; `*401#` Montag; `*000#` Sekunde 0.

##### Uhr lesen

Block **readRTC** ()
* <ins>Muss am Anfang jeder Schleife aufgerufen werden.</ins>
* Liest 7 Byte in Variable RTC_BUFFER.
* BCD codiert: 4 Bit pro Ziffer, Bit `7654` Zehner, Bit `3210` Einer, Jahr 2-stellig

> <ins>Die folgenden Blöcke **get** lesen nur die Variable, nicht den I²C-Bus.</ins>

Block **getRTC** (index) : Byte
* Liest 1 Byte aus Variable RTC_BUFFER[*index*] zu dezimal konvertiert.
* `0`Seconds, `1`Minutes, `2`Hours, `3`Days, `4`Weekdays, `5`Months, `6`Years

Block **getTimeString** () : String 8 Zeichen
* Liest Zeit aus Variable RTC_BUFFER: `HH:mm:ss`.

Block **getDateString** () : String 10 Zeichen
* Liest Datum aus Variable RTC_BUFFER: `dd.MM.20yy`.

Block **getWeekday** () : String 2 Zeichen
* Liest Wochentag aus RTC_BUFFER: ['So', 'Mo', 'Di', 'Mi', 'Do', 'Fr', 'Sa'].
