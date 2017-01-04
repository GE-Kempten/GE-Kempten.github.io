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


































