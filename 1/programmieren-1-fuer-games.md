# Programmieren 1 für Games

### Kompetenzen

- Arbeiten mit einer **Integrated Development Environment (IDE)** und **Präprozessor**, **Compiler** und **Linker** in dieser kennen und anwenden können. Erweitert wird dies durch
- Grundlegende und strukturierte **Datentypen**,
- **Kontrollstrukturen** und **logische Bedingungen**,
- **Felder, **Zeiger** und **dynamische Speichermanagement**, sowie
- **Funktionen** und **Prozeduren** aus C. Auch soll das
- **Objektorientierte Programmieren** mit den Grundlegenden Konzepten aus C++ gekannt und angewendet werden.
- Modulare Programme schreiben und die "toolchain" der Entwicklung von C/C++ Programmen und Biblioheken verstehen und anwenden.

### Lernergebnis

Am Ende des Semesters sollen die Stunden in der Lage sein mit der **IDE** zu arbeiten, d.h. sie **programmieren**, **übersetzen** den Code und **Fehler** werden behoben. Durch ständiges Üben ist es ihnen möglich Abhilfe für **kleine Probleme** der realen Welt mit strukturierten, modularen **Programmen** zu lösen.

# Einführung

**TODO**: Verlinkung zu Themen

Programmierung ist nötig, da der Computer bzw. der Prozessor nur exakt formulierte Aufgabenstellungen ausführen kann. Dieser ist im Resultat aber weitaus effizierter als der Mensch z.B. Ausrechnen von komplizierten Formeln.

Das Schreiben des Programms muss trotzdem der Mensch unternehmen, auch wenn sog. KIs (Künstliche Intelligenz) immer besser werden, wodurch sie das immer stärker übernehmen.

Problem ist nun leider, dass zwischen Mensch und Maschine eine Sprachbarriere ist. Wir Menschen sprechen die **natürlich Sprache**, welche während dem Gesprächs die Fähigkeit hat Informationen zu interpretieren und dadurch Ironie etc. versteht. Der Computer spricht in der Maschinensprache, welche binören Codes ließt und dadurch nur 0en und 1er versteht.

Als Schnittstelle der beiden Parteien bieten sich **Programmiersprachen** an, da diese für Beide verständlich sind und dadurch einen guten Kompromiss darstellen.

Dadurch entsteht folgendes **Vorgehen**:

- Der Mensch übersetzt sein Problem der realen Welt in eine Programmiersprache
- Speziele Übersetzungsprogramme wandeln diese in eine verständliche Maschinensprache um
- Der Computer kann nun die Anweisungen ausführen

## Anweisungen / Befehle

Anweisungen und Befehle sind unterschiedlich von Programmiersprache zu Programmiersprache, aber grundlegende Konzepte beliben identisch.

**Zuweisung**:

- Initialisierung: _Name = EinTollerName_
- Zuweisung: _EinJahr = 1980 + EinPaarJahreMehr_

**Kontrollstukturen**:

- Bedingte Anweisungen: _wenn dass eintrifft ... dann mache ... sonst tu ..._ (if - else)
- Blockanweisungen: _mache solange ... bis ... eintritt_ (Schleifen)

**Prozedur-/Funktionsaufrufe**:

- _SpieleMusik(Titelnummer)_
- Unterschied zwischen **Prozedur** und **Funktion** (geminersamer Begruff in der OOP ist **Methode**) nicht klar definiert, aber eine mögliche Unterscheidung ist, ob ein **Rückgabewert** vorliegt (Funktion) oder nicht (Prozedur).

## Programmiersprachen

Große Anzahl von Programmiersprachen, welche nach bestimmten Kriterien unterscheidbar sind:

- **Kompilierte vs. Interpretierte** Spachen -> Portabilität/Geschwindigkeit/...
- Programmierparadigmen -> Programmierstil, den die Sprache unterstützt (oder auch nicht)
- Datentypeigenschaften -> Definition/Kombination von Datentypen
- **Nähe zur Maschinensprache** -> High or low level Sprachen


### Kompilierte vs. Interpretierte Sprachen

**Kompilierte Sprachen**:

- werden in sogg. nativen Sprachen (**Maschinensprache**) des Zielsystems mithilfe des sogg. **Compilers** übersetzt.
- Sind i.d.R. **sehr schnell* ausführbare Programme, müssen aber
- für jeden Zielsystem und bei jeder Codebearbeitung **neu kompiliert** (übersetzt) werden.
- "Verschlüsselung" des Codes in gewisser Weise.
- z.B. C, C++

**Interpretierte Sprachen**:

