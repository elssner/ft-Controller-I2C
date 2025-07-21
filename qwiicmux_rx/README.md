
> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](../examples)


### qwiicmux_rx (Beispiel)

Der [I²C Multiplexer](https://www.sparkfun.com/products/16784) kann 8 I²C-Busse einzeln oder gemeinsam an und aus schalten. Gebraucht wird das unter anderem, um mehrere I²C Module mit gleicher I²C-Adresse gleichzeitig zu benutzen.
Der Multiplexer ermöglicht aber auch dem RX Controller mehr als 2 bis 3 I²C Module anzusteuern. Der Grund ist nicht bekannt, aber der RX Controller scheitert an zu vielen I²C-Adressen, nicht an zu vielen I²C Modulen.



#### qwiicmux_rx.py

* Quellcodedateien: **[qwiicbutton](../#qwiicbuttonpy)**, **[dipswitch](../#dipswitchpy)**
* Laden von fischertechnik GitLab: [I2C_Multiplexer](https://git.fischertechnik-cloud.com/i2c/I2C_Multiplexer)


[![](DSC00409_256.JPG)](DSC00409.JPG) [![](DSC00415_256.JPG)](DSC00415.JPG)


Beispiel 10 I²C Module gleichzeitig mit Multiplexer. Funktioniert am RX Controller, der nur 2 bis 3 I²C-Adressen gleichzeitig erkennt.
[Beispiel Projekt](https://git.fischertechnik-cloud.com/i2c/I2C_Multiplexer) | [Foto](https://git.fischertechnik-cloud.com/i2c/I2C_Multiplexer/-/blob/master/fotos/DSC00409.JPG)

Block **qmux_rx1**
* Beispiel kann beim Programmstart aufgerufen werden.
* 3 Displays, EEPROM, Keypad, GPIO, RTC, Speicherkarte, Ultraschallsensor und Multiplexer.


