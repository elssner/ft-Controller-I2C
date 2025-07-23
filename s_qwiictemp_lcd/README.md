
> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](../examples)


### s_qwiictemp_lcd (Beispiel Temperatursensoren)

Hier sind zwei I²C Temperatur Sensoren angeschlossen: [SparkFun Micro Temperature Sensor - STTS22H (Qwiic)](https://www.sparkfun.com/products/21273) und [SparkFun Digital Temperature Sensor - TMP102 (Qwiic)](https://www.sparkfun.com/products/16304).
Beide Temperaturen werden im LCD Display [SparkFun 16x2 SerLCD - RGB Text (Qwiic)](https://www.sparkfun.com/products/16397) angezeigt.\
Das erste Beispiel zeigt die Temperatur in der Konsole an und braucht kein Display.

* Quellcodedateien: **[i2cCode](../#i2ccodepy)**, **[advanced](../#advancedpy)**, **[qwiiclcd](../#qwiiclcdpy)**, **[s_qwiictemp](../#s_qwiictemppy)**, **[s_qwiictmp102](../#s_qwiictmp102py)**
* Laden von fischertechnik GitLab: [I2C_Temperatursensor_LCD](https://git.fischertechnik-cloud.com/i2c/I2C_Temperatursensor_LCD)

[![](DSC00452_256.JPG)](DSC00452.JPG) [![](DSC00454_256.JPG)](DSC00454.JPG)\
Zum Vergrößern auf das Bild klicken.

Block **temp_konsole**
* Zeigt Name des Sensor und Temperator in der Konsole an. Ohne LCD Display.
* Einmalige Anzeige, **temp_konsole** muss in Schleife aufgerufen werden.
* Das ermöglicht im Hauptprogramm, auch die Temperatur vom NTC-Widerstand anzuzeigen.
* Folgendes Programm gibt 3 Temperaturen und Leerzeile aus, aller 2,5 Sekunden.

![](temp_konsole.png)

Block **temp_lcd**
* b


![](temp_lcd.png)
