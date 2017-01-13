<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Modellierung und Animation 1

### Kompetenzen

- Überblick über Methoden und Techniken der Modellierung und Animation
- Verständnis über zugrundeliegende Konzepte
- Balance aus Theorie <-> Praxis

### Abgrenzung

Diese Aspekte sind nicht Ziel dieses Faches:

- Pre- und Postproduction, etc.
- Künstlerische Aspekte
- Theoretische Vertiefung
- Software-Umsetzung genannter Konzepte
- Programmspezifische Kenntnisse

### Themen

- [x] Einführung
- [x] Grundbegriffe
- [x] Mathematische Grundlagen (*)
- [x] Modellieren
	- [x] Modellierungstechnik (*)
		- [x] Basics
		- [x] Tools
		- [x] Modifiers
	- [x] Kamera (*)
	- [x] Polygonale Netze (*)
	- [x] Parametrische Patches (*)
	- [x] Einschub: Prozedurales Modellieren (*)
- [ ] Material und Licht
	- [ ] Physikalische Grundlagen
	- [ ] Begriffe für Licht
	- [ ] Licht (Lokale Beleichtung, etc.)
	- [ ] Schatten
	- [ ] Beleuchtung
	- [ ] Shading
	- [ ] Spiegelung
	- [ ] Transparenz
	- [ ] Transluzenz
	- [ ] Dispersion
	- [ ] Coating
	- [ ] Texture Mapping


(*) -> Todo's 













# Einführung

## Geschichte

### Anfang

* Winsor McCay -> 2D-Handzeichnungen (Gertie the Dinosaur, 1914)

