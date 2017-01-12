<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Lineare Algebra und Analytische Geometrie

## Kompetenzen

- Wesentliche Begriffe der Linearen Algebra und der Analytischen Geometrie wiedergeben
- Wesentliche Berechnungsmethoden der Linearen Algebra und Analytischen Geometrie anwenden
- Einfache algebraische Beweise analysieren und durchführen

---

# Grundbegriffe

## Mengen

Eine **Menge** M ist jede Zusammenfassung von bestimmten wohlunterschiedenen Objekten, welche die Elemente von M genannt werden, zu einem Ganzen. Gehört eine Element $$ x $$ nicht zur Menge $$ M $$, so schreibt man $$ x \notin M $$.

Mengen können endlich oder unendlich viele Elemente enthalten (jedoch keines doppelt) und auf folgende Weise Definiert werden:

- Aufzählung aller Elemente einer Menge: $$ M = \{ 1, 2, 3, 4 \} $$
- Verbale Angabe der Menge: Die Menge $$ M $$ enthält alle natürlichen Zahlen von $$ 1 $$ bis $$ 4 $$, also $$ \{ 1, 2, 3, 4 \} $$
- Durch Auswahl mit Eigenschaften: $$ M = \{ x \in \mathbb{N} \mid 1 \geq x \leq 4 \} $$

## Abbildungen

## Relationen

## Kartesisches Koordinatensystem

Ein Punkt in der Ebene in einem **Koordinatensystem** wird als Ursprung $$O$$ ausgezeichnet. Zwei aufeinander senkrecht stehend Zahlengeraden (die $$x_1$$- und $$x_2$$-Achse) mit dem Schnittpunkt $$O$$ bilden die Koordinatenachsen. Jedem Punkt $$P$$ wird genau ein Zahlenpaar ($$p_1$$, $$p_2$$) zugeordnet, welches die Koordinaten als senkrechte Projektion auf den entsprechenden Achsen repräsentiert: \$$ \mathbb{R} \times \mathbb{R} \{ (x_1, x_2) \mid x_1, x_2 \in \mathbb{R} \} $$

## Punkte

Jeden **Punkt** $$P$$ in der Ebene können wir durch genau einen Pfeil (gerichtete strecke) $$p = \overrightarrow{OP}$$ vom Ursprung $$O$$ zum Punkt $$P$$ beschreiben. Diese Strecke wird auch **Ortsvektor** genannt.

## Vektoren

**Verschiebung**

Durch eine Verschiebung wird jeder Punkt in einer Ebene um den gleichen Betrag verschoben, wobei sich die Länge der Pfeile nicht ändert. Die Verschiebung erzeugt eine Klasse mit unendlich vielen Verschiebungspfeilen, die in Richtung und Länge äquivalent sind.

**Translationsrelation**

Beschreiben wir die Punkte der Ebene durch Koordinatenpaare und die Verschiebungspfeile durch Punktepaare, können wir die Verschiebung mittels einer Relation algebraisch erklären:

- Die Verschiebungen (_Translationen_) definieren auf der Menge der Punktepaare der Ebene eine Relation, die **Translationsrelation** genannt wird.
- Zwei Punktepaare $$A, B$$ und $$C, D$$ stehen in Relation zueinander, wenn sie Verschiebungspfeile in der gleichen Klasse definieren: $$(A, B) \sim (C, D) \iff a_1 - b_1 = c_1 - d_1, a_2 - b_2 = c_2 - d_2$$

Verschiebungspfeile gleicher Richtung und gleicher Länge bilden die **Äquivalenzklasse einer Translationsrelation** oder **Äquivalenzrelationen**. Sie werden auch als **Translationsvektoren** bezeichnet. Der Einfachheit halber wird normalerweise der **Standardvertreter**, also die äquivalente Verschiebung eines Translationsvektors an den Ursprung angegeben: $$(0, 0), (p_1, p_2))$$

**Vektornotation**

Vektoren werden als kleine lateinische Buschtaben mit einem Pfeil $$\overrightarrow{a}$$ oder als fettgedruckte Buchstaben **a** notiert. Wird der Vektor als Pfeil dargestellt, bezeichnen wir die Punkte als **Fußpunkt** und **Spitze**. Im Fall des Standartvertreters eines Vektorpfeils werden nur die beiden Koordinaten der Spitze angegeben und übereinander geschrieben: \$$\overrightarrow{a} = \begin{pmatrix}a_1\\\\a_2\end{pmatrix}$$

### Vektoraddition

Duch Hintereinanderausführung bestimmter Translationen werden alle Punkte der Ebene in eine bestimmte Richtung um einen bestimmten Betrag verschoben: $$\overrightarrow{a} (\begin{pmatrix}a_1\\\\a_2\end{pmatrix}) + \overrightarrow{b}(\begin{pmatrix}b_1\\\\b_2\end{pmatrix}) = \overrightarrow{c}(\begin{pmatrix}a_1+b_1\\\\a_2+b_2\end{pmatrix})$$

## Elementare geometrische Objekte

### der Ebene

### des Raumes

## Einfache Kurven

## Einfache Flächen

## Skalarprodukt

## Orthogonalität

## Längen- und Winkelmessung

## Determinante

### in der Ebene

### im Raum

# Schnittmengenberechnung und Lineare Gleichungssysteme

# Lineare und Affine Abbildungen der Ebene und des Raumes

# Vektor- und Matrizenrechnung in der Ebene und im Raum
