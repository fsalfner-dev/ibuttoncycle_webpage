# Der Web-Inhalt von iButtonCycle

Dieses Repository dient der Verwaltung der Webseiten unter [https://ibuttoncycle.org](https://ibuttoncycle.org).

Die Webseiten werden mit einem sogenannten "static page generator" namens [Pelican](https://docs.getpelican.com/en/latest/index.html) erzeugt, und per [GitHub Actions](https://github.com/features/actions) automatisch auf den Webserver kopiert.

> :warning: **Jeder Commit in diesem Repository überschreibt den Inhalt der Webseite!** Änderungen dürfen also **nur auf GitHub** in diesem Repository gemacht werden.

## Aufbau des Repositories

Sämtlicher Inhalt der Webseite ist im Unterverzeichnis `content` zu finden:

* Artikel zur **Einrichtung** der App oder des iButtons im Unterverzeichnis `einrichtung/`
* Artikel zur **Benutzung** der App oder des iButtons im Unterverzeichnis `benutzung/`
* **Bilder**, die in den Artikeln verwendet werden liegen im Unterverzeichnis `images/`
* Statische Seiten (Impressum, AGB und Datenschutzbelehrung) sind im Unterverzeichnis `pages/`

## Aufbau von Artikeln

Jeder Artikel besteht aus einer Datei mit der Endung `.md`.

Beim Erzeugen der statischen HTML Seiten wird für jede Datei, die in den oben aufgelisteten Verzeichnissen ist, automatisch eine Seite erzeugt.

Es gibt zwei **Übersichtsseiten**: [ibuttoncycle.org/category/einrichtung.html](https://ibuttoncycle.org/category/einrichtung.html), und [ibuttoncycle.org/category/benutzung.html](https://ibuttoncycle.org/category/benutzung.html). Diese Seiten werden **automatisch aktualisiert**: Neue Artikel erscheinen automatisch.

Jeder Artikel-Markdown-Datei besteht aus 

* einem Header
* einem Inhalt

#### Header
* `Title`: Titel der Seite (*obligatorisch*)
* `Date`: Datum der letzten Änderung (wird nicht automatisch aktulisiert)
* `Star_prio`: Soll der Artikel auf der Startseite verlinkt werden? Falls ja, an welcher Position?
* `Summary`: Kurzbeschreibung, wird unter dem Titel und in den Artikel-Boxen angezeigt. (*obligatorisch*)

Sollen auf der Artikelseite Makros verwendet werden, müssen diese nach dem Header mit
`{% import 'macros.html' as macros %}` eingebunden werden. Die verfügbaren Makros sind in der Datei [themes/simple_bootstrap/templates/macros.html](themes/simple_bootstrap/templates/macros.html) definiert.

#### Inhalt

Für normale Seiten wird die [Markdown Sprache](https://daringfireball.net/projects/markdown/) verwendet. Falls die Konzepte von Markdown nicht bekannt sein sollten, bitte zuerst die Dokumentation lesen.

Sollten die Möglichkeiten von Markdown nicht ausreichen, kann auch einfach HTML eingefügt werden. Vor und nach dem HTML Teil muss allerdings eine Leerzeile stehen.

Soll auf Inhalt aus anderen Dateien verwiesen werden (z.B. bei Einfügen eines Bildes), ist die Syntax `{static}/<relativer Pfad zu statischer Datei>` bzw `{filename}<relativer Pfad zu Markdown Datei>` zu verwenden. Mehr Details finden sich in der [Pelican Dokumentation](https://docs.getpelican.com/en/latest/content.html#linking-to-internal-content).

Sofern die Seite noch nicht fertig ist, bitte oben auf der Seite das Macro `{{macros.info("Diese Seite ist noch unvollständig")}}` einfügen.


## Editieren von Inhalt im Browser über GitHub

Die folgende Anleitung funktioniert nur für angemeldete Nutzer:innen mit Zugriffsberechtigung auf dieses GitHub Repository. 

GitHub verfügt über einen Browser-basierten Editor. Kleinere Änderungen können einfach direkt im Browser gemacht werden.

Um Änderungen zu "speichern" wird durch den Browser ein Commit durchgeführt. Dieser Commit löst automatisch eine Aktualisierung der Webseiten aus. **Jede gemachte Änderung ist also sofort live auf den Webseiten sichtbar**

Daher sollte für größere Änderungen die folgende Variante mit Änderungen auf der lokalen Festplatte gewählt werden. Diese erlaubt einen *Preview* ohne dass die Änderungen live auf der Webseite erscheinen.

## Editieren von Inhalt auf der lokalen Festplatte mit abschließender Veröffentlichung

#### Installation aller nötigen Tools

* Git
* Python
* Texteditor

#### Vorbereitung der Arbeitsumgebung

* Ein virtual environment für Python einrichten: `python3 -m venv <name_of_venv>`
* Das virtual environment aktivieren: `source <name_of_venv>/bin/activate`
* Benötigte Pakete installieren: `python3 -m pip install -r requirements.txt`
* Git repository klonen: `git clone git@github.com:fsalfner-dev/ibuttoncycle_website.git`

#### Editieren von Inhalten

* Repository aktualisieren: `git pull`
* Den lokalen Entwicklungsserver starten:  `pelican content --listen --autoreload -o docs -s pelicanconf.py -t themes/simple_bootstrap`
* Editieren der Dateien mit einem Editor
* Speichern der Datei aktualisiert die Vorschau
* In der Vorschau unter [127.0.0.1:8000](http://127.0.0.1:8000) prüfen, ob die Seite veröffentlicht werden kann
* Commit der Änderungen: `git add .` und `git push`
* Nach ca 2 Min. die Änderungen auf [https://ibuttoncycle.org](https://ibuttoncycle.org) überprüfen
