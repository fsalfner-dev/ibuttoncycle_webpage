Title: Basaltemperatur
Date: 2022-08-01
Summary: Wie in BioLog Basaltemperaturen gehandhabt werden

{% import 'macros.html' as macros %}
## Einführung zu Basaltemperaturen

Bei der NFP Methode beruht die Bestimmung der unfruchtbaren Tage auf der Erkennung eines Anstiegs der sogenannten Basaltemperatur. Es gibt zwei unterschiedliche Ansätze zur Bestimmung der Basaltemperatur eines Zyklustages:

1. Temperaturmessung einmal pro Tag zu einer festgelegten Uhrzeit (z.B. jeden Morgen um 8 Uhr)
1. Temperaturmessung mehrmals pro Nacht und Auswahl der niedrigsten Temperaturen (unabhängig von der Uhrzeit)

Die zweite Methode benötigt ein automatisches Thermometer wie z.B. einen iButton, das die Temperatur automatisch misst und speichert. BioLog unterstützt beide Methoden. 

#### Bestimmung der Basaltemperatur auf Basis von mehreren Messungen pro Nacht (2. Methode)

Die Methode ist in folgender Darstellung skizziert:

{{macros.image("{static}../images/base_temperature_explanation.png", "Erklärung der Temperaturbestimmung mit mehreren Messungen", width=6)}}

Das Bild zeigt eine Temperaturmessung alle 30 Minuten zwischen 2 Uhr und 4 Uhr morgens. Die Basaltemperatur wird durch die Durchschnittstemperatur der drei niedrigsten Messwerte bestimmt. Die drei niedrigsten Messwerte sind blau umrandet. Die Durchschnittstemperatur ist durch die waagrechte gestrichelte blaue Linie angedeutet.

 Der Zeitpunkt des Basaltemperatur wird durch den ersten der drei niedrigsten Messwerte festgelegt, dargestellt durch die senkrechte gestrichelte blaue Linie. Der Zeitpunkt ist allerdings nur zur groben Überprüfung wichtig und hat keine Auswirkung auf die Erkennung des Temperaturanstiegs.

## Erklärungen zur Farbgebung der Tage

Jeder Tag trägt eine von drei Farben:

* rot, falls an diesem Tag eine Monatsblutung war
* grau, solange noch kein verlässlicher Temperaturanstieg festgestellt wurde
* grün, ab dem Tag, ab dem ein verlässlicher Temperaturanstieg festgestellt wurde (bis zur nächsten Periode)

{{ macros.image("{static}../images/screenshot_nfp_colors_explained.png", "Erklärung zur Farbgebung") }}

Ein verlässlicher Temperaturanstieg wird nach der [hier](https://www.mynfp.de/temperatur-auswerten) erklärten Methode bestimmt. Der erste grün dargestellte Tag ist **nicht der Tag der ersten höheren Messung, sondern der Tag nachdem die Regeln einen Temperaturanstieg bestätigen**. In den meisten Fällen ist dies der dritte Tag nach der ersten höheren Messung. Kann kein verlässlicher Temperaturanstieg erkannt werden, bleiben die Tage grau. 

#### Handhabung von Ausnahmen

Die Basaltemperatur ist ein wichtiger Bestandteil der symptothermalen Methode. Die Temperaturmessungen können aber verfälscht sein, z.B. durch

* Krankheit
* Konsum von Alkohol   
* Sportliche Anstrengungen
* Heiße Außentemperaturen
* ...

In BioLog können Temperaturmesswerte übersprungen werden, das heißt, sie werden vom Algorithmus zur Erkennung des Temperaturanstiegs ausgenommen. Um einen Messwert zu überspringen, setzen Sie den entsprechenden Tag als "Messwert ignorieren", wie im nächsten Screenshot dargestellt:

{{ macros.device_image("{static}../images/screenshot_ignore_temperature.png", "Screenshot zum ignorieren von Messwerten") }}

Temperaturmesswerte, die für die Auswertung des Temperaturanstiegs ignoriert werden, werden durch einen ausgegrauten Punkt dargestellt.
 
{{macros.warning("Grün eingefärbte Tage beziehen sich <strong>ausschließlich auf die Temperatur</strong>. Die symptothermale Methode verlangt zusätzlich zur Temperatur ein zweites Symptom:
<ul>
<li>Die Beschaffenheit des Gebärmutterschleims</li>
<li>Der Zustand des Gebärmutterhalses</li>
</ul>
<strong>Die unfruchtbare Phase kann dadurch eventuell erst später beginnen, obwohl die Tage schon grün markiert sind!</strong>
<p>BioLog unterstützt (noch) ausschließlich die Beschaffenheit des Gebärmutterschleims.</p>")}}





