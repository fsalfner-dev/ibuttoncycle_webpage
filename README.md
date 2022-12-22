# Der Web-Inhalt von iButtonCycle

Dieses Repository dient der Verwaltung der Webseiten unter [https://ibuttoncycle.org](https://ibuttoncycle.org).

Die Webseiten werden mit einem sogenannten "static page generator" namens [Pelican](https://docs.getpelican.com/en/latest/index.html) erzeugt, und per [GitHub Actions](https://github.com/features/actions) automatisch auf den Webserver kopiert.

> :warning: **Jeder Commit in diesem Repository überschreibt den Inhalt der Webseite!** Änderungen dürfen also **nur auf GitHub** in diesem Repository gemacht werden.

## Aufbau des Repositories

Sämtlicher Inhalt der Webseite ist im Unterverzeichnis `content` zu finden:

* Artikel zur **Einrichtung** der App oder des iButtons im Unterverzeichnis `einrichtung`
* Artikel zur **Benutzung** der App oder des iButtons im Unterverzeichnis `benutzung`
* **Bilder**, die in den Artikeln verwendet werden liegen im Unterverzeichnis `images`
* Statische Seiten (Impressum, AGB und Datenschutzbelehrung) sind im Unterverzeichnis `pages`

## Aufbau von Artikeln

* `Title`: Titel der Seite
* `Date`: Datum der letzten Änderung
* `Star_prio`: Soll der Artikel auf der Startseite verlinkt werden?
* `Summary`: Kurzbeschreibung


## Editieren von Inhalt im Browser über GitHub

Die folgende Anleitung funktioniert nur für angemeldete Nutzer:innen mit Zugriffsberechtigung auf dieses GitHub Repository. 

#### Ändern einer bestehenden Seite

Der Inhalt der Webseiten unter

## Editieren von Inhalt auf der lokalen Festplatte mit abschließender Veröffentlichung

### Installation aller nötigen Tools

* Git
* Python

### Vorbereitung der Arbeitsumgebung

* `python3 -m venv <name_of_venv>`
* `source <name_of_venv>/bin/activate`
* `python3 -m pip install -r requirements.txt`


### Editieren von Inhalten

* Branch erzeugen und auschecken
*  `pelican content --listen --autoreload -o docs -s pelicanconf.py -t themes/simple_bootstrap`
* Editieren von Dateien
* Vorschau unter [127.0.0.1:8000](http://127.0.0.1:8000)
* Commit der Änderungen auf neuem Branch

### Veröffentlichung der Webseiten auf ibuttoncycle.myibutton.eu

* `git push``
* Pull request auf GitHub erzeugen
* Pull request reviewen und approven
* Merge nach Main
* Prüfen auf https://ibuttoncycle.myibutton.eu
