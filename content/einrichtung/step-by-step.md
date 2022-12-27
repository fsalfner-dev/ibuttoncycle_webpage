Title: Einrichtung in 4 Schritten
Date: 2022-12-10
Star_prio: 1
Summary: Einfache Schritt-für-Schritt Anleitung zur Einrichtung der App

{% import 'macros.html' as macros %}
# Eine einfache Schritt-für-Schritt Anleitung zur Einrichtung der App in vier Schritten

Die iButtonCycle App dient der Aufzeichnung von der Basalthemperatur, der Zervixschleimkonsistenz und vieler anderer Werte und Symptome zur Unterstützung bei der [natürlichen Familienplanung (NFP)](https://www.familienplanung.de/verhuetung/verhuetungsmethoden/natuerliche-methoden-der-familienplanung-nfp/) 
Die App unterstützt die symptomatische Temperaturmethode.

## 1: Installation der App
Wenn Du ein Android Telefon besitzt, gehe zum [Google PlayStore](https://play.Google.com) oder im Falle eines iOS Gerätes zum [Apple AppStore](https://store.Apple.com) und installiere die App

## 2: Auswahl des Speicherorts

Starte die App. 

Du wirst zunächst gefragt, wo die Daten gespeichert werden sollen.

{{ macros.device_image("{static}../images/screenshot_setup_1.jpeg", "Screenshot zu Setup: Auswahl des Speicherorts") }}

Die beiden Optionen bedeuten folgendes:

* **Speicherung auf dem Telefon:**   
    Bei Auswahl dieser Option funktioniert die App eigenständig, alle Daten werden auf dem Telefon gespeichert. Dies ist die einfachste Option, Du musst nichts weiter tun, kannst allerdings auch ausschließlich von diesem Gerät aus auf Deine Daten zugreifen. Backups müssen selbst angelegt werden.

* **Speicherung auf einem Server**
    Bei Auswahl dieser Option verbindet sich die App mit einem Server, den Du selbst installieren und betreiben musst. Das Aufsetzen und der Betrieb des Servers benötigt fundierte IT Kenntnisse, bietet aber auch mehr Flexibilität, zusätzliche Datenauswertungen im Browser und mehr Möglichkeiten zur Datensicherung. 

Eine **Entscheidungshilfe** zwischen den beiden Optionen findest Du [hier]({filename}storage_auswaehlen.md).   

Wenn Du die Option **Speicherung auf dem Telefon** auswählst, tippe einfach auf **Los geht's**. Für die Option *Speicherung auf einem Server* benötigst Du ein Token des Servers, den Du zunächst [aufgesetzt]({filename}server-aufsetzen.md) haben musst.

## 3: Setzen des Datums der ersten Periode

In der iButtonCycle App sind alle Daten in einer Reihe aufgelistet, die vom heutigen Datum Zyklus für Zyklus in die Vergangenheit gehen. Der Anfang der Liste ist der erste Tag der Periode des ersten in der App erfassten Zyklus. Dieses Datum muss in diesem Schritt ausgewählt werden.

{{ macros.device_image("{static}../images/screenshot_setup_3.png", "Screenshot zu Setup: Information zur Datumsauswahl") }}

**Vorbereitung zur Auswahl des Datums:**

Wähle das Datum der ersten in der App erfassten Periode nach folgenden Kriterien aus:

* Du kennst das Datum des ersten Tags der Periode für **alle Zyklen** seit der ausgewählten ersten Periode bis heute. Dies ist für die Vorhersage des nächsten Periodenbeginns nötig, die auf der Länge Deiner bisherigen Zyklen beruht. Du benötigst diese Daten in Schritt 4.
* Du kannst später **keine Eintragungen vor dem ausgewählten Datum** machen. Das ausgewählte Datum ist quasi der "Beginn der iButtonCycle Zeitrechnung".

**Auswahl des Datums**

* Tippe auf *Datum auswählen* 
* Im darauffolgenden Dialog wähle das eben ausgewählte Datum als "Beginn der iButtonCycle Zeitrechnung".
* Tippe auf **OK** 

{{ macros.device_image("{static}../images/screenshot_setup_datumswahl.png", "Screenshot zu Setup: Auswahl des Datums der ersten Periode", padding=4) }}

## 4: Eintragung der weiteren Perioden

Die Vorhersage des Beginns der nächsten Periode basiert auf der Dauer früherer Perioden. Daher muss zumindest der Beginn jeder Periode seit dem unter 3 ausgewählten ersten Periodenstart eingetragen werden, da iButtonCycle davon ausgeht, es gäbe nur einen einzigen Zyklus, der am ausgewählten Datum beginnt und bis heute dauert. Die folgenden Screenshots erklären das Vorgehen für einen Zyklusbeginn, er muss aber für alle Zyklen bis heute durchgeführt werden.

#### 4.1: Ausgangssituation

Wenn Du nach Setzen des ersten Periodendatums (Schritt 3) ganz nach unten scrollst, siehst Du eine Ansicht wie die folgende:
{{ macros.device_image("{static}../images/screenshot_first_period_set.png", "Screenshot zu Setup: Anzeige nach Auswahl des ersten Periodendatums") }}

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
Markiere nach obigem Schema alle Tage, an denen Deine Periode eingesetzt hat. Du kannst natürlich auch beliebige weitere Eintragungen machen. 

Nach Abschluss aller Eintragungen siehst Du am oberen Bildschirmrand eine Vorhersage für das Einsetzen der nächsten Regelblutung:

{{ macros.device_image("{static}../images/screenshot_finished_setup.png", "Screenshot zu Setup: Periodenvorhersage nach Abschluss", padding=4) }}

## Fertig!

Die iButtonCycle App ist nun einsatzbereit! 

{{ macros.info("Solltest Du einen iButton zur Temperaturmessung verwenden, <a href=\"{filename}csv_freischalten.md\">richte als nächstes die Importfunktion ein</a>") }}

{{ macros.info("Eine Dokumentation aller efassbaren Symptome findest Du <a href=\"{filename}../benutzung/nfp_detail_screen_explanation.md\">hier</a>") }}
