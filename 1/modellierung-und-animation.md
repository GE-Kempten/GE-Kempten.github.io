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
































