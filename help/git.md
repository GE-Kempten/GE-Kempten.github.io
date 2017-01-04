<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Git

Git ist ein distributed version control system, mit dem sich Dateien kollaborativ verwalten lassen. Im Fall dieser Website verwenden wir den kostenlosen Service von GitHub als _remote repository_, auf dem die Dateien gespeichert werden. Jeder _Contributor_ unterhält außerdem ein lokales Repo auf seinem Computer, in dem er Dateien bearbeiten kann. Ist eine Bearbeitung abgeschlossen, können die Veränderungen (_Commits_) auf den Server ge_push_t werden, sodass sich andere Bearbeiter die aktuelle Version des Projekts vom Server _pull_en können.

## Einrichtung von Git

Es gibt zwar auch Gui-Programme für Git, aber den kompletten Funktionsumfang bekommt man nur in der Terminal-Version. Nach der [Installation](https://git-scm.com/) sollte man zunächst den Benutzernamen (`git config --global user.name "[Benutzername]"`) und die Email (`git config --global user.email "[email@domain.tld]"`) festlegen. Dann kann das Repository mit dem Befehl `git clone [URL]` an einen entsprechenden Ort heruntergeladen werden. Die Url findet sich auf der [Projektseite](https://github.com/GE-Kempten/GE-Kempten.github.io) unter dem grünen Download-Knopf.

## Workflow

Sobald die Einrichtung abgeschlossen ist und das Repo mit `git clone [URL]` geklont wurde, können Änderungen an den Dateien vorgenommen werden. Wenn seit dem Klonen bereits Zeit verstrichen ist, kann mit `git pull` die aktuelle Version heruntergeladen werden.

Die im Projektordner enthaltenen Dateien können wie jede andere Datei auf dem Computer bearbeitet werden. Bearbeitungen, Löschungen oder Neuzugänge können mit `git add [Datei 1] [Datei 2] [...]` (oder mit `git add .` um alle Änderugnen auszuwählen) zu einem neuen Commit hinzugefügt werden. Mit `git status` lässt sich anzeigen, welche Dateien bearbeitet wurden und ob diese bereits zu einem Commit hinzugefügt wurden. Ist die bearbeitung abgeschlossen, kann der Commit mit `git commit -m "[Nachricht]"` abgeschlossen werden. Dabei sollte möglichst genau beschrieben werden, was verändert wurde. Es empfiehlt sich, für eine jede Bearbeitung einen eigenen Commit anzulegen, sodass leicht nachvollzogen werden kann, was verändert wurde. Die Commits werden zunächst lokal auf dem Computer gespeichert und können mit `git push` auf GitHub veröffentlicht werden.

## Quick Reference

Hier sind die einfachsten Commands für die Navigation im Terminal und die Verwendung von Git aufgelistet.

### Navigation im Terminal

Real pros use Linux, also sind funktionieren einige Commands eventuell nicht auf Window$ oder macO$. Aber da hilft das Internet... ;)

|Command                    |Effekt                                            |
|---------------------------|--------------------------------------------------|
|cd [ORDNER]                |Navigiere in einen Ordner                         |
|cd ..                      |Übergeordneter Ordner                             |
|ls                         |Liste den Inhalt des Ordners auf                  |
|cat [Datei]                |Gib den Inhalt eier Textdatei aus                 |
|touch [Datei]              |Erstelle neue Datei oder aktualisiere das Datum   |
|rm [Datei]                 |Datei löschen                                     |
|rm -rf [Ordner]            |Ordner samt Inhalt löschen (Achtung!)             |
|mv [Quelle] [Ziel]         |Datei bewegen oder umbenennen (Vorsicht in Git!)  |
|mkdir [Ordner]             |Erstelle einen Ordner                             |

### Grundlegende Commands

Git hat unendlich viele Funktionen, hier sind nur die einfachsten aufgelistet. Mehr Commands findet man auch leicht im Internet. :)

|Command                    |Effekt                                |
|---------------------------|--------------------------------------|
|git clone [URL]            |Klone ein Repo                        |
|git pull                   |Lade die aktuelle Version             |
|git status                 |Zeigt an, ob Dateien bearbeitet wurden|
|git add [Datei]            |Fürge eine neue Datei zum Commit hinzu|
|git add .                  |Füge alle Dateien zum Commit hinzu    |
|git remove [Datei]         |Entfernt eine Datei vom Commit        |
|git commit -m "[Nachricht]"|Schließe einen Commit ab              |
|git push                   |Veröffentliche alle lokalen Commits   |
|git mv [Quelle] [Ziel]     |Datei in Git bewegen oder umbenennen  |
