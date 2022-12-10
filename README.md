# The Pelican-powered Website for iButtonCycle

Dieses Repository dient der Verwaltung der Webseiten unter https://ibuttoncycle.myibutton.eu 

## Editieren von Inhalt im Browser über GitHub

## Editieren von Inhalt auf der lokalen Festplatte mit abschließender Veröffentlichung

### Installation aller nötigen Tools

* Git
* Python

### Vorbereitung der Arbeitsumgebung

* `python3 -m venv <name_of_venv>`
* `source <name_of_venv>/bin/activate`
* `python3 -m pip install -r requirements.txt`


### Editieren von Inhalten

* `pelican content --listen --autoreload -o docs -s pelicanconf.py -t themes/simple_bootstrap`
* Editieren von Dateien
* Vorschau unter [127.0.0.1:8000](http://127.0.0.1:8000)

### Veröffentlichung der Webseiten auf ibuttoncycle.myibutton.eu

* `git push``
* Pull request auf GitHub erzeugen
* Pull request reviewen und approven
* Merge nach Main
* Prüfen auf https://ibuttoncycle.myibutton.eu
