
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](https://elssner.github.io/ft-Controller-I2C/examples)


### ROBO Pro Coding Blöcke für fischertechnik TXT 4.0 und RX Controller zur Programmierung eigener I²C Module.

Das Beispiel Projekt mit Blöcken für TXT 4.0 Controller ist im [fischertechnik GitLab](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C) veröffentlicht. <ins>Es kann für RX Controller konvertiert werden.</ins>
Alle I²C-Module und Programmierbeispiele auf dieser Seite wurden mit dem TXT 4.0 Controller und auch mit dem RX Controller getestet.

Mit der [App ROBO Pro Coding](https://www.fischertechnik.de/de-de/apps-und-software#apps) kann das Projekt ohne Anmeldung von fischertechnik GitLab geladen werden. 
Dazu bleibt das Zugriffstoken leer und auf der nächsten Seite im Suchfeld kann `i2c` eingegeben werden. Der Name ist `i2c / ft_Controller_I2C`. Das Projekt kann dann lokal als .ft-Datei gespeichert werden.

#### Im Projekt enthaltene Quellcodedateien (Blöcke) für I²C Module importieren.

Für eigene Projekte können aus der lokal gespeicherten .ft-Datei die Quellcodedateien importiert werden.
Die Datei [i2cCode](#i2ccodepy) muss immer mit importiert werden. Die Datei [advanced](#advancedpy) enthält keinen I²C spezifischen Code, aber Blöcke für nützliche Python Funktionen.\
Der Import muss mehrmals erfolgen: 
1. [i2cCode](#i2ccodepy) und optional [advanced](#advancedpy)
2. Quellcodedateien mit <code>I²C-Adresse</code>
3. Erweiterungen (für einfache Nutzung des I²C Moduls nicht erforderlich)
4. Beispiele


###### Tabelle 1:
* Quellcodedatei mit Link zur Beschreibung der Blöcke (auf dieser Seite unten).
* I²C Module mit Link zur Hersteller Webseite mit Bild und Dokumentation.
* (36) Quellcodedateien im GitLab Projekt [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C) 
  * (1) i2cCode
  * (22) mit <code>I²C-Adresse</code>: sind einem bestimmten I²C Modul zugeordnet.
  * (3) **Erweiterung**: zusätzliche Blöcke zum entsprechenden I²C Modul.
  * (10) [Beispiel](examples): Programmierbeispiel kann mehrere I²C Module betreffen.\
  Jedes Beispiel hat eine eigene GitHub Seite → [I²C Programmierbeispiele im Überblick](examples#tabelle-1).

Quellcodedatei|I²C-Adresse|I²C Module
---|---|---
[i2cCode](#i2ccodepy)||Python I²C für [RX](https://github.com/fischertechnik/RX-Controller-I2C) und [TXT 4.0](https://github.com/fischertechnik/TXT40-Controller-I2C)
[advanced](#advancedpy)|**Erweiterung**|Blöcke für fehlende / zusätzliche Funktionen
[dipswitch](#dipswitchpy)|<code>0x03</code>|[6-DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch), [5-Way Switch](https://wiki.seeedstudio.com/Grove-5-Way_Switch)
[keyboard](#keyboardpy)|<code>0x5F</code>|[M5Stack Card Keyboard](https://docs.m5stack.com/en/unit/cardkb_1.1)
[lcd16x2](#lcd16x2py)|<code>0x3E</code>|[Grove - LCD Display 16x2 Zeichen](https://wiki.seeedstudio.com/Grove-16x2_LCD_Series)
lcd16x2_keyboard_rtc|[Beispiel](lcd16x2_keyboard_rtc)|Grove LCD: Tastatur schreiben, Uhr, DIP Schalter
[oled](#oledpy)|<code>0x3C 0x3D</code>|OLED Displays [128x128](https://wiki.seeedstudio.com/Grove-OLED-Display-1.12-SH1107_V3.0), [128x64](https://wiki.seeedstudio.com/Grove-OLED-Yellow&Blue-Display-0.96-SSD1315_V1.0), [128x64](https://wiki.seeedstudio.com/Grove-OLED_Display_0.96inch/)
[oled_geometrie](#oled_geometriepy)|**Erweiterung**|Blöcke für Linien und Kreise
oled_text_analoguhr|[Beispiel](oled_text_analoguhr)|OLED Analoguhr, Text Zeichensatz aus EEPROM
[qwiicbutton](#qwiicbuttonpy)|<code>0x6F 0x6E</code>|[SparkFun Qwiic Button](https://www.sparkfun.com/products/16842)
qwiicbutton_int|[Beispiel](qwiicbutton_int)|2 I²C Buttons mit LED, /INT Ereignis, Optokoppler
[qwiicbutton_queue](#qwiicbutton_queuepy)|**Erweiterung**|Blöcke für Button Queue
[qwiiceeprom](#qwiiceeprompy)|<code>0x50</code>|[SparkFun Qwiic EEPROM - 512Kbit](https://www.sparkfun.com/products/18355)
[qwiicgpio](#qwiicgpiopy)|<code>0x27</code>|[SparkFun Qwiic GPIO](https://www.sparkfun.com/products/17047)
[qwiicjoystick](#qwiicjoystickpy)|<code>0x20</code>|[SparkFun Qwiic Joystick](https://www.sparkfun.com/products/15168)
[qwiickeypad](#qwiickeypadpy)|<code>0x4B</code>|[SparkFun Qwiic Keypad 12 Tasten](https://www.sparkfun.com/products/15290)
[qwiiclcd](#qwiiclcdpy)|<code>0x72</code>|Qwiic LCD Displays [20x4](https://www.sparkfun.com/products/16398), [16x2](https://www.sparkfun.com/products/16396), [16x2](https://www.sparkfun.com/products/16397)
qwiiclcd_keypad_rtc|[Beispiel](qwiiclcd_keypad_rtc)|LCD: Uhr stellen mit Keypad, GPIO-Tasten, Joystick
[qwiicmotor](#qwiicmotorpy)|<code>0x5D 0x5E</code>|[SparkFun Qwiic Motor Driver](https://www.sparkfun.com/products/15451)
qwiicmotor_joystick|[Beispiel](qwiicmotor_joystick)|2 oder 4 Motoren mit Joystick steuern
[qwiicmux](#qwiicmuxpy)|<code>0x70</code>|[SparkFun Qwiic Mux 8 Channel](https://www.sparkfun.com/products/16784)
qwiicmux_rx|[Beispiel](qwiicmux_rx)|RX mit I²C Multiplexer, 10 I²C Module
[qwiicopenlog](#qwiicopenlogpy)|<code>0x2A</code>|[SparkFun Qwiic OpenLog](https://www.sparkfun.com/products/15164) (Speicherkarte)
qwiicopenlog_rtc|[Beispiel](qwiicopenlog_rtc)|Dateien DIR, COPY, LOG mit Zeit aus RTC
[qwiicrelay](#qwiicrelaypy)|<code>0x18</code>|[SparkFun Qwiic Single Relay](https://www.sparkfun.com/products/15093)
[rtc](#rtcpy)|<code>0x51</code>|[Grove - RTC (Real Time Clock)](https://wiki.seeedstudio.com/Grove_High_Precision_RTC)
[s_co2](#s_co2py)|<code>0x62</code>|[Calliope CO2 Sensor - SCD40](https://calliope.cc/calliope-mini/erweiterungen/calliope-co2-sensor)
s_qwiic_distance|[Beispiel](s_qwiic_distance)|4 Abstands- und Nähesensoren, LCD 20x4
[s_qwiicinfrared](#s_qwiicinfraredpy)|<code>0x60</code>|[Proximity Sensor VCNL4040](https://www.sparkfun.com/products/15177)
[s_qwiiclaser](#s_qwiiclaserpy)|<code>0x29</code>|Laser Sensor [VL53L1X](https://www.sparkfun.com/products/14722), [VL53L4CD](https://www.sparkfun.com/products/18993)
[s_qwiictemp](#s_qwiictemppy)|<code>0x3C</code>|[Temperature Sensor - STTS22H](https://www.sparkfun.com/products/21273)
s_qwiictemp_lcd|[Beispiel](s_qwiictemp_lcd)|2 Temperatursensoren, LCD Display
[s_qwiictmp102](#s_qwiictmp102py)|<code>0x48</code>|[Temperature Sensor - TMP102](https://www.sparkfun.com/products/16304)
[s_qwiicultrasonic](#s_qwiicultrasonicpy)|<code>0x09</code>|[Ultrasonic Sensor HC-SR04](https://www.sparkfun.com/products/17777)
[wattmeter](#wattmeterpy)|<code>0x45</code>|[DFRobot Gravity Digital Wattmeter](https://www.dfrobot.com/product-1827.html)
wattmeter_co2_relay|[Beispiel](wattmeter_co2_relay)|Strom messen von CO₂ Sensor und I²C Relais


### I²C

> I²C: Inter-Integrated Circuit → [de.wikipedia.org/wiki/I²C](https://de.wikipedia.org/wiki/I%C2%B2C)

###### I²C Hardware

* <ins>Der I²C-Bus hat **3,3 Volt** Logik. Höhere Spannungen zerstören den **Controller** sofort!</ins>
* An einen I²C-Bus mit 4 Leitungen können mehrere I²C Module gleichzeitig angeschlossen werden: [Qwiic daisy chain](https://www.sparkfun.com/qwiic) oder [Grove - I2C Hub](https://wiki.seeedstudio.com/Grove-I2C_Hub/).
* [Anschlussbelegung](https://github.com/fischertechnik/TXT40-Controller-I2C) 6-pin: `1:+3,3V` `2:GND` `5:SCL` `6:SDA` (3 und 4 nichts anschließen).
* Die Anzahl gleichzeitig angeschlossener Module ist aus elektrischen Gründen begrenzt.
* Qwiic Module haben immer 3,3V Logik und sind hervorragend geeignet.
* Grove Module mit 3,3V/5V verabschieden sich zuerst, wenn mehrere am I²C-Bus sind.
* M5Stack und andere Module mit 5V und müssen getestet werden.
* RX Controller verträgt am I²C-Bus nur 2-3 I²C-Adressen gleichzeitig, TXT 4.0 viel mehr.
* Mit [I²C Multiplexer](#qwiicmuxpy) können auch [am RX mindestens 10 I²C Module](qwiicmux_rx) betrieben werden.

[6-pin Pfosten Stecker](https://www.conrad.de/de/p/fci-75867-131lf-pfosten-steckverbinder-rastermass-2-54-mm-polzahl-gesamt-6-anzahl-reihen-2-1-st-1401777.html) | [Qwiic Adapter](https://www.sparkfun.com/sparkfun-qwiic-adapter.html) | [Qwiic Cable - Grove Adapter](https://www.sparkfun.com/qwiic-cable-grove-adapter-100mm.html) | [Qwiic Cable Kit](https://www.sparkfun.com/sparkfun-qwiic-cable-kit.html)

###### I²C Module mit Hardware Interrupt

I²C Module, die eine Eingabe machen, müssen normalerweise in einer dauerhaft Schleife ständig über den I²C-Bus abgefragt werden, ob sich der Zustand geändert hat. 
Sensoren, Buttons, Keypad, GPIO und RTC haben einen zusätzlichen (Löt-) Interrupt-Pin /INT, der außerhalb vom I²C-Bus extra verdrahtet werden kann.

Die I²C Module haben 3,3V Logik, die fischertechnik Controller aber 9V Logik. Um die /INT Leitungen an einen Controller Input anzuschließen, wird ein Optokoppler empfohlen.\
Der Optokoppler hat am Ausgang einen Fototransistor. Die Controller können am Input einen Fototransistor digital hell/dunkel abfragen.

Somit kann beim **TXT 4.0 Controller** ![](ereignis_fototransistor.png) ausgelöst werden. Im Ereignis-Code → [buttons_event](examples#qwiicbutton_intpy) wird über den I²C-Bus das auslösende Modul gesucht und dessen /INT zurück gesetzt. → [buttons_interrupt](examples#qwiicbutton_intpy)\
Weil der **RX Controller** keine Ereignisse unterstützt, kann der Fototransistor hell/dunkel in einer Schleife abgefragt werden, was den I²C-Bus ebenfalls entlastet. → [buttons_polling](examples#qwiicbutton_intpy)

Die /INT Pins aller I²C Module können miteinander verbunden und als Minus an die LED im Optokoppler angeschlossen werden. Der + vom Optokoppler ist über einen Widerstand 220 Ohm mit +3,3V zu verbinden.
Ein 3V3 Löt-Pin ist an vielen I²C Modulen neben dem /INT vorhanden.\
**Die LED vom Optokoppler <ins>nicht</ins> an 9V anschließen!**


###### I²C Software

* Die I²C Module müssen verschiedene 7-Bit I²C-Adressen haben.
* I²C kennt nur 2 Funktionen:\
**an eine I²C-Adresse Bytes senden** oder **von einer I²C-Adresse Bytes empfangen**
* Es gibt noch eine Kombination aus beiden und i2c_scan soll alle Module am Bus finden.
* Die Anzahl über den I²C-Bus übertragener Bytes ist **nicht** auf 32 Byte begrenzt.

> [RX Controller nutzt CircuitPython](https://github.com/fischertechnik/RX-Controller-I2C), [TXT 4.0 Controller nutzt Python3](https://github.com/fischertechnik/TXT40-Controller-I2C). Beide unterstützen I²C, aber völlig verschieden.
> Die I²C Blöcke hier sind **plattformunabhängig** programmiert. Die Python Implementation wird erkannt und dann der entsprechende Code ausgeführt.

#### i2cCode.py

Block **i2c_write_buffer** (i2c_addr, write_buffer)

* Sendet alle Bytes aus der Liste *write_buffer* an die *i2c_addr*.
* *i2c_addr*: 7 Bit (0x00..0x7F bzw. 0..127)
* *write_buffer*: Liste darf nur 8-Bit Elemente (0x00..0xFF bzw. 0..255) enthalten.
* Parameter *write_buffer* kann mit `Datenstrukturen`**erzeuge Liste** übergeben werden.

Block **i2c_read_buffer** (i2c_addr, length) : Liste der Bytes

* Empfängt Bytes von der *i2c_addr*, *length* ist die Anzahl der Bytes.
* Die zurück gegebene Liste kann mit `Datenstrukturen`**in der Liste** gelesen werden.

Block **i2c_write_read_buffer** (i2c_addr, write_buffer, read_length) : Liste der Bytes

* Sendet und empfängt Bytes, ohne dazwischen den I²C-Bus frei zu geben.
* Erlaubt I²C Register adressieren und lesen mit nur einer Funktion.

<a name="i2c_scan"></a>
Block **i2c_scan** () : Liste der 7-Bit I²C-Adressen

* Versucht alle möglichen I²C-Adressen in einer Schleife zu erreichen.
* Wenn read oder write erfolgreich ist, wird die gültige I²C Adresse in einer Liste gesammelt.
* Die zurück gegebene Liste kann mit `Text` **gib aus** in der Konsole angezeigt werden.
* Es können Fehler auftreten, die Aus- und Einschalten des Controllers erfordern.
* Test i2cScan TXT 4.0 Controller mit echter Hardware (10 I²C Module gleichzeitig):\
['0x3', '0x20', '0x27', '0x3c', '0x4b', '0x50', '0x51', '0x5d', '0x5e', '0x72']

Block **is_rx** () : Boolean

* Gibt True zurück, wenn `sys.implementation.name == 'circuitpython'`.
* Davon abhängig werden für I²C verschiedene Importe gemacht:
* True: circuitpython `from adafruit_bus_device.i2c_device import I2CDevice`
* False: Python3 `from smbus2 import SMBus, i2c_msg`


### Beschreibung der Quellcodedateien (alphabetisch geordnet)
Inhaltsverzeichnis: [Tabelle 1](#tabelle-1)

#### advanced.py

> Allgemeine Blöcke, die Python-Funktionen bereit stellen (ohne I²C Bezug).

Block **comment** (text) : Kommentar Block ohne Funktion.\
Block **Int** (x) : Integer *int(x)*\
Block **Ord** (char) : Integer Zeichencode *ord(char)*\
Block **Chr** (asc) : String 1 Zeichen *chr(asc)*\
Block **print_bin** (zahl, length) : BIN String z.B. '00001010'; Binärzahl mit fester Länge\
Block **list_string** (string_data) : Liste der Zeichencodes *[ord(c) for c in string_data]*\
Block **encode_string** (string_data) : Liste der Zeichencodes *string_data.encode('utf-8')*\
Block **decode_string** (data_bytes) : String *data_bytes.decode('utf-8', 'replace')*\
Block **decode_latin** (data_bytes) : String *''.join(chr(b) for b in data_bytes)*\
Block **list_hex** (data_bytes) : HEX String *[hex(b) for b in data_bytes]*\
Block **sign** (i, exp) : Wandelt uint in int mit Vorzeichen um. *exp*: Anzahl der Bits z.B. 16.\
Block **system_time** () : Liste mit 9 Elementen
* TXT 4.0: RTC Systemuhr (year, mon, mday, hour, min, sec, wday, yday, isdst)\
Uhr wird bei Internetverbindung gestellt, Zeitzone Germany am Controller einstellen.
* RX: Zeitstempel umgerechnet in (0, 0, 0, hour, min, sec, 0, 0, 0) seit dem Einschalten.

Block **voltmeter** (input_pin, extended_range)
> TXT 4.0 Controller kann an den Input-Pins I1 bis I8 Spannung messen.

* *input_pin*: 1..8 Input Pin Nummer.
* *extended_range* Messbereich: False=0..6,3V; True=0..10V.
* TXT 4.0: gibt Spannung in Volt zurück mit 3 Kommastellen.
* RX: gibt None zurück.


#### dipswitch.py
→ DIP: dual in-line package; Switch: Schalter → [en.wikipedia.org/wiki/DIP_switch](https://en.wikipedia.org/wiki/DIP_switch)
###### [Grove - 6-Position DIP Switch](https://wiki.seeedstudio.com/Grove-6-Position_DIP_Switch) | [Grove - 5-Way Switch](https://wiki.seeedstudio.com/Grove-5-Way_Switch)
Block **switch_read** () : Byte
* Gibt 1 Byte zurück: 6 Bit (0..63), 1 Bit pro DIP Schalter.

#### keyboard.py
→ Keyboard: Tastatur →  [de.wikipedia.org/wiki/Tastatur](https://de.wikipedia.org/wiki/Tastatur)
###### [M5Stack Card Keyboard QWERTY 50-key](https://docs.m5stack.com/en/unit/cardkb_1.1)
Block **keyboard_read** () : Byte
* Gibt 0 zurück wenn keine Taste gedrückt, sonst ASCII-Code der gedrückten Taste.

#### lcd16x2.py
→ LCD: liquid-crystal display → [de.wikipedia.org/wiki/Flüssigkristallanzeige](https://de.wikipedia.org/wiki/Fl%C3%BCssigkristallanzeige)
###### [Grove - LCD Display 16x2 Zeichen](https://wiki.seeedstudio.com/Grove-16x2_LCD_Series) | Black on Yellow | Black on Red | White on Blue

Block **lcd_init** ()
* Muss einmal beim Start aufgerufen werden.

Block **lcd_text** (row, col, end, text, right)
* Schreibt an eine bestimmte Position Text mit fester Länge.
* *row*: Zeile 0 oder 1; *col*: Spalte 0..15; *end*: Spalte 0..15 (letztes Zeichen)
* *text*: Text, alle Datentypen werden mit str() konvertiert.
* *right*: None oder False=linksbündig; True=rechtsbündig\
Text wird mit Leerzeichen auf die Länge (end-col)+1 aufgefüllt.
* Parameter außer *text* können weg gelassen werden (None).\
default: *row*=0; *col*=0; *end*=15; right=False

Block **lcd_clear** ()
* Löscht das LCD Display.

Block **lcd_cursor** (row, col)
* Set Cursor für writeLCD oder wenn Cursor sichtbar ist oder blinkt.
* *row*: Zeile 0 oder 1; *col*: Spalte 0..15
* Parameter optional, default: *row*=0; *col*=0

Block **lcd_write** (text)
* Schreibt *text* an aktuelle Cursorposition.
* Alle Datentypen werden mit str() konvertiert.

Block **lcd_display** (display_on, cursor_on, blink_on)
* Alle Parameter Boolean: False oder True
* Schaltet das Display, Cursor und blinkenden Cursor an und aus.

#### oled.py
→ OLED: organic light-emitting diode → [de.wikipedia.org/wiki/OLED](https://de.wikipedia.org/wiki/Organische_Leuchtdiode)
###### [Grove - OLED Display 1.12 (128x128)](https://wiki.seeedstudio.com/Grove-OLED-Display-1.12-SH1107_V3.0) | [OLED Yellow&Blue Display 0.96 (128x64)](https://wiki.seeedstudio.com/Grove-OLED-Yellow&Blue-Display-0.96-SSD1315_V1.0) | [OLED Display 0.96](https://wiki.seeedstudio.com/Grove-OLED_Display_0.96inch)
> OLED Displays zeigen 128x64 oder 128x128 Pixel an. Alle Pixel werden zuerst in Variablen gespeichert. Dieser Speicher wird 'Matrix' genannt.
> Um die 'Matrix' auf dem OLED Display anzuzeigen, muss immer der Block **displayMatrix** aufgerufen werden.

Block **oled_init** (select_oled:Boolean) → Parameter optional
* Muss einmal beim Start aufgerufen werden.
* *select_oled*: Auswahl Display (I²C-Adresse) None oder False: 0x3C; True: 0x3D.
* Initialisiert die Matrix: Variablen zum Speichern der Pixel (1024 oder 2048 Byte).
* Initialisiert das Display mit der angegebenen I²C-Adresse 0x3C oder 0x3D (Lötbrücke).

> Wenn zwei Displays angeschlossen sind, muss der Block **init_oled** zweimal aufgerufen werden, mit False und True.
> Es gibt nur eine Matrix, die mit dem folgenden Block auf einem bestimmten Display angezeigt werden kann.

Block **display_matrix** (from_page, to_page, select_oled) → alle Parameter optional
* Immer aufrufen, um das in die Matrix gezeichnete Bild auf dem Display anzuzeigen.
* Ohne Parameter wird das komplette Display über den I²C-Bus neu geschrieben.
* Mit den optionalen Parametern *from_page*, *to_page* ist es möglich, nur einen Teil des Displays zu aktualisieren. Eine 'Page' ist eine Zeile 8 Pixel hoch und 128 Pixel breit (Breite des Displays).
* Das 128x64 Display hat 8 Zeilen (0-7). Das 128x128 Display hat 16 Zeilen (0-15).
* Der Parameter *select_oled* bestimmt, an welches OLED Display die Matrix gesendet wird.

> <ins>Die folgenden Blöcke ändern nur die Pixel in der Matrix, nicht das Display.</ins>

Block **clear_matrix** (from_page, to_page) → alle Parameter optional
* Löscht die gesamte Matrix (ohne Parameter) oder einzelne Zeilen.
* *from_page*: 0..7, default: 0
* *to_page*: 0..7 bzw. 0..15, default 7 bzw. 15

Block **set_pixel** (x, y, pixel)
* *pixel*: schaltet ein Pixel (in der Matrix) True:EIN oder False:AUS. 
* Für die Koordinate *x* sind Werte von 0 (links) bis 127 (rechts) möglich.
* Für die Koordinate *y* sind Werte von 0 (oben) bis 63 bzw. 127 (unten) möglich.

Block **write_matrix** (row, col, text)
###### erforderlich: [qwiiceeprom](#qwiiceprompy)
> Um Text mit Pixeln zu zeichnen, muss der EEPROM angeschlossen und der Zeichensatz programmiert sein. Pro Zeichen werden 8 Byte vom EEPROM in die Matrix kopiert.

* Schreibt Text an eine bestimmte Position in die Matrix.
* *row*: Zeile 0..7 bzw. 0..15; *col*: Spalte 0..15.
* *text*: Text, alle Datentypen werden mit str() konvertiert.
* Parameter optional, default: row=0; col=0.

Block **oled_paint_eeprom** (eeprom_startadresse, from_page, to_page) → alle Parameter optional
* *eeprom_startadresse*: 0x0000..0xFFFF; default 0xF800 (Anfang vom Zeichensatz)
* *from_page*: 0..7, default: 0; *to_page*: 0..7 bzw. 0..15, default 7 bzw. 15
* Kopiert aus dem EEPROM pro 'Page' 128 Byte in die Matrix.
* Ohne Parameter wird der gesamte Zeichensatz vom EEPROM in die Matrix kopiert.
* Im EEPROM können Bilder, die das ganze Display füllen, gespeichert werden.


#### oled_geometrie.py
###### Erweiterung zu: [oled](#oledpy)
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

#### qwiicbutton.py
→ Qwiic Connect System: I²C · 3,3V Logik · ohne Löten → [www.sparkfun.com/qwiic](https://www.sparkfun.com/qwiic)\
→ Button: Taste → [de.wikipedia.org/wiki/Taste](https://de.wikipedia.org/wiki/Taste)
###### [SparkFun Qwiic Button - Green LED](https://www.sparkfun.com/products/16842) | [SparkFun Qwiic Button - Red LED](https://www.sparkfun.com/products/15932) | [SparkFun Qwiic Button Breakout](https://www.sparkfun.com/products/15931)
> Button mit farbiger LED, Bordcomputer, FIFO, /INT-Pin, mehrere gleichzeitig am I²C-Bus.
> Unterscheidet PRESSED (drücken) und CLICKED (drücken und loslassen).\
> LED Helligkeit und Blink-Takt.
> [Qwiic_Button_I2C_Register_Map](https://cdn.sparkfun.com/assets/learn_tutorials/1/1/0/8/Qwiic_Button_I2C_Register_Map.pdf)

Block **button_set_i2c_addr** (new_i2c_addr, i2c_addr)
> Default i2c_addr ist 0x6F. Diese kann durch Lötbrücken von 0x60 bis 0x6E ODER mit diesem Block auf jede 7-Bit I²C-Adresse geändert werden.
> <ins>Wird bei den folgenden Blöcken der Parameter *i2c_addr* weg gelassen (None), gilt Default 0x6F.</ins>

* *i2c_addr* ist die aktuell gültige, *new_i2c_addr* die neue I²C-Adresse.
* Änderung bleibt beim Ausschalten erhalten.

Block **button_is_pressed** (i2c_addr)
* Gibt True zurück, wenn der Button jetzt gerade gedrückt ist.

Block **button_has_been_clicked** (clear, i2c_addr)
* Gibt True zurück, wenn der Button geklickt (gedrückt und losgelassen) war.
* *clear*: True löscht den Status hasBeenClicked.

Block **button_onoff** (i2c_addr)
* Wechselt True/False bei jedem Klick (und löscht den Status hasBeenClicked).

Block **button_interrupt_config** (when_clicked, when_pressed, i2c_addr)
* *when_clicked* = True: /INT Pin wird LOW wenn clicked (drücken und loslassen).
* /INT bleibt aktiv bis Status-Bit hasBeenClicked zurück gesetzt wird.
* *when_pressed* = True: /INT wird nur solange LOW wie der Button gedrückt ist.


Block **button_led** (brightness, i2c_addr)
* *brightness*: LED Helligkeit 0..255, 0 ist aus.

Block **button_led_config** (brightness, cycle_time, off_time, granularity, i2c_addr)
* Zum Zurücksetzen der (blinkenden) LED einfach ohne Parameter aufrufen.
* *brightness*, *granularity* : 8 Bit Register.
* *cycle_time*, *off_time* : 16 Bit Register.
* Ausprobieren was die LED macht oder [Register_Map](https://cdn.sparkfun.com/assets/learn_tutorials/1/1/0/8/Qwiic_Button_I2C_Register_Map.pdf) lesen.

Block **button_led_read_register** (i2c_addr)
* Zeigt Register 25..31 in Konsole an: 6 LED Register und I2C Address.



#### qwiicbutton_queue.py
###### Erweiterung zu: [qwiicbutton](#qwiicbuttonpy)
→ Queue: Warteschlange → [de.wikipedia.org/wiki/Warteschlange_(Datenstruktur)](https://de.wikipedia.org/wiki/Warteschlange_(Datenstruktur))\
→ FIFO: First In – First Out → [de.wikipedia.org/wiki/FIFO](https://de.wikipedia.org/wiki/First_In_%E2%80%93_First_Out)

> Diese Quellcodedatei wird nur benötigt, wenn die vergangene Zeit seit dem Drücken des Buttons ausgewertet werden soll.
> Button speichert bei PRESSED 8 und bei CLICKED 16 Zeitstempel (32 Bit Millisekunden) in QUEUE / FIFO.

Block **button_clicked_queue_empty** (i2c_addr)\
Block **button_clicked_queue_full** (i2c_addr)\
Block **button_pressed_queue_empty** (i2c_addr)\
Block **button_pressed_queue_full** (i2c_addr)
* Gibt True zurück, wenn das entsprechende Status Bit gesetzt ist.

Block **button_print_queue** (i2c_addr)
* Zeigt Status, neuesten und ältesten Zeitstempel aus der PRESSED_QUEUE und CLICKED_QUEUE in der Konsole an.

Block **button_pop_clicked_queue** (i2c_addr)\
Block **button_pop_pressed_queue** (i2c_addr)
* Gibt den ältesten Zeitstempel (32 Bit Millisekunden) zurück und löscht diesen aus der QUEUE.


#### qwiiceeprom.py
→ EEPROM: electrically erasable programmable read-only memory → [de.wikipedia.org/wiki/EEPROM](https://de.wikipedia.org/wiki/Electrically_Erasable_Programmable_Read-Only_Memory)
###### [SparkFun Qwiic EEPROM Breakout - 512Kbit](https://www.sparkfun.com/products/18355)
Block **eeprom_read** (adr16Bit, read_length) : Liste der Bytes
* *adr16Bit*: 0x0000..0xFFFF
* *read_length*: Anzahl zu lesender Bytes (**nicht** auf 32 begrenzt).
* Die zurück gegebene Liste kann mit `Datenstrukturen`**in der Liste** gelesen werden.

Block **eeprom_test** ()
* Testet, ob der ASCII Zeichensatz im EEPROM programmiert ist.
* Speicherbereich der 96 ASCII Zeichen F900-FBFF kann im Code geändert werden.
* Schreibt 6*128 Byte aus Speicherbereich in Konsole: ['0x3e', '0x51', '0x49', '0x45'].

#### qwiicgpio.py
→ GPIO: General Purpose Input/Output → [de.wikipedia.org/wiki/GPIO](https://de.wikipedia.org/wiki/GPIO)
###### [SparkFun Qwiic GPIO](https://www.sparkfun.com/products/17047)

> 3,3 Volt Logik; 16 Klemmen: 8 GPIO-Pins, 4 GND, 3 3V3, 1 /INT\
/INT Pin kann bei Zustandsänderung einen [Hardware Interrupt](#ic-module-mit-hardware-interrupt) auslösen.

Block **gpio_init** (io, inv)
* Muss einmal beim Start aufgerufen werden.
* Beide Parameter *io*, *inv*: String mit 8 Binärziffern (0 oder 1).
* Jede Binärziffer (Bit) ist einem von 8 GPIO-Pins zugeordnet.
* *io* CONFIGURATION Bit: 0=output Pin; 1=input Pin
* *inv* INVERSION Bit: 0=original polarity; 1=inverted
* INVERSION wirkt nur auf input Pins → Pin an GND → logische 1
* Beispiel:\
**gpio_init**('00000011', '00000000'): 6 output und 2 input\
**gpio_init**('11111111', '11111111'): alle 8 Pins input inverted
* ACHTUNG! GPIO INPUT und OUTPUT hat 3,3 Volt Pegel!

Block **gpio_read** () : Byte
* Gibt 1 Byte zurück, 1 Bit pro GPIO Pin.
* An input Pins max. 3,3 Volt Spannung anschließen!
* Taster schalten Pin an GND; Pull Up Widerstände (10 kOhm) an 3V3 erforderlich.

Block **gpio_write** (byte)
* *byte*: Schaltet 8 GPIO Pins, die als 0=output konfiguriert sind.
* Bit=0: aus (0 Volt); Bit=1: an (3,3 Volt)

#### qwiicjoystick.py
→ Joystick: Spielhebel → [de.wikipedia.org/wiki/Joystick](https://de.wikipedia.org/wiki/Joystick)
###### [SparkFun Qwiic Joystick](https://www.sparkfun.com/products/15168)
Block **joystick_read** ()
* <ins>Muss am Anfang jeder Schleife aufgerufen werden.</ins>
* Liest alle Joystick Register über den I²C-Bus in Variable JOYSTICK_BUFFER.

> <ins>Die folgenden Blöcke **get** lesen nur die Variable, nicht den I²C-Bus.</ins>

Block **joystick_get_x** () : Byte\
Block **joystick_get_y** () : Byte
* Gibt 1 Byte zurück mit der Stellung des Joystick in X bzw. Y Richtung.
* Mittelstellung ist 128, geringe Abweichung durch Hardware Toleranz.
* Endstellung unten bzw. links = 0; oben bzw. rechts = 255.

Block **joystick_get_button_position** () : Boolean
* Gibt True zurück, wenn der Joystick jetzt gerade gedrückt ist.

Block **joystick_get_button_onoff** () : Boolean
* Wechselt False / True bei jedem Drücken des Joystick.

#### qwiickeypad.py
→ Numeric Keypad: Tastatur, Ziffernblock → [en.wikipedia.org/wiki/Keypad](https://en.wikipedia.org/wiki/Keypad)
###### [SparkFun Qwiic Keypad - 12 Tasten](https://www.sparkfun.com/products/15290)
> Keypad speichert mehrere gedrückte Tasten, bei langsamer Abfrage geht nichts verloren.\
> Mit /INT kann ein [Hardware Interrupt](#ic-module-mit-hardware-interrupt) ausgelöst werden.

Block **keypad_read** () : Byte
* Gibt 0 zurück wenn keine Taste gedrückt, sonst ASCII-Code der gedrückten Taste.

Taste|0|1|2|3|4|5|6|7|8|9|*|#
---|---|---|---|---|---|---|---|---|---|---|---|---
Code|48|49|50|51|52|53|54|55|56|57|42|35

#### qwiiclcd.py
→ LCD: liquid-crystal display → [de.wikipedia.org/wiki/Flüssigkristallanzeige](https://de.wikipedia.org/wiki/Fl%C3%BCssigkristallanzeige)
###### [SparkFun Qwiic 20x4 SerLCD - RGB Backlight](https://www.sparkfun.com/products/16398) | [SparkFun Qwiic 16x2 SerLCD - RGB Backlight](https://www.sparkfun.com/products/16396)
Block **qlcd_init** ()
* Muss für Display 16x2 einmal beim Start aufgerufen werden.

Block **qlcd20x4_init** ()
* Muss für Display 20x4 einmal beim Start aufgerufen werden.

Block **qlcd_text** (row, col, end, text, right)
* Schreibt an eine bestimmte Position Text mit fester Länge.
* *row*: Zeile 0..3; *col*: Spalte 0..19; *end*: Spalte 0..19 (letztes Zeichen)
* *text*: Text, alle Datentypen werden mit str() konvertiert.
* *right*: None oder False=linksbündig; True=rechtsbündig\
Text wird mit Leerzeichen auf die Länge (end-col)+1 aufgefüllt.
* Parameter außer *text* können weg gelassen werden (None).\
default: *row*=0; *col*=0; *end*=COLS-1; right=False

Block **qlcd_clear** ()
* Löscht das LCD Display.

Block **qlcd_cursor** (row, col)
* Set Cursor für writeQLCD oder wenn Cursor sichtbar ist oder blinkt.
* *row*: Zeile 0..3; *col*: Spalte 0..19
* Parameter optional, default: *row*=0; *col*=0

Block **qlcd_write** (text)
* Schreibt *text* an aktuelle Cursorposition.
* Alle Datentypen werden mit str() konvertiert.
* Schreibt auf nächster Zeile weiter, max. Länge 32 Zeichen.

Block **qlcd_display** (display_on, cursor_on, blink_on)
* Alle Parameter Boolean: False oder True.
* Schaltet das Display, Cursor und blinkenden Cursor an und aus.

#### qwiicmotor.py
→ Gleichstrommotor → [de.wikipedia.org/wiki/Gleichstrommotor](https://de.wikipedia.org/wiki/Gleichstrommaschine)
###### [SparkFun Qwiic Motor Driver](https://www.sparkfun.com/products/15451)
Block **motor_init** (i2c_addr)
* Für jedes Motor-Modul einmal beim Start aufrufen (mit entsprechender *i2c_addr*).
* Parameter *i2c_addr* kann weg gelassen werden, default: 0x5D.
* 1 Modul steuert 2 Motoren 9V, mehrere Module können gleichzeitig angeschlossen werden.
* 10 I²C-Adressen mit Lötbrücken einstellbar: 0x58..0x61.

Block **motor_power** (on, i2c_addr)
* Parameter *i2c_addr* kann weg gelassen werden, default: 0x5D.
* *on* schaltet Motor Power: True=an; False=aus (für 1 Modul = 2 Motoren).
* Power für H-Bridge soll bei längerem Stillstand aus geschaltet werden, um Energie zu sparen.

Block **motor_drive_a** (speed, i2c_addr)\
Block **motor_drive_b** (speed, i2c_addr)
* Parameter *i2c_addr* kann weg gelassen werden, default: 0x5D.
* *speed* 0..128..255 Motor Drehzahl und Richtung.
* *speed* ist optional, default=128 (Stillstand).
* <ins>0 ist maximale Geschwindigkeit rückwärts!</ins>
* 0 max. rückwärts | ← 128 Stop → | max. vorwärts 255

<!--
rückwärts|STOP|vorwärts
---|---|---
max 0 ← 127|128|129 → 255 max
-->

#### qwiicmux.py
→ MUX: Multiplexer → [de.wikipedia.org/wiki/Multiplexer](https://de.wikipedia.org/wiki/Multiplexer)
###### [SparkFun Qwiic Mux Breakout - 8 Channel (TCA9548A)](https://www.sparkfun.com/products/16784)
> I²C Multiplexer: 8 I²C-Busse einzeln oder gemeinsam schaltbar.

Block **mux** (channel)
* *channel*: 0..7 schaltet genau einen Kanal ein. Jeder andere Wert schaltet alle aus.

Block **mux_write** (byte)
* *byte*: 0..255 für jedes Bit wird der entsprechende Kanal ein geschaltet.

Block **mux_read**
* Gibt ein Byte mit den gesetzen Bits der eingeschalteten Kanäle zurück.



#### qwiicopenlog.py
→ Logdatei → [de.wikipedia.org/wiki/Logdatei](https://de.wikipedia.org/wiki/Logdatei)\
→ SD-Karte: Speicherkarte → [de.wikipedia.org/wiki/SD-Karte](https://de.wikipedia.org/wiki/SD-Karte)
###### [SparkFun Qwiic OpenLog](https://www.sparkfun.com/products/15164)
> Lesen und Schreiben von Dateien auf microSD card 64MB .. 32GB, FAT16 oder FAT32.
> <ins>Dateinamen sollen im Format 8.3, nur ASCII Zeichen und Großbuchstaben enthalten.</ins>

Block **log_init**
* Muss <ins>nicht</ins> beim Start aufgerufen werden.
* Zeigt den Status binär und bei Fehler eine Meldung in der Konsole an.

Block **log_status**
* Gibt das Status Byte zurück. siehe → [Register Map](https://cdn.sparkfun.com/assets/learn_tutorials/8/6/5/newthing.JPG)

Block **log_dir** (filename, count)
* Gibt eine Liste mit Dateinamen zurück. *count* ist die maximale Anzahl.
* *filename* kann Platzhalter wie z.B. \*.\* oder \*.TXT enthalten.

Block **log_size** (filename)
* Gibt die Größe der Datei zurück.

Block **log_read** (filename, size)
* Gibt ein bytearray mit dem Inhalt der Datei zurück.
* *filename* im Format 8.3 und Großbuchstaben.
* *size* ist die maximale Länge. bytearray ist kürzer, wenn die Datei kleiner ist.
* Blöcke zum Umwandeln Bytes in Text sind in [advanced](#advancedpy).

Block **log_write** (filename, bu)
* Schreibt die Bytes aus *bu* in die Datei. Anhängen wenn Datei existiert.
* *filename* im Format 8.3 und Großbuchstaben.
* *bu* kann auch eine Liste sein, darf aber nur Bytes (0..255) enthalten.
* Blöcke zum Umwandeln Text in Bytes sind in [advanced](#advancedpy).

Block **log_test**
* Schreibt die Zeichencodes 32 bis 127 in die Datei ASCII.TXT.
* Aller 16 Byte wird CR (=13) und LF (=10) eingefügt.

Block **log_remove** (filename)
* Löscht eine oder mehrere Dateien.
* Gibt Anzahl der gelöschten Dateien zurück.

Block **log_sync**
* Kann vor dem Entfernen der Speicherkarte aufgerufen werden, muss aber nicht.


#### qwiicrelay.py
→ Relais: (englisch Relay) → [de.wikipedia.org/wiki/Relais](https://de.wikipedia.org/wiki/Relais)
###### [SparkFun Qwiic Single Relay](https://www.sparkfun.com/products/15093)
> Strom für Relais kommt aus dem 3,3 Volt I²C-Bus!

Block **relay** (on:Boolean)
* *on* schaltet Relais: True=an; False=aus.
* I2C_ADDRESS kann im Code geändert werden, default 0x18.

#### rtc.py
→ RTC: real-time clock → [de.wikipedia.org/wiki/Echtzeituhr](https://de.wikipedia.org/wiki/Echtzeituhr)
###### [Grove - High Precision RTC (Real Time Clock)](https://wiki.seeedstudio.com/Grove_High_Precision_RTC)

##### Uhr stellen

Block **rtc_write** (index, int8)
* Stellt die Uhr. Ändert ein bestimmtes Register *index*.
* `0`Seconds, `1`Minutes, `2`Hours, `3`Days, `4`Weekdays, `5`Months, `6`Years
* *int8*: 0..59 Byte wird in BCD konvertiert und im RTC-Modul gespeichert. 

Block **rtc_set** (key_code) : keyString
* Stellt die Uhr mit 5 ASCII Zeichen-Codes von Keypad oder Keyboard.
* Muss 5 mal mit ASCII Code aufgerufen werden, gibt den zusammengesetzten String zurück.\
  *1. Zeichen:* `*` neu, *2. Zeichen:* Register `0..6`,\
  *3. und 4. Zeichen:* 2 Ziffern dezimal `00..59`, *5. Zeichen:* `#` speichern
* Wenn 5 Zeichen gültig sind, wird mit **write_rtc** das Register geändert.
* Beispiel: `*120#`setzt Minute auf 20; `*401#` Montag; `*000#` Sekunde 0.

##### Uhr lesen

Block **rtc_read** ()
* <ins>Muss am Anfang jeder Schleife aufgerufen werden.</ins>
* Liest 7 Byte in Variable RTC_BUFFER.
* BCD codiert: 4 Bit pro Ziffer, Bit `7654` Zehner, Bit `3210` Einer, Jahr 2-stellig

> <ins>Die folgenden Blöcke **get** lesen nur die Variable, nicht den I²C-Bus.</ins>

Block **rtc_get** (index) : Byte
* Liest 1 Byte aus Variable RTC_BUFFER[*index*] zu dezimal konvertiert.
* `0`Seconds, `1`Minutes, `2`Hours, `3`Days, `4`Weekdays, `5`Months, `6`Years

Block **rtc_time_string** () : String 8 Zeichen
* Liest Zeit aus Variable RTC_BUFFER: `HH:mm:ss`.

Block **rtc_date_string** () : String 10 Zeichen
* Liest Datum aus Variable RTC_BUFFER: `dd.MM.20yy`.

Block **rtc_weekday** () : String 2 Zeichen
* Liest Wochentag aus RTC_BUFFER: ['So', 'Mo', 'Di', 'Mi', 'Do', 'Fr', 'Sa'].

Block **rtc_iso_string** () : String 12 Zeichen
* Liest aus Variable RTC_BUFFER: `yyMMddHHmmss`.
* Aus genau 12 Ziffern kann der benötigte Teilstring ausgeschnitten werden.
* Format ist sortierbar z.B. für Dateinamen.


#### s_co2.py
→ CO₂: Kohlenstoffdioxid → [de.wikipedia.org/wiki/CO2](https://de.wikipedia.org/wiki/Kohlenstoffdioxid)\
→ Relative Luftfeuchtigkeit → [de.wikipedia.org/wiki/Luftfeuchtigkeit](https://de.wikipedia.org/wiki/Luftfeuchtigkeit#Relative_Luftfeuchtigkeit)
###### [Calliope mini CO2 Sensor - SCD40](https://calliope.cc/calliope-mini/erweiterungen/calliope-co2-sensor)
> Sensor hat keine Pull Up Widerstände, deshalb immer mit anderen Modulen anschließen, die welche haben.
> Blockiert oft den I²C-Bus, dann Strom aus und einschalten. [Data Sheet](https://sensirion.com/media/documents/E0F04247/631EF271/CD_DS_SCD40_SCD41_Datasheet_D1.pdf#page=8)

Block **init_co2** (factory_reset)
* Muss einmal beim Start aufgerufen werden.
* *factory_reset*: True Reset aller Register.
* Ruft **start_continuous_measurement** auf.

Block **start_continuous_measurement**
* Startet die Messungen (etwa aller 5 Sekunden).

Block **stop_continuous_measurement**
* Beendet die Messungen. Immer abschalten wenn nicht benötigt, um Strom zu sparen.

Block **get_data_ready_status**
* Gibt True zurück, wenn ein neuer Messwert bereit ist. Etwa aller 5 Sekunden.

Block **read_measurement**
* Testet **get_data_ready_status**, wenn True werden die Messwerte in interne Variablen gelesen.
* Sonst bleiben die internen Variablen unverändert.
* Muss einmal in jeder Schleife (aller 5s) aufgerufen werden, um die Variablen zu aktualisieren.

> Die folgenden Blöcke **get** lesen nur die Variable, nicht den I²C-Bus.

Block **get_co2**\
Block **get_temperature**\
Block **get_relative_hunidity**
* Gibt CO₂ (Kohlenstoffdioxid), Temperatur °C oder relative Luftfeuchtigkeit zurück.




#### s_qwiicinfrared.py
→ Infrarotstrahlung → [de.wikipedia.org/wiki/Infrarot](https://de.wikipedia.org/wiki/Infrarotstrahlung)
###### [SparkFun Qwiic Proximity Sensor - 20cm, VCNL4040](https://www.sparkfun.com/products/15177)
> Nähe Sensor misst keinen genauen Abstand, nur ob ein Objekt näher als 20cm kommt (Seifenspender). Kann Interrupt auslösen.
> [VCNL4040_Datasheet](https://cdn.sparkfun.com/assets/2/3/8/f/c/VCNL4040_Datasheet.pdf#page=9)

Block **init_qinfrared**
* Muss einmal beim Start aufgerufen werden.
* Initialisiert die Konstanten (Register Nummern) und schaltet Sensor an **power_on_proximity**.

Block **power_on_proximity** (on)
* *on*: True schaltet Sensor an, False schaltet aus.
* Infrarot LED nimmt Strom vom 3,3V I²C-Bus (50..200mA). Aus schalten wenn nicht benutzt.

Block **get_proximity**
* Gibt Nähe zurück (16 Bit): 0..1 wenn nichts in der Nähe (20 cm), wird größer je näher.


#### s_qwiiclaser.py
→ Laser → [de.wikipedia.org/wiki/Laser](https://de.wikipedia.org/wiki/Laser)
###### [SparkFun Qwiic Distance Sensor - 4 Meter, VL53L1X](https://www.sparkfun.com/products/14722) | [SparkFun Qwiic Distance Sensor - 1.3 Meter, VL53L4CD](https://www.sparkfun.com/products/18993)
Block **init_qlaser**
* Muss einmal beim Start aufgerufen werden.
* Initialisiert den Sensor und wartet bis bereit (check_for_data_ready).

Block **read_distance_cm**
* Gibt Distance in cm (mit 1 Stelle hinter dem Komma) zurück. Genauigkeit ist mm.
* Ruft *start_ranging*, *get_distance*, *stop_ranging* nacheinander auf.

Block **start_ranging**
* Startet die Messungen mit Default Parametern. Kann konfiguriert werden. 

Block **stop_ranging**
* Beendet die Messungen.

Block **get_distance**
* Gibt Distance in mm zurück (16 Bit int). Ranging muss vorher gestartet werden.


#### s_qwiictemp.py
→ Temperatur → [de.wikipedia.org/wiki/Temperatur](https://de.wikipedia.org/wiki/Temperatur)\
→ Grad Celsius → [de.wikipedia.org/wiki/Grad_Celsius](https://de.wikipedia.org/wiki/Grad_Celsius)
###### [SparkFun Micro Temperature Sensor - STTS22H (Qwiic)](https://www.sparkfun.com/products/21273) | [SparkFun Temperature Sensor - STTS22H (Qwiic)](https://www.sparkfun.com/products/21262)

Block **temp_one_shot**
* Macht nur eine Messung und gibt Temperator in °C zurück. Spart Strom.
* Wartet auf Ergebnis ca. 50ms.

Block **temp_odr_1hz** (on)
* *on*: schaltet 1 Hz Output Data Rate True:an oder False:aus
* True: Macht eine Messung pro Sekunde. False: Keine Messungen.

Block **temp_read_data**
* Gibt Temperator in °C zurück, wenn laufende Messung aktiviert ist.

Block **temp_write_limit** (limit, register_h_l)
* *limit*: -39,68°C..+122,88°C Temperatur Limit, wann Interrupt ausgelöst wird.
* None oder Werte außerhalb des Bereichs deaktivieren Interrupt.
* *register_h_l*: False: speichert *limit* für höchste Temperatur.
* *register_h_l*: True: speichert *limit* für tiefste Temperatur.
* *limit* wird intern umgerechnet, gibt tatsächlichen Wert zurück.
* Gibt -40,32 zurück, wenn deaktiviert (*limit* ungültig oder None)

Block **temp_read_status**
* Gibt 1 Byte zurück mit 3 relevanten Bits:
* Bit 0: STATUS_BUSY (nur für one-shot mode)
* Bit 1: STATUS_OVER_THH; Bit 2: STATUS_UNDER_THL
* Erkennen, ob Temperatur über- oder unterschritten ist und zurücksetzen des /INT-Pin.



#### s_qwiictmp102.py

###### [SparkFun Digital Temperature Sensor Breakout - TMP102 (Qwiic)](https://www.sparkfun.com/products/16304)

Block **tmp102_read**
* Gibt Temperatur in °C zurück. Messung erfolgt dauerhaft mit 4 Hz.

Weitere Funktionen können noch programmiert werden z.B. Interrupt.



#### s_qwiicultrasonic.py
→ Ultraschall → [de.wikipedia.org/wiki/Ultraschall](https://de.wikipedia.org/wiki/Ultraschall)
###### [SparkFun Qwiic Ultrasonic Distance Sensor - HC-SR04](https://www.sparkfun.com/products/17777)
> Der I²C Sensor hat einen eigenen Prozessor für die Ultraschall Messung. Über den I²C-Bus wird nur der aktuelle Wert in mm ausgelesen.
> Dieses Modul erfasst außerdem einen großen Winkel. So erkennen Modelle auch Hindernisse schräg, oben und unten und fahren nicht dagegen. 

> Der [fischertechnik Ultraschallsensor](https://www.fischertechnik.de/de-de/produkte/einzelteile/bausteine/133009) hat auch einen Prozessor. → [Datenblatt](https://fiproductmedia.azureedge.net/media/Certification%20Documents/Technical%20Datasheets/fischertechnik/TDB_133009-ULTRASONIC-DISTANCE-SENSOR.pdf)

Block **ultrasonic_change_i2c** (old_i2c, new_i2c)
> Default I²C-Adresse ist 0x00. Damit funktioniert der Sensor. 0x00 gilt aber als reserviert und sollte geändert werden.

* Wenn *old_i2c* weg gelassen wird, gilt 0x00. Wenn *new_i2c* weg gelassen wird, gilt 0x09.
* Gültige Werte für *new_i2c*: 0x02 .. 0x7F. Empfohlen: 0x09 .. 0x77.
* Änderung bleibt beim Ausschalten erhalten.

Block **ultrasonic_read_mm**
* Gibt Distance in mm zurück (16 Bit int).
* I²C-Adresse ist 0x09. Kann im Code geändert werden.\
(Z.B. auf 0x00, um den Sensor mit der Original Adresse zu benutzen.)



#### wattmeter.py
→ Spannungsmesser, Voltmeter  → [de.wikipedia.org/wiki/Spannungsmessgerät](https://de.wikipedia.org/wiki/Spannungsmessger%C3%A4t)\
→ Strommesser, Amperemeter → [de.wikipedia.org/wiki/Strommessgerät](https://de.wikipedia.org/wiki/Strommessger%C3%A4t)\
→ Leistungsmesser, Wattmeter → [de.wikipedia.org/wiki/Leistungsmesser](https://de.wikipedia.org/wiki/Leistungsmesser)
###### [DFRobot Gravity: I2C Digital Wattmeter SKU: SEN0291](https://www.dfrobot.com/product-1827.html)
> Misst max. 26V, 8A. 4 I²C-Adressen, bis 4 Wattmeter gleichzeitig auslesen.

Block **wattmeter_init**
* Muss einmal beim Start aufgerufen werden.
* Im Code kann calibration_value für genauere Strom Messung angepasst werden.
* Spannung kann nicht kalibriert werden.

Block **wattmeter_volt**
* Gibt Spannung in V zurück, mit 2 Dezimalstellen.

Block **wattmeter_milliampere**
* Gibt Strom in mA zurück, integer kann auch negativ sein.

Block **wattmeter_milliwatt**
* Gibt Leistumg in mW zurück. Ist ungenau und eigentlich überflüssig, Datenblatt lesen.