- werden von einen anderem Programm, dem sogg. **Interpreter** nach und nach gelesen und ausgeführt, sind dadurch
- besser **portierbar** (übertragbar) auf andere Systeme, soweit ein anderer Interpreter für dieses System existiert, führen aber durch gleichzeitige lesen und ausführen zu einem
- wesentlich **langsameren** Ausführen des Programmes.
- z.B. MATLAB, BASIC, PHP, Perl

Just-in-Time kompilierte Sprachen (**Zwischensprache**):

- sind eine Kombination aus Beiden anderen und will dadurch deren Vor- und Nachteile ausgleichen
- Code wird zum Zeitpunkt des Bedarfs ausgeführt.

**Portabilität**:
- Jeder Prozessor/Zielsystem hat seine eigene Maschinensprache
- Portabilität beschreibt die Eigenschaft eines Programms auf **vielen verschiedenen Zielsystemen** eingesetzt werden zu können.


### High vs. Low Level Sprachen

Das **Level** beschreibt die Nähe/Ähnlichkeit zur Maschinensprache des Systems:

Je ähnlicher, desto **lower**:

- Anwendung: Treiberprogrammierung, hardwarenahe Programmierung
- Ziel ist es jede Funktion einer bestimmten Hardware höchsteffizient ansprechen zu können

Je abstrakter/universeller/für den Menschen besser lesbarer, desto "higher":

- Ziel ist es universelle Aufgaben einfach und schnell umsetzbar zu machen
- "Programmieren ist für jedermann"

=> Programmierer muss selbst entscheiden, welche Sprache er für sein Projekt benötigt:

- Ein **Computerspiel** wird eher in einer _high-level Sprache_ geschrieben, während aber
- der **Gamecontroller** für das Spiel eher in ein einer _low-level Sprache_ geschreiben wird.

### Assembler

