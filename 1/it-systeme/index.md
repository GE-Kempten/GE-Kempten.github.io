<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# IT-Systeme

## Kompetenzen

- Bauen eines funktionsfähigen Rechners, dazu werden
- **Digitale Schaltungen**, also die Boole'sche Algebra gebraucht um
- **Logische Bausteine** zu erstellen, welche elementare Bauteile für das
- **Programmierbare System** liefert. Dem nun funktionsfähigen Rechner möchten wir einfacher Befehle zuordnen können, wodurch die
- **Assemblerprogammierung** in Kraft tretet. Anschließend sollen noch
- **Peripherie**(-Geräte) mit dem Rechner kommunizieren.

---

# Digitale Schaltungen

## Einführung

### Schaltnetze und Schaltwerke

Ein Rechner enthält viele digitale Schalter, welche jeweils den Zustand 0 = Off oder 1 = On haben.

**Digitale Schaltungen**: Je nach _Spannungspegel_ fließt 0 oder 5 Volt. Eine Digitale Schaltungen mir 2 Spannungspegel wird auch Binäre Schaltung genannt, d.h. man könnte auch Schalter mit 3 Zuständen erstellen.

Man unterscheidet digitale Schaltungen zwischen Schaltnetzen und Schaltwerken:

|             |Schaltnetz    |Schaltwerk       |
|------------:|--------------|-----------------|
|Gedächtnis   |nein          |ja               |
|Rückkoppelung|nein          |ja       	       |
|Formal auch: |Schaltfunktion|endlicher Automat|

Der Rechner ist ein Schaltwerk, welcher aber durch Schaltnetze realisiert wird.

### Synchronisation

Jeder Schalter benötigt Zeit zum Umschalten (**Schaltzeit**), so auch digitale Schalter. D.h. dass das Ausgangssignal erst betrachtet werden darf, wenn der Umschaltvorgang abgeschlossen ist.

=> Nutzen von **Synchronisation** mithilfe von **Taktsignalen**

