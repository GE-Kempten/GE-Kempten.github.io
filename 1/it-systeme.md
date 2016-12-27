#IT-Systeme

###Kompetenzen

- Bauen eines funktionsfähigen Rechners, dazu werden
- Digitale Schaltungen, also die Boole'sche Algebra gebraucht um
- Logische Bausteine zu erstellen, welche elementare Bauteile für das
- Programmierbare System liefert. Dem nun funktionsfähigen Rechner möchten wir einfacher Befehle zuordnen können, wodurch die
- Assemblerprogammierung in Kraft tretet. Anschließend sollen noch
- Peripherie(-Geräte) mit dem Rechner kommunizieren.

#Digitale Schaltungen

##Einführung
#Schaltnetze und Schaltwerk

Ein Rechner enthält viele digitale Schalter, welche jeweils den Zustand 0 = Off oder 1 = On haben. 
**Digitale Schaltungen**: Je nach _Spannungspegel_ fließt 0 oder 5 Volt. Eine Digitale Schaltungen mir 2 Spannungspegel wird auch Binäre Schaltung genannt.
Man unterscheidet digitale Schaltungen zwischen Schaltnetzen und Schaltwerken:
|             |Schaltnetze   |Schaltwerken     |
|------------:|--------------|-----------------|
|Gedächtnis   |nein          |ja			   |
|Rückkoppelung|nein          |ja			   |
|Formal auch: |Schaltfunktion|endlicher Automat|
Der Rechner ist ein Schaltwerk, welcher aber durch Schaltnetze realisiert wird.

#Synchronisation

Jeder Schalter benötigt Zeit zum Umschalten (=**Schaltzeit**), so auch digitale Schalter. D.h.
dass das Ausgangssignal erst betrachtet werden darf, wenn der _Umschaltvorgang fertig_ ist. => Nutzen von **Synchronisation** -> *Taktsignale*
Das **Eingangssignal** wird zu einem bestimmten _Taktzeitpunkt_ angelegt und die
**Ausgangssignale** erst nach einer _festgelegten Anzahl von Takten_ gelesen.
![Synchronisation](https://puu.sh/t2oUW/81acca0e05.png)

##Schaltfunktionen
#Defintion und Begriffe

**Defintion Schaltfunktion**:
>Sei V={0, 1} die Menge der beiden Signale 0, 1. Die Funktion
>![Funktion](https://puu.sh/t2oU3/803a519966.png)
>mit m,n ≥ heißen *Boole'sche Funktionen* oder auch *Schaltfunktionen*.
Anmerkung:
- bei _m = 1_ spricht man von *echten* _Boole'schen Funktionen_.
- n heißt *Stelligkeit*.
- m heißt *Wertigkeit*.

Diese Funktion kann auch verschiedene Arten dargestellt werden. Üblich sind:
- Funktionstabellen
- Mathematische Beschreibung mit Boole'schen Termen (Schaltalgebra)
- Schaltbilder, Schaltungsdiagramma

#Funktionstabellen
sind *Auflistung aller möglichen Funktionswerte*.

Bsp: Die Funktion V

