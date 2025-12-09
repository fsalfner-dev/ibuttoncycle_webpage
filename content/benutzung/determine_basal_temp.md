Title: Basaltemperatur festlegen
Date: 2025-12-09
Summary: Festlegen der Basaltemperatur bei automatischer Temperaturmessung

{% import 'macros.html' as macros %}

## Übersicht ## {: #uebersicht }

Bei Verwendung eines automatischen Thermometers wie dem iButton muss aus den Messungen die Basaltemperatur bestimmt werden, die dann für die NFP Methode verwendet wird.

Diese Seite erklärt das Verfahren und die Bedienung der entsprechenden Screens in der App.

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

#### Festlegen der Basaltemperaturen in der App

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
