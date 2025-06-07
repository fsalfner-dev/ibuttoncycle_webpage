Title: Einrichtung in 4 Schritten
Date: 2025-06-04
Star_prio: 1
Summary: Einfache Schritt-für-Schritt Anleitung zur Einrichtung der App

{% import 'macros.html' as macros %}

Die iButtonCycle App dient der Aufzeichnung von der Basalthemperatur, der Zervixschleimkonsistenz und vieler anderer Werte und Symptome zur Unterstützung bei der [natürlichen Familienplanung (NFP)](https://www.familienplanung.de/verhuetung/verhuetungsmethoden/natuerliche-methoden-der-familienplanung-nfp/) 
Die App unterstützt die symptomatische Methode, die die Basaltemperatur und die Konsistenz des Gebärmutterschleims auswertet.

## 1: Installation der App
Wenn Du ein Android Telefon besitzt, gehe zum [Google PlayStore](https://play.Google.com) oder im Falle eines iOS Gerätes zum [Apple AppStore](https://store.Apple.com) und installiere die App

Starte die App. 

## 2: Das Tutorial


Zu Beginn wird Dir ein Tutorial angezeigt, das Dir die wesentlichen Elemente der App erklärt.

Drücke auf "Start" um mit dem Tutorial zu starten.

{{ macros.device_image("{static}../images/screenshot_tutorial_1.png", "Screenshot zum Start des Tutorials") }}

{{ macros.spacer() }}

{{ macros.info("Zur Veranschaulichung verwendet das Tutorial <b>fiktive Daten</b>. Bevor Du mit der Benutzung beginnst, werden diese Daten gelöscht.") }}

Der Bildschirm zeigt Dir 8 pulsierende blaue Punkte. Jeder Punkt zeigt auf ein Element wie z.B. den Kalendertag am linken Bildschirmrand. 

**Drücke auf einen pulsierenden Punkt** um zu erfahren, was das Element anzeigt.

## 3: Setzen des Datums der ersten Periode

In der iButtonCycle App sind alle Daten in einer Reihe aufgelistet, die vom heutigen Datum Zyklus für Zyklus in die Vergangenheit gehen. Der Anfang der Liste ist der erste Tag der Periode des ersten in der App erfassten Zyklus. Dieses Datum muss in diesem Schritt ausgewählt werden.

{{ macros.device_image("{static}../images/screenshot_setup_3.png", "Screenshot zu Setup: Information zur Datumsauswahl") }}

**Auswahl des Datums:**

* Wähle das Datum des **Beginns der ersten in der App erfassten Periode**. 
* Achtung: Damit die Vorhersage des nächsten Periodenbeginns möglich ist, wähle ein Datum, ab dem Du den Beginn **aller nachfolgenden Periodenblutungen**  kennst (sonst kann die App nicht ausrechnen, wie lang Deine Zyklen sind).
* Falls Du die Daten nicht zur Hand hast: kein Problem - Du kannst vorherige Zyklen auch später noch nachtragen.

**Eintragen des ersten Zyklus in die App**

* Tippe auf *Datum auswählen* 
* Im darauffolgenden Dialog wähle das eben ausgewählte Datum als "Beginn der iButtonCycle Zeitrechnung".
* Tippe auf **OK** 

{{ macros.device_image("{static}../images/screenshot_setup_datumswahl.png", "Screenshot zu Setup: Auswahl des Datums der ersten Periode", padding=4) }}

## 4: Eintragung der weiteren Perioden

Die Vorhersage des Beginns der nächsten Periode basiert auf der Dauer früherer Perioden. Daher muss zumindest **der Beginn jeder Periode** seit dem unter Punkt 3 ausgewählten ersten Periodenstart eingetragen werden. 

Gehe wie folgt vor, um eine weitere Periode einzutragen:

#### 4.1: Datum des Periodenbeginns finden

Der folgende Screenshot erklärt den Aufbau der iButtonCycle Kalenderansicht.

{{ macros.device_image("{static}../images/screenshot_first_period_set.png", "Screenshot zu Setup: Anzeige nach Auswahl des ersten Periodendatums", padding=4) }}

* Jede Zeile entspricht einem Kalendertag.
* Die Zeile ist rot eingefärbt, wenn Du an diesem Tag Deine Periode hattest.
* Am linken Bildschirmrand wird der Wochentag und das Datum des Kalenders angezeigt, der jeweilige Monat als Einschub in der Liste. In obigem Screenshot ist Sonntag, der 12. Juni 2022 markiert.  
* Am rechten Bildschirmrand wird der Tag des Zyklus angezeigt. Die Zählung beginnt wenn die Periode einsetzt. Der im Screenshot markierte Tag (12.6.2022) ist der 18. Zyklustag.

#### 4.2: Markieren eines Tages als Periodenbeginn

Durch Drücken auf die Zeile (im Beispiel der 12.6.2022) können Eintragungen für den gewählten Tag gemacht werden. Die Eintragungen werden mit einem Bildschirm wie dem folgenden gemacht:
{{ macros.device_image("{static}../images/screenshot_set_period.png", "Screenshot zu Setup: Setzen der Periodenstärke") }}
Du markierst den gewählten Tag als Periodenbeginn wie folgt:

* Drücke auf den (orange umrandeten) Winkel in der Karte "Periode"
* Die Periodenkarte klappt auf
* Ziehe den (orange umrandeten) Schieberegler unter "Periode" nach rechts. Mit dem Schieberegler kannst Du die Stärke der Periodenblutung angeben. Ein Tag gilt als "Periodentag" unabhängig von der Stärke der Blutung.
* Drücke auf den grünen Button "Speichern" am oberen Bildschirmrand.

Du gelangst zurück zum NFP Screen, in dem der gewählte Tag nun rot eingefärbt ist. Der Tag ist nun auch der erste Tag eines neuen Zyklus.

{{ macros.device_image("{static}../images/screenshot_after_setting_next_period.png", "Screenshot zu Setup: NFP Anzeige nach Setzen des nächsten Periodenbeginns", padding=4) }}

#### 4.3: Eintragung aller weiteren Daten des Periodenbeginns 

Wiederhole die Schritte 4.1 und 4.2 für jeden Zyklus bis zum ersten Zyklus (nach unten Scrollen!)

Für die Zyklus-Vorhersage reicht der erste Tag Deiner Periodenblutung. Du kannst aber natürlich auch **mehrere aufeinanderfolgende Tage als Periodenblutung markieren**, um einzutragen, wie lange Deine Periodenblutung angedauert hat.

## Fertig!

Die iButtonCycle App ist nun einsatzbereit! 

{{ macros.info("Solltest Du einen iButton zur Temperaturmessung verwenden, <a href=\"{filename}csv_freischalten.md\">richte als nächstes die Importfunktion ein</a>") }}

{{ macros.info("Eine Dokumentation aller efassbaren Symptome findest Du <a href=\"{filename}../benutzung/nfp_detail_screen_explanation.md\">hier</a>") }}
