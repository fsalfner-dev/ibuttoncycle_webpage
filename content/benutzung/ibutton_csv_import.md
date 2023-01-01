Title: Temperaturmessungen importieren
Date: 2022-12-11
star_prio: 2
Summary: iButton Temperaturmessungen importieren

{% import 'macros.html' as macros %}


{{macros.info("Diese Seite ist noch unvollständig")}}

## Übersicht ## {: #uebersicht }

Es gibt zwei verschiedene iButtons:

* den (älteren) iButton ohne Bluetooth, der mit einem USB Lesegerät ausgelesen werden muss
* den (neueren) Bluetooth iButton, der mit einem Smartphone per Bluetooth ausgelesen werden kann

Diese Seite erklärt, wie die Messwerte des iButtons in die iButtonCycle App eingelesen werden können.

Das Einlesen der Daten per USB kann mit mehreren Programmen / Apps erfolgen:

1. Mit dem Java-Programm [*iButtonReader* auf einem PC](#usb-ibutton-am-pc-mit-dem-ibuttonreader)
1. Auf einem Android Smartphone [mit der App iButtonAssist](#assist_app)
1. [Über einen Raspberry Pi]({filename}../einrichtung/automatisches_auslesen.md) (erfordert den [Betrieb eines eigenen Servers]({filename}../einrichtung/server-aufsetzen.md))

## USB iButton am PC mit dem iButtonReader

Das Programm iButtonReader muss am Rechner einerichtet sein. Hierzu gibt es [eine separate Anleitung]({filename}../einrichtung/ibuttonreader-einrichten.md).

Der grobe Ablauf gliedert sich in vier Phasen:

{{ macros.image("{static}../images/iButton_import_process_csv.png", "Überblick über die vier Phasen zum Import mit einer CSV Datei", width=12) }}


## USB IButton am Android Smartphone mit iButton Assist auslesen ## {: #assist_app}



