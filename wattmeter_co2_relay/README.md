
> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](../examples)


### wattmeter_co2_relay (Beispiel Strommessung)

Das [I2C Digital Wattmeter](https://www.dfrobot.com/product-1827.html) genannte Modul misst eigentlich Spannung und Strom am I²C-Bus. Die Spannung sollte 3,3 Volt betragen. Zum Strom messen wurden zwei I²C Module angeschlossen, die einen hohen Stromverbrauch haben.
Der [Calliope CO2 Sensor - SCD40](https://calliope.cc/calliope-mini/erweiterungen/calliope-co2-sensor) verbraucht nur während der Messungen - ungefähr aller 5 Sekunden - fast 100 mA Strom. 
Das [Relais](https://www.sparkfun.com/products/15093) kann mit dem Mini-Taster an geschaltet werden und verbraucht dann zusätzlich 100 mA.




* Quellcodedateien: **[i2cCode](../#i2ccodepy)**, **[lcd16x2](../#lcd16x2py)**, **[qwiicrelay](../#qwiicrelaypy)**, **[s_co2](../#s_co2py)**, **[wattmeter](../#wattmeterpy)**
* Laden von fischertechnik GitLab: [I2C_Strommessung_CO2_Relais](https://git.fischertechnik-cloud.com/i2c/I2C_Strommessung_CO2_Relais)

[![](DSC00481_256.JPG)](DSC00481.JPG)\
Zum Vergrößern auf das Bild klicken.


![](DSC00471_256.jpg) ![](DSC00473_256.jpg)