ist die **erste Programmiersprache** und ähnelt der Maschinensprache, ist aber für den Menschen noch lesbar. Ein Veranschaulichung des Codes bietet dieser [Übersetzer](http://gcc.godbolt.org/) von C++ in Assembler. Dies ist auch Thema in der Vorlesung [IT-Systeme - Assemblerprgrammierung](/1/it-systeme).

### Kommunikationsprotokolle

Auch wenn der Mensch mit dem Computer mit Programmiersprachen kommuniziert, heißt das nicht das **Computer gegenseitig** das Gleiche machen. Sie benutzen **Kommunikationsprotokolle**, wie z.B. TCP, IP, HTTP, FTP, SMTP, ...

### Syntax und Semantik

**Syntax**:

- Definiert das Erscheinungsbild des Quelltextes/Codes, d.h. ist ein Regelwerk (Grammatik)
- Aufgabe: Welche Wörter und Wortfolgen sind gültig um einen funktioniereden Code zu schreiben?

**Semanik**:

- Definiert die Bedeutung von Zeichen-/Wortfolgen 
- Aufgabe: Was bedeuten die Wörter und Wortfolgen bzw. welche Wirkung haben Sie in meinem Quellcode?

### Game-Engineering

Mit Game-Engine kommt man alleine schon recht weit, indem man "Featuren zusammenklickt", aber: die **eigene Innovation** wird dadurch eingeschränkt durch die Fähigkeit der Engine.

Viele Entwicklungsstudios entwickeln deshalb (und aus anderen Gründen) ihr eigene Engines.

Durch die eigenen Programmierkenntnisse können so spezielle Grafikeffekte, Interfaces/Controler, Charaktere (KI) und vieles mehr entwickelt und benutzt werden.

Außerdem werden neue Spielansätze und Anforderungen von herkömmlichen Engines noch gar nicht unterstützt. z.B. Kompatibilität zu VR, AR, ...

## C und C++

### C

wurde von **Dennis Ritchie** zwischen **1969-1973** in den Bell Laboratories, NJ, USA entwickelt, um das neue Betriebsystem UNIX zu programmieren und diente als Vorbild für andere von C insperierte Sprachen. C ist eine prozedurale Sprache.

### C++

wurde von Bjarne Stroustrup und seinen Mitarbeitern in den Bell Laboratories (AT & T, USA) entwickelt, um effizienter implementieren zu können. Frühe Versionen, wie "C mit Klassen", gibt es seit 1980. Ab 1989 wurde mit der Standardisierung von C++ begonnen, um Sprachdialekte zu vermeiden, so wurde dann 1998 der ISO Standard CD 14882 für C++ verabschiedet. 

Aus dem Namen ist schon ersichtlich, dass C++ aus C entstand, dabei wurden sogar die kompletten Eigenschaften übernommen.

Eigenschaften von C:

- Universell einsetzbare, modulare Programme
- Effiziente, maschinennahe Programmierung
- Übertragbarkeit auf verschiedene Rechner (Portabilität)

Eigenschaften von C++:

- OOP: Objektorientierte Programmierung

### Warum C und C++

- beinhaltet **alle wichtigen Programmierkonzepte** (insbesondere **OOP**) und ist eine gute Basis für den Einstueg in weitere Programmiersprachen
- Schult die Sensibilität mit dem **Umgang von Ressourcen** (Speicher und Rechenpower), d.h. man kümmert sich z.B. um den verwendeten Speicher selbst
- Sehr weit **verbreitet** -> leichter Einstieg, viele Bibliotheken, Unmengen an Ressourcen, größte Programmiersprache 2016 (Spectrum IEEE)
- Native Programmiersprache, d.h. dirkete Übersetzung des Quellcodes in Maschinensprache und damit **sehr schnell** => **echtzeitkritische Anwendungen**, Verarbeitung großer Daten
- Ermöglicht viele verschiedene Programmierstile(**Programmierparadigmen**) -> Prozedural, Generisch, OOP, ...
- Hot eine **hohe Portabilität** da weit verbreitet und für beinahe jedes Zielsystem Compiler vorhanden sind 
- Neue C++ Codes sind kompatibel mit ggf. älteren C-Codes
- Didaktische Gründe -> C veranschaulicht Konzepte von prozeduralen Programmiersprachen, C++ veranschaulicht die Vorzüge von objektorientierten Programmiersprachen
- Weite Verbreitung in anderen Anwendungsbereiechen z.B. Medizintechnik
- Schnittstelle zu den Grafik-APIs für die 3D Computergrafik, zB. OpenGL, DirectX

### Versionen und Standardisierung

- Gegen das "Wildwuchs" von Sprachdialekten -> Anmerkung: Deutsche Sprache ist nicht standardisiert z.B. Brötchen vs. Semmel
- Beteiligte Organisationen zu Entwicklung des Standard ist **ANSI** (American National Standard Institute) und ISO (Internationale Ordnung für Normung)
- Neuste C Version: C11
- Neuste C++ Version: C++14

## Erstes Programm 

Zunächst wird eine **Integrated Development Environment** (**IDE**) benötigt, da viele Funktionen für den Entwickler bereitstellt und somit die Arbeit an den Code angenehmer macht.
Wichtige Funktionen sind **Projekte aufsetzen**, **Quellcodeeditor**, **Fehlersuche**, **Kompilieren und Linken**, etc.

Das Programm wird aus **mehreren Dateien** zusammengesetzt**:

- Erstellen einer **Quelldatei** _.cpp_, indem der **Quellcode** geschrieben ist. Dabei werden **Header**-Dateien _.h_ hinzugefügt.
- Es entsteht eine **Objektdatei** _.obj_, welche durch **Bibliotheken** _.lib/.dll_ erweitert wird. Die Standardbibliothek zählt auch dazu. 
- Am Ende steht eine **ausführbare Datei** _.exe_ bereit.

Ein simples Programm für den Einstieg ist das sog. **Hello World!**-Projekt.

### Hello World

"Hello World" gibt einen kurzen Einblick in viele Funktionen einer Programmiersprache, da viele simple, aber allgemein wichtige Anweisungen aufgeführt werden.

´´´c++

#include <iostream>

using namespace std;

int main(){
	std::cout << "Hello World!" << endl; //endl gehört auch zu std
	cout << "Oder auch: Hallo Welt!\n";

	return 0;
}

´´´
**Präprozessordirektive**: z.B. _#include <header>_ oder _#include "header"

Diese wird eingeleitet durch ein **#** und wird ausgeführt am **Anfang der Kompilierphase**  erzeugt noch **keine Objektdatei**, sondern bündelt **Informationen** und bereitet diese vor. 

Das **include*+ gibt an, dass Dateien in das Projekt bzw. den Quellcode ingebunden werden. Allgemein gesagt: <header> bindet Standardbibliotheken ein und "header" eigen erstelle Dateien. Mehr dazu (sehr viel) später.

**iostream**: Ist zuständig für die Ein und Ausgabe auf der Konsole.

**int main**: Aufruf der Hauptfunktion.

Die **Hauptfunktion** ist Pflicht für jedes Programm, da diese Funktionen und Anweisung aufruft. Man könnte sie auch einen **roten Pfad** nennen, da hier alles zusammenführt und nach der Reihe ausgeführt werden. Das **return 0;** zeigt, dass das Programm den Exit-Code zurückgibt und ist ebenfalls Notwendigfür alle Funktionen mit einem Rückgabewert. Mehr dazu unter "Funktionen".

**Funktionsblock**: { inhalt }

In dem Funktionblock befindet sich alles, was das Programm berechnen/ausführen soll.

**Kommentare** //Inhalt oder /* Inhalt */

Kommentare werden vom Compiler **ignoriert** und können dadurch benutzt werden, den **Code übersichtlicher** zu machen. Dies ist besonders praktisch für das Verständnis anderer Personen, da diese den Code dadurch schneller verstehen. Den es gilt: Teamwork OP!

 // wird alles ignoriert -> Einzeiler-Kommentar

 /* -> Beginn eines Kommentarblocks
 */ -> Ende eines Kommentarblocks

**Anweisungen** enden immer mit einem Semicolon/Strichpunkt **;**

**Konsolenausgabe**:

Da wir _iostream_ eingebunden haben, können wir auf der Konsole des Computers schreiben und auslesen.

**std::** kennzeichnet den **Namensbereich**, indem _cout_ und _endl_ definiert sind. Da wir **using namespace std;** angegeben haben, muss std:: nicht benutzt werden.

**cout** (console output) ist eine Funktion der Standardbibliothek, die die _Ausgabe_ auf der Konsole ermöglicht.

**" Inhalt "** ist ein String und dessen Inhalt wird nach cout << ausgegeben.

**<<** ist ein Operator, der die Zeichen in den sogg. _outputstream_ schiebt.

**endl** (end of line) ist ebenfalls eine Funktion der Standardbibltiothek und ruft einen Zeilenvorschub hervor. Alternativ kann in dem String "**\n**" eingefügt werden, welcher den gleichen Effekt erzeugt.

# Elementare Datentypen - Integer und Strings

Ein wichtiger Bestandteil jedes Programmes sind **Variablen**. In diesen können verschiedene Werte gespeichert und wieder benutzt werden. Um Variablen zu speichern, müssen wir davor noch angeben, wie viel Speicher sie brauchen. Das ist abhängig von der Art des Wertes - also Zahl oder Buchstabe/n - und dem Wertebereich.

### Deklaration und Defintion

**Deklaration**: Wir legen **Datentyp** und **Name** fest, dadurch kann der Compiler Speicher reservieren, aber die Variable hat zurzeit noch keinen festgelegten Wert. 

**Syntax**: _Datentyp_ **Variablenname**;

**Namensregeln**:

- Anfang mit a-z, A-Z oder _
- Danach darf a-z, A-Z, _ und Zahlen benutzt werden
- Bereits reservierte Wörter wie _continue_ können nicht benutzt werden

_Anmerkung_: Benutzen wir die Variable jetzt, dann wird ein zufälliger Wert ausgegeben, falls der Compiler das überhaupt zulässt.

**Defintion**: Nun wird der Variablen ein Wert zugewiesen. Natürlich muss davor aber erstmal ein Datentyp festgelegt sein.

**Syntax**: **Variablenname** = _einWert_;

Es ist möglich Defintion und Deklaration zu kombinieren.

´´´c++

int eineZahl = 44; //Definition und Deklaration
int eineAndereZahl(21);

int x_pos, y_pos, z_pos; //Deklaration von drei Variablen

x_pos, y_pos, z_pos = 5; //Defintion durch verkettete Wertezuweisung.

//Aber:

int Zahl1, Zahl2, Zahl3 = 3; //Nur Zahl3 wird 3 zugewiesen

int nochEineAndereZahl(22), eineGanzAndereZahl(42);
´´´

**Fehlerquellen**:

Beschäftigen wir doch als nächstes mit Zahlen -> Integer und Float.

## Integer

I.d.R. hat ein Integer 4 Byte (16 Bits) Speicherplatz. Integer können aber verschiedene Formen annehmen, welche diese Tabelle darstellen soll:

|Datentyp|Speicherplatz (Byte)|Wertebereich|Notiz|
|--:|:-:|:--|:--|
|bool|1|1,0 bzw. true, false|Sehr viel Speicher für 2 Ziffern|
|char|1|-128, +127|Benutzung für ASCII|
|short|2|-32.768, +32.767|Hälfte von Integer|
|integer|4|-2.147.483.648, +2.147.483.647|Alternativer Name: long|
|long long|8|-9.223.372.036.854.775.808, +9.223.372.036.854.775.807|Doppeltes von Integer|

Mit Ausnahme von bool kann an jeden Datentyp noch ein **unsigned** (ohne Vorzeichen) angehängt werden, um den Wertebereich auf 0 zu verschieben. z.B. unsigned short -> 0, 65.535

Für die Umrechnung von Dezimalzahlen in Binärzahlen solle ein Blick in die Vorlesung ["Einführung in die Informatik"](/1/einfuehrung-in-die-informatik) gemacht werden.

### Overflow