![Gertie the Dinosaur](https://31.media.tumblr.com/71a0c9ec0d3a5c17f62f1674e27d3387/tumblr_n63nwtd3vc1sqmphzo1_500.gif)

* Earl Hund & John Bray -> Kombinierung von mehreren Schichten aus durchsichtige Cels (Celluloid)
* Disney -> Innovationsträger:
	* erstmalig Ton -> Steamboat Willie (1928)
	* multiplane camera:
		* Kamera über mehrere Ebene angebracht mit veränderbare Entfernung
		* Jede Ebene trägt eine Animationszelle -> Bewegung in 6 Richtungen
		* ermöglicht: 
			* Geschwindigkeit
			* motion blur
			* Tiefeneindruck

![multiplane camera](https://msmnam.files.wordpress.com/2011/01/multiplane_camera.jpg)

### Computeranimation (CA)

**70er**:

- Forschungsbereich: University of Utah
- Einfache Computeranimation z.B. in Werbung (Star Wars 1977)

**80er**:

- Produktionshäuser mit eigener Software und teilweise spezieller Hardware: Lucasfilm, Pixar
- Kein Zwang zur Realitätsnähe -> Weltraum als Kulisse

**90er**:

- CA wird normal
- Meilensteine: Aliens (Terminator II), Forrest Gump (Ping-Pong), Toy Story (komplett in CA), Titanic (künstliche Figuren, Wasser)
- Kommerzielle Software z.B: Autodesk 3D Studio, Lightwave 3D



## CA in Games

Bringt Nachteile mit:

1. Echtzeitfähigkeit
	- geringere Qualität/Komplexität
	- Mehraufwand für Artist z.B. Level of Detail
2. Weitere Limitationen:
	- Sound
	- Spielphyik wird live ausgewertet z.B. Kollistionsberechnung
	- Event-Handling
	- ...
3. Interaktion:
	- Animationen sind nicht fest vorgegeben z.B. Laufen in verschiedenen Richtungen
	- Oft physikalisch begründet
	- Umgebung:
		- Umgebung muss teilweise komplett ausgearbeitet sein, da die Kamera nicht statisch ist
		- Vereinfachungen sind nicht unbedingt möglich z.B. Türen kann man öffnen
		- Umgebung ist durch den Spieler veränderbar z.B. Gegenstände verschieben










# Grundbegriffe

- Ein Objekt einer 3D-Szene ist i.d.R. letztendlich ein Polygon-Netzmodell - **Mesh**
- Oberfläche eines Objekts -> Verbindung aus mehreren planare Polygone
- Ein Polygon - **Face** besteht aus einer List miteinander verbundener Punkte - **Vertices**
- Ein Vertex ist ein Punkt im **R3** (3D-Kooridnatensystem)
- Unterscheidung zwischen exakter Darstellung - z.B. ein Quader - und einer Näherung - z.B. Kugel
- Anzahl der Polygone = Genauigkeit der Näherung => Speicherplatz, Redering, evtl. Erstellungszeit der Artist










# Mathematische Grundlage

Ein **Polygon** ist definiert durch eine **Menge an Punkten**, i.d.R. besteht ein Polygon aus 3 Punkten.

Ein gesamten Objekt soll verändert werden können, z.B. Verschiebung, Skalierung und Rotation. Das sind **Affine Transformationen** einer Punktmenge in eine andere Punktmenge. Diese werden dargestellt durch **Vektoren und Matrizen**.





## Vektoren

**Notation**:

- Größe definiert durch einen Betrag (_magnitude_) 
- Richtung (_direction_) definiert im Raum 
- Grafische Darstellung als Pfeil -> Länge und Richtung

**Komponentenform**: $$ {\overrightarrow {v}} = \begin{pmatrix} v_0, v_1, \ldots , v_{n-1} \end{pmatrix} $$

**Betrag** ähnl. Notation des Absolutwert: $$ \| {\overrightarrow {v}} \| = \sqrt{\sum_{i=0}^{n-1} v_i^2} $$

**Rechenregeln**:

- Multiplikation mit einem reelen Skalar (positiv und negativ)
- Addition, Subtraktion und Vektoren
- -> siehe Vorlesung [Lineare Algebra und Analytische Geometrie](https://ge-kempten.github.io/1/lineare-algebra-und-analytische-geometrie)
- Skalarprodukt: $$ {\overrightarrow {a}} \cdot {\overrightarrow {b}} = \| {\overrightarrow {a}} \| \| {\overrightarrow {b}} \| \cos(\theta) = \sum_{i=0}^{n-1}  a_i b_i $$
- Vektorprodukt: $$ {\overrightarrow {a}} \times {\overrightarrow {b}} = \begin{pmatrix} a_y b_z & - & a_z b_y \\ a_z b_x  & - & a_x b_z \\ a_x b_y & - & a_y b_x \end{pmatrix} $$





## Matrizen 
- Matrixnotation: $$ A = \begin{pmatrix} a_{00} & \!\ldots\! & a_{0,n-1} \\ \vdots & \!\ddots\! & \vdots \\ a_{m-1,0} & \!\ldots\! & a_{m-1,n-1} \end{pmatrix} $$
- Multiplikation zweier Matrizen: "Zeile mal Spalte"
- Vektoren transformieren durch Matrizen: 
$$ {\overrightarrow {v^{\prime}}} = M {\overrightarrow {v}} = \begin{pmatrix} a_y b_z & - & a_z b_y \\ a_z b_x  & - & a_x b_z \\ a_x b_y & - & a_y b_x \end{pmatrix} \begin{pmatrix} v_0 \\ \vdots \\ v_{n-1} \end{pmatrix} = \begin{pmatrix} v_0^{\prime} \\ \vdots \\ v_{n-1}^{\prime} \end{pmatrix} $$





## Umsetzung

Mit diesen Grundlagen möchten wir nun Translation, Skalierung und Rotation kombinieren und umsetzen. Allerdings existiert _keine 3x3-Matrix_ für die Translation eines 3D-Vektors.

Dieses Problem kann aber gelöst werden, indem wir eine **neue Dimension** hinzufügen -> **homogene Koordinaten**:

$$ \begin{pmatrix} x \\ y \\ z \end{pmatrix} $$ -> $$ \begin{pmatrix} x \cdot \omega \\ y \cdot \omega \\ z \cdot \omega \\ \omega \end{pmatrix} $$ mit Skalierungsfaktor $$ \omega \neq 0 $$

Darstellung im Koordinatensystem: $$ x_k = x/\omega, y_k = y/\omega $$ und §§ z_k = z/\omega $$





### Translation

Eine Translation $$ T(t) = T(t_x, t_y, t_z) $$ versetzt jeden Punkt eines Objektes um einen bestimmten Wert in einer Dimension:

$$ x' = x + t_x $$

$$ y' = y + t_y $$

$$ z' = z + t_z $$

![Ein cooles Beispiel](https://puu.sh/tcboR/ae226ca5b2.png)



Kombiniert mit **homogenen Koordinaten** können wir die Translation nun als einzige **Matrizenmultiplikation** darstellen:

$$ V' = T V $$

$$ \begin{pmatrix} x' \\ y' \\ z' \\ 1 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 & t_x \\ 0 & 1 & 0 & t_y \\ 0 & 0 & 1 & t_z \\ 0 & 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \\ 1 \end{pmatrix} $$

Veranschaulichung: 

$$ V' = T V $$

$$ V = (2, 5, 3, 1) $$

$$ T = (3, -2, 0) $$

$$ \begin{pmatrix} x' \\ y' \\ z' \\ 1 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 & 3 \\ 0 & 1 & 0 & -2 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} 2 \\ 5 \\ 3 \\ 1 \end{pmatrix} $$

![Noch ein cooles Bild](https://puu.sh/tcf9k/837d537ae5.png)

$$ V' = (5, 3, 3, 1) $$





### Skalierung

Eine Skalierung $$ S(s) = S(s_x, s_y, s_z) $$, streckt das Objekt entlang der Achsen. Für jeden Punkt wird die neue Position mit den Skalierungsfaktoren ermittelt:

$$ x' = x \cdot s_x $$

$$ y' = x \cdot s_y $$

$$ z' = x \cdot s_z $$

![Mega cooles Bild](https://puu.sh/tcrbe/891212728d.png)



Darstellung als Matrixmultiplikation:

$$ V' = S V $$

$$ \begin{pmatrix} x' \\ y' \\ z' \\ 1 \end{pmatrix} = \begin{pmatrix} s_x & 0 & 0 & 0 \\ 0 & s_y & 0 & 0 \\ 0 & 0 & s_z & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \\ 1 \end{pmatrix} $$

Veranschaulichung: 

$$ V' = S V $$

$$ V = (-1, 1, 0 1) $$

$$ S = (2, 3, 1) $$

$$ \begin{pmatrix} x' \\ y' \\ z' \\ 1 \end{pmatrix} = \begin{pmatrix} 2 & 0 & 0 & 0 \\ 0 & 3 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} -1 \\ 1 \\ 0 \\ 1 \end{pmatrix} $$

$$ V' = (-2, 3, 0 ,1) $$

Man unterscheidet zwischen **isotropischer** $$ (s_x = s_y = s_z) $$ und **anisotropischer** Skalierung. Das Bsp grade eben ist eine anisotropische Skalierung.

Die Skalierung wird auf jeden Vertex angewendet und daher kann diese auf eine beliebige Punktmenge eines Objektes angewandt werden. Allerdings ist dann die Wahl des **Bezugspunktes** wichtig => **Ursprungspunkt der Skalierung**. I.d.R. ist der Standard-Bezugspunkt der **Objektmittelpunkt**. Abweichende Bezugspunkte sind z.B. Median und Fixpunkt, Individueller Ursprungspunkt, Ursprungspunkt des aktiven Elements, etc.

**Skalierungsfaktor**:

| > 1.0 | < 1.0 |
|:-:|:-:|
|höhere Entfernung vom Pivotpunkt|verringerte Entfernung vom Pivotpunkt|

**Veranschaulichung** - negativer Wert der Skalierungsfunktion:

Gegeben: $$ O_1 = (0, 0), O_2 = (6, 4), S = 0.5 $$ , Pivot: Median

1. Schritt - Mittelpunkt berechnen: $$ P = (O_1 + O_2)/2 = (3, 2) $$
2. Schritt - Rand berechnen: $$ D = S \cdot (O_2 - P) = S \cdot (3, 2) = (1.5, 1) $$
3. Schritt - Skalierte Punkte berechnen: $$ O'_1 = P - D = (1.5, 1), O'_2 = P + D = (4.5, 3) $$  





### Rotation

Um eine Rotation ausführbar zu machen, muss zunächst eine **Rotationsachse** definiert werden.
Im Folgenden Beispiel ist es einer der drei Hauptachsen.

Rotation um die z-Achse - $$ R_z(\varphi) $$:

$$ x' = x \cos(\varphi) - y \sin(\varphi) $$

$$ y' = x \cos(\varphi) + y \sin(\varphi) $$

$$ z' = z $$

![Super Mega cooles Bild](https://puu.sh/tdhOo/41a2a55671.png)



Darstellung als Matrizenmultiplikation:

$$ V' = R V $$

$$ R_x(\varphi) = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & \cos(\varphi) & -\sin(\varphi) & 0 \\ 0 & \sin(\varphi) & \cos(\varphi) & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} $$

$$ R_y(\varphi) = \begin{pmatrix} \cos(\varphi) & 0 & \sin(\varphi) & 0 \\ 0 & 1 & 0 & 0 \\ -\sin(\varphi) & 0 & \cos(\varphi) & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} $$

$$ R_z(\varphi) = \begin{pmatrix} \cos(\varphi) & -\sin(\varphi) & 0 & 0 \\ \sin(\varphi) & \cos(\varphi) & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} $$

**Veranschaulichung**:

$$ V' = R V $$, $$ V = (1, 1, 0, 1) $$, $$ R = R_z(45\circ) $$

$$ \begin{pmatrix} x' \\ y' \\ z' \\ 1 \end{pmatrix} = \begin{pmatrix} \cos(\varphi) & -\sin(\varphi) & 0 & 0 \\ \sin(\varphi) & \cos(\varphi) & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 1 \\ 0 \\ 1 \end{pmatrix} $$

![1 cooles Bild](https://puu.sh/tdiw3/2378417066.png)

$$ V' = (0, \sqrt{2}, 0, 1)^T $$

Bei der Rotation kann auch ein Pivotpunkt definiert werden, welcher dann die Rotationsachse(n) bestimmt.


### Kombination aus Matrizen

Und ist es nun möglich einen Punkt bzw. ein Objekt im $$ R^3 $$ zu verschieben (Translation), vergrößern bzw. verkleiern (Skalierung) und zu drehen (Rotation). Diese können nun kombiniert werden, da wir diese als homogene Koordinaten (4x4 Matrix) mit Multiplikationen darstellbar gemacht haben.

Eine Gesamttransformation besteht aus einzelnen Transformationen:

$$ V' = M_1 V $$

$$ V'' = M_2 V' $$

$$ M_3 = M_2 M_1 $$

$$ V'' = M_3 V $$

* Matrixmultiplikationen sind nicht kommutativ -> $$ M_2 M_1 \neq M_1 M_2 $$
* Bei dem Produkt $$ M_2 M_1 $$ wird zuerst $$ M_1 $$ angewendet werden.
* Insgesamt sollte man darauf achten, die richtige Reihenfolge zu benutzen


![Cooles Picture](https://puu.sh/tdlrI/628ae1a950.png) (Bild von André Kettner)

**Todo**: Veranschaulichung selbst malen





## Koordinatensysteme

Alle unsere Transformationen beziehen sich auf einen **Ursprung**. Welcher ist aber festgelegt? Dazu schauen wir auf das **Weltkoordinatensystem**, in dem alle Objekt untergebracht sind.

Im $$ R^3 $$ gibt es zwei Möglichkeiten die Achse zu definieren:

- **Rechtssystem (RHS)**
- **Linkssystem (LHS)**
 
Dazu nehmen wir unseren beide Hände zeigen sie **offen nach oben** und **winkeln** sie an. Das soll nun die **horizontale und vertikale Achse** darstellen. Nun schauen wir uns die letze Achse an. Zeigt sie nach links (also da wo der Daumen ist), dann bezeichnen wir sie als LHS, oder RHS, wenn die Achse nach rechts zeigt.

Zudem muss angemerkt werden, dass die **Gesamtorientierung nicht einheitlich** ist. Es haben sich einfach im Laufe der Zeit unterschiedliche Repräsentationen der Achsen eingebürgert. 

Für unsere Transformationen benötigen wir aber **unterschiedliche Bezugspunkte**, weswegen wir auch verschiedene Koordinatensysteme brauchen.

**Überblick** - Koordinatensysteme (KS):

|Deutsch|Englisch|
|:-:|:-:|
|Welt-KS|world space|
|Objekt.KS|objekt space|
|Kamera-KS|eye space|
|Licht-KS|light space|
|Bild-KS|image space, texture space|
|Geräte-KS|screen space|

Momentan interessiert uns nur der Welt-KS und Objekt-KS.

Möchten wir nun eine Transformation durchführen, erwarten wir, dass sich unser Objekt um seine eigene Achse dreht, also umdie Objekt-KS. Umgesetzt wird diese aber anders:

1. Verschiebung des Objektes in den Ursprung des Welt-KS.
2. Rotation (oder andere Transformationen)
4. Verschiebung des Objektes zu seiner ursprünglichen Position. 

Veranschaulichung:

Problem: ![Bild 1](https://puu.sh/tdoo0/22337ab93b.png)

Lösung: ![Bild 2](https://puu.sh/tdoo0/22337ab93b.png)

**Todo**: Ebenfalls selbst malen - Bilder von André Kettner










# Modellierungstechnik

Beim Beginn eines Projekts sollte man sich überlegen, welches typische Grundobjekt - **Primitive** - man wählt. Diese sind bereits parametrisiert, d.h. sie haben eine einheitliche Größe.

Anschließend kann die Bearbeitung des Modells beginnen - Transformation von Faces, Edges und Vertices.

## Basics 

sind Standard-Operationen auf bestimmte Elemente des Meshes.

### Origins

Jedes Objekt hat einen virtuellen **Center Point** - **Origin** - welcher i.d.R. der Mittelpunkt der Geometrie ist.

Die Geometrie bezieht sich auf das Objektkoordinatensystem (z.B. beim Abspeichern), aber Transformationen werden trotzdem am Weltkoordinatensystem ausgeführt (siehe Mathematische Grundlagen - Koordinatensysteme).

Origins sind außerdem auch der Ursprung - **Pivot Points** - für Rotationen und Skalierung, d.h. eine Translation vom Origin auf den Ursprung des Weltkoordinatensystems stattfindet.



### Duplikationen

Erstellt einen Klon, dbaei wird zwischen einer normalen Duplikation, Links - also Verknüpfungen bzw. Referenzen -, Prozedurale Duplikation - Erstellung von Klonen nach bestimmten Regeln - und Externe Duplikation - Einfügen von externen Objekten - unterschieden.





## Tools

sind spezielle Modellierungswerkzeuge.

### Glättung

ist eine **Sukzessive Angleichtung der Winkel benachbarter Flächen**, wodurch das Objekt runder und glatter wird, da die harten Kanten verändert werden.

Die Gemeotrie wird transformiert, d.h. sie wird nicht unterteilt, woduch die Anzahl der Elemente nicht verändert werden.

**Todo**: Beispiel hinzufügen



### Extrusion

Durch **parallele Verschiebung** wird ein **höherdimensionales Elementes+* erzeugt. Anwendung auf:

- Punkt => neue Kante
- Kante => neuer Polygon
- Polygon => neuer Körper

Im Regelfall findet die Extrusion **parallel zur Normalen** statt.

**Todo**: Beispiel hinzufügen



### Inset

In ein bereits existierenden Polygon werden **Subpolygone nach innen eingefüt**.

**Todo**: Beispiel hinzufügen



### Unterteilung

Verfeinerung des Meshes, in dem **Kanten in der Mitte geteilt** werden und dadurch neue Vertices, Edges und Faces entstehen. Die Form bleibt gleich, aber die _Topologie ändert sich_.

**Todo**: Beispiel hinzufügen



### Knife

**Teilung eines Meshes** entlang einer Linie nach Angabe des Artists.

**Todo**: Beispiel hinzufügen



### Bevel

Bearbeitung von harten Kanten, indem der Artist die Tiefe (**Offset**) und **Anzahl der Segmente** angibt und damit dem Objekt einen natürlicheren Look verleiht.

**Todo**: Beispiel hinzufügen





## Modifiers 

Im Gegensatz zu Basics und Tools, ändern Modifier das Mesh nicht permanent, d.h. der originelle Zustand geht nicht verloren.

Unterscheidung von Modifier:

- Modify: keine Änderung der Geometrie - Änderung an Meshdaten
- Generate: Erzeugung von Geometrie
- Deform: Veränderung der Geometrie
- Simulate: Simulationsoperationen

Modifier sind wie eine Art **Funktion**, d.h. dass das Mesh als Eingabeparameter dient, welches durch ein spezifisch verändertes Mesh ersetzt wird. Die Änderungen sind beeinflussbar durch viele **Parameter**.

An einem Objekt können **mehrere Modifier gleichzeitig wirken**, aber nur in einer festgelegten Reihenfolge. Zusätzlich können die bereits **eingerichteten Modifier zu jedem Zeitpunkt** geändert werden.

Modifier können aber auch wie Tools/Basics verwendet werden, indem man die Änderungen "backt", heißt die Parameter sind anschließend nicht mehr veränderbar und das Basismesh endgültig ersetzt.

Anwendungsbeispiele ist z.B. die sukzessive Erstellung eines Modelles oder Objekte zu verformen, ohne den Ausgangszustand zu überscheiben, welches nützlich für Animationen ist. Auch die Parameter der Modifier können bei Animationen verändert werden.

Ein paar Generate und Deform Modifier werden in den nächsten Zeilen erklärt.



### Basics und Tools als Modifier

Folgende Basics und Tools sind auch als Modifier einsetzbar:

- **Glättung**: Reduzierung der Winkel benachbarter Polygone
- **Bevel**: Bearbeitung aller Kanten
- **Solidify**: Aus flachen Objekt -> 3D-Körper
- **Triangulate**: n-Gons -> Dreiecke



### Array

erstellt eine **beliebige Anzahl an Kopien eines Objektes**. Dazu können verschiedene Regeln bestimmt werden. Die _Topologie des Basismeshes bleiben unverändert__, werden aber referenziert, was dazu führt, dass Änderungen am Basismesh auf die Kopien übertragen werden. Unter anderem können Fraktale Strukturen durch mehrdimensionale Arrays abgebildet werden.



### Boolean

Nutzung von **Boole'schen Operationen** auf die gewünschte Geometrie.

Operationen:

- Subtraktion / Difference
- Vereinigung / Union
- Schnittmenge / Intersect

Es muss ein **zweites Objekt als Parameter** angegeben werden.

Das Objekt wird durch das Ergebnis der Modification ersetzt.



### Decimate

**Reduktion der Polygon-Anzahl** des Meshes. Ggf. werden n-Gons davor _trianguliert_.

Verschiedene Reduktionsmethoden:

- Edge Collapse
- Un-Subdivide
- Planar

Anwendungsbeispiele sind die Bereinigung der Auflösung importierter Objekte und die Erstellung von verschiedenen Level-of-Detail(LOD)-Meshes. Zu LOD gibt es später mehr.



### Mirror

**Automatische Spiegelung** der Geometrie anhand einer _Ebene_.

Die Ebene ist frei wählbar, überlicherweise wird die **Hauptebene des lokalen Objektkoordinatessystems** gewählt. Optional können Punkte auf der Spiegelungsachse verbunden werden.

Symmetrische Objekte sind das idealle Beispiel für diesen Modifier.



### Subdivision Surfaces

ist eine **Formverändernde Unterteilung**, d.h. die _Kanten werden gleichmäßig geglättet_. Je öfter diese **wiederholt** wird, desto runder und stärker unterteilt ist die Geometrie.

Die Wiederholungszahl kann **seperat** für das **Modeling** (View) und **Rendering** angepasst werden, d.h. dass man an einem vereinfachtem Mesh effizienter arbeiten kann und trotzdem das Rendering hübsch aussieht. Dadurch eignet sich dieser Modifier auch für **LOD**.

Der weiteste Verbreitester Algorithmus ist der **Catmull-Clark** (1978) (Namen der Entwickler).

**Catmull-Clark Subdivion Surface Algorithmus**:

1. Ein neuer Punkt $$ f $$ wird für jedes Polygon in der Mitte erzeugt.
2. Für jede Kante werden neue Kantenpunkte $$ e $$ als Mittel der Endpunkte und der neuen Facettenpunkte $$ f $$ erzeugt.
3. Neuberechnug der alten Punkten - kleine Priorität auf die neuen Facettenpunkte, in denen $$ v $$ als Ecke enthalten ist und Kanten die $$ v $$ enthalten. 
4. Verbinden der neuen Kantenpunkte mit den zugehörigen Facettenpunkten und der "alten" Eckpunkte mit den zugehörigen Kantenpunkten.

**Todo**: Step-by-Step Referenzbilder hinzufügen

Zusätzlich werden **n-Gons in n-Quads unterteilt**, wodurch am Ende ein reines Quad-Mesh übrig bleibt.

**Berechnung der Anzahl von Polygone**:

**Kubus**:

$$ c_v = 6 * 4^{n+2} $$

$$ c_e = 3 * 4^{n+1} $$

$$ c_f = c_v - 2 $$

**Todo**: Graphen einfügen

**Quadrilateral*:

$$ c_v = (2^n + 1)^2 $$

$$ c_e = 2^{2n+1} + 2^{n+1} $$

$$ c_f = 4^n $$

**Todo**: Graphen hinzufügen

**Todo**: Vergleich hinzufügen



### Deform

**Deformation eines Objektes** anhand _verschiedener Optionen_:

- **Twist**: Rotation um eine Achse
- **Bend**: Verbiegung um eine Achse
- **Taper**: Verjüngung entlang einer Achse
- **Stretch**: Streckung entlang einer Achse

**Todo**: Einfügen von Referenzbildern



### Lattice

**Deformation eines Objektes** anhand der Form eines _"virtuellen" Lattice-Objekts_, welches das gesamte Zielobjekt umfasst.

Vorteile:

- Deformation des gesammten Objektes -> Unabhängigkeit von Auflösung und Geometrie
- Entsprechend "glatte" und saubere Deformation
- Da die Deformation in ein seperates Objekt - also der Lattice - ausgelagert wird, kann diese mehrfach verwendet werden -> mehr Effizienz und weniger Aufwand



### Shrinkwarp

**Abbildung des Meshes eines Objektes auf die Oberfläche eines Andern**. Man "umwickelt" das Objekt, wie ein _Kleidungsstück_.

Anwendung bei Kleidung, Beschiftung von Oberflächen und der Verteilung von Objekt auf Oberflächen.










## Kamera

Die Kamera befindet sich auf einem Punkt im §§ R_3 $$ (**eye**), dabei ist die Blickrichtung - **Orientierung** - abhängig vom sog. "look-at"-**Vektor**. 

Alternativ kann anstatt dem "look-at"-Vektor ein "Point-Of-Interest" (aka Coi, "Center-...") benutzt werden, dieser Punkt beeinflusst dann den "look-at"-Vektor: $$ \overrightarrow {v} = POI - EYE $$. 

Die Rotation ist abhängig von der "look at"-**Achse**, diese steht im Lot auf den "look-at"-Vektor und zeigt immer nach oben.

Zusätzlich zur Richtung der Kamera müssen noch weitere Eigenschaften geklärt werden.



### Eigenschaften

- Auflösung (**resolution**)
- Auflösungsverhältnis (**aspect ratio**)

![Auflösung und Auflösungsverhältnis]()

Linieneigenschaften:

- Brennweite (**focal length**)
- Field of View (**FOV): $$ focal length \alpha FOV^{-1}
- etc.

![FOV]()

Eigenschaften für Render-Effekte:

- Tiefenschärfe (Depth of Field - **DOF**)
- Bewegungsunschärfe (Motion Blur)



### Projektion

Vor der Projektion rechnen wir ins Kamera-Koordinatensystem um (**view transform**). Anschließend kann man Multiplikationen mit der Projektionsmatrix ausführen.

#### Orthogonale Projektion

![Ortho]()

**Proportionen und Abstände** sind besser abschätzbar, wodurch diese zur Modellierung besser geeignet ist. So können auch 2D-Darstellungen simuliert werden.

$$ M_{ortho} = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} \Rightarrow M_{ortho}
\begin{pmatrix} p_x \\ p_y \\ p_z \\ 1 \end{pmatrix} = 
\begin{pmatrix} p_x \\ p_y \\ 0 \\ 1 \end{pmatrix} $$

![Vor- und Hinterprojektion]()

Wie man an der Formel erkennt, wird die Z-Koordinate anders behandelt. Dadurch entstehen verschiedene Probleme:

- Punkt mit ± Werten für z werden projiziert $$\rightarrow$$ Objekte "hinter" der Kamera werden gerendert
- Die Projektion it irreversibel (z-Tiefeninformation geht verloren) $$\rightarrow$$ insuffizient für Z-Buffering

Aufgrund der Probleme werden i.d.R. der durch die **Clipping Planes** (top, bottom, right, left, near, far) definierte Quader in den **Ursprung transformiert** und auf die **Größe des Einheitswürfel skaliert**.

![Clipping Planes]()



#### Perspektivische Projektion

![Persp]()

**Gewohnte Sichtweise** des Menschen. Wird benutzt in der Renderingvorschau.

Beispiel: Projektionsebene entland der __negativen z-Achse_ -> Position $$ z = -d, d > 0 $$

![Beispielprojektion]()

Gesucht: Punkt $$ q $$ als Projektion von Punkt $$ p $$ auf die Projektionsebene.

Punkt $$ q = (q_x, q_y, -d, q)^T $$ gegeben durch:

$$ \frac{q_x}{p_x} = \frac{-d}{p_z} \Rightarrow
q_x = -d \frac{p_x}{p_z} $$

$$ \frac{q_x}{p_x} = \frac{-d}{p_z} \Rightarrow
q_y = -d \frac{p_y}{p_z} $$
d.h. $$ q = \begin{pmatrix} -d \frac{p_x}{p_z} \\ -d \frac{p_y}{p_z} \\ -d \\ 1 \end{pmatrix} $$

Matrix, die die oben genannte Projektion abbildet:
$$ M_{persp}p = q $$, also: $$ M_{persp} \begin{matrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & -\frac{1}{d} & 0 \end{matrix} $$

Probe: $$ M_{persp} \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & -\frac{1}{d} & 0 \end{pmatrix} \begin{pmatrix} p_x \\ p_y \\ p_z \\ 1 \end{pmatrix} = \begin{pmatrix} p_x \\ p_y \\ p_z \\ -\frac{p_z}{d} \end{pmatrix} $$


Transformationen von homogenen zu kartesischen Koordinaten: 
$$ \begin{pmatrix} p_x \\ p_y \\ p_z \\ -\frac{p_z}{d} \end{pmatrix} = \begin{pmatrix} -d\frac{p_x}{p_z} \\ -d\frac{p_y}{p_z} \\ -d\frac{p_z}{p_z} \\ 1 \end{pmatrix} = \begin{pmatrix} -d\frac{p_x}{p_z} \\ -d\frac{p_y}{p_z} \\ -d \\ 1 \end{pmatrix} = q $$

Die Projektion ist nicht invertierbar, d.h. z-Werte gehen verloren $$\rightarrow$$ geringe Erweiterung von $$M_{persp}$$ um die Clipping Planes des Hüllvolumens












## Polygonale Netze

verschiedene Darstellungen eines 3D-Modells:

- Polygonale Netze (Meshes)
- Parametrische Kurven und Flächen (Patches)
- Constructive Solid Geometry (CSG)
- Implizit, prozedural

**Hinweis**: Wir konzentrieren uns in nachfolgenden Themen primär auf Polygonnetze. Hier werden aber alle angeschnitten!



### Grundlagen

Ein Objekt besteht aus einer Mengen an Polygonen, wodurch **Krümmungen** durch Annäherung passiert. Je höher die Polygonanzahl, desto genauer ist die Annäherung.

Allerdings besteht zwischen realer Fläche und Mesh kein fester Bezug. Der Artist muss das klarstellen! Außerdem sind Polygon im Programm leider begrenzt auf Form und Punktanzahl (viele Programme akzeptieren inzwischen Abweichungen von der "3-Punkt"-Regel).

Praktischerweise existieren für Poly-Netze effiziente Schattierungsalgorithmen!

Poly-Netze sind am gebräuchlichsten in CGI und Games, deswegen wird es auch hier primär besprochen.

#### Anforderungen

Einem Polygon können technische Anforderungen gestellt:

- planar
- Punktanzahl
- Geschlossenheit
- Überschneidungsfrei
- Konvexität
- Frei von Löchern

![Bild mit Erklärung hinzufügen]()

Sollte die Punkteanzahl > 3 sein, dann ist das Polygon nicht zwangsweise planer und konvex!

Das Programm entscheidet letztendlich die Grenzen, trotzdem muss der Artist auf die Sauberkeit des Meshes achten!

#### Topologie und Geometrie

**Geometrie**: Koordinaten von Vertices

d.h. exakte Position und Form der Topologie

z.B. P1 (2, 4), P2 (3, 5)

**Topologie**: Struktur des Netzes

d.h. Information über Verbindungen zwischen Elementen unabhängig von Position und Form.

z.B. E1 = P1 & P2

### Normalen

Ein Normalenvektor ist eine **wichtige Eigenschaft** eines Polygons.

Dieser ist definiert als **senkrecht zur Polygonfläche** stehender Vektor und muss daher berechnet werden: Produkt zweier Vektoren, definiert durch drei nicht-kollineare Punkte.

![Beispiel - Normalenvektor]()

Die Normale wird i.d.R. als Einheitsvektor angegeben -> Normierung: $$ \overrightarrow{n_o} = \frac{\overrightarrow n}{\|\| \overrightarrow n \|\|} $$

=> Eine Ebene kann definiert werden als einen Normalenvektor und einen Punkt auf der Ebene.

Praktischerweise kann der Normalenvektor nun nur in **2 Orientierungen**** zeigen, also der **Ober- und Unterseite** des Polygons. Die Seiten sind abhängig von der **Repräsentation des Koordinatensystems** (RHS oder LHS).

Ein Problem entsteht durch z.B. die Rotation. die Normalenvektoren können sich **willkürlich ändern**, wodurch der Artist dieser wieder richten muss. Glücklicherweise gibt es dazu Tools!

##### Und warum aber nun Normalen?

Sie werden benutzt für **Berechnungen** an verschiedenen Stellen der Pipeline z.B. Beleuchtung, Schattierung, Rendering,...

Deswegen besitzen **Vertices, Edges und Faces** Normalen!

Die **Vertex Normals** werden durch **Mittelung der umgebenden Polygonnormalen** bestimmt: $$ N_v = \frac{\sum N_i}{\|\| N_i \|\|} $$

Normalen werden nochmal besprochen bei dem Thema "Materialien".

### Level of Detail (LOD)

Vor allem in Videospielen ist es oft gewollt **schöne Objekte** (besonders Charaktere) zu erstellen, wodurch aber die Polygonanzahl ansteigt.

Aber:
- **anspruchsvoller** für den Computer. 
- **nicht jedes Objekt** ist in der Szene **sichtbar**
- **weit entfernte Objekte** sind nicht aus der Entfernung nicht sehr wichtig 

Lösung: Ein Mesh wird in **verschiedene Detailliserungsgrade** (Entfernung <-> Auflösung) erstellt.

Also d.h. bei der Benutzung von LOD muss folgendes beachtet werden:

- Modell muss in **unterschiedlichen Auflösungen** erstellt sein
- Beim Rendern muss das **zur Entfernung passende Modell** herangezogen werden
- LOD-Management (what exactly?)

#### Umsetzung

![4-Stufen Diagramm]()

Automatisches Erstellen von simplerer Meshes -> **Edge Collapse** Methode:

![Edge Collapse]()

Problem: Manche Kanten kollabieren nicht optimal aneinander!

![Edge Collapse - Problem]()

Weiteres Problem: Bei dieser Form von LOD-Wechsel besteht das Makel, das die Sprünge sehr sichtbar sind -> **popping**

Lösung: **Switching**:

- Diskrete Geometrie -> popping
- lineares Blending zwischen zwei LOD-Stufen
- Alpha-LODs: Transparenz $$ \alpha $$ Abstand

**Alpha-LODs**: Übergehender Übergang zwischen Zustand A zu Zustand B, indem Zustand A ausgeblendet wird, während Zustand B eingeblendet wird. 

![Diagramm]()

LOD: Culling -> Besprechung in Vorlesung "Computergrafik"

### Nachteile von Polygon-Netzen

- gekrümmte Flächen können nur durch Annäherung dargestellt werden
- Änderung der Genauigkeit -> Aufwand steigt
- Kein fließender Übergang zwischen verschiedenen Genauigkeiten
- Genauigkeit ist nicht skalierungs-unabhängig

Um die Nachteile von Polygon-Netzen zu umgehen wurden Parametrische Patches entwickelt.










## Parametrische Patches

sind ±±mathematisch beschriebene, gekrümmte Flächen**. Ein Objekt wird aus **mehreren Patches** zusammengesetzt.

Aufgrund der Formel-Darstellung ist jeder Punkt des Patches exakt analytisch festgelegt, wodurch LOD einfacher umsetzbar ist.

Eine mögliche Metapher im $$ R^2 $$: Pixelgrafik (Netze) vs. Vektorgrafik (Patches)


### Mathematische Grundlage

**Parametrische Kurve**: $$ Q(u) = (X(u), Y(u), Z(u)) $$ mit $$ 0 ≤ u ≤ 1 $$

**Parametrische Fläche**: $$ Q(u,v) = (X(u,v), Y(u,v), Z(u,v)) $$ mit $$ 0 ≤ u ≤ 1 $$ und $$ 0 ≤ v ≤ 1 $$

Dieses Flächenelement ist definiert als **Patch**.

Mehr zu Patches und deren mathematische Grundlage gibt es in der VL Computergrafik.

**Normalen**:

- Jeder Punkt des Patches hat eine eigene Normale
- Kreuzprodukt aus den Tangenten beider Richtungen $$ u, v $$

Berechnung $$ N_{u,v} $$ einer param. Fläche $$ Q(u,v) $$:

- Tangenten gegeben durch $$ \frac {\partial}{\partial u} Q(u,v) $$ und $$ \frac {\partial}{\partial v} Q(u,v) $$
- (unnormierte) Normale $$ N_{u,v} $$ gegeben durch $$ N_{u,v} = \frac {\partial Q} {\partial u} \times \frac {\partial Q} {\partial v} $$

### Bézier

ist eine weit verbreite parametrische Kurve die von Paul de Caseljau und Pierre Bézier entwickelt wurde.

Der Kurvenverlauf ist beeinflussbar durch Position und Anzahl der Kontrollpunkte, wobei der Grad dieser Bézierkurve $$ n = Kontrollpunkte_{Anzahl} -1 $$ ist. Steigt die Anzahl der Kontrollpunkte, so steigt auch der Rechenaufwand.

![Beispiel Bézier]()

Übertragen auf das $$ R^3 $$ sprechen wir von einem **Bézier-Patch**.

#### Spline

Verbindung mehrerer Kurven ist nicht zwingend stetig. **Stetigkeit** wird erricht, wenn zwei verbindenden Kontrollpunkte **kollinear** sind.

Eine **Aneinanderreihung** wird als **Spline** bezeichnet. Hier: Bézier-Spline

#### Eigenschaften von Bézier-Splines

- Kurve bleibt in der Konvexen Hülle des Kontrollpolygons
- Kontrollpunkte haben einen globalen Einfluss (in unterschiedlichen Maße)
- Transformation durch Kontrollpunkte
- Kurvenverlauf ist durch Transformation invariant (?)

Störfaktoren:

- Eingeschränkte lokale Editierbarkeit
- Skalierender Aufwand mit Anzahl der Kontrollpunkte (Aneinanderreihung nötig)

#### B-Splines

Eigenschaften:

- Einfluss ist lokal beschränkt
- Grad unabhängig von der Anzahl der Kontrollpunkte
- Kurve führt analog Bézier nicht zwingend durch die Kontrollpunkte
- Gleiches gilt innerhalb der konvexen Hülle
- Transformation analog zu Bézier
- Ordnung bestimmt EInfluss der Kontrollpunkte

Spezielle B-Splines:
- **Uniformität**: Einfluss eines Kontrollpunktes ist konstant
- **Rationalität**: Analytische Beschreibung ist als Verhältnis ausdrückbar

=> **NURBS**: **N**on-**U**niform **R**ational **B**-**S**plines

##### Anwendungsbeispiele von NURBS

- Verbreitet in der Konstruktion (CAD)
- NURBS-Modeler: Rhinocerus, Mol, nPower

![Coole Bilder]()










## Prozedurales Modellieren

Gemeotrie wird anhand einer oder mehreren Regeln generiert. Die Regeln können mathematische Funktionen oder beliebe Algorithmen sein. Prozedurale Methoden sind stark unterschiedlichen in deren Komplexitätsgrad und bieten ein intensiver Forschung.

Parameter des Algorithmus schaffen Gestaltungsmöglichkeiten für den Artist.

Allgemeine Beispiele:

- Fraktale Formen
- Geländegeneration
- Städtegeneration
- Architektur
- Pflanzen, Wald, Gras
- Biologische Strukturen, Neuronen, Korallen,...

In Games:

- Prozeduraler Levelaufbau -> Daggerfall, Diablo, Minecraft, Binding of Isaac
- Pozedurale Animation -> Morrorwind, Spore
- Pozedurale Eigenschaften -> Borderlands
- Pozedurale Umgebungseffekte -> Left 4 Dead 2

![Beispielbilder]()







































