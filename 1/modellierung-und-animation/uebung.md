<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Modellieren und Animation Übungen

## Übung 2

### Aufgabe 1: Rendermethoden

**a)** Beschreiben Sie die beiden gängigen Rendermethoden

- **Rasterisierung**: Suche für jeden Pixel nach sichtbaren Dreiecken, Färbe den Pixel in der Farbe des vordersten Dreiecks ein. Renderaufwand steigt linear mit Pixelanzahl, sublinear mit Objektanzahl.
- **Raytracing**: Rückverfolg von Lichtstrahlen von der Kamera zur Lichtquelle. Renderaufwand steigt linear mit Objektanzahl, sublinear mit Pixelanzahl.

**b)** Vor- und Nachteile der Rendermethoden

|             |Raytracing|Rasterisierung|
|-------------|----------|--------------|
|Echtzeitfähig|          |X             |
|Spiegelung   |X         |              |
|Lichtbrechung|X         |              |
|Schatten     |X         |              |
|Fotorealismus|X         |              |

## Übung 4

### Aufgabe 1: Koordinatensystem

**a)** Welches Koordinatensystem verwendet Blender?

Blender verwendet ein rechtshändisches Koordinatensystem, bei dem die z-Achse die Höhe darstellt.

**b)** Welches Koordinatensystem verwendet Blender?

Cinema 4D verwendet ein linkshändisches Koordinatensystem, bei dem die y-Achse die Höhe darstellt.

**c)** In welche Richtung schaut die Kamera, wenn man sie zurücksetzt?

- Cinema 4D: Z-Richtung (horizontal)
- Blender: -Z-Richtung (unten)

### Aufgabe 2: Matrizen

**a)** Wie wird ein Polygon rotiert?

Das Polygon muss in den Ursprung versetzt, mit der Rotationsmatrix multipliziert, und wieder zurück verschoben werden.

**c)**

Verschiebung in den Ursprung:

M_1 = $$ \begin{pmatrix} 1 & 0 & 0 & -2 \\ 0 & 1 & 0 & -1 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} $$

Rotation um 90°:

M_2 = $$ \begin{pmatrix} 0 & -1 & 0 & 0 \\ 1 & 0 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} $$

Verschiebung zur ursprünglichen Position:

M_3 = $$ \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 2 & 1 & 0 & 1 \end{pmatrix} $$


Multiplikation der Matrizen:

M_2 * M_1:

M_{21} = $$ \begin{pmatrix} 0 & -1 & 0 & 1 \\ 1 & 0 & 0 & -2 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} $$

M_3 * M_{21}:

M_{321} = $$ \begin{pmatrix} 0 & -1 & 0 & 3 \\ 1 & 0 & 0 & -1 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} $$

$$ \implies $$ Dann die alten Punkte mit der Matrix multiplizieren.

## Übung 5

### Aufgabe 1

**a)**

Modifier verändern das Mesh nicht

**b)**

Wenn man den Sub-Surf Modifier anwenden würde, wäre es später sehr viel schwieriger das Mesh nochmals zu verändern

Wenn man etwas animieren möchte, ist es leichter mit Modifiern zu arbeiten

### Aufgabe 2

Beschreiben sie die Modifier

**a) Array Modifier**

Erstellt ein Feld von Objekten

**b) Bevel Modifier**

rundet Kanten ab

**c) Boolean Modifier oder alternativ Knife Project**

kombiniert mehrere Objekte nach boolschen Funktionen

**d) Mirror Modifier**

spiegelt das Mesh

### Aufgabe 3: Modellierung mit Lattices

Lattices sind diese Käfige

## Übung 6

### Aufgabe 1: Modellierung mit Splines

Splines sind Pfade

### Aufgabe 2: View Space Transformations

### Aufgabe 3: Mesh-Qualität

![Renderfehler](aufgabe-3.png)
