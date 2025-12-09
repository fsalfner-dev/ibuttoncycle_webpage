Title: Temperaturmessungen per USB auslesen
Date: 2025-12-09
Summary: iButton Temperaturmessungen mit dem USB Lesegerät importieren

{% import 'macros.html' as macros %}

## Übersicht ## {: #uebersicht }

Der iButton ist ein automatisches Thermometer, das nur über den physischen (elektrischen) Kontakt mit einem Lesegerät ausgelesen werden kann.

Es gibt zwei Lesegeräte:
1. Den BlueReader - ein Lesegerät, dass die Messwerte per Bluetooth an die iButtonCycle App überträgt
1. Ein USB-Lesegerät, das an den USB-Port eines PCs oder eines Android Handys angeschlossen werden muss.

Das Auslesen per BlueReader [ist auf einer separaten Seite erklärt]({filename}read_temperatures_with_bluereader.md).

Diese Seite erklärt, wie die Messwerte des iButtons per USB-Lesegerät in die iButtonCycle App eingelesen werden können.

Der Import von Temperaturmessungen in die App besteht aus folgenden Schritten:

1. **Messen der Körpertemperatur über Nacht** mit dem iButton. Der iButton nimmt automatisch eine Messung nach einem eingestellten Zeitintervall vor (z.B. jede Stunde) und speichert die Temperatur ab.
1. **Auslesen des iButtons in eine CSV Datei** und Abspeichern der CSV Datei auf dem Smartphone.  
Dieser Schritt kann auf verschiedene Weisen erfolgen:
    * Auslesen des iButton über USB auf dem PC mit dem Java-Programm [*iButtonReader*](#ibuttonreader)
    * Auslesen des iButton über USB auf einem Android Smartphone [mit der App iButtonAssist](#assist_app)
    * Auslesen des iButton über USB mit einem [Raspberry Pi](#raspberrypi)
1. [**Importieren der CSV Datei** in die iButtonCycle App](#csv_importieren)
1. [**Festlegung der Basaltemperaturen** in der iButtonCycle App](#basaltemperatur)

## Schritt 1 - Messen der Körpertemperatur über Nacht

Damit der iButton regelmäßig und automatisch die Körpertemperatur misst, muss eine sogenannte "Mission" gestartet werden. Die Einrichtung des iButtons wird z.B. in [diesem YouTube Video](https://youtu.be/f4T_bd714ks) erklärt.

## Schritt 2 - Auslesen des iButtons in eine CSV Datei

Wie oben beschrieben, können iButtons auf verschiedene Weise ausgelesen werden. Ziel ist es, eine CSV Datei mit den Temperaturmessungen zu erhalten, die dann auf dem Smartphone in der iButtonCycle App geöffnet und eingelesen werden kann.


#### USB iButton am PC mit Programm iButtonReader auslesen #### {: #ibuttonreader}

`iButtonReader` ist ein Programm, das wir zusammen mit der iButtonCycle App kostenlos zur Verfügung stellen. Der Download und die Installation werden in einer [separaten Anleitung]({filename}../einrichtung/ibuttonreader-einrichten.md) erklärt. 

Das Auslesen des iButton erfolgt in drei Schritten:

<ol>
<li>Verbinden des iButtons mit dem USB Port des PC {{ macros.image("{static}../images/usb_reader.webp","Bild des USB Lesegeräts für den iButton") }}</li>
<li>Auslesen der Temperaturwerte in eine CSV Datei mit Hilfe des Programms <code>iButtonReader</code>. Das Programm kann aufgerufen werden, durch
<ul>
<li>einen Doppelklick auf die Datei <code>run.bat</code> (Windows) bzw. <code>run.sh</code> (Linux) im Datei Manager</li>
<li>Ausführen der Datei <code>run.bat</code> bzw. <code>run.sh</code> auf der Kommandozeile (<code>cmd</code> unter Windows) im entsprechenden Verzeichnis</li>
</ul>
</li>
<li>Übertragung der CSV Datei auf das Smartphone. Es bestehen mehrere Möglichkeiten, u.a. 
    <ul>
        <li>Abspeichern der CSV Datei auf einem Cloudspeicher wie z.B. Nextcloud oder Google Drive, auf den sowohl Dein PC als auch Dein Smartphone Zugriff haben</li>
        <li>Versenden der CSV Datei per Email und Abspeichern auf dem Smartphone</li>
        <li>Verbinden des Smartphones mit dem PC per USB Kabel und kopieren der CSV Datei auf den Telefonspeicher</li> 
        <li>Kopieren der CSV Datei auf eine SD Speicherkarte</li>
    </ul>
</li>
</ol>


#### USB IButton am Android Smartphone mit iButton Assist auslesen #### {: #assist_app}

Auf YouTube haben wir ein ausführliches [Video zur Bedienung der iButton Assist App](https://youtu.be/6bW39J2xfQY) zur Verfügung gestellt.

Ähnlich wie bei der `iButtonReader` Software oben, muss die CSV Datei auf das Smartphone transferiert werden. Dies kann auf verschiedene Weisen erfolgen:

* Abspeichern der CSV Datei auf einem Cloudspeicher wie z.B. Nextcloud oder Google Drive, auf den sowohl Dein PC als auch Dein Smartphone Zugriff haben
* Versenden der CSV Datei per Email und Abspeichern auf dem Smartphone. Diese Variante ist im Video dargestellt
* Verbinden des Smartphones mit dem PC per USB Kabel und kopieren der CSV Datei auf den Telefonspeicher
* Kopieren der CSV Datei auf eine SD Speicherkarte


#### Auslesen über USB mit einem Raspberry Pi #### {: #raspberrypi}

Der USB iButton kann [ähnlich wie auf dem PC](#ibuttonreader) ebenfalls mit dem Programm `ibuttonreader` ausgelesen werden. Die CSV Datei muss dann vom Raspberry Pi aus zum Smartphone übertragen werden.

Das manuelle Starten des `run.sh` Scripts kann unter Linux auch automatisiert werden, so dass der Auslesevorgang automatisch gestartet wird, sobald man das USB Lesegerät in den Raspberry Pi einsteckt. Eine [Anleitung zur Einrichtung der Automation]({filename}../einrichtung/ibuttonreader-einrichten.md#automatisch) wird in einer separaten Anleitung beschrieben.

Wenn man einen [einen eigenen Server betreibt]({filename}../einrichtung/server-aufsetzen.md), können die Messwerte auch direkt (also ohne den Umweg über eine CSV Datei) an den Server gesendet und in der iButtonCycle App ausgewertet werden.

## Schritt 3 - CSV Datei in iButtonCycle importieren ## {: #csv_importieren}

{{macros.info('Wenn Du einen <a href="{filename}../einrichtung/server-aufsetzen.md">eigenen Server betreibst</a> ist keine Übertragung von CSV Dateien auf das Smartphone nötig. Die Messwerte werden direkt an den Server gesendet und können mit Hilfe des Buttons "Prüfen auf neue Messwerte" direkt ausgewertet werden (Schritt 4).')}}


{{macros.info('Beachte, dass der Import von CSV Dateien zunächst eingerichtet werden muss.  <a href="{filename}../einrichtung/csv_freischalten.md">Hier findest Du eine Anleitung, wie das geht</a>.')}}

Im vorherigen Schritt wurde eine CSV Datei mit den Temperaturmesswerten erzeugt, die nun in der iButtonCycle App eingelesen werden muss:

<ol>
    <li>Wechsele zum Reiter <em>Daten</em></li>
    <li>
        <div>Tippe auf den Button <em>CSV Datei auswählen</em>. Beachte, dass dieser Button nur vorhanden ist, wenn die <a href="{filename}../einrichtung/csv_freischalten.md">Funktion eingerichtet ist</a>.</div>
        <div class="mt-3">{{ macros.device_image("{static}../images/screenshot_open_csv.png","Screenshot mit Button zum Öffnen einer CSV Datei") }}</div>
    </li>
    <li>
        <div>Wähle die CSV Datei mit den Temperaturmesswerten. Wenn Du in Schritt 2 das Programm <code>iButtonReader</code> verwendet hast, haben die Dateinamen das Format <code>Jahr-Monat-Tag_Stunde-Minute-Sekunde</code></div>
        <div class="mt-3">{{ macros.device_image("{static}../images/screenshot_select_csv.png","Screenshot mit iOS Dateiauswahl") }}</div>
        <div>Falls Du CSV Dateien über einen Cloudspeicher mit Deinem Smartphone synchronisierst musst Du evtl zu einem anderen Speicherort wechseln (Nextcloud im folgenden Screenshot)</div>
        <div class="mt-3">{{ macros.device_image("{static}../images/screenshot_select_nextcloud.png","Screenshot zur Wahl des Speicherorts in iOS") }}</div>
    </li>
</ol>

## Schritt 4 - Festlegung der Basaltemperaturen ## {: #basaltemperatur }

Die NFP Methode basiert auf der sogenannten Basaltemperatur (das ist auch die Temperatur, die in der Kalenderansicht angezeigt wird). Je nachdem, wie der iButton eingerichtet ist, erfasst der iButton aber mehrere Messwerte in einer Nacht. Daher muss aus <strong>allen Messwerten einer Nacht die Basaltemperatur bestimmt werden.</strong>. Dies erfolgt in einer separaten Ansicht:

{{ macros.device_image("{static}../images/screenshot_set_base_temp_overview.png","Startscreen zur Festlegung der Basaltemperatur", padding=4) }}

Die Details zu dieser Ansicht sind [auf einer separaten Seite erklärt]({filename}determine_basal_temp.md)

Nach Drücken des "Speichern" Buttons auf der angezeigten Seite zur Festlegung der Basaltemperaturen wird der Import der Temperaturen wie in folgendem Screen bestätigt:

{{ macros.device_image("{static}../images/screenshot_set_base_temp_confirmation.png","Screenshot mit Bestätigung des Imports von Temperaturmesswerten", padding=4) }}

Die einzelnen Temperaturmesswerte können später auch in der Tages-Detailansicht eingesehen werden. Dort können auch im Nachgang noch einzelne Messwerte ignoriert und die Basaltemperatur angepasst werden.

{{ macros.device_image("{static}../images/screenshot_details_with_temperatures.png","Screenshot mit Bestätigung des Imports von Temperaturmesswerten", padding=4) }}

