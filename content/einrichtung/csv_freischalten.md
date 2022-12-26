Title: iButton Import einrichten
Date: 2022-12-10
Star_prio: 2
Summary: Import von iButton Temperaturmessungen einrichten

{% import 'macros.html' as macros %}

## Zielsetzung

Die iButtonCycle App unterstützt Temperaturmessungen mit Hilfe des iButtons. Zu diesem Zweck kann die App Messwerte des iButtons oder des neuen Bluetooth iButtons einlesen und so die Basaltemperatur bestimmen. Diese Funktion ist nach der Installation der App deaktiviert - Diese Anleitung zeigt Dir wie Du die Funktion einrichten kannst.


## Voraussetzungen

Das Freischalten von Temperaturmessungen des iButtons ist lediglich dann nötig, wenn bei der [Einrichtung]({filename}step-by-step.md) der iButtonCycle App die Option **"Speicherung auf dem Telefon"** ausgewählt wurde. Wird ein Server zur Datenspeicherung verwendet, erfolgt das Einlesen der Temperaturmessungen auf anderem Wege und eine Freischaltung ist nicht erforderlich. 

Zur Freischaltung ist ein **Freischaltcode** erforderlich. Diesen erhältst Du beim Erwerb eines iButtons in unserem [myibutton.eu Onlineshop](https://www.myibutton.eu). Solltest Du keinen Freischaltcode haben, schreibe uns eine Email an [NfP@myiButton.eu](mailto:NfP@myiButton.eu).

Den Freischaltcode erhältst Du per Email. Der Code besteht aus einer langen Zeichenkette, die mit `eyJhbGciO` beginnt.

## Schritt-für-Schritt Anleitung

Die Einrichtung erfolgt im Tab "Daten". Wechsle zum Daten Tab durch tippen auf das Icon am unteren Bildschirmrand.

##### 1. Codeeingabe starten
Drücke auf den Button "Code eingeben" in der obersten Karte.

{{ macros.device_image("{static}../images/screenshot_csv_unlock_1.png", "Screenshot zum Start des Freischaltvorgangs") }}

#### 2. Email-Adresse und Code eingeben
Gib im Feld "Email Adresse an die der Code verschickt wurde" die Email-Adresse ein. Groß- und Kleinschreibung spielen dabei keine Rolle.

Kopiere den Code, der mit `eyJhbGciO` beginnt, aus der Email, die wir Dir geschickt haben, und füge ihn in das zweite Eingabefeld ein. Am einfachsten geht das, wenn Du die Email mit dem Email-Programm auf Deinem Smartphone öffnest, den Code markierst, kopierst und dann in der iButtonCycle App einfügst. Bei iPhones muss seit iOS 16 das Einfügen des Codes aus der Zwischenablage extra bestätigt werden.

{{ macros.device_image("{static}../images/screenshot_csv_unlock_3.png", "Screenshot zur Eingabe von Email Adresse und Einfügen des Freischaltcodes") }}

#### 3. Code überprüfen
Tippe jetzt auf den Button "Code überprüfen" 
{{ macros.device_image("{static}../images/screenshot_csv_unlock_4.png", "Screenshot mit hervorgehobenem Button zur Prüfung des Freischaltcodes") }}

Sollte die Überprüfung fehlschlagen, wird am unteren Bildschirmrand eine Fehlermeldung ausgegeben. Bei erfolgreicher Überprüfung gelangst Du zurück zum "Daten" Tab. Dort hat die oberste Karte nun den Titel "Temperaturmessungen importieren" mit einem Button "CSV Datei auswählen". 

**Damit ist der iButton Import eingerichtet!**

{{ macros.device_image("{static}../images/screenshot_csv_unlock_5.png", "Screenshot nach erfolgreicher Eingabe des Freischaltcodes") }}

## Was tun im Fehlerfall
Sollte der eingegebene Code nicht akzeptiert werden, erscheint am unteren Bildschirmrand eine Fehlermeldung. 

Eine Reihe von Dingen kann zur Ablehnung des Codes führen:

* Der Code ist abgelaufen. Bitte beachte, dass der Code **nur 8 Tage gültig ist.** Solltest Du es nicht rechtzeitig geschafft haben, den Code einzugeben, schreib uns eine Email unter [NfP@myiButton.eu](mailto:NfP@myiButton.eu).
* Die Email-Adresse muss die gleiche sein wie die, mit der Du den Code angefordert hast. Bitte schaue nach, an welche Email-Adresse wir Dir den Code geschickt haben.
* Beim Kopieren und Einfügen ist ein Fehler passiert und es wurde nicht der gesamte Code eingefügt. Der Code ist sehr lang (> 300 Zeichen), bitte versichere Dich, dass Du den gesamten Code markiert und kopiert hast.


## Nächste Schritte

Die iButtonCycle App ist nun für den Import von iButton Temperaturmesswerten eingerichtet.

{{ macros.info("Eine Anleitung, wie Du Temperaturmesswerte importieren kannst, findest Du <a href=\"{filename}../benutzung/ibutton_csv_import.md\">hier</a>") }}
