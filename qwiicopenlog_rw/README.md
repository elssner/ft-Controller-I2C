
> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](../examples)


### qwiicopenlog_rw (Beispiel)

In das I²C Modul [SparkFun Qwiic OpenLog](https://www.sparkfun.com/products/15164) wird eine microSD card 64MB .. 32GB, FAT16 oder FAT32 gesteckt.
In diesem Programmierbeispiel wird die Anwendung der Blöcke in [qwiicopenlog](../#qwiicopenlogpy) mit Ausgabe in die Konsole demonstriert.
Auch für den eigentlichen Zweck des Moduls, in eine Datei protokollieren, ist eine Funktion vorhanden. Der Dateiname wird mit Hilfe des [Grove - RTC (Real Time Clock)](https://wiki.seeedstudio.com/Grove_High_Precision_RTC)
automatisch aus Datum und Zeit zusammengesetzt.

Vor allem für den RX Controller ist das interessant, weil der weder Speicherkarte noch Uhr integriert hat. 

* Quellcodedateien: **[i2cCode](../#i2ccodepy)**, **[advanced](../#advancedpy)**, **[qwiicopenlog](../#qwiicopenlogpy)**, **[rtc](../#rtcpy)**
