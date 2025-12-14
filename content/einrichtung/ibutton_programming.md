Title: Den iButton programmieren 
Date: 2025-12-10
Star_prio: 2
Summary: Den iButton für die automatische Temperaturmessung einrichten

{% import 'macros.html' as macros %}

## Inhalt dieser Seite

Bevor der iButton zur Temperaturmessung verwendet werden kann, muss er zunächst "gestartet" werden. 
Wenn Du einen iButton BlueReader besitzt, kannst Du das direkt von der iButtonCycle App aus tun. Diese Seite erklärt, was zu tun ist.

<div class="container p-3">
    <div class="row gx-2 gy-3 align-items-start justify-content-center justify-content-lg-around">
        {{ macros.image("{static}../images/foto_blue_reader.jpg", "iButtonCycle BlueReader") }}
    </div>
</div>


## Hintergrundinformationen

Der iButton ist ein automatisches Thermometer mit einer eingebauten Batterie. Jede Messung verbraucht Energie, daher "schläft" der iButton, wenn Du ihn neu gekauft hast.

Damit der iButton anfängt, Temperaturen zu messen und aufzuzeichnen, muss er zunächst gestartet werden. Dabei müssen zwei Dinge festgelegt werden:

* In welchem zeitlichen Abstand der iButton messen soll
* Wann er mit der ersten Messung starten soll

Die iButtonCycle App bietet **drei verschiedene Messintervalle** an. Welches das für Dich beste Intervall ist, hängt von Deinen individuellen Präferenzen ab. Die folgende Tabelle soll Dir bei der Entscheidung helfen:

<div class="table-responsive">
<table class="table mb-5">
<thead><tr><th>Intervall</th><th>Laufzeit</th><th>Auslesen</th></tr></thead>
<tbody>
<tr>
  <td class="fst-bold">15 Minuten</td>
  <td>knapp 2 Jahre</td>
  <td>nach max. 42 Tagen</td>
</tr>
<tr>
  <td class="fst-bold">30 Minuten</td>
  <td>ca. 3,5 Jahre</td>
  <td>nach max. 84 Tagen</td>
</tr>  
<tr>
  <td class="fst-bold">1x pro Nacht</td>
  <td>ca. 8 Jahre</td>
  <td>keine Beschränkung</td>
</tr>  
</tbody>
</table>
</div>

Eine Messung **alle 15 Minuten** erlaubt eine genaue Erfassung des Temperaturverlaufs. Das kann z.B. interessant sein, wenn die Temperatur auch tagsüber bei Aktivitäten erfasst werden soll.

Die **einmalige Messung pro Nacht** ermöglicht eine lange Laufzeit des iButtons, erlaubt aber keine Auswahl der niedrigsten Temperatur während der Nacht, was hilfreich ist, wenn man z.B. an einem Tag erst sehr spät ins Bett gegangen ist.

Die Messung **alle 30 Minuten** ist ein Kompromiss aus den beiden genannten Varianten.


{{ macros.info("Jede Temperaturmessung verbraucht Energie. Wenn Du länger keine Temperatur messen willst (z.B. während einer Schwangerschaft), dann lohnt es sich, die Messung zu <strong>stoppen</strong>. Wie das geht erfährst Du am Ende dieser Anleitung.") }}

## Einrichtung des iButtons mit der iButtonCycle App

Die Einrichtung erfolgt im Reiter "Daten" der iButtonCycle App. 

<ol>
    <li>
    Schließe den BlueReader an ein USB-Netzteil an. Der USB Stecker ist <strong>lediglich für die Stromversorgung</strong> da - die <strong>Daten werden per Bluetooth</strong> übertragen.<br>
    Der BlueReader leuchtet grün.
    </li>
    <li>
    Lege den iButton auf den BlueReader und halte ihn mit einer Hand fest. Der BlueReader sollte nun <strong>gelb leuchten</strong>
    </li>
    <li>
    Öffne die iButtonCycle App und wechsle in den Bereich <strong>Daten</strong>. Drücke dort auf den Button <strong>Messung starten / stoppen</strong>.
    <div class="mt-3">
        {{ macros.device_image("{static}../images/screenshot_program_ibutton_1.png", "Screenshot zum Start der iButton Programmierung") }}
    </div>
    </li>
    <li>
    Bei der ersten Benutzung benötigt die App die Freigabe für den Standortzugriff. Bitte wähle <strong>Bei Benutzung der App</strong>. Wichtiger Hinweis: iButtonCycle <strong>verwendet den Standort nicht</strong> - die Freigabe ist nötig, damit die App per Bluetooth nach BlueReader Geräten in der Umgebung suchen kann.
    <div class="mt-3">
        {{ macros.image("{static}../images/screenshot_bluereader_2.png","Screenshot zur Ortungsfreigabe", padding=4) }}
    </div>
    </li>
    <li>
    Nun muss das Messintervall und der Zeitpunkt der ersten Messung eingestellt werden.</br>
    Der Zeitpunkt der ersten Messung ist insbesondere dann relevant, wenn die Messung nur einmal pro Nacht erfolgen soll, da so festgelegt wird, <strong>wann die Messung jeweils erfolgt</strong>. Hier kann z.B. 4 Uhr morgens ausgewählt werden.</br>
    Drücke auf <strong>Messung starten</strong> um den iButton zu programmieren.
    <div class="mt-3">
        {{ macros.image("{static}../images/screenshot_program_ibutton_2.png","Screenshot zur Auswahl von Messintervall und Startzeit", padding=4) }}
    </div>
    </li>
    <li>Wenn alles geklappt hat, erscheint eine Meldung mit "Messung wurde gestartet" am unteren Bildschirmrand.
    </li>
</ol>

## Messung stoppen oder ändern

Der iButton kann mit Hilfe der iButtonCycleApp auch gestoppt werden.

<ol>
    <li>
    Schließe den BlueReader an ein USB-Netzteil an. Der USB Stecker ist <strong>lediglich für die Stromversorgung</strong> da - die <strong>Daten werden per Bluetooth</strong> übertragen.<br>
    Der BlueReader leuchtet grün.
    </li>
    <li>
    Lege den iButton auf den BlueReader und halte ihn mit einer Hand fest. Der BlueReader sollte nun <strong>gelb leuchten</strong>
    </li>
    <li>
    Öffne die iButtonCycle App und wechsle in den Bereich <strong>Daten</strong>. Drücke dort auf den Button <strong>Messung starten / stoppen</strong>.
    </li>
    <li>
    Die iButtonCycleApp liest den iButton aus und zeigt an, wie er gerade programmiert ist, wie in folgendem Screenshot:
    <div class="mt-3">
        {{ macros.device_image("{static}../images/screenshot_program_ibutton_3.png", "Screenshot zum Stop der iButton Messung") }}
    </div>
    </li>
    <li>Um die Messung zu stoppen, drücke auf den Button <strong>Messung stoppen</strong>.</br>
    Um die Messung zu ändern, muss sie zunächst gestoppt und dann neu gestartet werden.
    </li>
</ol>

