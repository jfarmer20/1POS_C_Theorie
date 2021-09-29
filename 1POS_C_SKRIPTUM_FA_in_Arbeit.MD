# 7. Mathematische Funktionen – `<math.h>`

In der Headerdatei `<math.h>` sind folgende nützliche mathematische Funktionen und Konstanten deklariert: 

```
double pow(double x, double y)	// x hoch y
double sqrt(double x)	        // Wurzel aus x
double fabs(double z)           // Absolutwert von x
double sin(double x)	        // Sinus von x
double cos(double x)	        // Cosinus von x
double tan(double x)	        // Tangens von x
double exp(double x)	        // Exponentialfunktion e hoch x
double log(double x)	        // Nat. Logarithmus von x

M_PI 	// symbolische Konstante für PI
M_PI_2 	// symbolische Konstante für PI/2
M_PI_4 	// symbolische Konstante für PI/4
M_E 	// symbolische Konstante für e 
```

Fürs kaufmännisch Runden, Abschneiden, Abrunden und Aufrunden stehen folgende Funktionen zur Verfügung: 

```
double round(double x);  // Kaufmännisch Runden 
double trunc(double x);  // Kommazahlen abschneiden
double floor(double x);  // auf nächste Ganzzahl abrunden 
double ceil(double x);	 // auf nächste Ganzzahl aufrunden 
```

Im folgenden Beispiel wird die Verwendung der Funktionen veranschaulicht: 

```c
#include <stdlib.h>
#include <math.h>

int main()
{
    double x1, x2, y1, y2; 
    x1 = 5.23487392;
    x2 = 5.89437524;
    y1 = round(x1 * 1000)/1000;  // ergibt 5.235000
    y2 = round(x2 * 1000)/1000;  // ergibt 5.894000
    y1 = trunc(x1);              // ergibt 5.000000
    y1 = floor(x1);              // ergibt 5.000000 
    y1 = ceil(x1);               // ergibt 6.000000 
} 
```

Kaufmännisch Runden und Abschneiden ist auch durch explizite Typumwandlung möglich: 

```c
#include <stdio.h>

int main()
{
    double x1, x2; 
    int y1, y2; 
    double y3, y4; 
    x1 = 5.23487392;
    x2 = 5.89437524;
    // Kaufmännisch Runden:
    y1 = (int)(x1 + 0.5);                // ergibt 5
    y2 = (int)(x2 + 0.5);                 // ergibt 6
    // auf z.B. 3 Kommastellen Runden:
    y3 = (int)(x1 * 1000 + 0.5)/1000.0;  // ergibt 5.235000
    y4 = (int)(x2 * 1000 + 0.5)/1000.0;  // ergibt 5.894000
    // Kommastellen abschneiden:
    y1 = (int)x1;                        // ergibt 5
    // Zahl nach z.B. der 3. Kommastelle abschneiden:
    y3 = (int)(x1 * 1000)/1000.0;        // ergibt 5.234000    
} 
```

# 8. Kommentare 

Regeln für Kommentare:

* Mehrzeilige Kommentare werden mit `/*` eingeleitet und mit `*/` abgeschlossen.
* Einzeilige Kommentare beginnen mit `//` und erstrecken sich bis zum Ende der Zeile.
* Kommentare können an beliebiger Stelle stehen.

# 9. Character- und Stringliterale 

## 9.1. Characterliterale

Die Zuweisung erfolgt durch genau ein Zeichen, das in einfachen Anführungszeichen eingeschlossen wird. Auf der char-Variablen wird der entsprechende ASCII-Wert des Zeichens gespeichert. 

```c 
char c1, c2, c3;

c1 = 'A';     	// numerischer Wert 65
c1 = 65;      	// identisch zur vorherigen Anweisung
c2 = 'F';     	// numerischer Wert 70
c3 = '1';     	// numerischer Wert 49
c4 = '\n';      // Zeilenumbruch
```

Zu den Characterliteralen gehören auch die Sonder- und Steuerzeichen, die mit einem Backslash '`\`'  eingeleitet werden (Escape-Sequenz) und trotzdem als einzelne Zeichen gelten. 

Das Umwandlungszeichen (conversion), um Characterliterale einzulesen bzw. auszugeben lautet „c“: 

