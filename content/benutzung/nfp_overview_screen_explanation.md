Title: Die NFP Übersichtsseite
Date: 2022-07-30
star_prio: 2
Summary: Die Dokumentation zur Hauptansicht der iButtonCycle App

{% import 'macros.html' as macros %}

Die Hauptansicht der iButtonCycle App ist eine Darstellung zur thermo-symptomalen Verhütungsmethode der natürlichen Familienplanung. Diese Seite erklärt die wesentlichen Elemente.

## Kalendarische Anordnung

Da iButtonCycle für Smartphones entwickelt wurde, verläuft die Zeitachse im Gegensatz zu den meisten anderen Apps zur Zyklusbeobachtung und natürlichen Familienplanung bei iButtonCycle *vertikal* und nicht horizontal. Die klassische NFP Tabelle, wie sie z.B. [hier zu finden ist](https://www.familienplanung.de/fileadmin/user_upload/familienplanung.de/downloads/Zyklustabelle_1_.pdf), ist um 90° nach rechts gedreht. Das bedeutet:

* Jede Zeile stellt einen Tag im Zyklus dar
* Das tagesaktuelle Datum befindet sich ganz oben in der Liste
* Weiter unten befinden sich vergangene Tage.
* Die Zyklen gehen nahtlos ineinander über (bis zum Beginn des bei der Einrichtung angegebenen ersten Zyklus)
* Horizontale graue Linien zeigen eine neue Woche an
* Bei jedem Monatswechsel wird die Liste unterbrochen

{{ macros.image("{static}../images/screenshot_first_period_set.png", "Screenshot zur Erklärung der Datumsanzeige", padding=4) }}

## Erklärungen zur Farbgebung der Tage

Jeder Tag trägt eine von drei Farben:

* rot, falls an diesem Tag eine Monatsblutung war
* grau, solange noch kein verlässlicher Temperaturanstieg festgestellt wurde
* grün, ab dem Tag, ab dem ein verlässlicher Temperaturanstieg festgestellt wurde (bis zur nächsten Periode)

{{ macros.image("{static}../images/screenshot_nfp_colors_explained.png", "Erklärung zur Farbgebung") }}

{{ macros.info("Eine detaillierte Anleitung zur Basalthemperatur finden Sie <a href=\"{filename}temperature_explanation.md\">hier</a>")}}

{{macros.warning("
Grün eingefärbte Tage beziehen sich <strong>ausschließlich auf die Temperatur</strong>. Die symptothermale Methode verlangt zusätzlich zur Temperatur <strong>ein zweites Symptom</strong>:
<ul>
  <li>Die Beschaffenheit des Gebärmutterschleims</li>
  <li>Der Zustand des Gebärmutterhalses (noch nicht von iButtonCycle unterstützt)</li>
</ul>
<strong>Die unfruchtbare Phase kann dadurch eventuell erst später beginnen, obwohl die Tage schon grün markiert sind!</strong> Siehe das <a href=\"{filename}temperature_explanation.md\">Beispiel</a>.
")}}


## Erklärung zur in der NFP Übersicht verwendeten Daten und Symbole

In der klassischen NFP Tabelle gibt es unterhalb des Temperaturverlaufs mehrere Zeilen, in denen vermerkt wird, wie die Beschaffenheit des Gebärmutterschleims war, ob man Geschlechtsverkehr hatte, oder andere Symptome aufgetreten sind. Die NFP Übersicht in iButtonCycle zeigt diese Dinge ebenfalls an, allerdings aufgrund der 90° Drehung der Tabelle als Spalten.

Der folgende Screenshot gibt einen Überblick:
{{ macros.image("{static}../images/screenshot_nfp_explanation.png", "Übersicht über Informationen in NFP Darstelltung") }}

### Darstellung der Basaltemperatur

Neben der Angabe des Kalendertags am linken Bildschirmrand gibt ein Punkt die Basaltemperatur an. Je weiter rechts der Punkt erscheint, desto höher war die Basaltemperatur. Ignorierte Messwerte werden durch einen grauen (statt schwarzen) Punkt dargestellt.

{{macros.info("Weitere Informationen zur Basalthemperatur finden Sie <a href=\"{filename}temperature_explanation.md\">hier</a>")}}

### Darstellung der Beschaffenheit des Gebärmutterschleims

Rechts neben der Anzeige der Basaltemperatur wird die Beschaffenheit des Gebärmutterschleims durch die Anzeige eines der Symbole `t`, `-`, `f`, `S`, `S+` angegeben.

{{macros.info("Weitere Informationen zur Beschaffenheit des Gebärmutterschleims finden Sie <a href=\"{filename}mucus_explanation.md\">hier</a>")}}

### Darstellung von Sex

Um das Risiko einer Schwangerschaft besser abschätzen zu können, können Sie eintragen, wann Sie Sex hatten, und ob Sie verhütet haben oder nicht. iButtonCycle unterscheidet die folgenden drei Fälle und stellt sie durch ein entsprechendes Symbol dar:

<div class="table-responsive">
<table class="table">
<thead><tr><th>Symbol</th><th>Art des Sex</th><th>Beschreibung</th></thead>
<tbody>
<tr><td><img src="{static}../images/condom.png" alt="Condom icon"/></td><th scope="row">mit Verhütung</th><td>Sie hatten Geschlechtsverkehr und haben ein Verhütungsmittel wie z.B. Kondome benutzt</td></tr>
<tr><td><img src="{static}../images/sperm.png" alt="Sperm icon"/></td><th scope="row">ohne Verhütung</th><td>Sie hatten Geschlechtsverkehr und haben <strong>kein</strong> Verhütungsmittel verwendet</td></tr>
<tr><td><img src="{static}../images/shield.png" alt="Shield icon"/></td><th scope="row">ohne Geschlechtsverkehr</th><td>Sie hatten Sex ohne Geschlechtsverkehr, so dass keine Gefahr einer Empfängnis besteht</td></tr>
</tbody>
</table>
</div>

### Weitere Anmerkungen

iButtonCycle erlaubt die Aufzeichnung von einer ganzen Reihe von Symptomen, Notizen etc. Wenn ein Tag weitere Anmerkungen enthält, erscheint am rechten Rand ein &#9432; Symbol.

Durch tippen auf den jeweiligen Tag gelangen Sie zur Detaildarstellung, in der Sie sehen können, welche Anmerkung sich hinter dem &#9432; verbirgt.

Anmerkungen können sich beziehen auf

* die Temperaturmessung
* das Körpergewicht
* Sex
* die Fruchtbarkeitssymptome
* die Periode
* Körpersymptome wie Kopfschmerzen
* Stimmungen

{{macros.info("Eine detaillierte Darstellung finden Sie <a href=\"{filename}nfp_detail_screen_explanation.md\">hier</a>")}}








