<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

### Probeklausur PROG 1

#### Aufgabe 1

Geben Sie die Ausgabe an.

**a)** 

```c++
int i = 10;
for(int i = 0; i < 4; i++)
	cout << i << " ";
	cout << i << " ";
```

**b)** 

```c++
for (int j = 3; (j % 2 == 1) && (j < 10); j += 2){
	cout << j << " ";
}
```

**c)**

```c++
int x = 0;
int y = 1;
do {
	x = x + 2*y;
	cout << x << " ";
	y = x;
} while (x < 15);
```

**d)**

```c++
for(int k = 4; k < 7; k++){
	for(int l = 15; l <= 18; j++){
		if (l%k == 1)
			cout << l << " -- " << k << endl;
	}
}
```

##### Ergebnis

a) 0 1 2 3 10

> Die for-Schleife besitzt keine geschweiften Klammern, d.h. sie ist ein Einzeiler

b) 3 5 7 9 

> (j % 2 == 1) ist immer _true_

c) 2 6 18 

d) 17 -- 4

16 -- 5





#### Aufgabe 2

Lesen Sie den Code und geben sie die Ausgaben an.

```c++
#include "stdafx.h"
#include <iostream>

using namespace std;

void ausgabe(int ein) {
	if (ein < 10){
		cout << "A ";
	}
	else if (ein < 20) {
		cout << "B ";
	}
	else {
		cout << "C ";
	}

	switch (ein%4){
	case 0:
		cout << "V ";
	case 1:
		cout << "W ";
		break;
	case 2:
		cout << "X ";
		break;
	case 3:
		cout << "Y ";
		break;
	default:
		break;
	}
}

float funktion1 (int a, int b){
	return a / b + 0.5f;
}

int funktion2 (int a, float b){
	return a * b;
}

int main(){
	//Ausgabe 1
	cout << funktion1(10, 3) << endl;
	//Ausgabe 2
	cout << funktion1(12, 2) << endl;
	//Ausgabe 3
	cout << funktion1(10, 2.f) << endl;
	//Ausgabe 4
	cout << funktion 2(10, 3.4f) << endl;

	float ergebnis = funktion1(funktion2(10, 2.4f), 2);
	//Ausgabe 5
	cout << ergebnis << endl;
	//Ausgabe 6
	ausgabe(ergebnis);

	return 0;
}
```

##### Ergebnis

**Ausgabe 1**: 3.5

> 10/3 = 3.3 aber: int-Wert -> 3 (rundet nicht, "hackt" einfach die Zahlen ab)

**Ausgabe 2**: 6.5

**Ausgabe 3**: 5.5

**Ausgabe 4**: 34

**Ausgabe 5**: 12.5

**Ausgabe 6**: B V W 

> float 12.5 -> int 12
>
> case 0: hat kein break;





#### Aufgabe 3

Entwerfen sie folgende Komponenten eines Superheldenspiels. Vermeiden Sie insbesondere fehlerhafte Speicherzugriffe, die zu Spielabsturz führen könnten.

> Heißt: Zeigervariablen der Klassen müssen mit NULL initialisiert werden.

**a)** Entwerfen sie eine abstrakte Klasse _Superheld_. Die Klasse soll eine rein virtuelle Funktion _void machtwastolles()_ besitzen.



**b)** Die Funktion _void machtwastolles()_ wird von den abgeleiteten Klassen _Superman_ und _Wasserman_ redefiniert. Ein _Superman_ soll sagen können "Ich fliege!", ein _Wasserman_ sagt "Ich schwimme!". 

Geben Sie für die Klasse _Superman_ die Klassedeklaration und die Definition von _void machtwastolles()_ an.



**c)** Definieren Sie in der main Funktion ein Array der Länge 5 von Zeigervariablen des Typs _Superheld_.

Geben Sie nur die Definition und Deklaration und Initialisierung des Arrays an.



**d)** Erzeugen sie dynamisch 1 Objekt vom Typ _Superman_ und 2 Objekt vom Typ _Wasserman_.



**e)** Geben Sie mithilfe einer For-Schleife durch das gesamte Array und prüfen sie, welcher Objekttyp (also _Superman_, _Wasserman_ oder _gar nichts_) ab der gespeicherten Adresse steht und geben sie entsprechend "Superman", "Wasserman" oder "kein Superheld definiert" aus.



**f)** Geben Sie mithilfe einer For-Schleife durch das gesamte Array und rufen Sie die Funktion _machtwastolles()_ für alle existierenden Superhelden auf.



**g)** Das Spiel soll jetzt beendet werden. Löschen Sie dazu alle dynamisch erzeugten Objekte aus dem Speicher.

##### Ergebnis

a)

```c++
class Superheld {
	public:
		virtual void machtwastolles() = 0;
}
```

b)

```c++
//Superman.h
#include "Superheld.h"
#include <iostream> //#include "stdafx.h"

class Superman :
public Superheld {
	public:
		Superman();
		~Superman();

		void machtwastolles(); //virtual void machtwastolles() override;
}

//Superman.cpp
#include "Superman.h"

Superman::machtwastolles(){
	cout << "Ich fliege!" << endl;
}
```

c)

```c++
const int sizearrray = 5;
Superheld* meineSuperhelden[sizearray] = {NULL};
```

d)

```c++
meineSuperhelden[0] = new Superman;
meineSuperhelden[1] = new Wasserman;
meineSuperhelden[2] = new Wasserman;
//meineSuperhelden[3] = NULL;
//meineSuperhelden[4] = NULL;
```

e)

```c++
for(short i = 0; i < sizearray; i++){
	//Superman* eineAdresseeinesSupermans = dynamic_cast<Superman*> (meineSuperhelden[i]);
	if (dynamic_cast<Superman*> (meineSuperhelden[i])){
		cout << "Superman" << endl;
	}
	else if (dynamic_cast<Wasserman*> (meineSuperhelden[i])){
		cout << "Wasserman" << endl;
	}
	else {
		cout << "Kein Superheld" << endl;
	}
}
```

f)

```c++
for(short i = 0; i < sizearray; i++){
	if(meineSuperhelden[i]){ //Prüfe ob kein Null-Pointer
		meineSuperhelden[i]->machtwastolles();
	}
}
```

g)

```c++
for(short i = 0; i < sizearray; i++){
	if(meineSuperhelden[i]){ //Prüfe ob kein Null-Pointer
		delete meineSuperhelden[i];
	}
}
```