```c
char zeichen; 
scanf("%c", &zeichen);
printf("%c", zeichen);
```

## 9.2. Stringliterale

Für Strings gibt es in C keinen eigenen Datentyp, daher müssen Zeichenketten in Form von `char`-Arrays behandelt werden.

Folgende Eigenschaften gelten für Zeichenketten:

* Sie bestehen aus einer Folge von Einzelzeichen. 
* Sie werden in doppelte Anführungszeichen eingeschlossen:	
 "Das ist eine Zeichenkette". 
* Am Ende muss ein NULL-Zeichen ('`\0`') zur Kennzeichnung des Endes angehängt werden.
Es gelten die gleichen Escape-Sequenzen wie bei einzelnen Zeichen.
* Zeichenketten können über Zeilengrenzen gehen, wenn unmittelbar vor dem Zeilentrenner ein Backslash '`\`' steht. 
Sie können einem Charaterfeld (char-Array) zugewiesen werden.
Sie dürfen nur bei der Initialisierung oder beim Einlesen zugewiesen werden, nicht aber zu einem späteren Zeitpunkt.

```c 
char str1[100] = "";
char str2[] = { "Hallo" };
char str3[] = { 'H', 'a', 'l', 'l', 'o', '\0' };
char str4[] = { 72, 97, 108, 108, 111, 0 }; 
char str2[20] = "Teil 1\
                 Teil2";       // Der Zeilenumbruch ist auf dem String nicht sichtbar

str1 = "ungültige Zuweisung";  // Compilerfehler!
```

Das Umwandlungszeichen (conversion), um Stringliterale auszugeben lautet „`%s`“: 

```c 
char str1[] = { "Hallo" };
printf("%s", str1);
```

Fürs Einlesen von Stringliteralen von der Konsole stehen die beiden Befehle `gets(s, max)` und `scanf("%s, s)` zur Verfügung: 

```c
char str1[100] ="";
gets(str1, 100); 
scanf("%s", str1); 
```

Um die Länge eines Stringliterals feszustellen, steht der Befehl `strlen(s)` zur Verfügung: 

```c 
char str[] = { "Hallo" };
int strLaenge; 
strLaenge = strlen(str); 
```

Der Zugriff auf einzelne Zeichen eines Stringliterals erfolgt folgendermaßen: 

```c 
char str[] = { "Hallo" };
char c; 
c = str[0];    // Weist der Variablen c das Zeichen ‚‘H‘ zu 
```

Zur Umwandlung von Zeichenketten in numerische Werte stehen in der C-Standard Library `<stdlib.h>` unter anderem folgende Konvertierungsfunktionen zu Verfügung: 

```c 
int atoi(<String>)	    // Konvertierung von String in int
double atof(<String>)	// Konvertierung von String in double
```

# 10. Operatoren – 2. Teil 

# 11. Arrays (Felder)

## 11.1. Eindimensionale Arrays

## 11.2. Eindimensionale Arrays dynamisch erzeugen 

Mit der Funktion `malloc()` lässt sich für ein Array ein zusammenhängender Speicherbereich zur Laufzeit reservieren.  
**Wichtig:** Sobald das Array im Programm nicht mehr benötigt wird, ist der Speicherbereich verlässliche mit der Funktion `free()` wieder freizugeben. 

Im folgende Programm wird ein Array dynamisch erzeugt, initialisiert, am Bildschirm ausgegeben und dessen Speicherbereich am Ende wieder freigegeben. 


Ein dynamisch erzeugtes Feld kann gleich wie statisch erzeugte Felder verwendet werden (z.B. bei Funktionsübergabe, Zugriff auf die einzelnen Elemente). 

```c 
#include <stdio.h>
#include <stdlib.h>

void printArray(int a[], int size)
{
    for (int i = 0; i < size; i++)
    {
        printf("%4d", a[i]);
        if (i % 10 == 9)
            printf("\n");
    }
}

int main()
{
    int *a1;
    int s1 = 100;

    // Array dynamisch erzeugen 
    a1 = (int *)malloc(sizeof(int) * s1);

    // Array initialisieren 
    for (int i = 0; i < s1; i++)
        a1[i] = i;

    // Array ausgeben
    printArray(a1, s1);

    // Reservierten Speicher freigeben 
    free(a1);

    return 0;
}
```

