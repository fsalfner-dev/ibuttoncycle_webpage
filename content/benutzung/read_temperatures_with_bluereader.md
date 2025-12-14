Title: Temperaturmessungen mit BlueReader auslesen
Date: 2025-12-09
Summary: iButton Temperaturmessungen per BlueReader importieren

{% import 'macros.html' as macros %}

## Worum es geht ## {: #uebersicht }

Es gibt eine bequeme Möglichkeit, die Messwerte des iButtons mit dem iButtonCycle BlueReader auszulesen. Der BlueReader sieht wie folgt aus:

<div class="container p-3">
    <div class="row gx-2 gy-3 align-items-start justify-content-center justify-content-lg-around">
        {{ macros.image("{static}../images/foto_blue_reader.jpg", "iButtonCycle BlueReader") }}
    </div>
</div>

Diese Anleitung erklärt, wie Du die Messwerte mit dem BlueReader auslesen und in die iButtonCycle App übertragen kannst.

## Anleitung zum Auslesen mit der iButtonCycle App

Um die Temperaturmessungen des iButtons mit dem BlueReader auszulesen, gehe wie folgt vor:

<ol>
    <li>
    Schließe den BlueReader an ein USB-Netzteil an. Der USB Stecker ist <strong>lediglich für die Stromversorgung</strong> da - die <strong>Daten werden per Bluetooth</strong> übertragen.<br>
    Der BlueReader leuchtet grün.
    </li>
    <li>
    Lege den iButton auf den BlueReader und halte ihn mit einer Hand fest. Der BlueReader sollte nun <strong>gelb leuchten</strong>
    </li>
    <li>
    Öffne die iButtonCycle App und wechsle in den Bereich <strong>Daten</strong>. Drücke dort auf den Button <strong>iButton auslesen</strong>.
    <div class="mt-3">
        {{ macros.image("{static}../images/screenshot_bluereader_1.png","Screenshot des Datenbereichs mit hervorgehobenem Button zum Auslesen von Messwerten", padding=4) }}
    </div>
    </li>
    <li>
    Bei der ersten Benutzung benötigt die App die Freigabe für den Standortzugriff. Bitte wähle <strong>Bei Benutzung der App</strong>. Wichtiger Hinweis: iButtonCycle <strong>verwendet den Standort nicht</strong> - die Freigabe ist nötig, damit die App per Bluetooth nach BlueReader Geräten in der Umgebung suchen kann.
    <div class="mt-3">
        {{ macros.image("{static}../images/screenshot_bluereader_2.png","Screenshot zur Ortungsfreigabe", padding=4) }}
    </div>
    </li>
    <li>
        Die App liest die neuesten Messwerte vom iButton aus. Insbesondere bei vielen auszulesenden Messwerten kann das einen Moment dauern.
    </li>
    <li>
        Die NFP Methode basiert auf der sogenannten Basaltemperatur (das ist auch die Temperatur, die in der Kalenderansicht angezeigt wird). Je nachdem, wie der iButton eingerichtet ist, erfasst der iButton aber mehrere Messwerte in einer Nacht. Daher muss aus <strong>allen Messwerten einer Nacht die Basaltemperatur bestimmt werden.</strong>. Dies erfolgt in einer separaten Ansicht:
        <div class="mt-3">
            {{ macros.device_image("{static}../images/screenshot_set_base_temp_overview.png","Startscreen zur Festlegung der Basaltemperatur", padding=4) }}
        </div>
        
        Die Details zu dieser Ansicht sind <a href="{filename}determine_basal_temp.md">auf einer separaten Seite erklärt</a>.
    </li>
    <li>
        Nach Drücken des "Speichern" Buttons auf der angezeigten Seite zur Festlegung der Basaltemperaturen wird der Import der Temperaturen wie in folgendem Screen bestätigt:
        <div class="mt-3">
            {{ macros.device_image("{static}../images/screenshot_set_base_temp_confirmation.png","Screenshot mit Bestätigung des Imports von Temperaturmesswerten", padding=4) }}
        </div>
    </li>
    <li>
        Die einzelnen Temperaturmesswerte können später auch in der Tages-Detailansicht eingesehen werden. Dort können auch im Nachgang noch einzelne Messwerte ignoriert und die Basaltemperatur angepasst werden.
        <div class="mt-3">
            {{ macros.device_image("{static}../images/screenshot_details_with_temperatures.png","Screenshot mit Bestätigung des Imports von Temperaturmesswerten", padding=4) }}
        </div>
    </li>
</ol>

