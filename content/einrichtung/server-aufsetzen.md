Title: Einen eigenen Server aufsetzen
Date: 2023-06-17
Summary: Detaillierte Anleitung zur Einrichtung eines iButtonCycle Servers

{% import 'macros.html' as macros %}

{{macros.info("Diese Seite ist noch unvollständig")}}

## Voraussetzungen zum Aufsetzen eines eigenen Servers

Die Hardware-Anforderungen an den iButtonCycle Server sind sehr gering - er lässt sich ohne Weiteres auf einem RaspberryPi 4 betreiben.

Zum Betrieb wird ein Linux-basierter Server mit folgenden Anforderungen benötigt:

* der Server muss ein 64-bit Betriebssystem der Architektur `amd64` oder `arm64` haben. 
* der Server benötigt Docker und Docker-compose
* der Server muss über das Internet erreichbar sein. 
* eine eigene Domain 
* Die Möglichkeit DNS Einträge für eine Subdomain zu machen

#### Hinweise zum Betriebssystem

Der iButtonCycle Server verwendet als Datenbank *MariaDB*, die für 32-bit Betriebssysteme nicht als Docker-Container zur Verfügung steht. Daher gibt es die iButtonCycle Server Software nur für ein 64-bit Betriebssystem der Architekturen `amd64` oder `arm64`. 

Für den Betrieb auf einem RaspberryPi bedeutet dies, dass das Standard-Betriebssystem `raspbian` nicht funktioniert, da es lediglich ein 32-bit Betriebssystem ist. Daher stattdessen z.B. die 64-bit Raspberrypi Variante von Ubuntu Server verwenden.

#### Hinweise zu Docker

Der iButtonCycle Server wird als Docker Container zur Verfügung gestellt, d.h. auf dem Server muss Docker und [Docker-compose](https://docs.docker.com/compose/) installiert sein. Installationsanleitungen finden sich [auf den Webseiten von Docker](https://www.docker.com)

#### Hinweise zur Erreichbarkeit über das Internet

Für den Betrieb zu Hause muss daher meistens Port-Forwarding im Router freigeschaltet werden. 

Da bei privaten Internetanschlüssen normalerweise die IP-Adresse alle 24 Stunden wechselt, muss zusätzlich ein dynamischer DNS Dienst wie z.B. [dynDNS](https://ddnss.de) oder [myFRITZ](https://myfritz.net) eingerichtet sein.

#### Hinweise zur eigenen Domain und Subdomain

Damit die iButtonCycle App den Server erreichen kann, muss der iButtonCycle Server über eine eigene Domain erreichbar sein. 

Etwas konkreter greift die App auf eine URL `https://ibuttoncycle-api.<your>.<domain>` zu, wobei das `<your>.<domain>` nur ein Platzhalter für Deine eigene Domain ist - Du benötigst also eine eigene Domain.

Damit Du Nutzer auf Deinem iButtonCycle Server einrichten kannst, etc., gibt es ein Browser-basierte Administrationsoberfläche, die über die URL `https://ibuttoncycle.<your>.<domain>` aufgerufen wird.

Beide URLs (`ibuttoncycle` und `ibuttoncycle-api`) sind Subdomains von `<your>.<domain>` und sollen auf den Server zeigen, auf dem Du den iButtonCycle Server installierst. Dies wird in der Regel dadurch erreicht, dass Du einen `CNAME` oder einen `A` bzw. `AAAA` DNS Eintrag für Deine Domain `<your>.<domain>` erstellst. 

Falls Du Dich an dieser Stelle fragst, wie die App eigentlich "weiß", unter welcher URL sie den Server erreichen kann: die URL ist im (weiter unten beschriebenen) Json-Web-Token enthalten, den Du bei der Einrichtung der App angeben musst.

## Einrichten des Servers

Die Software für den iButtonCycle Server wird über Docker HUB zur Verfügung gestellt. Die [detaillierte Anleitung zur Einrichtung des Servers](https://hub.docker.com/r/fsalfnerdev/ibuttoncycle-api) etc. ist ebenfalls dort hinterlegt und leider nur auf Englisch verfügbar.

Die Anleitung endet damit, dass man eine funktionierende Administrationsoberfläche unter der URL `https://ibuttoncycle.<your>.<domain>` aufrufen kann.

## Einrichten eines iButtonCycle Nutzers im Admin-Interface

Der iButtonCycle Server ist **multi-Benutzerfähig**, kann also die Daten von mehreren App-Nutzer:innen verwalten. Die iButtonCycle App ist allerdings immer nur mit einem:r Nutzer:in verbunden. 

Beispielsweise können so Nutzerkonten für Mutter und Tochter einer Familie eingerichtet werden.

Um einen Nutzer auf dem iButtonCycle Server einzurichten, sind folgende Schritte nötig:

#### 1. Einloggen als Administrator

Bei der Einrichtung des Servers musste in der `.env` Datei unter `IBUTTONCYCLE_ADMIN_PWD` ein Administrator-Passwort vergeben werden. Dieses Passwort wird benötigt, um sich als Administrator einzuloggen.

* Rufe im Browser die URL `https://ibuttoncycle.<your>.<domain>` auf
* Gib' das Administrator-Passwort im rechten Eingabefeld "Administrator Passwort" ein.

{{ macros.image("{static}/images/screenshot_admin_login.png", "Login Screen der Administrationsoberfläche", width=8) }}

#### 2. Anlegen einer Nutzer:in

Um datenschutzrechtliche Probleme zu vermeiden benötigt der iButtonCycle Server keinerlei Email-Adresse oder andere persönliche Daten. Zur Einrichtung eines Nutzers wird lediglich nach Vor- und Nachnamen gefragt. Der Namen dient lediglich der Personalisierung in der App und dem Web-Interface - es **können problemlos Pseudonyme verwendet werden**.

Es wird **kein Passwort benötigt**, da die Authentifizierung über sogenannte JSON-Web-Tokens funktioniert (siehe nächster Abschnitt).

Zum Anlegen eines Nutzerkontos:

* Vor- und Nachname in den entsprechenden Feldern eingeben, und den
* "Nutzer anlegen" Button drücken

{{ macros.image("{static}/images/screenshot_admin_create_user.png", "Neuen Nutzer Anlegen in der Administrationsoberfläche", width=8) }}

#### 3. Token in die App übertragen

Die Authentifikation von Nutzer:innen in iButtonCycle funktioniert über sogenannte "JSON-Web-Tokens" (kurz: JWT). Die Tokens, verwenden kryptografische Verfahren, um sicherzustellen, dass ein:e Nutzer:in berechtigten Zugriff haben.

{{ macros.warning("Tokens sind wie Passwörter - also nicht an unbefugte Personen weitergeben, und auch nicht per Email oder andere unverschlüsselte Kanäle verschicken!") }}

Um einen Token in die App zu übertragen:

* auf den Button "Token anzeigen" klicken
* den Token in die Zwischenablage kopieren

{{ macros.image("{static}/images/screenshot_admin_show_token.png", "Anzeigen des Tokens für die angelegte Nutzer:in", width=8) }}

{{ macros.image("{static}/images/screenshot_admin_copy_token.png", "Anzeigen des Tokens für die angelegte Nutzer:in", width=8) }}