## 11.3. Mehrdimensionale Arrays 

Jede Dimension des Arrays wird über einen eigenen Index angesprochen. 

Syntax der Arraydeklaration: 

```
datentyp arrayName[anzahl_dim1][anzahl_dim2] . . . [anzahl_dimN];
```

Beispiele einer Arraydeklaration: 

```c 
 int f1d[10];                      // 1-dimensionales Feld
 int f2d[10][5];                   // 2-dimensionales Feld: Entspricht einer 
                                   // Tabelle mit 10 Zeilen + 5 Spalten = 50 Elementen
 ```
 
Initialisieren lassen sich mehrdimensionale Arrays wie folgt: 

 ```c
 int f22[][3] = {{1,2,3},          // 2-dimensionales Feld: Entspricht einer 
                 {4,5}};           // Tabelle mit 2 Zeilen + 3 Spalten = 6 Elementen
 int f3d[100][5][2] = {0};         // 3-dimensionales Array mit 100*5*2 = 1000 Elementen 
 ```
 
 ```c 
 int dim1, dim2, dim3, dim4;

 dim1 = sizeof(f1d)/sizeof(int);
 dim2 = sizeof(f2d)/sizeof(int);
 dim3 = sizeof(f22)/sizeof(int);
 dim4 = sizeof(f3d)/sizeof(int);

 printf("Anzahl der Elemente von f1d: %4d\n",dim1);
 printf("Anzahl der Elemente von f2d: %4d\n",dim2);
 printf("Anzahl der Elemente von f22: %4d\n",dim3);
 printf("Anzahl der Elemente von f3d: %4d\n",dim4);
 ```

Testlauf:

```
Anzahl der Elemente von f1d:   10
Anzahl der Elemente von f2d:   50
Anzahl der Elemente von f22:    6
Anzahl der Elemente von f3d: 1000
```

Bei der Initialisierung kann die Größenangabe der ersten Dimension - und nur der ersten Dimension - weggelassen werden. Eventuell nicht initialisierte Elemente werden auf 0 gesetzt.  Die einzelnen Arrayelemente von `f22` werden daher folgendermaßen initialisiert:

```c
f22[0][0] = 1	f22[0][1] = 2	f22[0][2] = 3
f22[1][0] = 4	f22[1][1] = 5	f22[1][2] = 0
````

```c
int f31d[][10][5] = {0};            // Array mit 1*10*5 = 50 Elementen
int f32d[][10][5] = {{0},           // Array mit 3*10*5 = 150 Elementen
                     {0},
                     {0}};  
int f33d[][][10] = {0};             // Compilerfehler!
int aTest[][] = {{1,2},             // Compilerfehler! 
                 {3,4}}; 
```

Die dritte Deklaration führt zu einem Compilerfehler, da mehr als nur die erste Dimension nicht angegeben sind und der Compiler daher die Arraygröße nicht bestimmen kann. 

## 11.4. Übergabe von mehrdimensionalen Arrays an Funktionen 

Gleich wie bei eindimensionalen Arrays, erfolgt auch bei mehrdimensionalen Arrays die Parameterübergabe nach dem *call-by-reference* Prinzip. 

In der formalen Parameterliste muss für jede Dimension ein Klammerpaar `[]` stehen. Die Anzahl der Elemente muss erst ab der zweiten Dimension definiert sein und die Anzahl der Werte jeder Dimension sind zusätzlich als Parameter mitzuübergeben. 

Beispiel: 

```c 
void initArray(int a2d[][10], int rows, int columns);   // Funktionsprototyp

int main()
{
    int a2d[10][10] = {0};
    initArray(a2d, 10, 10);
    . . .
    return 0;
}

void initArray(int a2d[][10], int rows, int columns)
{
    srand(time(NULL));
    int i, j;
    for (i = 0; i < rows; i++)
        for (j = 0; j < columns; j++)
            a2d[i][j] = rand() % 100 + 1;
}
```

## 11.5. Mehrdimensionale Arrays dynamisch erzeugen 

```c 
/* 2D_dyn_array.c */
#include <stdio.h>
#include <stdlib.h>
#define BUF 255