![Synchronisation](https://puu.sh/t2oUW/81acca0e05.png)

Das **Eingangssignal** wird zu einem bestimmten _Taktzeitpunkt_ angelegt und die
**Ausgangssignale** erst nach einer _festgelegten Anzahl von Takten_ gelesen.

## Schaltfunktionen

### Defintion und Begriffe

**Defintion Schaltfunktion**:

>Sei $$V=\{0, 1\}$$ die Menge der beiden Signale 0, 1. Die Funktion $$ f: v^n \to n^m $$ mit $$m,n ≥ 1$$ heißen *Boole'sche Funktionen* oder auch *Schaltfunktionen*.

Anmerkung:

- bei _m = 1_ spricht man von *echten* _Boole'schen Funktionen_.
- n heißt *Stelligkeit*.
- m heißt *Wertigkeit*.

Diese Funktion kann auch verschiedene Arten dargestellt werden. Üblich sind:

- Funktionstabellen
- Mathematische Beschreibung mit Boole'schen Termen (Schaltalgebra)
- Schaltbilder, Schaltungsdiagramma

### Funktionstabellen

sind **Auflistung aller möglichen Funktionswerte**.

Bsp: Die Funktion V² -> V (V = {0,1}, V² = V x V)

|a|b|f(a,b)|
|-|-|:----:|
|0|0|0|
|0|1|0|
|1|0|0|
|1|1|1|

### Einstellige Schaltfunktionen

a ist ein Schalzustand.

|a|f0|f1|f2|f3|
|:-:|:-:|:-:|:-:|:-:|
|0|0|1|0|1|
|1|0|0|1|1|

||Schreibweise|Bezeichnung|
|:-:|:-:|:-:|
|f0|0|Konstante 0|
|f1|$$ \lnot a $$|Negation|
|f2|$$ a $$|Identität|
|f3|$$ 1 $$|Konstante 1|

### Zweistellige Schaltfunktionen

a und b sind Schaltzustände.

|a|b||f0|f1|f2|f3|f4|f5|f6|f7|f8|f9|f10|f11|f12|f13|f14|f15|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|0|0||0|0|0|0|0|0|0|0|0|1|1|1|1|1|1|1|
|0|1||0|0|0|0|1|1|1|1|0|0|0|0|1|1|1|1|
|1|0||0|0|1|1|0|0|1|1|0|0|1|1|0|0|1|1|
|1|1||0|1|0|1|0|1|0|1|0|1|0|1|0|1|0|1|

||Schreibweise|Bezeichnung|
|:-:|:-:|:-:|
|f0|$$ 0 $$|_Konstante 0_|
|f1|$$ a \land b $$|Konjunktion (AND)|
|f2|$$ \lnot (a \Rightarrow b) $$|Negation der Implikation|
|f3|$$ a $$|_Identität a_|
|f4|$$ \lnot (b \Rightarrow a) $$|Negation der Implikation|
|f5|$$ b $$|Identität b|
|f6|$$ \lnot (a\Leftrightarrow b) $$|Antivalenz (XOR)|
|f7|$$ a \lor b $$|Oder(OR)|
|f8|$$ \lnot (a\lor b) $$|Nicht-Oder (NOR)|
|f9|$$ a \Leftrightarrow b $$|Äquivalenz|
|f10|$$ \lnot b $$|Negation b|
|f11|$$ b \Rightarrow a $$|Implikation|
|f12|$$ \lnot a $$|_Negation a_|
|f13|$$ a \Rightarrow b $$|Implikation|
|f14|$$ \lnot (a \land b) $$|Nicht-Und (NAND)|
|f15|$$ 1 $$|_Konstante 1_|

### Sätze der Boole'schen Funktionen

![Sätze](https://puu.sh/t2NEW/3b5c50a19a.png)

### Boole'sche Algebra

**Definition**:

> Eine _nichtleere Menge V_ auf der _zwei zweistellige Verknüpfungen $$ \land $$ und $$ \lor $$ definiert sind_, heißt **Verband**, wenn die nachfolgende aufgeführten _Axiome 1-4_ gelten

|Axiom|Gesetz|Formel 1| Formel 2|
|:-:|:-:|---|---|
|1|**Kommutativgesetz**|$$ a \land b = b \land a $$|$$ a \lor b = b \lor a $$|
|2|**Assoziativgesetz**|$$ (a \land b) \land c = a \land (b \land c) $$|$$ (a \lor b) \lor c = a \lor (b \lor c) $$|
|3|**Asorptionsgesetz**|$$ a \land (a \lor b) = a $$|$$ a \lor (a \land b) = a $$|
|4|**Existenz neutraler Elemente**|$$ a \land 1 = a $$|$$ a \lor 0 = a $$|

> Ein Verband heißt **distributiver Verband**, wenn zusätzlich noch das _Axiom 5_ gilt.

> Ein Verband heiß **komplementärer, distributiver Verband**, wenn zusätzlih noch das Axiom 6 gilt.

|Axiom|Gesetz|Formel 1| Formel 2|
|:-:|:-:|---|---|
|5|**Distributivgesetz**|$$ a \land (b \lor c) = (a \land b) \lor (a \land c) $$|$$ a \lor (b \land c) = (a \lor b) \lor (a \lor c) $$|
|6|**Definition des komplementären Elements**|$$ a \land \lnot a = 0 $$|$$ a \lor \lnot a = 1 $$|

> Ein _komplementärer, distributiver Verband_ wird **Boole'scher Verband** oder auch **Boole'sche Algebra** genannt.

**Anmerkung**: Die **Schaltalgebra** ist eine spezielle Form einer Boole'schen Algebra.

- Menge $$ V = \{0,1\} $$
- $$ \lor = $$ logisches ODER
- $$ \land = $$ logisches UND

### Boole'sche Terme

**Definiton**:

> Boole'sche Terme sind **induktiv** wie folgt definiert:

- $$0$$ und $$1$$ sind Boole'sche Terme
- Jede Variable (a, b, c, ...) ist ein Boole'scher Term
- sind $$t1$$ und $$t2$$ Boole'sche Terme, so auch:

> 1. t1 $$ \lor $$ t2
> 2. t1 $$ \land $$ t2
> 3. $$ \lnot $$ t1
> 4. (t1)

**Beispiele für Beweise**:

![Beweise](https://puu.sh/t3tCk/56274bda77.png)

### Dualität

**Defintion**:

> Zu jedem Boole'schen Term $$ t $$ erhält man den dualen Term $$ t^d $$, indem man $$ \lor $$ durch $$ \land $$, sowie $$1$$ duch $$0$$ ersetzt.e26adf920ade9545b797d6ad17

Der Boole'sche Term und der duale Term haben nicht unbedingt den gleichen Wert!

=> Satz: Für jeden beliebigen Boole'schen Term gilt:

![Satz](https://puu.sh/t3tXP/b82c874b9b.png)

Anwendung: Negation bilden und Zeichen austauschen

![Anwendung](https://puu.sh/t3u7R/0446433100.png)

### Rechengesetze

Aus den Axiomen der Boole'schen Algebra lassen sich eine Reihe von Sätzen ableiten:

|Name|Satz||
|--:|---|---|
|Idempotenz|$$ a \lor a = a $$|$$ a \land a = a$$|
|deMorgan|$$ \lnot (a \lor b) = \lnot a \land \lnot b $$|$$ \lnot (a \land b) = \lnot a \lor \lnot b $$|
|Operation mit 0 bzw. 1|$$ a \lor 1 = 1 $$|$$ a \land 0 = 0 $$|
|Doppeltes Kompliment|$$ \lnot \lnot a = a $$||
|Negation|$$ \lnot 0 = 1 $$|$$ \lnot 1 = 0 $$|

**Bemerkung**:

1. Schaltfunktionen lassen sich durch Boole'sche Terme beschreiben.

2. Zwei Boole'sche Terme sind gleich, wenn sie identische Schaltfunktionen beschreiben.

3. Durch Anwenden der Rechengesetze der Boole'schen Algebra lassen sich Schaltungen vereinfachen.

### Disjunktive und Konjunktive Normalform

Vereinfachung der Schreibweise durch folgende Notation:

![Notation](https://puu.sh/t3vd7/a9b00cc781.png)

Jede echte Boole'sche Funktion f lässt sich in einer der beiden folgenden eindeutigen Normalformen schreiben:

**Disjunktive Normalform (DNF)**:

![DNF](https://puu.sh/t3vvQ/4cd4cea76d.png)

**Konjunktive Normalform (KNF)**:

![KNF](https://puu.sh/t3vwa/6f5c629351.png)

**Anmerkung**:

- Die durch _Konjunktion verknüpfte Terme_ der _DNF_ heißen **Minterme**,
- die _entsprechenden Disjunktionen_ der _KNF_ heißen **Maxterme**.
- Aus jeder Schaltfunktion (als Tabelle) kann mit den Normalformen ein äquivalenter Boole'scher Term konstruiert werden.
- *Umsetzung*: DNF -> wegen der Konjunktion muss man nur die Terme $$f(x_1, ..., x_n) = 1$$ betrachten | KNF -> wegen der Disjunktion können die Terme $$f(x_1, ..., x_n) = 1$$ ignoriert werden.

Zur Darstellung von Schaltfunktionen durch Boole'sche Terme genügen neben den Variablen xi die folgenden alternativen Operatormengen: {$$\lor$$, $$\lnot$$}, {$$\land$$, $$\lnot$$}, {$$NAND$$}, {$$NOR$$}.

### Karnaugh-Veitch-Diagramme (KV-Diagramm)

Prinzip:

- Graphische Darstellung der Minterme
- Zusammenfassung von Termen in Beziehungen -> Minimierung der Schaltfunktion (siehe Axiome und Rechengesetze)

Vorgehensweise:

1. Bestimmung der DNF
2. Konstruktion des KV-Diagramms
3. Eintragen der Minterme in das KV-Diagramm
4. Verschmelzung benachbarter Minterme

Beispiel (Übung 1 Aufgabe 8):

![1.8](https://puu.sh/t4y8x/349b4f1d27.png)

# Logische Bausteine

Schaltnetze/Schaltglieder sind digitale Schalteungen, die eine Schaltfunktion realisieren.
Elementare Schaltglieder werden auch Gatter genannt.

## Gatter

<table>
<tr>
	<th>Gatter</th>
    <th>Symbol</th>
    <th>Wahrheitstabelle</th>
</tr>

<tr>
	<td>
    	<ul style="list-style-type:none">
        	<li>NOT</li>
        	<li>\net</li>
        </ul>
    </td>
    <td><img src="https://upload.wikimedia.org/wikipedia/commons/3/31/IEC_NOT_label.svg" alt="NOT" width="170" height="75"></td>

  <td>
  	<table style="width:100%">
    	<tr><th>A</th><th>Y</th></tr>
        <tr><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>0</td></tr>
	</table>
  </td>
</tr>

<tr>
	<td>
    	<ul style="list-style-type:none">
        	<li>AND</li>
        	<li>∧</li>
        </ul>
    </td>
    <td><img src="https://upload.wikimedia.org/wikipedia/commons/c/c2/IEC_AND_label.svg" alt="AND" width="170" height="75"></td>

  <td>
  	<table style="width:100%">
    	<tr><th>A</th><th>B</th><th>Y</th></tr>
        <tr><td>0</td><td>0</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>0</td></tr>
        <tr><td>1</td><td>0</td><td>0</td></tr>
        <tr><td>1</td><td>1</td><td>1</td></tr>
	</table>
  </td>
</tr>

<tr>
	<td>
    	<ul style="list-style-type:none">
        	<li>OR</li>
        	<li>∨</li>
        </ul>
    </td>
    <td><img src="https://upload.wikimedia.org/wikipedia/commons/4/40/IEC_OR_label.svg" alt="OR" width="170" height="75"></td>

  <td>
  	<table style="width:100%">
    	<tr><th>A</th><th>B</th><th>Y</th></tr>
        <tr><td>0</td><td>0</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>1</td></tr>
	</table>
  </td>
</tr>

<tr>
	<td>
    	<ul style="list-style-type:none">
        	<li>XOR</li>
        	<li>⊻</li>
        </ul>
    </td>
    <td><img src="https://upload.wikimedia.org/wikipedia/commons/6/6c/IEC_XOR_label.svg" alt="OR" width="170" height="75"></td>

  <td>
  	<table style="width:100%">
    	<tr><th>A</th><th>B</th><th>Y</th></tr>
        <tr><td>0</td><td>0</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>0</td></tr>
	</table>
  </td>
</tr>

<tr>
	<td>
    	<ul style="list-style-type:none">
        	<li>NAND</li>
        	<li>⊼</li>
        </ul>
    </td>
    <td><img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/IEC_NAND_label.svg" alt="OR" width="170" height="75"></td>

  <td>
  	<table style="width:100%">
    	<tr><th>A</th><th>B</th><th>Y</th></tr>
        <tr><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>1</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>0</td></tr>
	</table>
  </td>
</tr>

<tr>
	<td>
    	<ul style="list-style-type:none">
        	<li>NOR</li>
        	<li>⊽</li>
        </ul>
    </td>
    <td><img src="https://upload.wikimedia.org/wikipedia/commons/3/37/IEC_NOR_label.svg" alt="OR" width="170" height="75"></td>

  <td>
  	<table style="width:100%">
    	<tr><th>A</th><th>B</th><th>Y</th></tr>
        <tr><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>1</td><td>0</td></tr>
        <tr><td>1</td><td>0</td><td>0</td></tr>
        <tr><td>1</td><td>1</td><td>0</td></tr>
	</table>
  </td>
</tr>

</table>

## Technische Realisierung mit Transistoren

Metalloxid-Halbleiter-Feldeffekt-Transistor (_**M**etal**O**xide-**S**emiconductor-**F**ield**E**ffect **T**ransistor_ -> **MOSFET**) wird in der Computertechnik am häufigsten verwendet.

**Todo**

# Programmierbare Systeme

Ein **Universalrechner** nach J. von Neumann (1946/47) besteht aus folgenden essenziellen Bestandteilen:

|Bestandteil|Funktion             |
|-----------|---------------------|
|Rechenwerk |Ausführung von Rechenoperationen und logischen Verknüpfungen|
|Steuerwerk |Steuerung des Programmablaufs|
|Speicher   |Speicherung von Programmen und Daten|
|I/O        |Ein-/Ausgabe von Programmen und Daten|

## Rechenwerk (ALU)

Das Rechenwerk besteht aus mindestens einer [Arithmetisch-Logischen-Einheit](https://de.wikipedia.org/wiki/Arithmetisch-logische_Einheit) (**ALU**), also einem Bauteil, welches sowohl Arithmetische, als auch Logische Operationen ausführen kann.

![ALU](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0f/ALU_block.gif/800px-ALU_block.gif)

- Eine ALU hat drei **Daten**-Busse, zwei für die Eingabe von Operanden sowie einen für die Ausgabe des Ergebnisses.
- Die Daten-Busse sind mit **Registern** verbunden, die gelesen und beschrieben werden können.
- Um den Zugriff auf die Register zu regulieren, wird ein **Tristate-Buffer** verwendet, einem Schalter, der eine Verbindung über eine Steuerleitung unterberechen kann.
- Über einen **OpCode** erfährt die ALU, welcher Operator angewand werden soll und ob es sich um eine arithmetische oder eine logsiche Operation handelt.
- Die **Status**-Leitung enthält Informationen zu dem Ergebnis und wird verwendet um mehrere ALUs miteinander zu verketten.

## Steuerwerk

Damit Operationen hintereinander ausgeführt werden können, wird die Rechenzeit in _Takte_ aufgeteilt, die aus drei _Phasen_ bestehen:

- In der **Holphase** werden die Daten aus den Registern geholt
- In der **Rechenphase** werden Rechenoperationen durchgeführt
- In der **Brignphase** wird das Ergebnis in die Mehrzweckregister zurückgeschrieben

Die **Timing Unit** (auch _TU_) gibt den Takt vor, meißtens mithilfe eines Quarzes. _And yes, that is how you say it._

Alle Operationen, die in einem Takt ausgeführt werden, werden **Mikrobefehl** genannt. Ein **Mikrobefehlswort** setzt sich zusammen aus

- einem **OpCode**, der der ALU mitteilt, welcher Befehl ausgeführt werden soll,
- den Nummern der Steuerleitungen der **Quellregister**, in denen die Operanden liegen,
- sowie einer Steuerleitungsnummer für das **Zielregister**, in dem das Ergebnis gespeichert werden soll.
- Außerdem enthält das Wort eine **Speicheraddresse**
- und Informationen über den **RAM-IO-Modus**.

|OpCode |Quellregister 1|Quellregister 2|Zielregister|Speicheraddresse|IO|
|:-----:|:-------------:|:-------------:|:----------:|:--------------:|::|
|0000 00|00 0000 00     |00 0000 00     |00 0000 00  |00 0000         |00|

Diese Steuersignale werden zu einer Binärzahl zusammengefasst und bilden ein **Mikrobefehlswort**. Eine `1` an einer Stelle bedeutet, dass die entsprechende Leitung eingeschaltet wird; eine `0`, dass die Leitung aus ist.

## Speicher

### RAM

Der **Haupt-** oder **Arbeitsspeicher** wird als Halbleiterspeicher mit wahlfreiem Zugriff realisiert (**R**andom **A**ccess **M**emory), in dem der Prozessor einzelne Bytes lesen und schreiben kann. Man unterscheidet zwischen statischem **SRAM**, der Informationen in _Flip-Flops_ speichert, und dynamischem **DRAM**, der _Kondensatoren_ verwendet. Beide Techniken haben gemein, dass der Speicher in kurzen Abständen aufgefrischt werden muss und die Daten nach dem lesen wieder in den Speicher zurückgeschrieben werden müssen. Da bei DRAM Verluste beim Lesen auftreten können und er langsamer und billiger ist, werden die beiden Techniken in der Praxis oft kombiniert: Zusätzslich zum DRAM-Arbeitsspeicher wird dann ein SRAM-Pufferspeicher verwendet (zB. DDR 4).

**SRAM-Funktionsweise**

Ein SRAM-Baustein besteht aus einem **MAR** (Memory Address Register), einem **MDR** (Memory Data Register) und einer Schaltleitung für Schreib-, Lese-, oder Wartemodus.

### ROM

In Festwertspeichern (**R**ead **O**nly **M**emory) werden konstante Daten gespeichert. Er ist in folgenden Ausführungen möglich:

- **ROM** Read Only Memory: Programmierung fest verdrahtet (Hardcoded, Hardwired)
- **PROM** Programmable Read Only Memory: Ein mal programmierbar
- **EPROM** Erasable Programmable Read Only Memory: Mit spezieller Hardware programmierbar
- **EEPROM** Electrical Erasable Porgrammable Read Only Memory: Programmierung und Löschung einzelner Bytes durch Elektrische Spannung
- **Flash-EPROM**: Programmierbar, Elektronische Löschung ganzer Sektoren durch Elektrische Spannung

# Assemblerprogammierung

Die Aufgabe der CPU ist es, _Assembler-Befehle_ zu auszuführen, welche vom Hersteller definiert werden. Moderne CPUs haben einen Befehlssatz voneinigen hundert Befehlen für Datentransfer und Arithmetische oder logische Operationen.

|Vorteile                       |Nachteile                      |
|:------------------------------|:------------------------------|
|unmittelbarer Hardwarezugang   |Hardwareabhängig               |
|genauere Kontrolle             |Unübersichtlich                |

### Syntax

`Mnemonic [Arg1[,Arg2]] ; Kommentar`

- Speicheradressen werden in eckigen Klammern angegeben
- Werte können in unterschiedlichen Zahlensystemen angegeben werden und werden durch in zusätzliches Zeichen am Ende gekennzeichnet (**b**inär, **h**ex, **d**ez)
- Eine Hexadezimalzahl wird manchmal auch durch ein `$` vor der Zahl gekennzeichnet

### Gängige Befehle

Jeder Prozessor hat seinen eigenen **Assembler-Befehlssatz**. Einige essenzielle Befehle, die in den meißten Befehlssätzen enthalten sind, sind im folgenden Aufgelistet.

```assembly
; Arithmetik
ADD A,B     ; A = A + B
SUB A,B     ; A = A - B
ADD A,[4FFH]; addiere Inhalt von Speicherzelle 4FFH zu A und speichere das Ergebnis in A
ADD A,0101b ; addiere 101 (=5) zu A und speichere das Ergebnis in A
INC B       ; erhöhe B um 1

; Logik
CMP A,B     ; vergleicht Inhalt von A und B
TEST A,B    ; wie CMP, allerdings wird A nicht überschrieben
AND A,B     ; logisches UND der Register A und B
OR A,B      ; logisches ODER der Register A und B
```

**Speichermanagement**

```assembly
LDA [FFH]   ; lade den Inhalt von Speicherzelle FFH
STA [5FH]   ; speichern in Speicherzelle 5FH
MOV A,[FFH] ; lade den Inhalt von FFH in Reg. A
MOV [5FH],A ; speicher den Inhalt des Registers A in Speicherzelle 5FH
```

**Indirekte Adressierung**

```assembly
; Anstatt alle Speicherzellen direkt anzugeben, können Adressen auch in
; Registern gespeichert werden (ähnlich wie Pointer in C++)
MOV B, 110H   ; lade Startadresse des Feldes (110H) in B
MOV A, [B]    ; lade erstes Feldelement in A
ADD X, A      ; bilde Summe
INC B         ; erhöhe B um 1
MOV A, [B]    ; lade zweites Feldelement in A
ADD X, A      ; bilde Summe
              ; usw.
```

**Stacks**

```assembly
; Stacks transferieren Registerinhalte in den Speicher und legen einen
; Stackpointer im Register an.
PUSH A      ; speicher den Inhalt von A in der Speicherzelle, die im Pointer
            ; angegeben ist und erhöhe den Pointer um 1
POP A       ; lade den obersten Wert vom Stack in A und erniedrige den Pointer
```

**Programmsteuerung**

```assembly
; Unbedingte Sprünge
JMP 4FDCh   ; springe an die Stelle 4FDC
JMP loop    ; springe an die Stelle "loop:" im Programm
; Bedingte Sprünge
JZ ende     ; springe nach "ende", wenn die letzte Operation Null war
JNZ ende    ; springe, wenn die letzte Operation nicht Null war
JA weiter   ; (nach CMP) "jump above" vorzeichenloses >
JB weiter   ; (nach CMP) "jump below" vorzeichenloses <
JG weiter   ; (nach CMP) "jump greater" > mit Vorzeichen
JL weiter   ; (nach CMP) "jump less" < mit Vorzeichen
; Unterprogramme
CALL Test   ; Springe in ein Unterprogramm
RET         ; Rückkehr aus einem Unterprogramm (Rücksprungaddresse wird
            ; automatisch im Stack gespeichert, Vorsicht bei Datenübergabe!)
```

### Flagbits

|Flagbit     |Bedeutung                                    |
|:----------:|:--------------------------------------------|
|**C**arry   |Bereichsüberschreitung (Zahl ohne Vorzeichen)|
|**O**verflow|Bereichsüberschreitung (Zahl mit Vorzeichen) |
|**S**ign    |Ergebnis ist negativ                         |
|**Z**ero    |Ergebnis ist Null                            |
|**P**arity  |Ergebnis hat eine gerade Anzahl von Nullen   |

### Programmablauf

Diese Befehle werden in einer im Speicher vorliegenden Reihenfolge von **Opcodes** ausgeführt. Der **Befehlszähler** (eine Variable, die auf den auszuführenden Befehl zeigt) wird nach jeder Aktion _inkrementiert_ oder mittels _Sprungbefehlen_ auf einen anderen Wert gesetzt, um Schleifen, Funktionen, usw. umzusetzen.

Ein als Folge von Opcodes vorliegendes Programm wird in einer Datei gespeichert, die zur Ausführung in den Speicher geladen wird. Dafür durchläuft die CPU den sogenannten **Load-Increment-Execute-Zyklus**. Der Opcode wird geladen, der Befehlszähler wird erhöht, der Befehl wird ausgeführt, Repeat.

# Peripherie

**Todo**

# Der PC

**Todo**
