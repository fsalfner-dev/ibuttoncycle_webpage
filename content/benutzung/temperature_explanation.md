Title: Basaltemperatur
Date: 2025-06-06
Summary: Wie in iButtonCycle Basaltemperaturen gehandhabt werden

{% import 'macros.html' as macros %}
## Einführung zu Basaltemperaturen ## {: #methoden_uebersicht }

Bei der NFP Methode beruht die Bestimmung der unfruchtbaren Tage auf der Erkennung eines Anstiegs der sogenannten Basaltemperatur. Es gibt zwei unterschiedliche Ansätze zur Bestimmung der Basaltemperatur eines Zyklustages:

1. Temperaturmessung einmal pro Tag zu einer festgelegten Uhrzeit (z.B. jeden Morgen um 8 Uhr)
1. Temperaturmessung mehrmals pro Nacht und Auswahl der niedrigsten Temperaturen (unabhängig von der Uhrzeit)

Die zweite Methode benötigt ein automatisches Thermometer wie z.B. einen iButton, das die Temperatur automatisch misst und speichert. iButtonCycle unterstützt beide Methoden. 

## Darstellung der Temperaturkurve in iButtonCycle

In der NFP Ansicht wird für jeden Zyklustag eine Basaltemperatur angezeigt. Bei mehreren Messungen pro Nacht wird aus den Messwerten eine Basaltemperatur bestimmt (mehr Details [hier]({filename}ibutton_csv_import.md)) 

IButtonCycle färbt den Hintergrund der Zyklustage farbig ein um anzuzeigen:

* rot, falls an diesem Tag eine Monatsblutung war
* grau, solange die Auswertungsmethode noch keine sichere Phase erkannt hat
* grün, ab dem Tag, ab dem eine sichere Phase erkannt wurde (bis zur nächsten Periode)

{{ macros.image("{static}../images/screenshot_nfp_colors_explained.png", "Erklärung zur Farbgebung") }}

{{macros.warning("Die iButtonCycle App besitzt unterschiedliche Auswertungs-modi:
<ol>
<li>Die NFP Methode aus Basaltemperatur und Beschaffenheit des Gebärmutterschleims (Zervixschleim). Die sichere (grüne) Phase hängt von einem Anstieg der Basaltemperatur und einer Veränderung der Beschaffenheit des Gebärmutterschleims ab. Eine ausführliche Anleitung gibt die Webseite <a href=\"https://www.mynfp.de/nfp-regeln\">MyNFP</a></li>
<li>Eine Auswertung der Basaltemperatur <em>ohne ein weiteres Symptom</em> (<strong>nicht kompatibel mit NFP</strong>). Die sichere (grüne) Phase hängt ausschließlich vom Anstieg der Basaltemperatur ab.</li>
</ol>
<p>
</p>
Die Methode kann im Reiter <em>Mehr</em> unter <em>Einstellungen</em> ausgewählt werden.
")}}

## Wann erkennt iButtonCycle einen Anstieg der Basaltemperatur?

iButtonCycle erkennt einen verlässlichen Anstieg der Basaltemperatur mit Hilfe eines Algorithmus, der in mehr Details [hier](https://www.mynfp.de/temperatur-auswerten) erklärt wird. Im wesentlichen basiert der Algorithmus auf folgender Logik:

Ein verlässlicher Temperaturanstieg wird erkannt, wenn

1. drei Messwerte höher als die sechs vorherigen Messwerte sind, wobei die Temperatur des dritten Tages mindestens 0.2°C  höher sein muss als die Temperatur des höchsten der sechs vorherigen Messungen
1. ist die Temperatur des dritten höheren Tages zwar höher, aber nicht 0.2°C, dann wird ein Temperaturanstieg erkannt, wenn ein vierter Tag ebenfalls höher als die sechs vorherigen ist
1. Fällt die Temperatur des 2. oder 3. höheren Tage wieder auf den Wert der vorherigen sechs Tage, wird ein Temperaturanstieg erkannt, falls ein vierter Tag mit mindestens 0.2°C höherer Termperatur vorliegt.


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

Die Auswertung der Messwerte eines automatisierten Thermometers ist ausführlich in einem [separaten Artikel am Beispiel iButton]({filename}ibutton_csv_import.md) beschrieben. 

