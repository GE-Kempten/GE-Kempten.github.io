<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

### Probeklausur INF

- [Hauptseite](https://ge-kempten.github.io/)
- [INF](https://ge-kempten.github.io/1/einfuehrung-in-die-informatik/)

#### Aufgabe 1 (5P)

Die Informatik wird in verschiedene Teilgebiete untergegliedert.

a) Welches Teilgebiet befasst sich mit der Entwicklung von System- und Anwendungssoftware? (1P)

b) Womit beschäftigt sich die Technische Informatik? (4P)

#### Aufgabe 2 (12P)

a) Konvertieren Sie die Zahl $$(1100101011111110)_2$$ in das Oktalsystem und in das Hexadezimalsystem. (2P)

b) Stellen Sie die Zahl $$(0,8)_{10}$$ im Dualsystem dar. Geben Sie das Resultat auf 4 Nachkommastellen gerundet an. (4P)

c) Welche prinzipielle Methoden gibt es, im Rechner negative Zahlen darzustellen? Erläutern Sie jeweils das angewendetete Prinzip. (6P)

#### Aufgabe 3 (6P)

a) Mit welchen Schwierigkeiten ist zu rechnen, wenn man Spezifikationen für sehr umfangreiche Programme formulieren muss? (4P)

b) Welche Teildisziplin der Informatik befasst sich mit der systematischen Behandlung von Spezifikationen? (1P)

c) Wo werden Spezifikationen üblicherweise schriftlich festgehalten? (1P)

#### Aufgabe 4 (12P)

Gegeben sei folgender Algorithmus in Pseudocode-Notation (x, y, r und s seien **ganze** Zahlen!):

```psudo
Lese x aus Datei
s=0
SOLANGE x > 0 WIEDERHOLE
	y = x/10
	r = x-y*10
	WENN r == 5
	DANN
		s = s + 1
	ENDE
	x = y
ENDE
Gebe s aus
```

a) Welche Ausgabe liefert der Algorithmus für x = 525 (3P)

b) Was berechnet der in Teilaufgabe a) angegebene Algorithmus? (3P)

c) Welche Bedeutung hat die Variable r in diesem Algorthmus? (2P)

d) Wie muss der Algorithmus modifiziert werden, damit als Ergebnis s die Quersumme von x berechnet wird. (4P)

#### Aufgabe 5 (12P)

Zur Formulierung von Programmen existieren unterschiedliche Typen von Programmiersprachen.

a) Was ist der Unterschied zwischen einer maschinen-orientierten Sprache und einer problem-orientierten Sprache? (4P)

b) Welche beide grundsätzlichen Vorgehensweisen gibt es, von problem-orientierten Sprachen in maschinen-orientierten Sprachen zu übersetzten? Nennen sie jeweils ein Beispiel für eine Programmiersprache des entsprechenden Typs! (6P

c) Nennen sie jeweils einen Vorteil, der für die entsprechende Vorgehensweise spricht. (2P)

#### Aufgabe 6 (10P)

In der Vorlesung wurde der Datentyp char (Zeichen) dargestellt.

a) Geben sie zwei Funktionen an, die zu diesem Datentyp gehören, und beschreiben Sie sie in Stichpunkten. (4P)

b) Nennen Sie zwei Relationen, die auf diesem Datentyp definiert sind, und erläutern Sie sie kurz. (4P)

c) Nennen Sie zwei Datentypen, die sich aus diesem Datentyp ableiten lassen. (2P)

#### Aufgabe 7 (12P)

Gegeben sei die Buchstabenfolge: K E G S C X A P D F Q H L 

a) Zeichnen Sie den binären Suchbaum, der sich ergibt, wenn die Buchstaben in der obengenannten Reihenfolge in den Baum eingefügt werden. (5P)

b) Mit wievielen Knoten muss verglichen werden, wenn man in diesem Baum überprüfen will, ob der Buchstabe _R_ enthalten ist? Geben sie jeweils die entsprechenden Knoten an. (3P)

c) Welche Knoten können in diesen Baum noch eingefügt werden, ohne dass sich die Suche verlängert? Begründe! (4P)

#### Aufgabe 8 (11P)

Gegeben sei der folgende Automat A:

![Automat A]()

a) Um welchen Typ von Automaten handelt es sich? (1P)

b) Wie lautet die von diesem Automaten akzeptierte Sprache L(A)? (6P)

c) Wie muss der Automat modifiziert werden, damit er die Wörter $$\{ab^n \| n \in \mathbb{N}\}$$ und $$\{ac^n \| n \in \mathbb{N}\}$$ ebenfalls erkennt? Geben Se die jeweiligen Kanten und deren Beschriftung an! (4P)

#### Aufgabe 9 (10P)

Das Software-Engineering kennt die Phase Systemintegration/Systemtest.

a) Beschreiben Sie die Tätigkeiten, die in dieser Phase durchgeführt werden. (4P)

b) Was dient als Grundlage für die Tests? (1P)

c) Was passiert, wenn Tests nicht erfolgreich absolviert werden? (2P)

d) Welche Phasen werden nach einem erfolgreichen Test durchlaufen? (3P)