int main(void)
{
    int i, j, zeilen, spalten;
    /* Matrix ist Zeiger auf int-Zeiger. */
    int **matrix;

    printf("Anzahl Zeilen : ");
    scanf("%d", &zeilen);
    printf("Anzahl Spalten: ");
    scanf("%d", &spalten);

    /* Speicher reservieren für die Zeiger auf die einzelnen Zeilen */
    matrix = malloc(zeilen * sizeof(int *));

    /* Speicher für die Zeilen reservieren */
    for (i = 0; i < zeilen; i++)
    {
        matrix[i] = malloc(spalten * sizeof(int));
    }

    /* Array initialisieren */
    for (i = 0; i < zeilen; i++)
        for (j = 0; j < spalten; j++)
            matrix[i][j] = (i * spalten) + j; /* matrix[zeilen][spalten] */

    /* Matrix ausgeben */
    for (i = 0; i < zeilen; i++)
    {
        for (j = 0; j < spalten; j++)
            printf("%4d ", matrix[i][j]);
        printf("\n");
    }

    /* Speicherplatz (in umgekehrter Reihenfolge!) wieder freigeben. */

    /* Zeilen freigeben */
    for (i = 0; i < zeilen; i++)
        free(matrix[i]);
    /* Speicher der Zeiger auf die Zeilen freigeben */
    free(matrix);

    return EXIT_SUCCESS;
}
```

# 12. Anhang 

## 12.1. Weitere Literatur

[Sedgewick, R.; Wayne, K.: Algorithms. Fourth Edition. Pearson Education 2011, HTML-Version](https://algs4.cs.princeton.edu/home/)  

[Sedgewick, R.; Wayne, K.: Algorithms. Fourth Edition. Pearson Education 2011, PDF-Version](https://github.com/Mcdonoughd/CS2223/raw/master/Books/Algorithhms%204th%20Edition%20by%20Robert%20Sedgewick%2C%20Kevin%20Wayne.pdf) 

## 12.2. Übersicht des Unterrichtsstoffs

* Windows-Command-Shell (cmd): `dir`, `mkdir`, `ren`, `rmdir`, `cd`, `copy`, `del`, `help <command>`, … 

* Entwicklungsumgebung [Visual Studio Code](https://code.visualstudio.com/)  

* Programmiersprachenunabhängiger Programmentwurf mittels Struktogrammen (Nassi-Shneiderman-Diagrammen) [Structorizer](https://structorizer.fisch.lu/) 

* Formatierte Ausgabe, `printf()`-Befehl

* Eingabe mit `scanf()`-Befehl und Menüführung, sobald Schleifen bekannt 

* Datentypen für Ganzzahlen, Gleitkommazahlen, Characterliterale. 

* Arithmetische Operatoren (`+`, `-`, `*`, `/`, `%`, `++`, `--`) inklusive Ganzzahl-Division und Modulo

* Arrays mit einfachen Datentypen (auch mit Characterliterale) 

* Vergleichs- und logische Operatoren 

* Entscheidung (if-else, switch-case) 

* Zufallszahlengenerierung, ganzzahlig und mit Gleitkommazahlen

* Kaufmännisch Runden bzw. Abschneiden mit expliziter Typumwandlung (typecast) 

* Schleifen: 
  * while
  * do-while 
  * for (mit inkrementierender und dekrementierender Zählvariable, Inkrement und Dekrement ungleich Schrittweite 1) 
  * `continue`, `break` im Schleifenkontext 
  * Schreibtischtest

* Zahlensysteme: Binär, Dezimal, Hexadezimal; Umwandlung; 2er-Komplement, Horner-Schema in Form von Beispielen 

* Stringliterale 

* Programmstrukturierung mittels Funktionen und Vorwärtsdeklarationen, *call-by-value*, *call-by-reference*, Array-Übergabe 

  **Optional**

* 2-dimensionale Arrays 

* Fehlersuche (mit printf()-Ausgaben, Debugger) 

* Strukturen

* Rekursion versus Iteration (am Beispiel Fakultätsberechnung und Fibonacci-Zahlen) 