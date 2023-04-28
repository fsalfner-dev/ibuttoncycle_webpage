Title: iButtonReader einrichten
Date: 2023-01-01
Summary: Das Programm iButtonReader am PC einrichten.

{% import 'macros.html' as macros %}

## iButtonReader installieren

Achtung: Stecke den iButton noch nicht in den Rechner ein. Zunächst müssen die Treiber installiert werden.

#### Einrichten der iButtonReader Software

1. Lade Dir den [iButtonReader]({static}/download/iButtonReader.zip) herunter.
1. Entpacke das ZIP Archiv in einem Ordner Deiner Wahl
1. Im ZIP Archiv gibt es eine Datei `ibuttonreader_sample.properties`. Erstelle eine Kopie dieser Datei mit dem Namen `ibuttonreader.properties` (ohne das "_sample").
1. Editiere die Datei `ibuttonreader.properties` und gib in der Zeile `FILE_PATH` den vollständigen Pfad eines Ordners an, in dem die CSV Dateien abgespeichert werden sollen.  
Falls Du einen Cloudspeicher nutzt, um die CSV Datei mit dem Smartphone zu synchronisieren, gib den Pfad des Cloudspeichers an, also z.B. `/home/user/Nextcloud/ibutton` 

#### Einrichten der 1-wire Treiber unter Windows

* Stecke den USB Reader **noch nicht** in den Rechner
* Installiere Java auf Deinem Rechner, z.B. von [Adoptium](https://adoptium.net/)
* Lade die [1-wire Treiber von Analog Devices](https://www.analog.com/en/design-center/evaluation-hardware-and-software/1-wire-sdks/download-1wire-ibutton-drivers.html) herunter.
* Installiere die 1-wire Treiber
* Stecke den USB Reader in den Rechner und warte, bis die automatische Treiberinstallation abgeschlossen ist
* Teste die Installation durch Öffnen des Programms `OneWireViewer`

Eine ausführliche Anleitung ist auf den (Seiten von Analog Devices)[https://www.analog.com/en/technical-articles/onewireviewer-and-ibutton-quick-start-guide.html] verfügbar.

#### Einrichten der 1-wire Treiber unter Linux

* Installiere libusb, z.B. unter Debian / Ubuntu mit `apt install libusb` bzw. `dnf install libusb` 
* Java muss auf dem System installiert sein
* Der USB Reader funktioniert nicht, wenn das `ds2490` Kernel Modul aktiv ist. Um zu verhindern, dass das Modul geladen wird, muss die Zeile `blacklist ds2490` in einer Blacklist Datei hinzugefügt werden. Je nach Linux Distribution kann z.B. die Datei `/etc/modprobe.d/ibutton-blacklist.conf` angelegt werden, die die Blacklist-Zeile enthält
* Um den Reader mit den richtigen Berechtigungen auszustatten, erstelle eine Datei `/etc/udev/rules.d/99-one-wire.rules` mit dem Inhalt `ATTRS{idVendor}=="04fa", ATTRS{idProduct}=="2490", GROUP="plugdev", MODE="0664"`.

Eine ausführliche Anleitung ist bei [Analog Devices zu finden](https://www.analog.com/media/en/technical-documentation/user-guides/instructions-for-compiling-the-onewireviewer-for-linux.pdf)

#### Ausführen der iButtonReader Software

* Stecke den iButton in das USB Lesegerät
* Stecke das USB Lesegerät in den Rechner
* Wechsele in das Verzeichnis, in das Du das ZIP Archiv entpackt hast
* Führe die Datei `run.bat` bzw. `sudo run.sh` aus.
* Die ausgelesenen Temperaturdaten des iButtons findest Du in einer CSV Datei im Ordner, der in der Datei `ibuttonreader.properties` angegeben wurde.

Eine detaillierte Anleitung zur Anwendung findest Du [hier]({filename}../benutzung/ibutton_csv_import.md).


## Automatisches Auslesen unter Linux einrichten ## {: #automatisch}

Da `udev` keine längerlaufenden Prozesse direkt aufrufen kann, muss ein sogenannter Oneshot Service für Systemd eingerichtet werden, der dann beim Einstecken des USB Readers über eine `udev` Regel gestartet wird.

#### Einrichten des systemd oneshot Service

Lege im Verzeichnis `/etc/systemd/system/` eine Datei `ibuttonupload.service` an mit dem Inhalt
```
[Unit]
Description=execute upload script when iButton is plugged in

[Service]
Type=oneshot
User=root
WorkingDirectory=<absolute/path/to/run.sh/directory/>
ExecStart=<path/to/run.sh>
```

Mache `root` zum Eigentümer des `run.sh` Skripts durch den Aufruf `sudo chown root:root run.sh`

Rufe `sudo systemctl daemon-reload` auf, um den neuen Service systemd bekannt zu machen.


#### Einrichten einer UDEV Regel

Um den oben angelegten `ibuttonupload.service` per `udev` aufzurufen, wenn der USB Reader in den Rechner eingesteckt wird, muss die oben schon angelegte Datei `/etc/udev/rules.d/99-one-wire.rules` erweitert werden.

1. Modifiziere die entsprechende Zeile so, dass sie folgendermaßen lautet: `ACTION=="add", ATTRS{idVendor}=="04fa", ATTRS{idProduct}=="2490", GROUP="plugdev", MODE="0664", TAG+="systemd", ENV{SYSTEMD_WANTS}+="ibuttonupload"`
1. Rufe `sudo udevadm control --reload` auf
1. Rufe `sudo service udev restart` auf.

