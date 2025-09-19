> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](../examples)


### voice_konsole (Spracherkennung, Ausgabe in Konsole)

* [DFRobot Gravity: Offline Language Learning Voice Recognition Sensor](https://www.dfrobot.com/product-2665.html)

Das Beispiel demonstriert den Hardware Interrupt von zwei I²C Buttons. Die im Button eingebaute LED rot bzw. grün wird beim Klicken an und aus geschaltet. 
Der I²C DIP Schalter steuert bei der grünen LED die Helligkeit, bei der roten die Blinkfrequenz. Mit der grünen LED kann auch noch ein I²C Relais geschaltet werden.

* Quellcodedateien: **[i2cCode](../#i2ccodepy)**, **[qwiicbutton](../#qwiicbuttonpy)**, **[dipswitch](../#dipswitchpy)**, **[qwiicrelay](../#qwiicrelaypy)**, **qwiicbutton_int**
* I²C Module: 2 Stück I²C Button mit LED rot und grün, I²C DIP Schalter, optional I²C Relais
* → [I²C Module mit Hardware Interrupt](../#ic-module-mit-hardware-interrupt)
* Projekt laden von fischertechnik GitLab: [I2C_Buttons_DipSwitch_Relay](https://git.fischertechnik-cloud.com/i2c/I2C_Buttons_DipSwitch_Relay)

[![](DSC00423_512.JPG)](DSC00423.JPG)\
Zum Vergrößern auf das Bild klicken.

