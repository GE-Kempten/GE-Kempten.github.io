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
- [ ] Mathematische Grundlagen
- [ ] Modellieren
	- [ ] Mathematische Grundlage
	- [ ] Modellierungstechnik
		- [ ] Basics
		- [ ] Tools
		- [ ] Modifiers
	- [ ] Kamera
	- [ ] Polygonale Netze
	- [ ] Parametrische Patches
	- [ ] Einschub: Prozedurales Modellieren
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
- Vektoren transformieren durch Matrizen: $$ {\overrightarrow {v'} = M {\overrightarrow {v'}}  = \begin{pmatrix} a_y b_z & - & a_z b_y \\ a_z b_x  & - & a_x b_z \\ a_x b_y & - & a_y b_x \end{pmatrix} \begin{pmatrix} v_0 \\ \vdots \\ v_{n-1} \end{pmatrix} = \begin{pmatrix} v_0^{\prime} \\ \vdots \\ v_{n-1}^{\prime} \end{pmatrix} $$





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

Veranschaulichung: ![Ein cooles Beispiel](https://puu.sh/tcboR/ae226ca5b2.png)

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

Veranschaulichung: ![Mega cooles Bild](https://puu.sh/tcrbe/891212728d.png)

Darstellung als Matrixmultiplikation:

$$ V' = S V $$

$$ \begin{pmatrix} x' \\ y' \\ z' \\ 1 \end{pmatrix} = \begin{pmatrix} s_x & 0 & 0 & 0 \\ 0 & s_y & 0 & 0 \\ 0 & 0 & s_z & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \\ 1 \end{pmatrix} $$

Veranschaulichung: 

$$ V' = S V $$

$$ V = (-1, 1, 0 1) $$

$$ S = (2, 3, 1) $$

$$ \begin{pmatrix} x' \\ y' \\ z' \\ 1 \end{pmatrix} = begin{pmatrix} 2 & 0 & 0 & 0 \\ 0 & 3 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} -1 \\ 1 \\ 0 \\ 1 \end{pmatrix} $$

$$ V' = (-2, 3, 0 1)

Man unterscheidet zwischen **isotropischer** $$ (s_x = s_y = s_z) $$ und **anisotropischer** Skalierung. Das Bsp grade eben ist eine anisotropische Skalierung.

Die Skalierung wird auf jeden Vertex angewendet und daher kann diese auf eine beliebige Punktmenge eines Objektes angewandt werden. Allerdings ist dann die Wahl des **Bezugspunktes** wichtig => **Ursprungspunkt der Skalierung**. I.d.R. ist der Standard-Bezugspunkt der **Objektmittelpunkt**. Abweichende Bezugspunkte sind z.B. Median und Fixpunkt, Individueller Ursprungspunkt, Ursprungspunkt des aktiven Elements, etc.

**Skalierungsfaktor**:

| > 1.0 | < 1.0 |
|:-:|:-:|
|höhere Entfernung vom Pivotpunkt|verringerte Entfernung vom Pivotpunkt|

Veranschaulichung - negativer Wert der Skalierungsfunktion:

Gegeben: $$ O_1 = (0, 0), O_2 = (6, 4), S = 0.5, Pivot: Median $$

1. Schritt - Mittelpunkt berechnen: $$ P = (O_1 + O_2)/2 = (3, 2) $$
2. Schritt - Rand berechnen: $$ D = S \cdot (O_2 - P) = S \cdot (3, 2) = (1.5, 1) $$
3. Schritt - Skalierte Punkte berechnen: $$ O'_1 = P - D = (1.5, 1), O'_2 = P + D = (4.5, 3) $$  











































