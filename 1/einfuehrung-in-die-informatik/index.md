<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Einführung in die Informatik

## Kompetenzen

- Informationsdarstellung im Rechner beschreiben
- Einfache Algorithmen und Datenstrukturen wiedergeben
- Die Vorgehensweise beim Übersetzen von Programmen erläutern
- Einfache Automaten und Sprachen definieren
- Die wichtigsten Schritte bei der Software-Entwicklung erläutern

---

# Inhalte

## Einführung

Die Informatik ist die Wissenschaft der automatischen Verarbeitung von Informationen, insbesondere mit Hilfe von Digitalrechnern. Der Begriff setzt sich aus „Information“ und „Automatik“ Sie ist eine interdisziplinäre Wissenschaft mit Wurzeln im Elektroingenieurwesen und in der Mathematik und ist in folgende Teilbereiche unterteilt: 


### Theoretische Informatik

Erforschung der theoretischen Grundlagen, Informations- und Codierungstheorie, Formale Sprachen, Automatentheorie, Algorithmen, Datenstrukturen, Berechenbarkeit, etc.

### Angewandte Informatik

Praktische Anwendung des Rechners in verschiedenen Anwendungsbereichen, ethische und soziale Fragen der EDV, Datenschutz und -sicherheit

### Technische Informatik

Konstruktion von Rechnern, Speicherchips, Prozessoren und Peripheriegeräten, Erforschung und Anwendung Technischer Möglichkeiten

### Praktische Informatik

Konstruktion von System- und Anwendungssoftware, Compilerbau

## Geschichte der Datenverarbeitung

### Konstruktion von Rechenhilfen und mechanischen Rechenmaschinen 

- 2000 v. Chr.: Abakus (Rechenhilfe für die vier Grundrechenarten mit beweglichen Kugeln)
- 100 v. Chr.: Mechanismus von Antikythera (Mechanische Rechenmaschine, die mit Hilfe von Zahnrädern astronomische Berechnungen ermöglicht)
- 1617 n. Chr.: Napier‘sche Rechenstäbchen (Rechenhilfe für Multiplikation und Division)

### Bau digitaler mechanischer Rechenmaschinen (Zahnräder zur Ausführung arithmetischer Operationen)

- 1624: Schickard
- 1640: Pascal
- 1673: Leibniz

### Elektronische mechanische Rechenmaschinen
- 1833: Analytical Engine von Babbage (Erster mit Lochkarten programmierbarer Rechner, logische Trennung von Rechenwerk, Steuerwerk, Speicher und I/O)

### Elektronische Rechenmaschinen mit Relais oder Elektronenröhren
- 1941: Z3, Zuse
- 1944: MARK1, Aiken
- 1946: ENIAC, Eckert u. Mauchly
- Entwicklung zum Microcomputer
- 1955: Einsatz von Transistoren statt Röhren
- 1960: Einsatz von Integrierten Schaltkreisen
- 1970: Einsatz von Hochintegrierten Schaltkreisen
- 1985: Ende der von-Neumann-Architektur

## Grundbegriffe der Informatik

## Information

**Information** ist eine Mitteilung, die sich aus einer Räumichen oder Zeitlichen Folge physikalischer Signale zusammensetzt, die beim Empfänger ein bestimmtes Verhalten bewirkt und Kenntnis über bestimmte Sachverhalte und Vorgänge in einem Teil der wahrgenommenen Realität vermittelt. Information ist immateriell und kann nur in Form von Daten im Rechner verarbeitet werden.

**Daten** stellen Informationen zum Zweck der Verarbeitung anhand bekannter oder unterstellter Abmachungen dar. Sie sind die physikalische Repräsentation von Information. Dabei wird die Information codiert und muss zur Verarbeitung decodiert werden.

Die **Codierung** beschreibt die Art der Repräsentation von Information zur Datenverarbeitung. Mögliche Anforderung an eine Codierung sind Kompakte Darstellung um die Dateigröße zu verringern oder Redundanz um Übertragungssicherheit zu gewährleisten.

