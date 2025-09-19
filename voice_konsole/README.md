> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](../examples)


### voice_konsole (Spracherkennung, Ausgabe in Konsole)

* [DFRobot Gravity: Offline Language Learning Voice Recognition Sensor](https://www.dfrobot.com/product-2665.html)

>Learning Command Words → [Anleitung](https://wiki.dfrobot.com/SKU_SEN0539-EN_Gravity_Voice_Recognition_Module_I2C_UART#Command%20Words)\
Fixed Command Words → [Tabelle](https://wiki.dfrobot.com/SKU_SEN0539-EN_Gravity_Voice_Recognition_Module_I2C_UART#Command%20Words%2FWake-up%20Words%20%26amp%3B%20ID%20Table)

## Befehlswörter (Command Words)
### Weckwort (Wake-up word)

Das Weckwort bezieht sich auf das Wort, das ein Produkt vom Standby-Modus in den Betriebsmodus schaltet. Es dient als erster Interaktionspunkt zwischen Benutzern und sprachgesteuerten Geräten.

* Standardweckwort (fixed wake-up word): **"Hello robot"**

### Weckwort lernen (Learning wake-up word):

* Wecke (Initiate) den Sprachassistenten, indem du das Standardweckwort verwendest, und sage dann **"Learning wake word"**. Folge den Anweisungen, um das neue Weckwort zu lernen.
(Vor jedem Lernbefehl ist es notwendig, das zuvor gelernte Weckwort zu entfernen. Bitte beachte die Anweisungen zum Löschen von Weckwörtern und Befehlsphrasen.)
* Hinweis: Jetzt lernen, still sein, bitte das Weckwort sagen, das gelernt werden soll!
* Das vorgesehene Weckwort, das gelernt werden soll): **"hello, there"**.\
("hello, there" ist nur ein Beispiel)
* Ansage: *"Learning successful, please say it again!*"\
(Lernen erfolgreich, bitte sage es noch einmal!)
* Das vorgesehene Weckwort, das gelernt werden soll: **"hello, there"**.
* Ansage: *"Learning successful, please say it again!*"
* Das vorgesehene Weckwort, das gelernt werden soll: **"hello, there"**.
* Ansage: *"Ok, learning completed!"* (Ok, Lernen abgeschlossen!)

Sobald der Lernprozess abgeschlossen ist, kannst du den Satz **"hello, there"** verwenden, um den Sprachassistenten zu wecken!

### Feste Befehlswörter (Fixed command words):

Feste Befehlswörter beziehen sich auf das festgelegte Vokabular, das von Benutzern verwendet wird, um spezifische Anweisungen an sprachinteraktive Produkte zu erteilen und eine effektive Kommunikation mit ihnen zu ermöglichen.

### Erlernen von Befehlswörtern (Learning command words):

Verwende ein Weckwort (Standard oder gelernt), um den Sprachassistenten zu aktivieren, und sage dann **"Learning command word"**, um den Prozess des Lernens von Befehlswörtern zu starten. Vor jeder Sitzung des Lernens von Befehlsphrasen ist es notwendig, die zuvor gelernten Befehlsphrasen zu löschen. Bitte beachte die Anweisungen zum Löschen von Weckwörtern und Befehlsphrasen.

* Hinweis: Jetzt lernen, still sein, bitte das Befehlswort sagen, das gelernt werden soll!
* Zu lernendes Befehlswort: **"rotes Licht einschalten"**\
("rotes Licht einschalten"  ist nur ein Beispiel)
* Ansage: *"Learning successful, please say it again!"*\
(Lernen erfolgreich, bitte noch einmal sagen!)
* Zu lernendes Befehlswort: **"rotes Licht einschalten"**
* Ansage: *"Learning successful, please say it again!"*
* Zu lernendes Befehlswort: **"rotes Licht einschalten"**
* Ansage: *"OK, learned the first command successfully! Please say the second command to be learned!"*\
OK, den ersten Befehl erfolgreich gelernt! Bitte sage den zweiten Befehl, der gelernt werden soll!

... (weiter lernen)

Befehlsphrase zum Beenden des Lernmodus: **"Exit learning"** ("Lernen beenden")

Nach Abschluss des Lernprozesses wird automatisch eine ID generiert. Bitte beachten die Tabelle: "Command Words/Wake-up Words & ID Table". Durch die Verwendung dieser eindeutigen ID kannst du Programme erstellen, um die Kontrolle entsprechend auszuüben.

### Weckwörter und Befehlswörter löschen (Delete Wake Words and Command Words):

Rufe den Sprachassistenten mit dem Weckwort (Standard oder gelernt) auf, und sage dann **"I want to delete"** ("Ich möchte löschen"). Befolge die Anweisungen, um den angegebenen Befehlssatz wie angewiesen zu entfernen.

* Ansage: `Do you want to delete the learned wake word or command word?`\
(Möchten Sie das gelernte Weckwort oder Befehlswort löschen?)
* **Delete command word** (Befehlswort löschen): Entfernen Sie die zuvor erworbenen Befehlsphrasen.
* **Delete wake word** Weckwort löschen: Löscht die gelernten Weckwörter aus dem System.
* **Delete all** (Alle löschen): Eliminieren Sie die assimilierten Erweckungsäußerungen und Befehlsphrasen aus dem Speicher.
* **Exit deleting** (Beenden Sie das Löschen).


[![](DSC00423_512.JPG)](DSC00423.JPG)\
Zum Vergrößern auf das Bild klicken.

