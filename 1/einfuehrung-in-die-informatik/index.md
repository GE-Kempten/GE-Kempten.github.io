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

- Theoretische Informatik: Erforschung der theoretischen Grundlagen
- Angewandte Informatik: Einsatz des Rechners in verschiedenen Anwendungsbereichen
- Technische Informatik: Konstruktion von Rechnern
- Praktische Informatik: Softwareentwicklung

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
>
> $$ I(x_i) $$ -> minimaler Anzahl von 0/1-Entscheidungen $$

Entropie bzw. mittlerer Informationsgehalt $$ H $$:

$$ H = \sum^n_{i=1} w(x_i) * I(x_i) = \sum^n_{i=1} w(x_i) * log_2 \frac {1}{w(x_i)} $$

Mittlere Wortlänge einer Codierung:

$$ L = \sum^n_{i=1} w(x_i) * l(i) $$

> $$ l(i) $$ -> Wortlänge des Codes des i-ten Zeichens 

Shannon'sches Codierungstheorem: 

$$ L ≥ H $$

> wenn = -> Codierung kompakt

Code Redundanz: 

$$ R = L - H $$

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
|Negation|$$ \lnot a$$|
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

![Addition](https://puu.sh/tr4w2/edf6089322.png)

![Multiplikation](https://puu.sh/tr4vK/27dea8e6d4.png)

#### Umrechnung

##### Pozentrechnung

Die n-te Stelle der Ziffer wird auf Basis des Zahlensystems (Anzahl an möglichen Werten) potenziert und anschließend mit dem Wert der Stelle multipliziert.

Ergebnis: Dezimalzahl

> \$$ (0010 1010)_2 = $$
> 
> \$$ 2^7 * 0 + 2^6 * 0 + 2^5 * 1 + 2^4 * 0 + 2^3 * 1 + 2^2 * 0 + 2^1 * 1 + 2^0 * 0 = $$
>
> 32 + 8 + 2 =
>
> 42

> \$$ (DAB)_{16} = $$
>
> \$$ 16^2 * D + 16^1 * A + 16^0 * B = $$ 
>
> 3328 + 160 + 11 =
>
> 3499

##### Horner-Schema

$$ N = ((...(b_n * B + b_{n-1})* B + b_{n-2})* B + ... + b_1)*B + b_0 $$

> B = Basis des Zahlensystems (z.B. Hexadezimal: 16)
>
> b = Umwandelnde Ziffern; n = Stelle der Ziffer
>
> Ergebnis: Dezimalzahl

**Beispiel 1**: $$(1011)_2$$ in Dezimal

\$$(1011)_2 = (((1*2+0)*2+1)*2+1) $$

\$$(1011)_2 = (11)_{10} $$

**Beispiel 2**: $$(345)_8$$ in Dezimal

\$$(345)_8 = ((3*8+4)*8+5) $$

\$$(345)_8 = (229)_{10} $$

##### Sukzessive Division

Wir nehmen eine beliebige Zahl und teilen diese durch die Basis des gewünschten Systems. Das Ergebnis wird ohne Kommazahl genommen (nicht Runden!) und der Rest neben dran geschrieben. Wenn das Ergebnis 0 erreicht, dann werden die Reste rückwärts aneinandergereiht.

$$ n : B = q_0 Rest b_0 $$

$$ q_0 : B = q_1 Rest b_1 $$

$$ ... $$

$$ q_{n-2} : B = q_{N-1} Rest b_{N-1} $$

$$ q_{n-1} : B = 0 Rest b_N $$

> n = Umwandelbare Zahl
>
> B = Basis des Zielzahlensystems
>
> q = Ergebnis ohne Rest (bzw. ohne Komma)
>
> b = Reste
>
> Anschließend die Reste (b) rückwärts zusammenzählen
>
> Ergebnis: Zahlensystem von B

**Beispiel 1**: Umwandlungs von $$(1337)_{10}$$ nach Binär/Dual

$$ 1337 : 2 = 668 $$ R 1

$$ 668 : 2 = 334 $$ R 0

$$ 334 : 2 = 167 $$ R 0

$$ 167 : 2 = 83 $$ R 1

$$ 83 : 2 = 41 $$ R 1

$$ 41 : 2 = 20 $$ R 1 

$$ 20 : 2 = 10 $$ R 0

$$ 10 : 2 = 5 $$ R 0 

$$ 5 : 2 = 2 $$ R 1 

$$ 2 : 2 = 1 $$ R 0

$$ 1 : 2 = 0 $$ R 1

$$ \implies (1337)_{10} = (0101 0011 1001)_2 $$

**Beispiel 2**: Umwandlung von $$(525)_{10}$$ nach Hexadezimal

$$ 525 : 16 = 32 $$ R D

> **Tipp**: 32*16 = 512 -> 525 - 512 = 13 bzw. D

$$ 32 : 16 = 2 $$ R 0 

$$ 2 : 16 = 0 $$ R 2 

$$ (525)_{10} = (20D)_{16} $$

**Sukzessive Multiplikation**:

$$ q_{N-2} = b_N * B + b_{N-1} $$

$$ q_{N-1} = q_{N-2} * B + b_{N-2} $$

$$ ... $$

$$ q_{N-1} = q_{N-2} * B + b_{N-2} $$

$$ q_0 = q_1 * B + b_1 $$

$$ n = q_0 * B + b_0 $$

> "Braucht niemand" - Jeb 2017

##### Vereinfachtes Schema: 

1. Umrechnung ins Binärsystem
2. Aufteilung jeder Ziffer in ein Block
3. Umwandlung in Zahlensystem anhand Anzahl der Blöcke (2er Potenzen):
	- Oktal: 3 Blöcke ($$2^3$$ = 8)
	- Hexadezimal: 4 Blöcke ($$2^4$$ = 16) 

![Vereinfachtes Schema](https://puu.sh/tr4wd/966ea36969.png)

**Vorteil**: Schnellere und kürzere Umrechnung

**Nachteil**: Nur Umwandlung zwischen 2er Potenzen möglich

### Ganze Zahlen

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
>
> - Short Real: V (1bit), E(8bit), Mantisse (23 bit)
> - Long Real: V(1bit), E(11bit), Mantisse (52 bit)

### Einzelzeichen

**ASCII**: American Standard Code for Information Interchange

- Code mit fester Bitlänge (7bit für 128 Zeichen)
- 1967 als Standard veröffentlich
- 0-32 -> Steuerzeichen
- 33-127 -> Druckbare Zeichen

![ASCII](http://www.jimprice.com/ascii-0-127.gif)

#### Erweiterung

* Erweiterter ASCII (8bit) 
	* +128 Zeichen (Sonderzeichen und länderspezifische Ergänzungen)
* ISO-8859-Normen(8bit)
	* Erweiterung für andere Alphabete (kyrillisch, griechisch, thai)
	* ISO-8859-1 für West-Europa enthält ASCII
* Unicode (> 16bit)
	* 100.000+ Zeichen
	* Organisation: 17 Ebenen zu je $$2^{16}$$ = 65536 Zeichen (momentan nur 3 Ebenen gebraucht)

#### UTF-8

Unicode-Zeichen werden eine Byte-Kette mit variabler Länge zugeordnet. 

Dadurch soll Kompatibilität mit bisherigen Zeichensätzen erreicht werden und in Zukunft im Internet den ASCII-Standard und HMTL-Sonderzeichen ablösen.

Code-Zuordnung:

|Bsp.|Unicode|UTF-8|
|:-:|:-:|:--|
|1.|0000 0000 - 0000 007F|0xxx xxxx|
|2.|0000 0080 - 0000 07FF|110x xxxx 10xx xxxx|
|3.|0000 0800 - 0000 FFFF|1110 xxxx 10xx xxxx 10xx xxxx|
|4.|0001 0000 - 0010 FFFF|1111 10xx 10xx xxxx 10xx xxxx 10xx xxxx|

zu 1.: Höchstens Bit 0, restliche Bits entsprechen ASCII Code.

ab 2.: Die x enthalten die Bitkombination des Unicode-Zeichens (rechtsbündig aufgefüllt), die Anzahl der 1en- zu Beginn steht für die Anzahl der Bytes.

## Einführung in Algorithmen und Datenstrukturen

## Grundlagen der Automatentheorie und formaler Sprachen

## Grundlagen der Softwareentwicklung

## Wirtschaftliche und gesellschaftliche Bedeutung der Informatik

















































