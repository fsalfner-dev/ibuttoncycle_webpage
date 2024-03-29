Title: Temperaturmessungen importieren
Date: 2023-03-19
star_prio: 2
Summary: iButton Temperaturmessungen importieren

{% import 'macros.html' as macros %}

## Übersicht ## {: #uebersicht }

Es gibt zwei verschiedene iButtons:

* den (älteren) iButton ohne Bluetooth, der mit einem **USB Lesegerät** ausgelesen werden muss
* den (neueren) Bluetooth iButton, der mit einem Smartphone **per Bluetooth** ausgelesen werden kann

Diese Seite erklärt, wie die Messwerte des iButtons in die iButtonCycle App eingelesen werden können.

Der Import von Temperaturmessungen in die App besteht aus folgenden Schritten:

1. **Messen der Körpertemperatur über Nacht** mit dem iButton. Der iButton nimmt automatisch eine Messung nach einem eingestellten Zeitintervall vor (z.B. jede Stunde) und speichert die Temperatur ab.
1. **Auslesen des iButtons in eine CSV Datei** und Abspeichern der CSV Datei auf dem Smartphone.  
Dieser Schritt kann auf verschiedene Weisen erfolgen:
    * Auslesen des iButton über USB auf dem PC mit dem Java-Programm [*iButtonReader*](#ibuttonreader)
    * Auslesen des iButton über USB auf einem Android Smartphone [mit der App iButtonAssist](#assist_app)
    * Auslesen des Bluetooth iButtons mit dem [Smartphone per Bluetooth](#bluetooth)
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

#### Bluetooth iButton auslesen #### {: #bluetooth}

Der Bluetooth iButton befindet sich noch in der Testphase. Eine Anleitung zum Auslesen werden wir bald zur Verfügung stellen.

#### Auslesen über USB mit einem Raspberry Pi #### {: #raspberrypi}

Der USB iButton kann [ähnlich wie auf dem PC](#ibuttonreader) ebenfalls mit dem Programm `ibuttonreader` ausgelesen werden. Die CSV Datei muss dann vom Raspberry Pi aus zum Smartphone übertragen werden.

Das manuelle Starten des `run.sh` Scripts kann unter Linux auch automatisiert werden, so dass der Auslesevorgang automatisch gestartet wird, sobald man das USB Lesegerät in den Raspberry Pi einsteckt. Eine [Anleitung zur Einrichtung der Automation]({filename}../einrichtung/ibuttonreader-einrichten.md#automatisch) wird in einer separaten Anleitung beschrieben.

Wenn man einen [einen eigenen Server betreibt]({filename}../einrichtung/server-aufsetzen.md), können die Messwerte auch direkt (also ohne den Umweg über eine CSV Datei) an den Server gesendet und in der iButtonCycle App ausgewertet werden.

## Schritt 3 - CSV Datei in iButtonCycle importieren ## {: #csv_importieren}

{{macros.info('Wenn Du einen <a href="{filename}../einrichtung/server-aufsetzen.md">eigenen Server betreibst</a> ist keine Übertragung von CSV Dateien auf das Smartphone nötig. Die Messwerte werden direkt an den Server gesendet und können mit Hilfe des Buttons "Prüfen auf neue Messwerte" direkt ausgewertet werden (Schritt 4).')}}

Im vorherigen Schritt wurde eine CSV Datei mit den Temperaturmesswerten erzeugt, die nun in der iButtonCycle App eingelesen werden muss:

<ol>
    <li>Wechsele zum Reiter <em>Daten</em></li>
    <li>
        <div>Tippe auf den Button <em>CSV Datei auswählen</em>. Beachte, dass diese <a href="{filename}../einrichtung/csv_freischalten.md">Funktion erst eingerichtet</a> werden muss</div>
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

Nach dem Import der Temperaturmesswerte im vorherigen Schritt öffnet sich der Bildschirm zur Festlegung der Basaltemperaturen für die gemessenen Tage/Nächte.

#### Darstellung des Verfahrens

IButtonCycle unterstützt 

1. eine einzelne Temperaturmessung pro Nacht zu einer festgelegten Uhrzeit
1. mehrere Temperaturmessungen pro Nacht, so dass die niedrigste Temperaturen ausgewählt werden können.  
 **Achtung:** Dies entspricht nicht der NFP Standardmethode, hat sich allerdings in einigen Fällen bewährt.

Bei mehreren Messungen pro Nacht wird die Basaltemperatur folgendermaßen festgelegt:

1. Als Messwerte für eine Nacht werden alle Messungen von 15 Uhr des vorherigen Nachmittags bis 15 Uhr des Datums verwendet. Zum Beispiel gehen in die Bestimmung der **Basaltemperatur des 10.4.** alle Messungen zwischen dem 9.4. 15:00 Uhr bis zum 10.4. 14:59 Uhr ein. 
1. Es werden ausschließlich Messwerte **über 35°C** verwendet
1. Der **erste und der letzte Messwert werden ignoriert**, um falsche Messwerte beim Einlegen / Herausnehmen des iButtons auszuschließen
1. Es können manuell weitere Messwerte ignoriert werden (zum Beispiel wenn man nachts bei niedrigen Temperaturen draußen war)
1. Von den verbleibenden Messwerten werden die **drei niedrigsten Messwerte herausgesucht**
1. Die (später in der Kalenderansicht verwendete) Basaltemperatur ist der **Mittelwert der drei niedrigsten Messwerte**

Methode ist in folgender Darstellung skizziert:

{{macros.image("{static}../images/base_temperature_explanation.png", "Erklärung der Temperaturbestimmung mit mehreren Messungen", width=6)}}

Das Bild zeigt eine Temperaturmessung alle 30 Minuten zwischen 2 Uhr und 4 Uhr morgens. Die Basaltemperatur wird durch die Durchschnittstemperatur der drei niedrigsten Messwerte bestimmt. Die drei niedrigsten Messwerte sind blau umrandet. Die Durchschnittstemperatur ist durch die waagrechte gestrichelte blaue Linie angedeutet.

Der Zeitpunkt der Basaltemperaturmessung wird durch den ersten der drei niedrigsten Messwerte festgelegt, dargestellt durch die senkrechte gestrichelte blaue Linie. Der Zeitpunkt ist allerdings nur zur groben Überprüfung wichtig und hat keine Auswirkung auf die Erkennung des Temperaturanstiegs.

#### Überprüfung der ausgewählten Basaltemperaturen

Das Festlegen der Basaltemperatur erfolgt für alle Tage/Nächte, für die 

* Temperaturmesswerte in der CSV Datei gefunden wurden, und
* keine Basaltemperatur eingetragen wurde (egal ob manuell oder mit Hilfe eines iButtons)

Du kannst daher mit dem Thermometer **mehrere Tage messen**, und dann die Temperaturen für mehrere Tage auf einmal eintragen.


##### Aufbau des Bildschirms

Der Bildschirm zur Überprüfung der Basaltemperaturen besteht aus mehreren Teilen:

{{macros.image("{static}../images/screenshot_set_base_temp_explanation.png", "Screenshot mit Erklärungen zur Überprüfung der Basaltemperaturen", padding=5)}}

* ganz oben zwei Buttons: ein grüner Button zum *Speichern* (Icon mit Pfeil), und ein roter Button, um den Importprozess (für alle Nächte) *beenden* (Icon mit dem Kreuz).
* eine Datumszeile mit Navigation. Hier kann zwischen allen Tagen/Nächten, für die Messwerte vorliegen, gewechselt werden
* Einem Tabellenkopf, der die **Durchschnittstemperatur der drei niedrigsten (blau markierten) Messwerte** angibt
* Einer (scrollbaren) Liste aller Temperaturmesswerte für den jeweiligen Tag / Nacht, als "vertikaler Zeitverlauf" mit den neuesten / spätesten Messungen weiter oben.

Jede Zeile mit einem Temperaturmesswert hat dabei folgenden Aufbau: 

* Am linken Rand ist der Messzeitpunkt im Format "Wochentag + Uhrzeit" angegeben.
* Der Punkt stellt die gemessene Temperatur grafisch dar. Je weiter rechts, desto höher war die gemessene Temperatur.
* Die gemessene Temperatur in °C
* Einem Schalter, mit dem Messwerte manuell von der Berechnung der Basaltemperatur ausgenommen werden können
* Die Zeile ist **blau hinterlegt**, falls es sich um eine der drei niedrigsten Temperaturmessungen handelt
* Die Zeile ist **durchgestrichen / ausgegraut**, falls der Messwert (durch Betätigen des Schalters) ignoriert werden soll

Der oben dargestellte Screenshot stellt den Messwertverlauf zur Bestimmung der Basaltemperatur für `Mittwoch, den 7.02.24` dar. 

* Es werden alle Messungen zwischen `Dienstag dem 6.2.24 15:00 Uhr` bis zur letzten Messung am `Mittwoch, den 7.2.24 14:59 Uhr` berücksichtigt, die *über 35°C liegen* und nicht der erste Messwert nach dem Anstieg über 35°C bzw. der letzte Messwert vor dem Abfall unter 35°C sind.
* Die Temperatur, die nach Drücken von "Speichern" als Basaltemperatur in der Kalenderansicht eingetragen werden soll ist `36,578°C` (blaue Schrift im Tabellenkopf)
* Die zwei blau hinterlegten Zeilen zeigen zwei der drei Messwerte, die zur Berechnung der Basaltemperatur von 36,578°C herangezogen werden. Es sind die Messwerte von
    * `Dienstag, 21:12 Uhr`
    * `Dienstag, 21:27 Uhr`
    * der dritte Messwert ist im Screenshot nicht zu sehen (man kann aber scrollen)
* Der Messwert am `Dienstag, 23:57 Uhr` wird ignoriert.


##### Bedienung des Bildschirms ##### {: #basaltemperatur_bedienung}

Die Basaltemperaturen der gemessenen Tage/Nächte werden gemäß folgender Schritte überprüft:

1. **Überprüfe, ob die blau markierten Messwerte verwendet werden können**. iButtonCycle sucht automatisch die drei niedrigsten Messwerte raus und markiert sie blau. Falls Du den iButton aber zum Beispiel auch tagsüber getragen hast und im Winter draußen warst, sollten diese Messwerte nicht zur Bestimmung der Basaltemperatur herangezogen werden.
1. **Entferne einen blauen Messwert** durch Betätigen des Schalters am rechten Rand der Zeile. Der Messwert wird dann rot hinterlegt. iButtonCycle aktualisiert daraufhin die drei niedrigsten Messwerte.
1. Wiederhole Schritt 1 und 2, bis alle drei blauen Zeilen verwendet werden können
1. **Wechsle zur nächsten Nacht/Tag** durch Drücken des kleinen Pfeils rechts neben der Datumsangabe am oberen Bildschirmrand
1. Wiederhole die Schritte 1 bis 4 für **alle Tage/Nächte**
1. **Drücke auf "Speichern"** um die Basaltemperaturen in die "NFP Kalenderansicht" zu übernehmen. Drücken von "Abbruch" beendet den Importvorgang ohne zu Speichern. Es wird für *keine* Basaltemperatur übernommen. 

{{macros.warning('Der "Speichern" Button rechts oben speichert die Basaltemperaturen <strong>für alle Tage/Nächte</strong> - er soll erst gedrückt werden, wenn die <strong>Messwerte für alle Tage/Nächte überprüft wurden</strong>. Gleichermaßen beendet "Abbruch" den Importvorgang - es wird für keine der Tage/Nächte eine Basaltemperatur eingetragen.')}}

##### Was tun bei nicht verwertbaren Messungen?

Sollten für einen Tag Messungen angezeigt werden, Du aber keinen Wert für diesen Tag eintragen möchtest (z.B. weil Du den iButton erst nach 15:00 Uhr entfernt hast), gibt es zwei Möglichkeiten:

* Du ignorierst alle Messwerte, indem Du alle blauen "Schalter" nach links "auf grau" schaltest. Wenn iButtonCycle keine Durchschnittstemperatur ermitteln kann (siehe angezeigte Basaltemperatur am oberen Bildschirmrand), dann wird auch keine Basaltemperatur eingetragen.
* Oder Du merkst Dir das Datum mit dem ungültigen Wert, und drückst zunächst auf "Speichern". Dann wird zunächst der falsche Temperaturwert eingetragen, den Du anschließend in der Kalenderdarstellung wie folgt entfernen kannst:
    * Wechsle zur Kalenderansicht
    * Tippe auf die Zeile mit der falschen Temperatur
    * In der Detailansicht, klappe die oberste Karte "Temperatur" aus
    * Tippe auf die blaue Schrift "editieren" am rechten oberen Rand der Karte
    * Wähle "Eintrag löschen" im Dialog aus
    * Drücke auf "Speichern" um die Detailansicht zu verlassen

{{macros.device_image("{static}../images/screenshot_delete_temperature.png","Screenshot mit Dialog zum Löschen eines Temperatureintrags")}}
