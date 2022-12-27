Title: Speicherort auswählen
Date: 2022-12-26
Summary: Entscheidungshilfe zum Speicherort

{% import 'macros.html' as macros %}

## Zielsetzung

In der iButtonCycle App können die Daten auf zwei unterschiedliche Weisen gespeichert werden:

1. Auf dem Telefon
1. Auf einem selbst betriebenen Server

Die folgende Übersicht hilft bei der Auswahl des Speicherorts während der Einrichtung.

{{ macros.warning("Die Auswahl des Speicherorts kann nur <a href=\"{filename}step-by-step.md\">ganz zu Anfang während der Einrichtung der App</a> erfolgen. Eine Änderung des Speicherorts ist nicht möglich, auch können Daten nicht von einem zum anderen Speicherort übertragen werden.") }}

## Speicherung auf dem Telefon

Bei dieser Option werden alle Daten lokal auf Deinem Telefon gespeichert. 
Das hat die folgenden Vor- und Nachteile:

#### Vorteile:

* Die App funktioniert ohne Internetverbindung
* Es werden keinerlei Daten über das Internet übertragen
* Die App ist sofort einsatzbereit, da kein Server aufgesetzt werden muss
* Es sind keine IT Kenntnisse nötig und es fällt kein Wartungsaufwand für die Wartung des Servers an

#### Nachteile:

* Die App benötigt mehr Speicherplatz
* Es kann nur von einem Gerät aus auf die Daten zugegriffen werden.
* Die Daten können lediglich auf dem kleinen Smartphone Bildschirm angesehen und ausgewertet werden
* Das Auslesen der Temperaturen des USB iButtons erfordert mehr Arbeit 
* Backups müssen von Hand erzeugt und abgespeichert werden. Wird kein Backup erstellt und das Telefon geht verloren / kaputt sind auch die Daten weg. 

## Speicherung auf einem Server

**Wichtig:** Wir stellen keinen zentralen Server zur Verfügung - wir stellen lediglich die Server-Software kostenfrei zur Verfügung. Der Server muss selbst aufgesetzt und betrieben werden. Der Server muss nicht sehr leistungsfähig sein - ein Raspberry Pi 4 ist ausreichend.

[Diese Anleitung]({filename}server-aufsetzen.md) beschreibt, wie ein Server mit Docker Containern aufgesetzt werden kann.

Der Server stellt ein Web-Interface bereit, über das man ein Token herunterladen kann. Dieses Token ist quasi das "Passwort" für den Zugang zum Server und muss bei der Einrichtung in der App angegeben werden.

#### Vorteile:

* Es kann von mehreren Geräten aus auf die Daten zugegriffen werden, z.B. von einem Smartphone und einem Tablet, oder auch von beiden Partnern auf ihren Smartphones
* Das Auslesen der Temperaturmesswerte des USB iButtons erfordert weniger Schritte - ein Einstecken des USB Lesegeräts genügt
* Das Web-Interface des Servers bietet eine bequemere Art der Datenauswertung, da ein größerer Bildschirm zur Verfügung steht
* Das Web-Interface des Servers bietet zusätzliche Auswertungen an, die auf dem Smartphone nicht zur Verfügung stehen
* Ein Backup der Daten erfolgt automatisch auf dem Server. Bei Verlust / Ersetzen des Smartphones muss das neue Gerät lediglich mit dem Server verbunden werden, und alle Daten stehen wieder zur Verfügung.

#### Nachteile:

* Es sind fundierte IT Kenntnisse nötig, um selbst einen Server aufzusetzen und zu betreiben
* Die App funktioniert nur mit Internetzugriff, da alle Daten auf dem Server liegen und nicht in der App zwischengespeichert werden
* Zwar erfolgt die Datenübertragung mit neuesten Verschlüsselungsverfahren, dennoch werden sensible persönliche Daten zwischen Smartphone und Server über das Internet übertragen

