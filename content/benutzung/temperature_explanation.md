Title: Basaltemperatur
Date: 2022-12-10
Summary: Wie in iButtonCycle Basaltemperaturen gehandhabt werden

{% import 'macros.html' as macros %}
## Einführung zu Basaltemperaturen ## {: #methoden_uebersicht }

Bei der NFP Methode beruht die Bestimmung der unfruchtbaren Tage auf der Erkennung eines Anstiegs der sogenannten Basaltemperatur. Es gibt zwei unterschiedliche Ansätze zur Bestimmung der Basaltemperatur eines Zyklustages:

1. Temperaturmessung einmal pro Tag zu einer festgelegten Uhrzeit (z.B. jeden Morgen um 8 Uhr)
1. Temperaturmessung mehrmals pro Nacht und Auswahl der niedrigsten Temperaturen (unabhängig von der Uhrzeit)

Die zweite Methode benötigt ein automatisches Thermometer wie z.B. einen iButton, das die Temperatur automatisch misst und speichert. iButtonCycle unterstützt beide Methoden. 

#### Bestimmung der Basaltemperatur auf Basis von mehreren Messungen pro Nacht (2. Methode) #### {: #methode_2_einfuehrung }

Die Methode ist in folgender Darstellung skizziert:

{{macros.image("{static}../images/base_temperature_explanation.png", "Erklärung der Temperaturbestimmung mit mehreren Messungen", width=6)}}

Das Bild zeigt eine Temperaturmessung alle 30 Minuten zwischen 2 Uhr und 4 Uhr morgens. Die Basaltemperatur wird durch die Durchschnittstemperatur der drei niedrigsten Messwerte bestimmt. Die drei niedrigsten Messwerte sind blau umrandet. Die Durchschnittstemperatur ist durch die waagrechte gestrichelte blaue Linie angedeutet.

Der Zeitpunkt der Basaltemperaturmessung wird durch den ersten der drei niedrigsten Messwerte festgelegt, dargestellt durch die senkrechte gestrichelte blaue Linie. Der Zeitpunkt ist allerdings nur zur groben Überprüfung wichtig und hat keine Auswirkung auf die Erkennung des Temperaturanstiegs.

