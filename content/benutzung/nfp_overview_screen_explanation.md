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

**Die unfruchtbare Phase kann dadurch eventuell erst später beginnen, obwohl die Tage schon grün markiert sind!** Ein Beispiel ist im nächsten Abschnitt angegeben.



### Erklärungen zur Beschaffenheit des Gebärmutterschleims

Die symptothermale Methode beruht auf der Erkennung eines Temperaturanstiegs zusammen mit der Beobachtung eines weiteren Symptoms, nämlich entweder der Beschaffenheit des Gebärmutterschleims oder des Zustands des Gebärmutterhalses. BioLog unterstützt die Aufzeichnung der Gebärmutterschleimbeschaffenheit. 
Eine gute Erklärung zur Bestimmung der Beschaffenheit des Gebärmutterschleims findet sich bei [myNFP](https://www.mynfp.de/zervixschleim-beobachten).

Es werden die folgenden vier Beschaffenheiten unterschieden: `t`, `-`, `f`, `S`, `S+`

##### Bestimmung der Beschaffenheit des Gebärmutterschleims

Zur Bestimmung der Beschaffenheit müssen Empfinden und Aussehen bewertet werden:

<table class="mb-5">
<tr><th>Empfinden</th><th></th><th>Aussehen</th><th>Symbol</th></tr>
<tr>
  <td>trocken, trockenes, raues, juckendes, unangenehmes Gefühl</td>
  <td class="px-3">und</td>
  <td>nichts gesehen, kein Schleim am Scheideneingang</td>
  <td class="fst-bold">t</td>
</tr>
<tr>
  <td>nichts gefühlt, keine Feuchtigkeit, keine Empfindung am Scheideneingang</td>
  <td class="px-3">und</td>
  <td>nichts gesehen, kein Schleim am Scheideneingang</td>
  <td class="fst-bold">-</td>
</tr>  
<tr>
  <td>feucht</td>
  <td class="px-3">aber</td>
  <td>nichts gesehen, kein Schleim am Scheideneingang</td>
  <td class="fst-bold">f</td>
</tr>  
<tr>
  <td>feucht oder nichts gefühlt</td>
  <td class="px-3">und</td>
  <td>dicklich, weißlich, trüb, cremig, klumpig, gelblich, klebrig, milchig, nicht ziehbar oder zäh</td>
  <td class="fst-bold">S</td>
</tr>  
<tr>
  <td>feucht oder nichts gefühlt</td>
  <td class="px-3">und</td>
  <td>glasig, glasklar, glasig durchscheinend, wie rohes Eiweiß (glasig mit weißen Fäden durchsetzt), dehnbar fadenziehend, spinnbar, flüssig, so dünnflüssig, dass er "wegrinnt wie Wasser", rötlich, rotbraun gelblich-rötlich</td>
  <td class="fst-bold">S+</td>
</tr>
<tr>
  <td>nass, schlüpfrig, rutschig, glitschig, wie eingeölt, weich, glatt</td>
  <td class="px-3">und/oder</td>
  <td>glasig, glasklar, glasig durchscheinend, wie rohes Eiweiß (glasig mit weißen Fäden durchsetzt), dehnbar, fadenziehend, spinnbar, flüssig, so dünnflüssig, dass er "wegrinnt wie Wasser", rötlich, rotbraun, gelblich-rötlich</td>
  <td class="fst-bold">S+</td>
</tr>  
</table>

##### Notieren der Gebärmutterschleimbeschaffenheit in BioLog

Um die Beschaffenheit des Gebärmutterschleims in BioLog aufzuzeichnen, führen Sie die folgenden Schritte aus:

1. Tippen Sie in der Hauptansicht auf den Tag für den Sie Beschaffenheit notieren wollen
1. Tippen Sie auf den kleinen Pfeil im Abschnitt **Fruchtbarkeit**
1. Tippen auf die blaue Schrift in der Zeile **Zervixschleim** 
1. Wählen Sie darauf die passende Beschaffenheit
1. Tippen Sie auf **Speichern** am oberen Bildschirmrand

Die folgenden Screenshots zeigen den Vorgang:

{{ macros.device_image("{static}../images/screenshot_set_mucus_1.png", "Screenshot zum Setzen der Gebärmutterschleimbeschaffenheit") }}

{{ macros.device_image("{static}../images/screenshot_set_mucus_2.png", "Screenshot zur Auswahl der Gebärmutterschleimbeschaffenheit") }}

##### Auswertung der Gebärmutterschleimbeschaffenheit zur Bestimmung der unfruchtbaren Tage

Die Gebärmutterschleimbeschaffenheit gibt (zusammen mit der Basalthemperatur) Auskunft darüber, wann die unfruchtbaren Tage beginnen. Eine ausführliche Beschreibung finden Sie auf den Seiten von [myNFP](https://www.mynfp.de/temperatur-und-zervixschleim-kombinieren).

Der folgende Screenshot zeigt einen beispielhaften Verlauf:

{{ macros.device_image("{static}../images/screenshot_nfp_mucus.png", "Screenshot eines beispielhaften Verlaufs der Gebärmutterschleimbeschaffenheit") }}

<i class="bi bi-exclamation-triangle"></i><strong> Warnhinweis:</strong> 

Der Screenshot oben gibt ein Beispiel für den Fall, in dem die grüne Einfärbung der Zyklustage irreführend sein kann: Der 15. Tag des Zyklus (Freitag der 22.7.) ist aufgrund des Temperaturanstiegs grün markiert (die erste höhere Messung war am 12. Zyklustag). Die Regeln zur Auswertung der Beschaffenheit des Gebärmutterschleims verlangen allerdings drei aufeinanderfolgende Tage mit schlechterer Schleimqualität. Diese Auswertungsregel ist erst ab dem 16. Zyklustag erfüllt. **Der erste unfruchtbare Tag ist daher erst der 16. Zyklustag und nicht, der aufgrund des Temperaturanstiegs grün eingefärbte 15. Zyklustag!**

{{ macros.device_image("{static}../images/screenshot_nfp_explanation.png", "Überblick über die Visualisierungselemente") }}





