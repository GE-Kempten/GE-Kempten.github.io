# IT-Systeme

### Kompetenzen

- Bauen eines funktionsfähigen Rechners, dazu werden
- **Digitale Schaltungen**, also die Boole'sche Algebra gebraucht um
- **Logische Bausteine** zu erstellen, welche elementare Bauteile für das
- **Programmierbare System** liefert. Dem nun funktionsfähigen Rechner möchten wir einfacher Befehle zuordnen können, wodurch die
- **Assemblerprogammierung** in Kraft tretet. Anschließend sollen noch
- **Peripherie**(-Geräte) mit dem Rechner kommunizieren.

# Digitale Schaltungen

## Einführung

### Schaltnetze und Schaltwerk

Ein Rechner enthält viele digitale Schalter, welche jeweils den Zustand 0 = Off oder 1 = On haben. 

**Digitale Schaltungen**: Je nach _Spannungspegel_ fließt 0 oder 5 Volt. Eine Digitale Schaltungen mir 2 Spannungspegel wird auch Binäre Schaltung genannt, d.h. man könnte auch Schalter mit 3 Zuständen erstellen.

Man unterscheidet digitale Schaltungen zwischen Schaltnetzen und Schaltwerken:

|             |Schaltnetze   |Schaltwerken     |
|------------:|--------------|-----------------|
|Gedächtnis   |nein          |ja			   |
|Rückkoppelung|nein          |ja			   |
|Formal auch: |Schaltfunktion|endlicher Automat|

Der Rechner ist ein Schaltwerk, welcher aber durch Schaltnetze realisiert wird.


### Synchronisation

Jeder Schalter benötigt Zeit zum Umschalten (=**Schaltzeit**), so auch digitale Schalter. D.h. dass das Ausgangssignal erst betrachtet werden darf, wenn der _Umschaltvorgang fertig_ ist. 

=> Nutzen von **Synchronisation** -> *Taktsignale*

