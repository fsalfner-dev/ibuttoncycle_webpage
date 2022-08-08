Title: Basaltemperatur
Date: 2022-08-01
Summary: Wie in BioLog Basaltemperaturen gehandhabt werden

{% import 'macros.html' as macros %}
# Einführung zu Basaltemperaturen

### Erklärungen zur Farbgebung der Tage

Jeder Tag trägt eine von drei Farben:

* rot, falls an diesem Tag eine Monatsblutung war
* grau, solange noch kein verlässlicher Temperaturanstieg festgestellt wurde
* grün, ab dem Tag, ab dem ein verlässlicher Temperaturanstieg festgestellt wurde (bis zur nächsten Periode)

{{ macros.image("{static}../images/screenshot_nfp_colors_explained.png", "Erklärung zur Farbgebung") }}

Ein verlässlicher Temperaturanstieg wird nach der [hier](https://www.mynfp.de/temperatur-auswerten) erklärten Methode bestimmt. Der erste grün dargestellte Tag ist **nicht der Tag der ersten höheren Messung, sondern der Tag nachdem die Regeln einen Temperaturanstieg bestätigen**. In den meisten Fällen ist dies der dritte Tag nach der ersten höheren Messung. Kann kein verlässlicher Temperaturanstieg erkannt werden, bleiben die Tage grau. 

##### Handhabung von Ausnahmen

Die Basaltemperatur ist ein wichtiger Bestandteil der symptothermalen Methode. Die Temperaturmessungen können aber verfälscht sein, z.B. durch

* Krankheit
* Konsum von Alkohol   
* Sportliche Anstrengungen
* Heiße Außentemperaturen
* ...

In BioLog können Temperaturmesswerte übersprungen werden, das heißt, sie werden vom Algorithmus zur Erkennung des Temperaturanstiegs ausgenommen. Um einen Messwert zu überspringen, setzen Sie den entsprechenden Tag als "Messwert ignorieren", wie im nächsten Screenshot dargestellt:

{{ macros.device_image("{static}../images/screenshot_ignore_temperature.png", "Screenshot zum ignorieren von Messwerten") }}

Temperaturmesswerte, die für die Auswertung des Temperaturanstiegs ignoriert werden, werden durch einen ausgegrauten Punkt dargestellt.
 

<h5><i class="bi bi-exclamation-triangle"></i> Wichtiger Hinweis</h5>

Grün eingefärbte Tage beziehen sich **ausschließlich auf die Temperatur**. Die symptothermale Methode verlangt zusätzlich zur Temperatur **ein zweites Symptom**:

* Die Beschaffenheit des Gebärmutterschleims
* Der Zustand des Gebärmutterhalses

BioLog unterstützt (noch) ausschließlich die Beschaffenheit des Gebärmutterschleims.

**Die unfruchtbare Phase kann dadurch eventuell erst später beginnen, obwohl die Tage schon grün markiert sind!** 

Der folgende Screenshot zeigt einen beispielhaften Verlauf:

{{ macros.device_image("{static}../images/screenshot_nfp_mucus.png", "Screenshot eines beispielhaften Verlaufs der Gebärmutterschleimbeschaffenheit") }}

<i class="bi bi-exclamation-triangle"></i><strong> Warnhinweis:</strong> 

Der Screenshot oben gibt ein Beispiel für den Fall, in dem die grüne Einfärbung der Zyklustage irreführend sein kann: Der 15. Tag des Zyklus (Freitag der 22.7.) ist aufgrund des Temperaturanstiegs grün markiert (die erste höhere Messung war am 12. Zyklustag). Die Regeln zur Auswertung der Beschaffenheit des Gebärmutterschleims verlangen allerdings drei aufeinanderfolgende Tage mit schlechterer Schleimqualität. Diese Auswertungsregel ist erst ab dem 16. Zyklustag erfüllt. **Der erste unfruchtbare Tag ist daher erst der 16. Zyklustag und nicht, der aufgrund des Temperaturanstiegs grün eingefärbte 15. Zyklustag!**

{{ macros.device_image("{static}../images/screenshot_nfp_explanation.png", "Überblick über die Visualisierungselemente") }}





