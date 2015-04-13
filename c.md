C Programmieren
===============

###Was ist C überhaupt?

C ist eine imperative Programmiersprache (Befehlorientierte Programmiersprache). Einige andere Sprachen wie C++, Objective-C und C# orientieren sich an C.
Sie ist die Grundsprache aller C lastigen Programmiersprachen, da die für Betriebsysteme genutzt wird.
Bevor man richtig mit C-Programmiert muss man richtige Werkzeuge und Grundwissen besitzen. Zuerst braucht man eine Programmierer Oberfläche (IDE = integrated development enviroment), diese beinhaltet:
* Texteditor
* Compiler
* Linker
* Debugger
* Quelltextformatierungsfunktion

###Texteditor, Compiler was ist das?

Beim Texteditor handelt es sich um die Schreibfläche, wo man neue .c files schreibt. Der Compiler ist der Übersetzter. Von unserer C-Syntax (z.B. printf("")) ins 0 und 1 umwandeln. Weil der Computer nur dieses "Sprache" spricht, braucht es einen Compiler, der von unseren Befehlen ins Binärsystem umwandelt.

![alt text](https://github.com/michaelhaenzi/c-language/blob/master/compiler.PNG)

###Grundgerüst

| Was? | Beschreibung |
| ---- | ------------ |
| #include <stdio.h> | einbinden einer Bibliothek |
| int main () | Hauptprogramm/ Hauptfunktion |
| {} | Anfang und Ende einer Funktion |
| ; | Abschliessung jedes Befehles (Semikolon) |
| return 0; | Zürckgabewert: 0 () |

![alt text](https://github.com/michaelhaenzi/c-language/blob/master/grundgeruest.png)

**Zusatz Befehle**

| Was? | Beschreibung |
| ---- | ------------ |
| /* \* / | Mehrzeiliger Kommentar, wird vom Compiler ausgelassen |
| // | Kommentar, wird vom Compiler ausgelassen |
| printf("") | Etwas in Textform ausgeben |
| system("pause") | Bei anwendung von .exe Programm startet ohne zu schliessen |

###Hello World

Das waren die zwei "Worte" die das erste B Programm (Vorgänger von C) ausgab. Bis heute ist es die bekannteste Ausgabe mit C.
Nun gehts auch los:

Quellcode:

```c
#include <stdio.h>

int main() {
  printf("Hello World!");
  return 0;
}
```

Ausgabe:

![alt text](https://github.com/michaelhaenzi/c-language/blob/master/helloworld.PNG)

Da man jetzt im Stande ist einen Text auszugeben, bietet dies viele Möglichkeiten an.

###Variablen

In einer einer Variable lässt sich ein Wert speichern, man kann dieser Variable einen Namen geben und verschiedene Typen von Variablen auswählen.

**Daten-Typen**

| Datentyp | Beschreibung | Reichweite | Bytes | Adressoperator |
| -------- | ------------ | ---------- | ----- | -------------- |
| int | Interger (Ganz-Zahlen) | -32 768 .. +32 767 | 2 | %d |
| char | Charater (ASCII-Tabelle) | -128 .. +127 | 1 | %c oder %d |
| float | Float (Fliesskomma-Zahl) | Max. 7 Stellen | 4 | %f oder %.xf |
| long | Long (Ganz-Zahl) | -2 147 483 648 .. +2 147 483 647 | 4 | %d oder %l |
| Double | Double (Fliesskomma-Zahl) | Max. 19 Stellen | 8 | %f, %lf oder %.xf |

**Syntax**

```c
datentyp variablenname;
//oder
datentyp variablenname = wert;

//Beispiel
int zahl1 = 7;
float zahl2 = 7.2;
char charakter1 = 'a';
```

**Variablen in der Ausgabe**

```c

char ch = 'a';
int a = 3;
/*
Innerhalb der Hänsefüsschen(""), Text und Adressoperator.
Ausserhalb, die Variablen, mit Kommas getrennt und der Reihenfolge aufgeführt.
*/

//Beispiel 1
printf("Variable a hat den Wert: %d", a);
//Beispiel 2
printf("Variable %c hat den Wert: %d", ch, a);
```

**Operatoren**

* Addition ( + )
* Subtraktion ( - )
* Multiplikation ( * )
* Division ( / )
* Modulo ( % )
* Zuweisung ( = )
* Inkrement ( ++ )
* Dekrement ( -- )

###Benutzerinteraktionen

**scanf-Befehl**

Mit dem Befehle scanf, wird der Benutzer aufgefordert eine Eingabe zu tätigen.
Man speichert die Eingabe in eine Variable.
Hierbei ist wichtig die Richtigen Datentypen zu verwenden:

```c
//Deklaration der Variable a
int a;

//Text, dann Eingabe mit Adressoperator und Kaufmanns-& um auf die Variable hinzuweisen.
printf("Geben Sie eine Zahl ein: ");
scanf("%d", &a);

//Ausgabe
printf("Der eingegebene Zahlenwert ist: %d", a);
```
```c
//String (Charkette, Wort) deklariert
char ch[15] = "";

//Eingabe des Strings (Charkette, Wort)
printf("Geben Sie ein Wort ein: ");
scanf("%s" &ch);
```

**getch-Befehl**

Eine andere Variante ist der Befehl `getch()`, welcher erlaubt einen char (Zeichen) einzulesen.

```c
//Deklaration
char ch;

//Einlesen eines Chars
ch =  getch();
```

###Verzweigungen

Wir kommen zu einem Thema, welches komplexer sein kann. Die Abzweigungen können in verschiedenen Varianten vorkommen und einige Bedingungen beinhalten, was das sind schauen wir gleich an.

**IF-ELSE Verzweigung**

```c
//Deklaration und Initialisierung
int zahl = 5;

//if (Bedingung) {
//Befehl
//}

if (zahl == 5) {
  printf("Zahl ist fuenf.");
}
```

Die Ausgabe ist `fuenf`. Zuerst kommt das Schlüsselwort if am Anfang. In den runden Klammern kommt die Bedigung (Im Beispiel, Ausgesprochen: Wenn die Variable Zahl den Wert 5 hat.). Wenn die Bedigung zutrifft, also True (Wahr), wird der/ die Befehl/ e in den geschwungenen Klammer ausgeführt.

```c
//Deklaration und Initialisierung
int zahl = 6;

//True/ Wahr
if (zahl == 5) {
  printf("Zahl ist fuenf.");
}
//Flase/ Falsch
else {
  printf("Zahl ist nicht fuenf.");
}
```

Da die Variable zahl nicht mehr fuenf ist, sondern 6 wird der Compiler in die else Verzweigung gehen, also false (Falsch). Die Ausgabe ist: Zahl ist nicht fuenf.
