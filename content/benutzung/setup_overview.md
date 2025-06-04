Title: Überblick über Messmethoden
Date: 2024-04-03
star_prio: 1
Summary: Wie kommen Temperaturmessungen in die App?

{% import 'macros.html' as macros %}

## Problemstellung

Die iButtonCycle App unterstützt verschiedene Methoden, wie Temperaturmessungen von Thermometern "in die App" gelangen können. Das ist einerseits schön flexibel, andererseits ist es aber auch nicht ganz einfach, die richtige Anleitung zu finden.

Diese Seite führt Dich anhand von ein paar wenigen Fragen zur richtigen Anleitung. 

## Was für ein Thermometer benutzt Du?

Die NFP Methode verlangt die Bestimmung einer Basaltemperatur mit einem Thermometer. Was für eine Art Thermometer benutzt Du?

**Ein Klick auf eines der Bilder führt Dich zur richtigen Anleitung**

<div class="container p-3">
    <div class="row gx-2 gy-3 align-items-start justify-content-center justify-content-lg-around">
        {{ macros.linkbox("klassisches Fieberthermometer", "{static}../images/foto_fieberthermometer.jpg", "klassisches Fieberthermometer", "#klassisch") }}
        {{ macros.linkbox("iButton", "{static}../images/usb_reader.webp", "iButton", "#ibutton") }}
    </div>
</div>

## Messung mit klassischem Fieberthermometer ## {: #klassisch }

Wenn Du die Basaltemperatur z.B. morgens nach dem Aufwachen mit einem klassischen Thermometer (mit Auflösung in 1/100°C) misst, kannst Du die Basaltemperatur direkt auf der Detailseite eingeben.

Um die Temperatur einzugeben, musst Du zunächst von der NFP Ansicht zu den Details des entsprechenden Tages gehen. Tippe dazu auf den entsprechenden Zeilenbalken in der NFP Ansicht. Im Screenshot unten Sonntag, der 31.3.2024.
{{ macros.device_image("{static}../images/screenshot_temp_klassisch_1.png","Screenshot zum Öffnen des Details Screens") }}

Klappe in der Detailansicht den Abschnitt **Temperatur** aus, indem Du auf den kleinen Pfeil rechts tippst, und tippe dann in der Zeile darunter auf **"editieren"**.
{{ macros.device_image("{static}../images/screenshot_temp_klassisch_2.png","Screenshot wie man zur Temperatureingabe kommt", padding=5) }}

Tippe in das Eingabefeld und gib die gemessene Temperatur ein (37,01°C im Screenshot), und tippe anschließend auf **OK**:
{{ macros.device_image("{static}../images/screenshot_temp_klassisch_3.png","Screenshot wo man die Temperatur eingibt") }}

Die Temperatur wird nun angezeigt. Tippe auf das grüne **Speichern Symbol** am rechten oberen Bildschirmrand, um die Eintragung zu speichern:
{{ macros.device_image("{static}../images/screenshot_temp_klassisch_4.png","Screenshot wie man die Temperatur abspeichert") }}

Die Temperatur wird nun als Punkt in der NFP Ansicht angezeigt:
{{ macros.device_image("{static}../images/screenshot_temp_klassisch_5.png","Darstellung der eingetragenen Tempeatur als Punkt in der NFP Ansicht") }}

## Messung mit dem iButton ## {: #ibutton }

Mit welchem Gerät liest Du den iButton aus?

**Ein Klick auf eines der Bilder führt Dich zur richtigen Anleitung**

<div class="container p-3">
    <div class="row gx-2 gy-3 align-items-start justify-content-center justify-content-lg-around">
        {{ macros.linkbox("ibuttonCycle BlueReader", "{static}../images/foto_fieberthermometer.jpg", "iButtonCycle BlueReader", "#bluereader") }}
        {{ macros.linkbox("USB Lesegerät", "{static}../images/usb_reader.webp", "USB Lesegerät", "#usb") }}
    </div>
</div>

#### Auslesen mit dem BlueReader #### {: #bluereader }

#### Auslesen mit dem USB Reader #### {: #usb }



