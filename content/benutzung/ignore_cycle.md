Title: Zyklen von der Auswertung ausnehmen
Date: 2025-12-08
Summary: Im Falle einer Schwangerschaft oder beginnender Menopause können Zyklen von der Auswertung ausgenommen werden.

{% import 'macros.html' as macros %}

## Zielstellung

Die iButtonCycle App wertet z.B. die Länge der Zyklen der letzten zwei Jahre aus, um eine Vorhersage für das Auftreten der nächsten Periode zu treffen. Im Falle einer Schwangerschaft tritt viele Monate keine Periodenblutung auf und es entsteht ein sehr langer "Zyklus", der die Vorhersage der nächsten Periode verfälscht.

Ein weiteres Szenario ist die einsetzende Menopause, in der es z.B. Zyklen ohne Eisprung geben kann, die dann ebenfalls die Vorhersage beeinträchtigen.

Zu diesem Zweck lassen sich einzelne Zyklen von der Auswertung ausnehmen.

## Die Zyklusübersicht

Im Reiter "Zyklus" gibt es eine Übersicht über die vergangenen Zyklen:

{{ macros.image("{static}../images/screenshot_ignore_cycle_1.png", "Screenshot zur Übersicht über Zykluslängen", padding=4) }}

In der Karte "Durchschnittliche Zykluslänge" wird angezeigt, wieviel Tage ein Zyklus im Durchschnitt der letzten zwei Jahre gedauert hat. Diese Zahl wird auch für die Berechnung des Beginns der nächsten Periodenblutung herangezogen.

In der Karte darunter wird eine grafische Darstellung der Zykluslängen über den Zeitverlauf hinweg gegeben:

* Jeder **rote Balken** stellt einen Zyklus dar.
* Die **Länge der Balken** zeigt an, **wie lang der Zyklus** war. 
* Die Zahl rechts neben dem Balken gibt die **Zykluslänge in Tagen** an
* Die **Datumsangaben** im Balken nennt den Beginn und das Ende des Zyklus

Zum Beispiel hat der Zyklus, der am 13.10.25 mit Einsetzen der Periodenblutung begann und bis zum 21.10.25 dauerte (die nächste Periodenblutung hat also am 22.10. begonnen) eine Zyklusdauer von 9 Tagen. Er ist somit deutlich kürzer als die anderen gezeigten Zyklen.

Der **oberste Balken** stellt den aktuell laufenden Zyklus dar. Da noch nicht bekannt ist, wie lange der Zyklus wirklich dauern wird, ist er nicht rot dargestellt, sondern nur angedeutet.

## Einzelne Zyklen von der Auswertung ausnehmen

Die gezeigten Zyklen haben sehr unterschiedliche Längen. Nehmen wir an, wir sind der Meinung, dass der Zyklus mit der Zykluslänge von nur 9 Tagen kein richtiger Zyklus war, und wir möchten ihn von der Auswertung ausnehmen.

Jeder Zyklus-Balken hat am linken Rand einen kleinen Schalter. Durch **Betätigen des Schalters** kann ein Zyklus von der Auswertung ausgenommen werden, wie in folgendem Bild dargestellt:

{{ macros.device_image("{static}../images/screenshot_ignore_cycle_2.png", "Screenshot mit einem ausgenommenen Zyklus", padding=4) }}

Der Balken wird nun **hellblau** dargestellt, was anzeigen soll, dass der Zyklus nicht in der Auswertung berücksichtigt wird. Im Bild ist zu sehen, dass sich dadurch auch die **durchschnittliche Zyklusdauer** von 24.0 auf 31.5 Tage verlängert hat.

Der Zyklus kann jederzeit durch ein **erneutes Betätigen des Schalters** wieder in die Auswertung aufgenommen werden.

## Darstellung von ausgenommenen Zyklen in der Kalenderansicht

Zyklen, die von der Auswertung ausgenommen wurden, werden ebenfalls in der Kalenderansicht hellblau dargestellt, wie in folgenden Screenshot zu sehen ist:

{{ macros.device_image("{static}../images/screenshot_ignore_cycle_3.png", "Darstellung von ausgenommenen Zyklen in der Kalenderdarstellung", padding=4) }}