![Synchronisation](https://puu.sh/t2oUW/81acca0e05.png)

Das **Eingangssignal** wird zu einem bestimmten _Taktzeitpunkt_ angelegt und die
**Ausgangssignale** erst nach einer _festgelegten Anzahl von Takten_ gelesen.


## Schaltfunktionen

### Defintion und Begriffe

**Defintion Schaltfunktion**:

>Sei V={0, 1} die Menge der beiden Signale 0, 1. Die Funktion

>![Funktion](https://puu.sh/t2oU3/803a519966.png)

>mit m,n ≥ 1 heißen *Boole'sche Funktionen* oder auch *Schaltfunktionen*.

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
|f1|\lnot a|Negation|
|f2|a|Identität|
|f3|1|Konstante 1|

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
|f0|0|_Konstante 0_|
|f1|a \land b|Konjunktion (AND)|
|f2|\lnot (a \Rightarrow b)|Negation der Implikation|
|f3|a|_Identität a_|
|f4|\lnot (b \Rightarrow a)|Negation der Implikation|
|f5|b|Identität b|
|f6|\lnot (a\Leftrightarrow b)|Antivalenz (XOR)|
|f7|a \lor b|Oder(OR)|
|f8|\lnot (a\lor b)|Nicht-Oder (NOR)|
|f9|a \Leftrightarrow b|Äquivalenz|
|f10|\lnot b|Negation b|
|f11|b \Rightarrow a|Implikation|
|f12|\lnot a|_Negation a_|
|f13|a \Rightarrow b|Implikation|
|f14|\lnot (a \land b)|Nicht-Und (NAND)|
|f15|1|_Konstante 1_|

**Todo**: Hinzufügen von mathematischen Symbolen

- \lnot
- \land
- \lor
- \Rightarrow
- \Leftrightarrow

### Sätze der Boole'schen Funktionen 

![Sätze](https://puu.sh/t2NEW/3b5c50a19a.png)

### Boole'sche Algebra

**Definition**:

> Eine _nichtleere Menge V_ auf der _zwei zweistellige Verknüpfungen \land und \lor definiert sind_, heißt **Verband**, wenn die nachfolgende aufgeführten _Axiome 1-4_ gelten

|Axiom|Gesetz|Formel 1| Formel 2|
|:-:|:-:|---|---|
|1|**Kommutativgesetz**|a \land b = b \land a| a \lor b = b \lor a|
|2|**Assoziativgesetz**|(a \land b) \land c = a \land (b \land c)| (a \lor b) \lor c = a \lor (b \lor c)|
|3|**Asorptionsgesetz**|a \land (a \lor b) = a| a \lor (a \land b) = a|
|4|**Existenz neutraler Elemente**|a \land 1 = a| a \lor 0 = a|

> Ein Verband heißt **distributiver Verband**, wenn zusätzlich noch das _Axiom 5_ gilt.

> Ein Verband heiß **komplementärer, distributiver Verband**, wenn zusätzlih noch das Axiom 6 gilt.

|Axiom|Gesetz|Formel 1| Formel 2|
|:-:|:-:|---|---|
|5|**Distributivgesetz**|a \land (b \lor c) = (a \land b) \lor (a \land c)| a \lor (b \land c) = (a \lor b) \lor (a \lor c)|
|6|**Definition des komplementären Elements**|a \land \lnot a = 0| a \lor \lnot a = 1|

> Ein _komplementärer, distributiver Verband_ wird **Boole'scher Verband** oder auch **Boole'sche Algebra** genannt.

**Anmerkung**: Die **Schaltalgebra** ist eine spezielle Form einer Boole'schen Algebra.

- Menge V = {0,1}
- \lor = logisches ODER
- \land = logisches UND

### Boole'sche Terme

**Definiton**:

> Boole'sche Terme sind **induktiv** wie folgt definiert:

- 0 und 1 sind Boole'sche Terme
- Jede Variable (a,b,c...) ist ein Boole'scher Term
- sind t1 und t2 Boole'sche Terme, so auch:

> 1. t1 \lor t2
> 2. t1 \land t2
> 3. \lnot t1
> 4. (t1)

**Beispiele für Beweise**:

![Beweise](https://puu.sh/t3tCk/56274bda77.png)

### Dualität

**Defintion**:

> Zu jedem Boole'schen Term t ergält man den dualen Term t^d, indem man \lor und \land, sowie 1 und 0 vertauscht.

Der Boole'sche Term und der duale Term haben nicht unbedingt den gleichen Wert!

=> Satz: Für jeden beliebigen Boole'schen Term gilt:

![Satz](https://puu.sh/t3tXP/b82c874b9b.png)

Anwendung: Negation bilden und Zeichen austauschen

![Anwendung](https://puu.sh/t3u7R/0446433100.png)

### Rechengesetze

Aus den Axiomen der Boole'schen Algebra lassen sich eine Reihe von Sätzen ableiten:

|Name|Satz||
|--:|---|---|
|Idempotenz|a \lor a = a|a \land a = a|
|deMorgan|\lnot (a \lor b) = \lnot a \land \lnot b|\lnot (a \land b) = \lnot a \lor \lnot b|
|Operation mit 0 bzw. 1|a \lor 1 = 1|a \land 0 = 0|
|Doppeltes Kompliment|\lnot \lnot a = a||
|Negation|\lnot 0 = 1|\lnot 1 = 0|

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
- *Umsetzung*: DNF -> wegen der Konjunktion muss man nur die Terme f(x1,...xn) = 1 betrachten | KNF -> wegen der Disjunktion kann man die Terme f(x1,...xn) = 1 ignoriert werden.

Zur Darstellung von Schaltfunktionen durch Boole'sche Terme genügen neben den Variablen xi die folgenden alternativen Operatormengen: {\lor, \lnot}, {\land \lnot}, {NAND}, {NOR}.

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

**Todo**

# Programmierbare Systeme

**Todo**

# Assemblerprogammierung

**Todo**

# Peripherie

**Todo**
