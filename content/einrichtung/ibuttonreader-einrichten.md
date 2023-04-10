Title: iButtonReader einrichten
Date: 2023-01-01
Summary: Das Programm iButtonReader am PC einrichten.

{% import 'macros.html' as macros %}

{{macros.info("Diese Seite ist noch unvollständig")}}

## iButtonReader installieren

Achtung: Stecke den iButton noch nicht in den Rechner ein. Zunächst müssen die Treiber installiert werden.

#### Einrichten der iButtonReader Software

1. Lade Dir den [iButtonReader]({static}/download/iButtonReader.zip) herunter.
1. Entpacke das ZIP Archiv in einem Ordner Deiner Wahl
1. Im ZIP Archiv gibt es eine Datei `ibuttonreader_sample.properties`. Erstelle eine Kopie dieser Datei mit dem Namen `ibuttonreader.properties` (ohne das "_sample").
1. Editiere die Datei `ibuttonreader.properties` und gib in der Zeile `FILE_PATH` den vollständigen Pfad eines Ordners an, in dem die CSV Dateien abgespeichert werden sollen.  
Falls Du einen Cloudspeicher nutzt, um die CSV Datei mit dem Smartphone zu synchronisieren, gib den Pfad des Cloudspeichers an, also z.B. `/home/user/Nextcloud/ibutton` 

#### Einrichten der 1-wire Treiber unter Windows

* TBD

#### Einrichten der 1-wire Treiber unter Linux

* Install libusb, e.g. `apt install libusb` bzw. `dnf install libusb` 
* Verhindern, dass das Standard Kernel-Modul ds2490 geladen wird: Editiere/erstelle die Datei `/etc/modprobe.d/ibutton-blacklist.conf`
* Setzen der richtigen UDEV Berechtigungen: Erstelle eine Datei `/etc/udev/rules.d/99-one-wire.rules` mit dem Inhalt `ATTRS{idVendor}=="04fa", ATTRS{idProduct}=="2490", GROUP="plugdev", MODE="0664"`

#### Ausführen der iButtonReader Software

* Stecke den iButton in das USB Lesegerät
* Stecke das USB Lesegerät in den Rechner
* Wechsele in das Verzeichnis, in das Du das ZIP Archiv entpackt hast
* Führe die Datei `run.bat` bzw. `sudo run.sh` aus.
* Die ausgelesenen Temperaturdaten des iButtons findest Du in einer CSV Datei im Ordner, der in der Datei `ibuttonreader.properties` angegeben wurde.


## Automatisches Auslesen unter Linux einrichten

Hierfür gibt es eine [separate Einleitung]({filename}automatisches_auslesen.md)


