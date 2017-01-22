<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# IT-Systeme Übung 4

- [Hauptseite](https://ge-kempten.github.io)
- [ITS](https://ge-kempten.github.io/1/it-systeme/)

### Aufgabe 1

Analysieren sie das Programm:

```pseudo
00:  010e 8080 ffc0
01:  0000 0000 0000
02:  0000 0000 0000
03:  0000 0000 0000

04:  4000 0080 0080
05:  c001 0000 8091
06:  0000 0000 0000
07:  0000 0000 0000

08:  0101 0040 4000
09:  0000 0000 0000
0a:  0000 0000 0000
0b:  0000 0000 0000

0c:  0106 0040 4000
0d:  0000 0000 0000
0e:  0000 0000 0000
0f:  0000 0000 0000

10:  0000 0000 0000
11:  0000 0000 0000
12:  0000 0000 0000
13:  0000 0000 0000

14:  0102 4020 4000
15:  0000 0000 0000
16:  0000 0000 0000
17:  0000 0000 0000
```

00: berechnet XOR aus R0 mit R0 --> liefert immer 0

  lädt in alle Register, sowie MDR & MAR

  springt zu absoluter Adresse 1(\*4)

04: lädt R1(IP) in MAR

  springt relativ um 0 weiter (von 04 zu 05)

05: liest Wert aus Speicher als OpCode (und schiebt y nach R1)

  springt zu 4*Opcode (0 --> beginnt von vorne)

### Aufgabe 2

|Aufgabe|Speicherzelle|Mikrobefehl|
|:-:|:-:|:-:|
|a|0x18|0101 0010 1000|
|b|0x1c|0106 0010 1000|
|c|0x24|4000 0000 4021|
||0x25|0101 0080 8080|
|d|0x28|4000 0000 1021|
||0x29|0101 0080 8000|
|e|0x2c|4000 0040 0080|
||0x2d|0102 0800 0821|
