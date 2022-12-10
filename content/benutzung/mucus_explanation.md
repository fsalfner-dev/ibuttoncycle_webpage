Title: Beschaffenheit des Gebärmutterschleims
Date: 2022-12-10
Summary: Wie in iButtonCycle die Beschaffenheit des Gebärmutterschleims verwendet wird.

{% import 'macros.html' as macros %}
# Einführung zur Beschaffenheit des Gebärmutterschleims in iButtonCycle

Die symptothermale Methode beruht auf der Erkennung eines Temperaturanstiegs zusammen mit der Beobachtung eines weiteren Symptoms, nämlich entweder der Beschaffenheit des Gebärmutterschleims oder des Zustands des Gebärmutterhalses. iButtonCycle unterstützt die Aufzeichnung der Gebärmutterschleimbeschaffenheit. 
Eine gute Erklärung zur Bestimmung der Beschaffenheit des Gebärmutterschleims findet sich bei [myNFP](https://www.mynfp.de/zervixschleim-beobachten).

Es werden die folgenden vier Beschaffenheiten unterschieden: `t`, `-`, `f`, `S`, `S+`

### Bestimmung der Beschaffenheit des Gebärmutterschleims

Zur Bestimmung der Beschaffenheit müssen Empfinden und Aussehen bewertet werden:

<div class="table-responsive">
<table class="table mb-5">
<thead><tr><th>Empfinden</th><th></th><th>Aussehen</th><th>Symbol</th></tr></thead>
<tbody>
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
</tbody>
</table>
</div>

### Notieren der Gebärmutterschleimbeschaffenheit in iButtonCycle

Um die Beschaffenheit des Gebärmutterschleims in iButtonCycle aufzuzeichnen, führe die folgenden Schritte aus:

1. Tippe in der Hauptansicht auf den Tag für den Du die Beschaffenheit notieren willst
1. Tippe auf den kleinen Pfeil im Abschnitt **Fruchtbarkeit**
1. Tippe die blaue Schrift in der Zeile **Zervixschleim** 
1. Wähle darauf die passende Beschaffenheit
1. Tippe auf **Speichern** am oberen Bildschirmrand

Die folgenden Screenshots zeigen den Vorgang:

{{ macros.device_image("{static}../images/screenshot_set_mucus_1.png", "Screenshot zum Setzen der Gebärmutterschleimbeschaffenheit") }}

{{ macros.device_image("{static}../images/screenshot_set_mucus_2.png", "Screenshot zur Auswahl der Gebärmutterschleimbeschaffenheit") }}

### Auswertung der Gebärmutterschleimbeschaffenheit zur Bestimmung der unfruchtbaren Tage

Die Gebärmutterschleimbeschaffenheit gibt (zusammen mit der Basalthemperatur) Auskunft darüber, wann die unfruchtbaren Tage beginnen. Eine ausführliche Beschreibung findest Du auf den Seiten von [myNFP](https://www.mynfp.de/temperatur-und-zervixschleim-kombinieren).

Der folgende Screenshot zeigt einen beispielhaften Verlauf:

{{ macros.device_image("{static}../images/screenshot_nfp_mucus.png", "Screenshot eines beispielhaften Verlaufs der Gebärmutterschleimbeschaffenheit") }}

{{macros.warning("
Der Screenshot oben gibt ein Beispiel für den Fall, in dem die grüne Einfärbung der Zyklustage irreführend sein kann: Der 15. Tag des Zyklus (Freitag der 22.7.) ist aufgrund des Temperaturanstiegs grün markiert (die erste höhere Messung war am 12. Zyklustag). Die Regeln zur Auswertung der Beschaffenheit des Gebärmutterschleims verlangen allerdings drei aufeinanderfolgende Tage mit schlechterer Schleimqualität. Diese Auswertungsregel ist erst ab dem 16. Zyklustag erfüllt. <strong>Der erste unfruchtbare Tag ist daher erst der 16. Zyklustag und nicht, der aufgrund des Temperaturanstiegs grün eingefärbte 15. Zyklustag!</strong>
")}}