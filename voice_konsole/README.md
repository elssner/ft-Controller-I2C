> ROBO Pro Coding I²C Blöcke von fischertechnik GitLab: [ft_Controller_I2C](https://git.fischertechnik-cloud.com/i2c/ft_Controller_I2C)\
> [I²C Module](https://elssner.github.io/ft-Controller-I2C/#tabelle-1) |
[I²C Hardware, Software](https://elssner.github.io/ft-Controller-I2C/#ic) |
[I²C Quellcodedateien, Blöcke](https://elssner.github.io/ft-Controller-I2C/#beschreibung-der-quellcodedateien-alphabetisch-geordnet)\
[I²C Programmierbeispiele im Überblick](../examples)


### voice_konsole (Spracherkennung, Ausgabe in Konsole)

* [DFRobot Gravity: Offline Language Learning Voice Recognition Sensor](https://www.dfrobot.com/product-2665.html)


## Befehlswörter
### Weckwort (Wake-up word)

Das Weckwort bezieht sich auf das Wort, das ein Produkt vom Standby-Modus in den Betriebsmodus schaltet. Es dient als erster Interaktionspunkt zwischen Benutzern und sprachgesteuerten Geräten.

### Weckwort lernen:

* Initiieren Sie den Sprachassistenten, indem Sie das Standardweckwort verwenden, und sagen Sie dann **"Learning wake word"**. Folgen Sie den Anweisungen, um das neue Weckwort zu lernen. (prior to each learning command, it is necessary to remove the previously learned wake-up word; kindly refer to the instructions for wake-up word and command phrase deletion)
* Hinweis: Jetzt lernen, still sein, bitte das Weckwort sagen, das gelernt werden soll!
* Das vorgesehene Weckwort, das man sich aneignen soll (am Beispiel "Hallo, da"): "Hallo, da"
* Hinweis: Lernen erfolgreich, bitte noch einmal sagen!
* Das vorgesehene Weckwort, das man sich aneignen soll: "Hallo, da"
* Eingabeaufforderung: Lernen erfolgreich, bitte noch einmal sagen!
* Das vorgesehene Weckwort, das man sich aneignen soll: "Hallo, da"
* Eingabeaufforderung: Ok, Lernen abgeschlossen!

Sobald der Lernprozess abgeschlossen ist, können Sie den Satz "Hallo, da" verwenden, um den Sprachassistenten zu wecken!

### Korrigierte Befehlswörter:

Feste Befehlswörter beziehen sich auf das festgelegte Vokabular, das von Benutzern verwendet wird, um spezifische Anweisungen an sprachinteraktive Produkte zu erteilen und eine effektive Kommunikation mit ihnen zu ermöglichen.

### Erlernen von Befehlswörtern:

Verwenden Sie ein Aktivierungswort (Standard oder gelernt), um den Sprachassistenten zu aktivieren, und sagen Sie dann "Befehlswort lernen", um den Prozess des Lernens von Befehlsphrasen zu starten, indem Sie den bereitgestellten Anweisungen folgen. Vor jeder Sitzung des Lernens von Befehlsphrasen ist es notwendig, die zuvor gelernten Befehlsphrasen zu löschen. Bitte beachten Sie die Anweisungen zum Löschen von Weckwörtern und Befehlsphrasen.

* Hinweis: Lernen Sie jetzt, seien Sie still, lernen Sie bitte das Befehlswort gemäß der Eingabeaufforderung! Bitte sagen Sie den ersten Befehl, den es zu lernen gilt!
* Zu lernende Befehlsphrase (am Beispiel "Rotlicht einschalten"): "Rotes Licht einschalten"
* Hinweis: Lernen erfolgreich, bitte noch einmal sagen!
* Zu lernender Befehlssatz: "Schalten Sie rotes Licht ein"
* Hinweis: Lernen erfolgreich, bitte noch einmal sagen!
* Zu lernender Befehlssatz: "Schalten Sie rotes Licht ein"
* Anzeige: OK, den ersten Befehl erfolgreich gelernt! Bitte sagen Sie den zweiten Befehl, den es zu lernen gilt!

... (Lernen Sie weiter)

Befehlsphrase zum Beenden des Lernmodus: "Lernen beenden"

Nach Abschluss des Lernprozesses wird automatisch eine ID generiert. Bitte beachten Sie das folgende Dokument mit dem Titel "Command Words/Wake-up Words & ID Table". Durch die Verwendung dieser eindeutigen ID können Sie Programme erstellen, um die Kontrolle entsprechend auszuüben.

### Weckwörter und Befehlswörter löschen:

Rufen Sie den Sprachassistenten mit dem Weckwort (Standard oder benutzerdefiniert) auf, und artikulieren Sie den Satz "Ich möchte löschen". Befolgen Sie die Anweisungen, um den angegebenen Befehlssatz wie angewiesen zu entfernen.

* Hinweis: Möchten Sie das gelernte Weckwort oder Befehlswort löschen?
* Befehlswort löschen: Entfernen Sie die zuvor erworbenen Befehlsphrasen.
* Weckwort löschen: Löscht die gelernten Weckwörter aus dem System.
* Alle löschen: Eliminieren Sie die assimilierten Erweckungsäußerungen und Befehlsphrasen aus dem Speicher.
* Beenden Sie das Löschen.


[![](DSC00423_512.JPG)](DSC00423.JPG)\
Zum Vergrößern auf das Bild klicken.

