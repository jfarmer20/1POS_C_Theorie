# 1. Einführung in die Programmiersprache C

## 1.1. Hinweise 
Dieses Skriptum umfasst den Unterrichtsstoff für POS des ersten Jahrgangs der Abteilung Informatik an der HTBLA Kaindorf ab dem Schuljahr 2017/18. 

Falls aus dem Unterricht etwas unklar bleibt oder man sich vertiefen möchte steht ein frei verfügbares Lehrbuch zur Programmiersprache C unter dem Link: 
http://openbook.rheinwerk-verlag.de/c_von_a_bis_z/ 
zur Verfügung. 

## 1.2. Weitere Literatur

Sedgewick, R.; Wayne, K.: Algorithms. Fourth Edition. Addison-Wesley Professional 2011: Homepage:  
https://algs4.cs.princeton.edu/home/  
PDF-Download: 
https://github.com/Mcdonoughd/CS2223/raw/master/Books/Algorithhms%204th%20Edition%20by%20Robert%20Sedgewick%2C%20Kevin%20Wayne.pdf 

Für Rätselfüchse: Projekt Euler:  
https://projecteuler.net/ 

## 1.3. Inhaltsverzeichnis 

- [1. Einführung in die Programmiersprache C](#1-einführung-in-die-programmiersprache-c)
  - [1.1. Hinweise](#11-hinweise)
  - [1.2. Weitere Literatur](#12-weitere-literatur)
  - [1.3. Inhaltsverzeichnis](#13-inhaltsverzeichnis)
  - [1.4. Übersicht – Unterrichtsstoff POS, 1. Jahrgang](#14-übersicht--unterrichtsstoff-pos-1-jahrgang)
- [2. Quick Start](#2-quick-start)
  - [2.1. Wichtige Begriffe für Programmierer](#21-wichtige-begriffe-für-programmierer)
  - [2.2. Geschichte von C](#22-geschichte-von-c)
  - [2.3. Installation von Visual Studio Code](#23-installation-von-visual-studio-code)
  - [2.4. Erstes Programm mit Visual Studio Code (VSC)](#24-erstes-programm-mit-visual-studio-code-vsc)
  - [2.5. `helloworld.c` kompilieren](#25-helloworldc-kompilieren)
  - [2.6. `helloworld.c` starten/debuggen](#26-helloworldc-startendebuggen)
  - [2.7. Einführungsbeispiel](#27-einführungsbeispiel)
- [3. Mein erstes Programm mit Eingabe, Zuweisung und Ausgabe](#3-mein-erstes-programm-mit-eingabe-zuweisung-und-ausgabe)
  - [3.1. `printf()`-Befehl: Steuerzeichen und Sonderzeichen](#31-printf-befehl-steuerzeichen-und-sonderzeichen)
  - [3.2. Struktogramm](#32-struktogramm)
- [4. Operatoren – 1. Teil](#4-operatoren--1-teil)
  - [4.1. Zuweisungsoperator](#41-zuweisungsoperator)
    - [4.1.1. Variablentausch mit Hilfsvariable](#411-variablentausch-mit-hilfsvariable)
  - [4.2. Variablentausch ohne Hilfsvariable](#42-variablentausch-ohne-hilfsvariable)
  - [4.3. Arithmetische Operatoren](#43-arithmetische-operatoren)
    - [4.3.1. Vorzeichenoperatoren](#431-vorzeichenoperatoren)
    - [4.3.2. Binäre arithmetische  Operatoren](#432-binäre-arithmetische--operatoren)
- [5. Datentypen](#5-datentypen)
- [6. Zufallszahlen](#6-zufallszahlen)


## 1.4. Übersicht – Unterrichtsstoff POS, 1. Jahrgang 

* MS-Windows Einführung (Menüleiste, …) erfolgt in DBI; Kurzeinführung in die command-Shell (cmd, mkdir, cd, del, …) allerdings erforderlich

* Die Verwendung der USB-Sticks mit Linux können POS1-Hauptlehrer für sich entscheiden (allerdings teilweise Probleme mit den USB-Buchsen der Schul-PCs) 

* Einheitliche IDE: Visual Studio Code mit Code Runner  

* Programmiersprachenunabhängiger Programmentwurf mittels Struktogrammen (Minimalanforderung: Schüler*innen können Struktogramme lesen und als Programm umsetzen) 

* Formatierte Ausgabe, `printf()`-Befehl

* Eingabe mit `scanf()`-Befehl und Menüführung (erst wenn Schleife bekannt) 

* Datentypen für Ganzzahlen, Gleitkommazahlen, Characterliterale. 

* Arithmetische Operatoren (`+`, `-`, `*`, `/`, `%`, `++`, `--`) inklusive Ganzzahl-Division und Modulo

* Felder mit einfachen Datentypen (auch mit Characterliterale) 

* Vergleichs- und logische Operatoren 

* Entscheidung (if-else, switch-case) 

* Zufallszahlengenerierung, ganzzahlig und als Gleitkommazahl  

* Kaufmännisch Runden bzw. Abschneiden mit expliziter Typumwandlung (typecast) 

* Schleifen: 
  * while
  * do-while 
  * for (mit inkrementierender und dekrementierender Zählvariable und Inkrementen und Dekrementen ungleich Schrittweite 1) 
  * `continue`, `break` im Schleifenkontext 
  * Schreibtischtest

* Zahlensysteme: Binär, Dezimal, Hexadezimal; Umwandlung; 2er-Komplement, Horner-Schema in Form von Beispielen (kein Oktalsystem, keine Multiplikation, keine Division, keine Kommazahlen) 

* Stringliterale 

* Programmstrukturierung mittels Funktionen und Vorwärtsdeklarationen, Call-by-Value, Call-by-Reference, Array-Übergabe 

* ~~Rekursion versus Iteration (am Beispiel Fakultätsberechnung und Fibonacci-Zahlen)~~ zu anspruchsvoll für den ersten Jahrgang 

* 2-dimensionale Arrays (abhängig von der Klasse) 

* Fehlersuche (mit printf()-Ausgaben, Debuggen) 

# 2. Quick Start 

## 2.1. Wichtige Begriffe für Programmierer

Ein **Programm** ist eine Abfolge von Befehlen/Anweisungen und wird meist in einer höheren Programmiersprache geschrieben. 

Ein **Compiler** übersetzt ein Programm, geschrieben in einer höheren Programmiersprache (z.B. C, Java, Python) in Maschinensprache (01100010001…). 

Ein **Debugger** dient zur Fehlersuche in Programmen. 

Eine **Entwicklungsumgebung** (IDE … Integrated Development Environment) wie z.B. QtCreator unterstützt Programmierer beim 
* Schreiben von Programmen
* Debuggen von Programmen 
* Compilieren und Ausführen von Programmen

Jede Programmiersprache stellt **Befehle** für: 
1.	Eingabe
2.	Ausgabe
3.	Mathematische Operationen
4.	Entscheidungen
5.	Schleifen  

zur Verfügung. 

Zudem stellt jede Programmiersprache **Datentypen** für 
* Ganze Zahlen
* Gleitkommazahlen
* Einen logischen Datentyp
* Literale (Zeichen und Zeichenketten)

bereit. 

## 2.2. Geschichte von C 
C ist eine imperative und prozedurale Programmiersprache. C wurde 1972 „erfunden“ und seit damals stets in Varianten weiterentwickelt. Das American National Standards Institute (ANSI) vereinheitlichte diese C-Varianten und veröffentlichte 1989 ein standardisiertes C. Dieser C-Standard wird im Sprachgebrauch als C89 bzw. ANSI-C bezeichnet. Er wurde von der International Organization for Standardization (ISO) übernommen und wird im Sprachgebrauch auch als C90 bezeichnet. 

Im Jahr 1999 erschien C99 mit Elementen der Programmiersprache C++. 

## 2.3. Installation von Visual Studio Code 
**Achtung**: Der Open-Source-Code-Editor Microsoft **Visual Studio Code** darf nicht verwechselt werden mit der viel umfangreicheren integrierten Entwicklungsumgebung (IDE) „Visual Studio 2019“. 

Hier der Download-Link:  
https://code.visualstudio.com/ 

Mingw-w64 (oder **Mingw64**) ist eine Portierung der Linux-Entwicklerwerkzeuge GNU Compiler Collection (GCC) und GNU Debugger (GDB) auf Windows.  

Homepage: http://mingw-w64.org/

Hier der Download-Link:  
https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe 

Wie starte ich Visual Studio Code? Einfach in der Windows-Suche “code“ eingeben und App öffnen.  
Wichtig ist noch: Menü „View“ und „Extensions“ öffnen. Im Suchfeld „c++“ eingeben und die **C/C++ Extension** von Microsoft installieren: 

![Screenshot Hello World without Persistency](./pictures/Screenshot_C_Cpp_Extension.png "Screenshot Hello World without Persistency")

Danach noch **Umgebungsvariable** konfigurieren (https://code.visualstudio.com/docs/cpp/config-mingw):   	
Windows-Suche: “Einstellungen“  
Suchfeld: „Umgebungsvariablen für dieses Konto bearbeiten“  
Variable `Path` auswählen und „Bearbeiten…“ drücken  	
Drücke „Neu“ und füge den Pfad zum „\bin“-Verzeichnis deiner mingw-w64-Installation hinzu (z.B. C:\Program Files (x86)\mingw-w64\i686-8.1.0-posix-dwarf-rt_v6-rev0\mingw32\bin) 

**Installation und Konfiguration prüfen**: 	
Visual Studio Code starten: Windows-Suche: „code“ eingeben.  
Terminal (Konsole) öffnen: Menü „View -> Terminal“  
In der Kommando-Zeile „g++ --version“ eingeben:  

![Screenshot Visual Studio Code Command Line Interface](./pictures/Screenshot_VSC_CLI.png "Screenshot Visual Studio Code Command Line Interface")

## 2.4. Erstes Programm mit Visual Studio Code (VSC)

In Windows-Suche „cmd“ eingeben und Eingabeaufforderung öffnen. 

Projektverzeichnis erstellen und VSC starten: 

```
mkdir projects
cd projects
mkdir helloworld
cd helloworld
code .
```

Quelldatei “helloworld.c” erstellen: 

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 1](./pictures/Screenshot_VSC_1.png "Screenshot Visual Studio Code Command Erstes Programm - Schritt 1")

```c
 // #include bewirkt das Einfügen von Quellcode aus einer anderen  
 // Datei. Die Header-Datei stdio.h wird in das Programm eingefügt.  
 // Sie beinhaltet die Funktionen, die wir zur 
 // (Standard)-Ein/-Ausgabe benötigen 
#include <stdio.h>                          

int main()         // Funktion main() definiert das Hauptprogramm
{                  // definiert den Anfang der Funktion
  printf("Hello World!\n");        // Aufruf der Funktion printf()
  printf("Press a key to continue... ");
  fflush(stdin);
  getchar();
  return 0;                    // Rückgabewert der Funktion main()
}                              // definiert das Ende der Funktion
```

Datei speichern: Menü File -> Save 

## 2.5. `helloworld.c` kompilieren 
Um VSC zu sagen, wie die Quelldatei helloworld.c nun zu kompilieren ist, braucht es eine tasks.json Datei: 	

Menü Terminal -> Configure Default Build Task…, “C/C++:gcc.exe build active file” auswählen. 

Quelldatei helloworld.c auswählen  

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 2](./pictures/Screenshot_VSC_2.png "Screenshot Visual Studio Code Command Erstes Programm - Schritt 2")

und mit der Tastenkombination Strg+Shift+b kompilieren. 

## 2.6. `helloworld.c` starten/debuggen 

Um helloworld.c starten oder debuggen zu können, braucht VSC die Datei launch.json: 

Menü Run -> Add Configuration…, „C++ (GDB/LLDB)“ und “gcc.exe – Aktive Datei erstellen und debuggen“ auswählen. 

Das Programm wird anschließend gleich ausgeführt was man mit der Tastenkombination Shift+F5 stoppen kann. 

Quelldatei helloworld.c auswählen 

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 3](./pictures/Screenshot_VSC_3.png "Screenshot Visual Studio Code Command Erstes Programm - Schritt 3") 

und mit der Tastenkombination Strg+F5 starten. 

Will man das Programm debuggen, an geeigneter Stelle einen Breakpoint setzen und das Programm mit der Taste F5 starten: 

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 4](./pictures/Screenshot_VSC_4.png "Screenshot Visual Studio Code Command Erstes Programm - Schritt 4") 

## 2.7. Einführungsbeispiel 

Lernt man eine neue Programmiersprache, dann ist meist ein „Hello World“ Programm, das erste Programm, das man schreibt. Und das machen wir im folgenden Einführungsbeispiel genauso. 

Das folgende „Hello World“ Programm zeigt die grundlegende Struktur eines C-Programms: 

```c 
// #include bewirkt das Einfügen von Quellcode aus einer anderen 
// Datei. Die Header-Datei stdio.h wird in das Programm eingefügt. 
// Sie beinhaltet die Funktionen, die wir zur 
// (Standard)-Ein/-Ausgabe benötigen 
#include <stdio.h>                        

int main()          // Funktion main() definiert das Hauptprogramm
{                   // definiert den Anfang der Funktion
  printf ("Hello World!\n");       // Aufruf der Funktion printf()
  return 0;         // Rückgabewert der Funktion main()
}                   // definiert das Ende der Funktion
```
**Erklärungen:**

* die Funktion `main()` muss in jedem C-Programm genau einmal vorhanden sein 
* die geschweiften Klammern definieren einen Funktionskörper oder Block 
* `printf()` ist eine Funktion zur formatierten Ausgabe auf der Konsole 
* Parameter der Funktion `printf()` ist hier der String `"Hello World!\n"`
Die Datei `stdio.h` muss inkludiert sein.
* die Zeichenkombination `'\n'` ist das Steuerzeichen für „Zeilenende“  
* Jede Anweisung wird mit `;` beendet 
* Mehrzeilige Kommentare werden in `/*` und `*/` eingeschlossen
* Einzeilige Kommentare beginn mit `//` und erstrecken sich bis zum Zeilenende
* C unterscheidet zwischen Groß- und Kleinschreibung 

Das folgende Listing zeigt eine modifizierte Version des „Hello World“ Programms:

```c 
#include <stdio.h>
int main()
{
  printf ("Hello");
  printf (" World!");
  printf ("\n");
  return 0;
}
```

# 3. Mein erstes Programm mit Eingabe, Zuweisung und Ausgabe 

Im folgenden Listing werden zuerst 

* Die Variable a vom Datentyp `int` (Integer … Ganzzahl) 
* Die Variable x vom Datentyp `float` (Float … Fließkommazahl) 
* Die Variable y vom Datentyp `double` (Double float … Fließkommazahl mit doppelter Genauigkeit) 

definiert.

Danach wird dem Anwender mit dem `printf()`-Befehl ausgegeben, dass er bitte entsprechende Zahlen eingibt.  
Mit dem `scanf()`-Befehl werden die Eingaben des Anwenders der jeweils passenden Variable (`a`, `x` und `y`) zugewiesen.  
Zum Schluss werden die Werte der Variablen (`a`, `x` und `y`) dem Anwender mit dem `printf()`-Befehl an der Konsole ausgegeben. 

```c
#include <stdio.h>

int main()
{
    int a;
    float x;
    double y;
    printf("Bitte eine ganze Zahl eingeben: ");
    scanf("%d", &a);
    printf("Bitte eine Kommazahl eingeben : ");
    scanf("%f", &x);
    printf("Bitte eine grosse Kommazahl eingeben: ");
    scanf("%lf", &y);
    printf("-------------------------------\n");
    printf("a = %d\n", a);
    printf("x = %f\n", x);
    printf("y = %lf\n", y);
    return 0;
}
```

Erklärungen: 

* Beim `scanf()`-Befehl, dienen `%d`, `%f` und `%lf` als Platzhalter, um den vom Anwender eingegebenen Wert einzulesen und der Variable `a`, `x` bzw. `y` zuzuweisen. 
* `%d` ist ein Platzhalter für eine Ganzzahl (d … decimal) 
* `%f` ist ein Platzhalter für eine Fließkommazahl (f … float) 
* `%lf` ist ein Platzhalter für eine Fließkommazahl  mit doppelter Genauigkeit (lf … long float) 
* Die Platzhalter für die Ausgabe der Variablen `a`, `x` und `y` mit dem `printf()`-Befehl sind gleich wie beim `scanf()`-Befehl. 
* Das `&`-Zeichen im scanf()-Befehl wird zu einem späteren Zeitpunkt erklärt. 

## 3.1. `printf()`-Befehl: Steuerzeichen und Sonderzeichen 

Sogenannte Escape-Sequenzen ermöglichen Steuerzeichen und Sonderzeichen auszugeben. Eine Escape-Sequenz wird durch einen Backslash `\`  eingeleitet, dem ein weiteres Zeichen folgt. Eine Escape-Sequenz gilt trotzdem als einzelnes Zeichen.
In der folgenden Tabelle sind die wichtigsten Escape-Sequenzen aufgelistet: 

| Escape-Sequenz | Bedeutung |
| --- | --- |
| `\n` | Zeilenumbruch |
| `\t` | Tabulator |
| `\'` | Einfaches Hochkomma |
| `\"` | Doppeltes Hochkomma |
| `\?` | Fragezeichen |
| `\\` | Backslash |
| `\0` | NULL zum Terminieren von Strings |
| `\b` | Backspace - Zurücksetzen um ein Zeichen |
| `\f` | Formfeed - Seitenumbruch |
| `\a` | Piepston |

## 3.2. Struktogramm 

Mit Struktogrammen, auch Nassi-Shneiderman-Diagramme genannt, werden Programme unabhängig von der Programmiersprache, mit der sie letztendlich umgesetzt werden, entworfen.   
Ein Struktogramm setzt sich aus Strukturblöcken zusammen. Diese können, wie wir noch sehen werden, ineinander verschachtelt sein. 

Beispiel eines Struktogramms mit Sequenz-Symbolen: 

![Nassi-Shneiderman-Diagramm nur mit Sequenzsymbolen](./pictures/NSD_01.png "Nassi-Shneiderman-Diagramm nur mit Sequenzsymbolen") 

**Aufgabe**: Lese eine Ganzzahl ein, erhöhe diese um eins und gib die Zahl aus. 

Struktogramm: 

![Nassi-Shneiderman-Diagramm Beispiel 1](./pictures/NSD_02.png "Nassi-Shneiderman-Diagramm Beispiel 1") 

Programm: 

```c
#include <stdio.h>

int main()
{
    int zahl;                        // ROT  
    printf("Ganze Zahl: ");          // ROT
    scanf("%d", &zahl);              // ROT
    zahl = zahl + 1;                 // GRÜN
    printf("Ergebnis: %d\n", zahl);  // BLAU
    return 0;
}
```

**Vorteil von Struktogrammen**:  
Man braucht sich beim Entwurf des Programms noch nicht mit Befehls- und Datentypdetails einer Programmiersprache auseinandersetzen. 

# 4. Operatoren – 1. Teil  

Es gibt in C drei Arten von Operatoren:
* Unäre Operatoren: benötigen nur einen Operanden, wie z.B. die Vorzeichenoperatoren `+` und `-`.
* Binäre Operatoren: benötigen zwei Operanden
* Ternäre Operatoren: benötigen drei Operanden

Im folgenden Abschnitt werden die wichtigsten Operatoren beschrieben:

## 4.1. Zuweisungsoperator 

Der Zuweisungsoperator `=` weist der Variablen auf der linken Seite den Wert des Ausdrucks der rechten Seite zu. 

### 4.1.1. Variablentausch mit Hilfsvariable 

Oft müssen die Inhalte zweier Variablen (z.B. a, b) vertauscht werden. Am einfachsten macht man das mit einer Hilfsvariablen h: 

```c
int a, b, h; 
...
h=a;
a=b;
b=h;
```

## 4.2. Variablentausch ohne Hilfsvariable 

Mathematikfüchse kommen ohne Hilfsvariable aus: 

```c 
int a, b; 
...
a=a+b;
b=a-b;
a=a-b;
```

## 4.3. Arithmetische Operatoren 

### 4.3.1. Vorzeichenoperatoren

Zur Darstellung der mathematischen Vorzeichen 'plus' und 'minus' werden die unären Vorzeichenoperatoren `+` und `–` verwendet.

```c
int z1, z2;
z1 = +5;
z2 = -9;
```
### 4.3.2. Binäre arithmetische  Operatoren

| Operator | Bedeutung |
| :---: | --- |
| `+` |	Addition |
| `-` |	Subtraktion |
| `*` |	Multiplikation |
| `/` |	Division |
| `%` |	Modulo-Division |

Regeln für die arithmetischen Operatoren: 

Wie in der Mathematik gilt Punkt- vor Strichrechnung, wobei der Modulooperator ein Punktoperator ist.

Gleichrangige Operatoren werden von links nach rechts ausgewertet.

* Sind beide Operanden vom selben Datentyp so ist auch das Ergebnis der Berechnung von diesem Datentyp, mindestens jedoch vom Typ `int`.
  
Sind die Operanden von unterschiedlichen Datentypen so ist das Ergebnis vom größeren der beiden Datentypen.
* Der Modulooperator ist nur für ganzzahlige Operanden zulässig. Das Ergebnis ist der ganzzahlige Rest der Division: `17 % 5 = 2`.
Bei den Divisionsoperatoren (`/` und `%`) führt eine Divison durch `0` zu einem Laufzeitfehler.

# 5. Datentypen

In C gibt es 4 Grunddatentypen. Deren Größe und Wertebereich sind nicht normiert. Bei den meisten Systemen gelten aber folgende Werte: 

| Name | Datentyp | Bytes |	Minimalwert | Maximalwert
| --- | --- | :---: | --- | --- |
| `int` | Ganze Zahl | 4 | -2147483648 (= $-2^{31}$) | 2147483647 (= $+2^{31}-1$) | 
| `char` | Ein Zeichen | 1 | -128 (= $-2^7$) | 127 (= $+2^7-1$) |
| `float` |	Fließkommazahl, 6-stellige Genauigkeit | 4 | 1.175494E-038 | 3.402813E+038 | 
| `double` | Große Fließkommazahl, 15-stellige Genauigkeit | 8 | 2.225074E-308 | 1.797693E+308 |

In C existiert kein logischer Datentyp (Datentyp boolean)! Stattdessen werden Variablen vom Datentyp int für Bedingungen verwendet werden, wobei folgende Regeln gelten:

Variablenwert gleich 0 -> `FALSE`  
Variablenwert ungleich 0 -> `TRUE`

Alle Variablen müssen vor ihrer Verwendung deklariert werden. Die Deklaration legt den Namen und den Typ fest. Deklarationen müssen immer am Anfang eines Programms stehen. 

# 6. Zufallszahlen 

Zum Erzeugen von ganzzahligen Zufallszahlen stehen in der C Standard Library `<stdlib.h>` folgende Funktionen zu Verfügung:

```c 
srand(<seed>)       // Anweisung zum Erzeugen eines Zufallszahlen-Seeds
srand(time(NULL))   // Erzeugen eines Zufallszahlen-Seeds,  
                    // initialisiert mit der aktuellen Systemzeit   
rand()              // Erzeugen einer ganzzahligen Zufallszahl
```

Für die Funktion `time()` muss zusätzlich die Datei `<time.h>` inkludiert werden. Die Funktion `srand()` definiert den Startwert (Seed) zum Erzeugen der Zufallszahlen. Durch die Übergabe der Funktion `time()` an `srand()` wird sichergestellt, dass bei jedem Programmstart neue Zufallszahlen erzeugt werden. 
Die Funktion `rand()` gibt eine Zufallszahl im Bereich von `[0,RAND_MAX]` zurück. Wobei die symbolische Konstante `RAND_MAX` dem Wert 32767 entspricht. Durch Verwendung des Modulo-Operators (`%`) kann der Wertebereich eingeschränkt werden. 

Benötigt man eine Zufallszahl im Intervall `[Untergrenze, Obergrenze]` gilt folgende Formel: 
```c 
rand()%(Obergrenze + 1 – Untergrenze) + Untergrenze
```
Im folgenden Beispiel wird eine Zufallszahl zwischen `[1, 100]` erzeugt:

```c
#include <stdlib.h>
#include <time.h>

int main()
{
  int zz;
  srand(time(NULL));
  zz = rand()%100 + 1; 
}
```

Wird eine Zufallszahl vom Datentyp `double` benötigt, so lässt sich folgende Formel anwenden: 

```c 
(double)rand()/RAND_MAX*(Obergrenze – Untergrenze) + Untergrenze
```

Im folgenden Beispiel wird eine Zufallszahl zwischen `[1.0, 5.0]` erzeugt:

```c 
#include <stdlib.h>
#include <time.h>

int main()
{
  double zz;
  srand(time(NULL));
  zz = (double)rand()/RAND_MAX*(5.0-1.0) + 1.0; 
}
```

