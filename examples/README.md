
> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](https://elssner.github.io/ft-Controller-I2C/examples)


### I²C Programmierbeispiele (Blöcke) für ROBO Pro Coding und fischertechnik TXT 4.0 und RX Controller.

Alle Beispiele sind plattformunabhängig programmiert und für TXT 4.0 und RX Controller geeignet. In der ROBO Pro Coding Projektkonfiguration kann jedes Projekt einfach für den anderen Controller konvertiert werden.\
Der BT Smart Controller hat keine I²C Anschlüsse und ist nicht verwendbar.

Beim RX Controller ist die Anzahl der I²C-Adressen begrenzt. Zu viele I²C Module gleichzeitig am I²C-Bus werden dann nicht erkannt. Ein [I²C Multiplexer](../#qwiicmuxpy) kann das Problem lösen.\
Beim TXT 4.0 Controller sind solche Einschränkungen nicht bekannt.


###### Tabelle 1:

Quellcodedatei|kurze Beschreibung
---|---
[lcd16x2_keyboard_rtc](../lcd16x2_keyboard_rtc)|Grove LCD: Text mit Tastatur schreiben, Datum, Uhrzeit, DIP Schalter
[oled_text_analoguhr](../oled_text_analoguhr)|OLED Analoguhr, Text Zeichensatz aus EEPROM
[qwiicbutton_int](../qwiicbutton_int)|2 I²C Buttons mit LED, /INT Ereignis, Optokoppler
[qwiiclcd_keypad_rtc](../qwiiclcd_keypad_rtc)|Qwiic LCD: Uhr stellen mit Keypad, 8 Tasten→GPIO→ASCII, Joystick
[qwiicmotor_joystick](../qwiicmotor_joystick)|2 oder 4 Motoren (I²C Motor Driver) mit I²C Joystick steuern
[qwiicmux_rx](../qwiicmux_rx)|RX Controller mit I²C Multiplexer, 10 I²C Module
[qwiicopenlog_rtc](../qwiicopenlog_rtc)|Dateien von Speicherkarte DIR, COPY, LOG mit Zeit aus RTC
[s_qwiic_distance](../s_qwiic_distance)|4 verschiedene Abstands- und Nähesensoren, Qwiic LCD 20x4
[s_qwiictemp_lcd](../s_qwiictemp_lcd)|2 Temperatursensoren STTS22H und TMP102 , Qwiic LCD Display
[wattmeter_co2_relay](../wattmeter_co2_relay)|Strom messen von CO₂ Sensor und I²C Relais, Grove LCD Display



#### Hauptprogramm in der App ROBO Pro Coding
* Mit Drahtbrücken an den Eingängen `I8 I7 I6 I5` kann der Start eines bestimmten Programmierbeispiels codiert werden. [Tabelle 2](#tabelle-2) zeigt die Codierung der Eingänge.
* Beispiel 0 **i2c_scan** zeigt die gefundenen I²C-Adressen in der Konsole an.
* Beispiel 8 **log_konsole** zeigt Dateien von der Speicherkarte in der Konsole an.
* Alle anderen Beispiele können nach Übertragung des Programms auf dem Controller (ohne Verbindung zur App) gestartet werden. Nur Drahtbrücken umstecken und Programm starten.
* Ausgabe erfolgt auf Display, LEDs, Motoren, Speicherkarte.

###### Tabelle 2:
* Codierung der Eingänge, um ein Beispiel vom Hauptprogramm zu starten.
* Name des Beispiel-Blocks und Link zur Beschreibung.

`I8`|`I7`|`I6`|`I5`|Beispiel (Block)|&nbsp;|Funktion
---|---|---|---|---|:---:|---
`0`|`0`|`0`|`0`|[i2c_scan](../#i2c_scan)|0|I²C-Adressen in Konsole anzeigen
`0`|`0`|`0`|`1`|[grovelcd_keyboard](../lcd16x2_keyboard_rtc#grovelcd_keyboard)|1|mit Tastatur in Display schreiben
`0`|`0`|`1`|`0`|[oled2_demo](../oled_text_analoguhr#oled2_demo)|2|Digital-, Analoguhr, Text aus EEPROM
`0`|`0`|`1`|`1`|[buttons_polling](../qwiicbutton_int#buttons_polling)|3|2 I²C-Buttons mit LED, DIP-Schalter
`0`|`1`|`0`|`0`|[qlcd_uhr_stellen](../qwiiclcd_keypad_rtc#qlcd_uhr_stellen)|4|Uhr anzeigen und stellen mit Keypad
`0`|`1`|`0`|`1`|[qlcd_gpio_ascii](../qwiiclcd_keypad_rtc#qlcd_gpio_ascii)|5|Binär Schreibmaschine, GPIO→ASCII
`0`|`1`|`1`|`0`|[joy_4motoren](../qwiicmotor_joystick#joy_4motoren)|6|2 I²C Motor Module mit Joystick
`0`|`1`|`1`|`1`|[qmux_rx1](../qwiicmux_rx#qmux_rx1)|7|RX mit Multiplexer, 10 I²C Module
`1`|`0`|`0`|`0`|[log_konsole](../qwiicopenlog_rtc#log_konsole)|8|Dateien von Speicherkarte anzeigen
`1`|`0`|`0`|`1`|[log_tmp102](../qwiicopenlog_rtc#log_tmp102)|9|auf Speicherkarte protokollieren
`1`|`0`|`1`|`0`|[qdistance_qlcd4](../s_qwiic_distance#qdistance_qlcd4)|10|Abstand Sensoren, LCD 20x4
`1`|`0`|`1`|`1`|[temp_lcd](../s_qwiictemp_lcd#temp_lcd)|11|Temperatur Sensoren, Limit, /INT
`1`|`1`|`0`|`0`|[wattmeter_lcd_co2](../wattmeter_co2_relay#wattmeter_lcd_co2)|12|Strommessung, CO₂ Sensor, Relais
`1`|`1`|`0`|`1`||13|
`1`|`1`|`1`|`0`||14|
`1`|`1`|`1`|`1`||15|



<!--
#### Beispiele.py
* Programmierbeispiele zeigen die Nutzung mehrerer I²C Module gleichzeitig.
* Alle Programme sind für TXT 4.0 und (nach Projekt konvertieren) RX Controller geeignet.

###### Tabelle 3:

n|Beispiel (Block)|Beschreibung
---|---|---
0|**i2c_scan**|I²C-Adressen der angeschlossenen Module in Konsole
1|**grovelcd_rtc**|Grove LCD 16x2 zeigt Uhrzeit und Datum an.
2|**grovelcd_keyboard**|Grove LCD 16x2 schreiben mit Card Keyboard (50 Tasten).
3|**grovelcd_dipswitch**|Grove LCD 16x2 mit 6 DIP Schaltern oder 5-Way Switch.
4|**qlcd_rtc_keypad**|Qwiic LCD 16x2 oder 20x4 Uhr stellen und anzeigen.
5|**qlcd_gpio_keypad**|Qwiic LCD 16x2 oder 20x4 8 Bit Zeichencode Eingabe mit GPIO.
6|**qlcd_joystick**|Qwiic LCD 16x2 oder 20x4 zeigt Joystick Positionen an.
7|**qbutton2_queue**|2 Qwiic Buttons mit LED, FIFO in Konsole anzeigen.
8|**oled_zeichnen**|OLED 128x64 oder 128x128 Linien und Kreise anzeigen.
9|**oled_eeprom_copy**|OLED 128x64 oder 128x128 Zeichensatz aus EEPROM anzeigen.
10|**oled_eeprom_rtc**|OLED 128x64 oder 128x128 Datum, Uhrzeit digital und analog.
11|**oled2_systemtime**|2 OLED Displays, verschiedener Inhalt, Analoguhr System-Zeit.
12|**qlcd_qus_qir**|Qwiic LCD zeigt 2 Sensoren (Abstand und Nähe) an.
13|**qlaser_konsole**|Laser Distance Sensor in Konsole anzeigen.
14|**joy_2motoren**|2 Motoren (1 Modul) mit Joystick steuern.
15|**joy_4motoren**|4 Motoren (2 Module) mit Joystick umschalten und steuern.



### Beschreibung der Beispiele (Quellcodedateien alphabetisch geordnet)
Inhaltsverzeichnis: [Tabelle 1](#tabelle-1)


#### qwiicbutton_int.py

* Quellcodedateien: **[qwiicbutton](../#qwiicbuttonpy)**, **[dipswitch](../#dipswitchpy)**
* [I²C Module mit Hardware Interrupt](../#ic-module-mit-hardware-interrupt)
* Laden von fischertechnik GitLab: [I2C_Buttons_DipSwitch_Relay](https://git.fischertechnik-cloud.com/i2c/I2C_Buttons_DipSwitch_Relay)

[![](DSC00417_512.JPG)](DSC00417.JPG)

I²C Module, die eine Eingabe machen wie Buttons, müssen normalerweise in einer dauerhaft Schleife ständig über den I²C-Bus abgefragt werden, ob sich der Zustand geändert hat.\
Solche I²C Module haben oft einen zusätzlichen (Löt-) Interrupt-Pin /INT, der außerhalb vom I²C-Bus extra verdrahtet werden kann.

Die I²C Module haben 3,3V Logik, die fischertechnik Controller aber 9V Logik. Um die /INT Leitungen an einen Controller Input anzuschließen, wird ein Optokoppler empfohlen.
Der Optokoppler hat am Ausgang einen Fototransistor. Die Controller können am Input einen Fototransistor digital hell/dunkel abfragen. → [I²C Module mit Hardware Interrupt](../#ic-module-mit-hardware-interrupt)

Somit kann der Fototransistor an einem beliebeigen Input I1 bis I8 (beim TXT 4.0 Controller auch C1 bis C4) angeschlossen werden. 
Mit dem Block `ist Fototransistor hell` wird erkannt, ob ein Hardware /INT von einem I²C Modul aktiv ist, weil ein Button geklickt wurde. 
Nur dann wird der I²C-Bus abgefragt.




Block **buttons_polling**
* Beispiel ohne Interrupt kann beim Programmstart aufgerufen werden.
* Buttons werden in dauerhaft Schleife über den I²C-Bus abgefragt (polling).
* Keine Verdrahtung der /INT Pins erforderlich.

Block **buttons_interrupt**
* Beispiel mit Interrupt kann beim Programmstart aufgerufen werden.
* Konfiguriert Button-Interrupt *when_clicked*.
* Buttons werden nur bei aktiver /INT Leitung abgefragt, im Block **buttons_event**.
* Verdrahtung der /INT Pins über Optokoppler erforderlich.

Block **buttons_event**

* Ereignis-Blöcke werden nur vom TXT 4.0 Controller unterstützt.
* Block **buttons_event** muss in das Fototransistor Ereignis eingefügt werden.

![](fototransistor_button_event.png)
* Beim RX Controller kann der Block in einer dauerhaft Schleife abgefragt werden.

![](fototransistor_button_polling.png)
* Funktion sucht über den I²C-Bus den geklickten Button und setzt dessen /INT zurück.
* Die LED wird bei jedem Klick an und aus geschaltet.
* Der DIP Schalter steuert bei der grünen LED die Helligkeit, bei der roten die Blinkfrequenz.



#### qwiicmux_rx.py

* Quellcodedateien: **[qwiicbutton](../#qwiicbuttonpy)**, **[dipswitch](../#dipswitchpy)**
* Laden von fischertechnik GitLab: [I2C_Multiplexer](https://git.fischertechnik-cloud.com/i2c/I2C_Multiplexer)


[![](DSC00409_256.JPG)](DSC00409.JPG) [![](DSC00415_256.JPG)](DSC00415.JPG)


Beispiel 10 I²C Module gleichzeitig mit Multiplexer. Funktioniert am RX Controller, der nur 2 bis 3 I²C-Adressen gleichzeitig erkennt.
[Beispiel Projekt](https://git.fischertechnik-cloud.com/i2c/I2C_Multiplexer) | [Foto](https://git.fischertechnik-cloud.com/i2c/I2C_Multiplexer/-/blob/master/fotos/DSC00409.JPG)

Block **qmux_rx1**
* Beispiel kann beim Programmstart aufgerufen werden.
* 3 Displays, EEPROM, Keypad, GPIO, RTC, Speicherkarte, Ultraschallsensor und Multiplexer.

-->

### Foto

10 Module gleichzeitig am TXT 4.0 Controller I²C-Bus
* 0x03 Grove - 6-Position DIP Switch
* 0x20 SparkFun Qwiic Joystick
* 0x27 SparkFun Qwiic GPIO
* 0x3c Grove - OLED Yellow&Blue Display 0.96(SSD1315) 128x64 Pixel
* 0x4b SparkFun Qwiic Keypad - 12 Tasten
* 0x50 SparkFun Qwiic EEPROM Breakout - 512Kbit
* 0x51 Grove - High Precision RTC (Real Time Clock)
* 0x5d SparkFun Qwiic Motor Driver, 2 Motoren XS 9V
* 0x5e SparkFun Qwiic Motor Driver, 1 Motor XS 9V, 1 Elektromagnet
* 0x72 SparkFun Qwiic 20x4 SerLCD - RGB Backlight
* Grove - I2C Hub(6 Port)
* Qwiic Cable - Grove Adapter (100mm)
* SparkFun Qwiic Cable Kit
* SparkFun Qwiic MultiPort
* SparkFun Qwiic Adapter
* Pfosten-Steckverbinder Rastermaß: 2.54 mm Polzahl Gesamt: 6
* Beim Adapter löten gut isolieren, Spannung >3,3V am I²C-Bus zerstört den Controller!
* [Schrumpfschlauch](https://www.conrad.de/de/p/tru-components-t1904ca026-schrumpfschlauch-ohne-kleber-schwarz-1-50-mm-0-80-mm-schrumpfrate-2-1-1-m-2108776.html)
* [Modellbahn Tastenpult](https://www.tillig.com/Produkte/produktinfo-08211.html) 2 Stück\
2 Tasten GND an I1, I2; 8 Tasten GND an GPIO (Pull Up 10 KOhm an 3V3)

![](DSC00388.JPG)