Eine **Nachricht** ist eine Folge von Zeichen, die von einem _Sender_ ausgehend in der Form von Daten an einen _Empfänger_ übermittelt wird.

### Codierungstheorie

**(Binär-)Codierung)**: Festlegung einer Abbildungvorschrift -> bestimmter Art von Information und bestimmtes Mustern aus Nullen und Einsen

#### Eigenschaften

- **Kompakte Darstellung** -> Möglichst geringe Anzahl an Bits
- **Redundantz**: robust bei Übertragungsfehler
- **Handlichkeit**: leichte Verarbeitnung der Daten

Aber: Nicht alle Anforderungen können gleichzeitig erfüllt werden

=> Entscheidung des Codes durch Anwendungszweck

#### Informationsgehalt

Informationsgehalt/Entscheidungsinformation $$ I $$ eines Zeichens $$ x_i $$ (in bit):
$$ I(x_i) = log_2 \frac {1}{w(x_i)} $$

> $$ w(x_i) $$ -> Auftretungswahrscheinlichkeit des Zeichens $$ x_i $$
> $$ I(x_i) $$ -> minimaler Anzahl von 0/1-Entscheidungen $$

Entropie bzw. mittlerer Informationsgehalt $$ H $$:

$$ H = \sum^n_{i=1} w(x_i) * I(x_i) * log_2 \frac {1}{w(x_i)} 

Mittlere Wortlänge einer Codierung:

$$ L = \sum^n_{i=1} w(x_i) * l(i) $$

> $$ l(i) $$ -> Wortlänge des Codes des i-ten Zeichens 

Shannon'sches Codierungstheorem: $$ L ≥ H $$

> wenn = -> dann Codierung kompakt

Code Redundanz: $$ R = L - H $$

> Größe der Anteil einer Nachricht, die im statistischen Sinne keine Information trägt 

#### Umsetzung

Darstellung von:

- Logische Werte
- Zahlen
- Einzelzeichen
- Zeichenketten

### Logische Werte

- true (1)
- false (0)

|Name|Schreibweise|
|--:|:--|
|Negation|$$ \lnot $$|
|Konjunktion|$$a \land b$$|
|Disjunktion|$$a \lor b$$|

### Polyadische Zahlensysteme
Polyadische Zahlensysteme unterscheiden sich in erster Linie durch ihre Basis, also durch die Anzahl der verwendeten Symbole.
- Zehnersystem (Dezimalsystem): { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 }
- Zweiersystem (Dualsystem): { 0, 1 }
- Vierersystem (Quarternärsystem): { 0, 1, 2, 3 }
- Achtersystem (Oktalsystem): { 0, 1, 2, 3, 4, 5, 6, 7 }
- Sechzehnersystem (Hexadezimalsystem): { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F }

nicht-polyadische Zahlensysteme sind z.B. gemischte Zahlen und römische Zahlen.

#### Natürliche Zahlen

Allgemein Darstellung (natürlichen Zahlen, polyadische Zahlensysteme):

$$ n = \sum^N_{i=0} b_i * B^i = (b_N b_{N-1} ... b_2 b_1 b_0)_B $$

> Arithmetische Operationen funktionieren genauso wie im Dezimalsystem

#### Umrechnung
zwischen Zahlensystemen -> Horner-Schema:

$$ n = ((...(b_N * B + b_{n-1})* B + b_{n-2})* B + ... + b_1)

**Sukzessive Division**:

$$ n : B = q_0 Rest b_0 $$

$$ q_0 : B = q_1 Rest b_1 $$

$$ ... $$

$$ q_{n-2} : B = q_{N-1} Rest b_{N-1} $$

$$ q_{n-1} : B = 0 Rest b_N $$

**Sukzessive Multiplikation**:

$$ q_{N-2} = b_N * B + b_{N-1} $$

