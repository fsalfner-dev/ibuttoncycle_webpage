Title: Die NFP Übersichtsseite
Date: 2022-07-30
star_prio: 2
Summary: Die Dokumentation zur Hauptansicht der BioLog App

{% import 'macros.html' as macros %}
# Die Dokumentation zur Hauptansicht der BioLog App

Die Hauptansicht der BioLog App ist eine Darstellung zur thermo-symptomalen Verhütungsmethode der natürlichen Familienplanung. Diese Seite erklärt die wesentlichen Elemente.

### Kalendarische Anordnung

Da BioLog für Smartphones entwickelt wurde, verläuft die Zeitachse im Gegensatz zu den meisten anderen Apps zur Zyklusbeobachtung und natürlichen Familienplanung bei BioLog *vertikal* und nicht horizontal. Die klassische NFP Tabelle, wie sie z.B. [hier zu finden ist](https://www.familienplanung.de/fileadmin/user_upload/familienplanung.de/downloads/Zyklustabelle_1_.pdf), ist um 90° nach rechts gedreht. Das bedeutet:

* Jede Zeile stellt einen Tag im Zyklus dar
* Das tagesaktuelle Datum befindet sich ganz oben in der Liste
* Weiter unten befinden sich vergangene Tage.
* Die Zyklen gehen nahtlos ineinander über (bis zum Beginn des bei der Einrichtung angegebenen ersten Zyklus)
* Horizontale graue Linien zeigen eine neue Woche an
* Bei jedem Monatswechsel wird die Liste unterbrochen

{{ macros.image("{static}../images/screenshot_first_period_set.png", "Screenshot zur Erklärung der Datumsanzeige", padding=4) }}

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

<h5><i class="bi bi-exclamation-triangle"></i> Wichtiger Hinweis</h5>

Grün eingefärbte Tage beziehen sich **ausschließlich auf die Temperatur**. Die symptothermale Methode verlangt zusätzlich zur Temperatur **ein zweites Symptom**:

* Die Beschaffenheit des Gebärmutterschleims
* Der Zustand des Gebärmutterhalses

BioLog unterstützt (noch) ausschließlich die Beschaffenheit des Gebärmutterschleims.

**Die unfruchtbare Phase kann dadurch eventuell erst später beginnen, obwohl die Tage schon grün markiert sind!** 



### Erklärungen zur Beschaffenheit des Gebärmutterschleims

Eine gute Erklärung zur Bestimmung der Beschaffenheit des Gebärmutterschleims findet sich by [myNFP](https://www.mynfp.de/zervixschleim-beobachten)