Die Auswahl der drei tiefsten Messwerte erfolgt ebenfalls in iButtonCycle und ist [weiter unten beschrieben](#basaltemp_eintragen).

#### Wann erkennt iButtonCycle einen Anstieg der Basaltemperatur?

iButtonCycle erkennt einen verlässlichen Anstieg der Basaltemperatur mit Hilfe eines Algorithmus, der in mehr Details [hier](https://www.mynfp.de/temperatur-auswerten) erklärt wird. Im wesentlichen basiert der Algorithmus auf folgender Logik:

Ein verlässlicher Temperaturanstieg wird erkannt, wenn

1. drei Messwerte höher als die sechs vorherigen Messwerte sind, wobei die Temperatur des dritten Tages mindestens 0.2°C  höher sein muss als die Temperatur des höchsten der sechs vorherigen Messungen
1. ist die Temperatur des dritten höheren Tages zwar höher, aber nicht 0.2°C, dann wird ein Temperaturanstieg erkannt, wenn ein vierter Tag ebenfalls höher als die sechs vorherigen ist
1. Fällt die Temperatur des 2. oder 3. höheren Tage wieder auf den Wert der vorherigen sechs Tage, wird ein Temperaturanstieg erkannt, falls ein vierter Tag mit mindestens 0.2°C höherer Termperatur vorliegt.

## Darstellung der Temperaturkurve in iButtonCycle

Jeder Zyklustag hat eine Basaltemperatur (zur Bestimmung siehe oben). Ab einem erkannten Temperaturanstieg werden die Zyklustage grün dargstellt, so dass sich folgende Farbgebung ergibt:

* rot, falls an diesem Tag eine Monatsblutung war
* grau, solange noch kein verlässlicher Temperaturanstieg festgestellt wurde
* grün, ab dem Tag, ab dem ein verlässlicher Temperaturanstieg festgestellt wurde (bis zur nächsten Periode)

{{ macros.image("{static}../images/screenshot_nfp_colors_explained.png", "Erklärung zur Farbgebung") }}

{{macros.warning("Grün eingefärbte Tage beziehen sich <strong>ausschließlich auf die Temperatur</strong>. Die symptothermale Methode verlangt zusätzlich zur Temperatur ein zweites Symptom:
<ul>
<li>Die Beschaffenheit des Gebärmutterschleims</li>
<li>Der Zustand des Gebärmutterhalses</li>
</ul>
<strong>Die unfruchtbare Phase kann dadurch eventuell erst später beginnen, obwohl die Tage schon grün markiert sind!</strong>
<p>iButtonCycle unterstützt als zweite Methode (noch) ausschließlich die Beschaffenheit des Gebärmutterschleims.</p>")}}

#### Überspringen von Messwerten

Die Basaltemperatur ist ein wichtiger Bestandteil der symptothermalen Methode. Die Temperaturmessungen können aber verfälscht sein, z.B. durch

* Krankheit
* Konsum von Alkohol   
* Sportliche Anstrengungen
* Heiße Außentemperaturen
* ...

In iButtonCycle können Temperaturmesswerte übersprungen werden, das heißt, sie werden vom Algorithmus zur Erkennung des Temperaturanstiegs ausgenommen. Um einen Messwert zu überspringen, setze den entsprechenden Tag als "Messwert ignorieren", wie im nächsten Screenshot dargestellt:

{{ macros.device_image("{static}../images/screenshot_ignore_temperature.png", "Screenshot zum ignorieren von Messwerten") }}

Temperaturmesswerte, die für die Auswertung des Temperaturanstiegs ignoriert werden, werden durch einen ausgegrauten Punkt dargestellt.


## Eintragen von Basaltemperaturen in iButtonCycle ## {: #basaltemp_eintragen }

iButtonCycle erlaubt das Eintragen von Basaltemperaturen auf drei verschiedene Weisen:

1. Manuelles Eintragen einer Basaltemperatur bei nur einer Messung pro Zyklustag ([Methode 1](#methoden_uebersicht))
1. Eintragen einer gemessenen Basaltemperatur pro Zyklustag ([Methode 1](#methoden_uebersicht)) bei Verwendung eines automatisierten Thermometers wie dem iButton, das einmal pro Nacht misst
1. Auswahl von drei niedrigsten Temperaturen bei Verwendung eines automatischen Thermometers, das mehrmals pro Nacht misst ([Methode 2](#methode_2_einfuehrung))

Das manuelle Eintragen ist im folgenden Abschnitt beschrieben, die Optionen 2 und 3 erfordern die Auswertung eines automatisierten Thermometers und sind im [weiter unten beschrieben](#automatisiert).

#### Manuelles Eintragen einer Basaltemperatur

Um die Temperatur für einen Zyklustag einzutragen gehe wie folgt vor:

1. Tippe in der NFP Hauptansicht auf den entsprechenden Zyklustag
1. Klappe die Karte "Temperatur" aus, indem Du auf den Winkel tippst
1. Tippe auf "editieren" in der Zeile "Temperatur"
1. Trage die Temperatur im Dialogfenster ein
1. Tippe auf "OK"
1. Tippe auf "Speichern"

Diese Schritte sind in den folgenden Screenshots dargestellt:

{{macros.device_image("{static}../images/screenshot_set_temp_1.png","Screenshot zu Temperaturdetails")}}
{{macros.device_image("{static}../images/screenshot_set_temp_2.png","Screenshot zu Dialog zur Temperatureingabe")}}

#### Eintragen von Temperaturen eines automatisierten Thermometers {: #automatisiert }

Die Auswertung der Daten eines automatisierten Thermometers unterscheidet sich, je nachdem ob Du die iButtonCycle App mit einem Server verbunden hast (siehe [einen eigenen Server aufsetzen]({filename}../einrichtung/server-aufsetzen.md)) oder nicht.

##### Laden der Temperaturmesswerte

Wenn die App nicht mit einem Server verbunden ist, musst Du zunächst das automatisierte Thermometer auslesen. Gehe dann wie folgt vor:

1. *Nicht in der iButtonCycle App:* Lese Dein Thermometer aus und lege die CSV Datei auf Deinem Smartphone ab
1. Wähle am unteren Bildschirmrand das Symbol "Daten"
1. Wähle "CSV Datei auswählen" 
1. Wähle eine CSV Datei aus, die die einzelenen Messungen (z.B. von einem iButton) enthält. 

{{macros.device_image("{static}../images/screenshot_open_csv.png","Screenshot zum Öffnen eines CSVs")}}

Wenn die App mit einem Server verbunden ist, ist die Vorgehensweise ähnlich, wobei Schritt 2 "Prüfen auf neue Messwerte" lautet und Schritt 3 entfällt.

{{macros.info("Das Festlegen der Basaltemperatur erfolgt für mehrere Tage auf einmal. Du kannst daher mit dem Thermometer mehrere Tage messen, und dann die Temperaturen für mehrere Tage eintragen.")}}

##### Überprüfung der ausgewählten Basaltemperaturen

Der Bildschirm zur Überprüfung der Basaltemperaturen stellt den Messwertverlauf eines Zyklustages dar, der um 15 Uhr des Vortages beginnt. Das bedeutet, dass alle Messungen von `Dienstag den 19.7.22 15:00 Uhr` bis zur letzten Messung vor `Mittwoch, den 20.7.22 14:59 Uhr` als Temperaturmessungen für `Mittwoch, den 20.7.` gelten. Dieser Ansatz funktioniert auch für die Methode, bei der Du nur einmal jeden Morgen die Temperatur bestimmst, z.B. um 4 Uhr morgens.  

{{macros.image("{static}../images/screenshot_set_base_temp_explanation.png", "Screenshot mit Erklärungen zur Überprüfung der Basaltemperaturen")}}

Die einzelnen Messungen werden (ähnlich der NFP Anzeige auf dem Hauptbildschirm) als vertikaler Zeitverlauf dargestellt (neueste Messungen oben, ältere Messungen weiter unten). Jede Zeile entspricht einer Temperaturmessung. Die einzelnen Elemente der Zeilen bedeuten folgendes:

* Am linken Rand ist der Messzeitpunkt angegeben
* Der Punkt stellt die gemessene Temperatur grafisch dar (rechts: höhere Temperatur, links niedriger)

 