$$ q_{N-1} = q_{N-2} * B + b_{N-2} $$

$$ ... $$

$$ q_{N-1} = q_{N-2} * B + b_{N-2} $$

$$ q_0 = q_1 * B + b_1 $$

$$ n = q_0 * B + b_0 $$

![Beispielrechnungen]()

**Vereinfachtes Schema**: Konvertierung in n-große Blöcke -> Blöcke getrennt Konvertieren.

![Vereinfachtes Schema]()

### Ganze Zahleb

- Vorzeichendarstellung:
	- 1. Bit -> Vorzeichen +(0) oder -(1)
	- Aber: Rechnung kompliziert
	- ![Beispielrechnung]()
- Zweierkompliment:
	- Idee: Zahlen geordnet nach: modulo 2N
	- 1. Bit -> Vorzeichen
	- Erzeugen einer negativen Zahl im Zweierkompliment: bitweise Negation und Addition von 1 => einfach zu bilden und einfach Rechnen möglich
	- ![Beispielrechnung]()
- Verschieben des Zahlenbereichs
	- Addition einer Konstante -> alle Zahlen positiv
	- ![Beispielrechnung]()

### Reelle Zahlen

**Festpunktdarstellung**: Komma immer an vorher festgelegten Stelle

![Grafik]()

Bsp: Finanzbereich: EUR in ct, d.h. Verschiebung um 2 Kommastellen

**Gleitpunktdarstellung**: Fest Anzahl von Bits für Vorzeichen (V), Exponent(E) ud Mantisse (M)

![Grafik]()

> Genormte Formate (IEEE):
> - Short Real: V (1bit), E(8bit), Mantisse (23 bit)
> - Long Real: V(1bit), E(11bit), Mantisse (52 bit)

### Einzelzeichen

**ASCII**: American Standard Code for Information Interchange

- Code mit fester Bitlänge (7bit für 128 Zeichen)
- 1967 als Standard veröffentlich
- 0-32 -> Steuerzeichen
- 33-127 -> Druckbare Zeichen

![ASCII-Tabelle]()

#### Erweiterung

- Erweiterter ASCII (8bit) 
	- +128 Zeichen (Sonderzeichen und länderspezifische Ergänzungen)
- ISO-8859-Normen(8bit)
	- Erweiterung für andere Alphabete (kyrillisch, griechisch, thai)
	- ISO-8859-1 für West-Europa enthält ASCII
- Unicode (> 16bit)
	- > 100.000 Zeichen
	- Organisation: 17 Ebenen zu je $$2^{16}$$ = 65536 Zeichen (momentan nur 3 Ebenen gebraucht)

#### UTF-8

Unicode-Zeichen werden eine Byte-Kette mit variabler Länge zugeordnet. 

Dadurch soll Kompatibilität mit bisherigen Zeichensätzen erreicht werden und in Zukunft im Internet den ASCII-Standard und HMTL-Sonderzeichen ablösen.

Code-Zuordnung:

|Unicode|UTF-8|Bemerkung|
|:-:|:-:|:--|
|0000 0000 - 0000 007F|0xxx xxxx|Höchstens Bit 0, restliche Bits entsprechen ASCII Code|
|0000 0080 - 0000 07FF|110x xxxx 10xx xxxx|Die x enthalten die Bitkombination des Unicode-Zeichens|
|0000 0800 - 0000 FFFF|1110 xxxx 10xx xxxx 10xx xxxx|(rechtsbündig aufgefüllt), die Anzahl der 1en- zu Beginn|
|0001 0000 - 0010 FFFF|1111 10xxx 10xx xxxx 10xx xxxx 10xx xxxx|steht für die Anzahl der Bytes|

## Einführung in Algorithmen und Datenstrukturen

## Grundlagen der Automatentheorie und formaler Sprachen

## Grundlagen der Softwareentwicklung

## Wirtschaftliche und gesellschaftliche Bedeutung der Informatik


