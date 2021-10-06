<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/jfarmer20/1POS_C_Theorie/blob/main/1POS_C_SKRIPTUM_FA.md">Unterrichtsskriptum "Programmieren und Software Engineering", Erster Jahrgang der Abteilung Informatik, HTBLA-Kaindorf an der Sulm, Austria, Europe</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/jfarmer20">Johannes Farmer </a> is licensed under <a href="http://creativecommons.org/licenses/by-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"></a></p>

# Allgemeines <!-- omit in toc -->

Dieses Skriptum umfasst den Unterrichtsstoff für POS (Programmieren und Software Engineering) des ersten Jahrgangs der Abteilung Informatik an der Höheren Technischen Bundeslehranstalt Kaindorf, Österreich. 

Als Erweiterung dieses Skriptums steht das frei verfügbare Lehrbuch zur Programmiersprache C des Rheinwerk Verlags zur Verfügung:  
[Wolf, Jürgen: C von A bis Z](https://openbook.rheinwerk-verlag.de/c_von_a_bis_z/)

Werden die Grundlagen beherrscht, können die Programmierfähigkeiten auf folgenden Seiten perfektioniert werden: 

[Project Euler](https://projecteuler.net/)  
[CodinGame](https://www.codingame.com/start)  

# Inhaltsverzeichnis <!-- omit in toc -->

- [1. Einführung](#1-einführung)
  - [1.1. Begriffe](#11-begriffe)
  - [1.2. Geschichtliches der Programmiersprache C](#12-geschichtliches-der-programmiersprache-c)
- [2. Installation der Programmierumgebung auf Windows 10](#2-installation-der-programmierumgebung-auf-windows-10)
  - [2.1. Installationsanleitung für *Visual Studio Code (VS Code)* auf *Windows 10* mit *Windows Subsystem for Linux (WSL)*](#21-installationsanleitung-für-visual-studio-code-vs-code-auf-windows-10-mit-windows-subsystem-for-linux-wsl)
  - [2.2. Erstes Programm mit Visual Studio Code (VS Code)](#22-erstes-programm-mit-visual-studio-code-vs-code)
  - [2.3. `helloworld.c` kompilieren](#23-helloworldc-kompilieren)
  - [2.4. `helloworld.c` starten/debuggen](#24-helloworldc-startendebuggen)
    - [2.4.1. Wichtige Tastenkombinationen](#241-wichtige-tastenkombinationen)
    - [2.4.2. Zugriff Dateisystem Windows <-> WSL](#242-zugriff-dateisystem-windows---wsl)
  - [2.5. Einführungsbeispiel](#25-einführungsbeispiel)
- [3. Mein erstes Programm mit Eingabe, Zuweisung und Ausgabe](#3-mein-erstes-programm-mit-eingabe-zuweisung-und-ausgabe)
  - [3.1. `printf()`-Befehl: Steuerzeichen und Sonderzeichen](#31-printf-befehl-steuerzeichen-und-sonderzeichen)
  - [3.2. Struktogramm](#32-struktogramm)
- [4. Operatoren – 1. Teil](#4-operatoren--1-teil)
  - [4.1. Zuweisungsoperator](#41-zuweisungsoperator)
    - [4.1.1. Variablentausch mit Hilfsvariable](#411-variablentausch-mit-hilfsvariable)
    - [4.1.2. Variablentausch ohne Hilfsvariable](#412-variablentausch-ohne-hilfsvariable)
  - [4.2. Arithmetische Operatoren](#42-arithmetische-operatoren)
    - [4.2.1. Vorzeichenoperatoren](#421-vorzeichenoperatoren)
    - [4.2.2. Binäre arithmetische  Operatoren](#422-binäre-arithmetische--operatoren)
- [5. Datentypen](#5-datentypen)
- [6. `printf()`-Befehl: Formatierte Ausgabe](#6-printf-befehl-formatierte-ausgabe)
- [7. Zufallszahlen](#7-zufallszahlen)
- [8. Mathematische Funktionen – `<math.h>`](#8-mathematische-funktionen--mathh)
- [9. Kommentare](#9-kommentare)
- [10. Character- und Stringliterale](#10-character--und-stringliterale)
  - [10.1. Characterliterale](#101-characterliterale)
  - [10.2. Stringliterale](#102-stringliterale)
- [11. Operatoren – 2. Teil](#11-operatoren--2-teil)
  - [11.1. Arithmetische  Zuweisungsoperatoren](#111-arithmetische--zuweisungsoperatoren)
  - [11.2. Inkrement- und Dekrementoperatoren `++` und `--`](#112-inkrement--und-dekrementoperatoren--und---)
  - [11.3. Vergleichsoperatoren](#113-vergleichsoperatoren)
  - [11.4. Logische Operatoren](#114-logische-operatoren)
  - [11.5. Die Operatorenrangfolge](#115-die-operatorenrangfolge)

# 1. Einführung

## 1.1. Begriffe 

Ein **Programm** ist eine Abfolge von Befehlen/Anweisungen in einer bestimmten Programmiersprache. 

Ein **Compiler** übersetzt ein Programm, geschrieben in einer  Programmiersprache (z.B. C, Java, Python) in Maschinensprache (`01100010001`…). 

Ein **Debugger** dient zur Fehlersuche in Programmen. Damit lassen sich Programme Schritt für Schritt ausführen und Variableninhalte anzeigen.  

Eine **Entwicklungsumgebung** oder **IDE** (*Integrated Development Environment*) wie z.B. Visual Studio Code oder IntelliJ unterstützt Programmierer beim 
* Schreiben, 
* Debuggen,  
* Compilieren und 
* Ausführen 

von Programmen.  

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
* Zeichen und Zeichenketten (String)

bereit.  

## 1.2. Geschichtliches der Programmiersprache C 
C ist eine imperative und prozedurale Programmiersprache. C wurde 1972 „erfunden“ und seit damals in Varianten weiterentwickelt. Das *American National Standards Institute* (ANSI) vereinheitlichte die C-Varianten und veröffentlichte 1989 ein standardisiertes C. Dieser C-Standard wird im Sprachgebrauch als C89 bzw. ANSI-C bezeichnet. Dieser C-Standard wurde auch von der *International Organization for Standardization* (ISO) übernommen und im Sprachgebrauch mit C90 bezeichnet. 

[ANSI-C Reference Card](http://users.ece.utexas.edu/~adnan/c-refcard.pdf)  

Im Jahr 1999 erschien C99 mit Elementen der objekt-orientierten Programmiersprache C++. 

# 2. Installation der Programmierumgebung auf Windows 10 

## 2.1. Installationsanleitung für *Visual Studio Code (VS Code)* auf *Windows 10* mit *Windows Subsystem for Linux (WSL)*  

1. Windows auf die neueste Version aktualisieren: 

    `Start` > `Einstellungen` > `Update und Sicherheit`

    ![Screenshot_Setup1.PNG](./pictures/Screenshot_Setup1.PNG "Screenshot Windows 10 Update")  

2. Windows Subsystem für Linux installieren: 

    `Windows Suche` > `cmd` > `Als Administrator ausführen`

    ![Screenshot_Setup2.PNG](./pictures/Screenshot_Setup2.PNG "Screenshot Windows 10 Command Line Interface CLI") 

    `wsl --install` ausführen 

   ![Screenshot_Setup3.PNG](./pictures/Screenshot_Setup3.PNG "Screenshot Windows Subsystem for Linux Installation") 


    Nach fertiger Installation muss der Rechner neu gestartet werden. 
    Ubuntu Linux installiert sich danach automatisch.  

    ![Screenshot_Setup4.PNG](./pictures/Screenshot_Setup4.PNG "Screenshot Ubuntu Linux Installation") 


3. Linux-User anlegen: 

    Einfachen Username und leicht zu merkendes Passwort wählen: 

    ![Screenshot_Setup5.PNG](./pictures/Screenshot_Setup5.PNG "Screenshot Linux User Configuration") 


4. Visual Studio Code (Windows 10) downloaden und installieren:  

    [Visual Studio Code Download Page](https://code.visualstudio.com/Download)  

5. Erweiterungen für VS Code (`Remote Development`, `C/C++ IntelliSense`) installieren: 

    Die genaue Anleitung, ergänzt mit den nachfolgenden Screenshots, findet sich hier: 

    https://code.visualstudio.com/docs/cpp/config-wsl#_set-up-your-linux-environment

    ![Screenshot_Setup6a.PNG](./pictures/Screenshot_Setup6a.PNG) 

    ![Screenshot_Setup7a.PNG](./pictures/Screenshot_Setup7a.PNG) 

    ![Screenshot_Setup8.PNG](./pictures/Screenshot_Setup8.PNG) 

    ![Screenshot_Setup9a.PNG](./pictures/Screenshot_Setup9a.PNG)  

## 2.2. Erstes Programm mit Visual Studio Code (VS Code)

Ubuntu starten und in der Shell Projektverzeichnis erstellen und VS Code starten: 

```
mkdir projects
cd projects
mkdir helloworld
cd helloworld
code .
```

Quelldatei “helloworld.c” erstellen: 

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 1](./pictures/Screenshot_New_File.PNG "Screenshot Visual Studio Code Command Erstes Programm - Schritt 1")

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

## 2.3. `helloworld.c` kompilieren 
Um VS Code zu sagen, wie die Quelldatei `helloworld.c` nun zu kompilieren ist, braucht es eine `tasks.json` Datei: 	

Menü `Terminal` > `Configure Default Build Task…` > `C/C++:gcc build active file` auswählen. 

Quelldatei `helloworld.c` auswählen  

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 2](./pictures/Screenshot_VSC_2.PNG "Screenshot Visual Studio Code Command Erstes Programm - Schritt 2")

und mit der Tastenkombination `Strg` + `Shift` + `B` kompilieren. 

## 2.4. `helloworld.c` starten/debuggen 

Um `helloworld.c` starten oder debuggen zu können, braucht VS Code die Datei `launch.json`: 

Menü `Run` > `Add Configuration…` > `C++ (GDB/LLDB)` und `gcc.exe – Build and debug active file` auswählen. 

Das Programm wird anschließend gleich ausgeführt, was man mit der Tastenkombination Shift+F5 stoppen kann. 

Quelldatei helloworld.c auswählen 

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 3](./pictures/Screenshot_VSC_3.PNG "Screenshot Visual Studio Code Command Erstes Programm - Schritt 3") 

und mit der Tastenkombination Strg+F5 starten. 

Will man das Programm debuggen, an geeigneter Stelle einen Breakpoint setzen und das Programm mit der Taste F5 starten: 

![Screenshot Visual Studio Code Command Erstes Programm - Schritt 4](./pictures/Screenshot_VSC_4.PNG "Screenshot Visual Studio Code Command Erstes Programm - Schritt 4") 

### 2.4.1. Wichtige Tastenkombinationen 

- Strg + Shift + B: Programm kompilieren 
- Strg + F5 / F5: Programm starten / debuggen  
- Strg + Ö: Terminal anzeigen  

- Quellcode formatieren: Shift + Alt + F 
- Kommentar toggle/untoggle: Strg + #
- Speichern / Speichern als: Strg + S / Strg + Shift + S
- Drucken: F1 > 'PrintCode'
- Schrift größer/kleiner: Strg + '+'/'-'
- Light-/Dark-Modus umschalten: Strg+K + Str+T
- Alles Auswählen: Strg + A
- In Zwischenablage kopieren: Strg + C
- Aus Zwischenablage einfügen: Strg + V  

### 2.4.2. Zugriff Dateisystem Windows <-> WSL

Linux Shell: Zugriff aufs Benutzerverzeichnis in Windows:  
`/mnt/c/Users/<USERNAME>`

Windows-File-Explorer: Zugriff aufs WSL home-Verzeichnis:  
`\\wsl$\Ubuntu\home\<USERNAME>`

## 2.5. Einführungsbeispiel 

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

Im folgenden Listing werden  

* Die Variable a und b vom Datentyp `int` (Integer … Ganzzahl) eingelesen. 
* Aus den beiden Summanden `a` und `b` die Summe `s` gebildet. 
* Die Rechnung formatiert ausgegeben.  

```c
#include <stdio.h>

int main()
{
    int a = 0;
    int b = 0;
    int s = 0;
    printf("Bitte Summanden 1 eingeben: ");
    scanf("%d", &a);
    printf("Bitte Summanden 2 eingeben: ");
    scanf("%d", &b);
    s = a + b; 
    printf("-------------------------------\n");
    printf("Die Summe von %d und %d ergibt %d\n\n", a, b, s); 
    return 0;
}
```

Erklärungen: 

* Beim `scanf()`-Befehl, dient `%d` als Platzhalter, um den vom Anwender eingegebenen Wert einzulesen und der Variable `a` bzw. `b` zuzuweisen. 
* `%d` ist ein Platzhalter für eine Ganzzahl (d … decimal) 
* Die Platzhalter für die Ausgabe der Variablen `a`, `b` und `s` mit dem `printf()`-Befehl sind gleich wie beim `scanf()`-Befehl. 
* Das `&`-Zeichen im scanf()-Befehl wird zu einem späteren Zeitpunkt erklärt. 

## 3.1. `printf()`-Befehl: Steuerzeichen und Sonderzeichen 

Sogenannte Escape-Sequenzen ermöglichen Steuerzeichen und Sonderzeichen auszugeben. Eine Escape-Sequenz wird durch einen Backslash `\` (Tastenkombination `alt gr` und `ß`) eingeleitet, dem ein weiteres Zeichen folgt. Eine Escape-Sequenz gilt trotzdem als einzelnes Zeichen.
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

![Nassi-Shneiderman-Diagramm nur mit Sequenzsymbolen](./pictures/NSD_01.PNG "Nassi-Shneiderman-Diagramm nur mit Sequenzsymbolen") 

**Aufgabe**: Lese eine Ganzzahl ein, erhöhe diese um eins und gib die Zahl aus. 

Struktogramm: 

![Nassi-Shneiderman-Diagramm Beispiel 1](./pictures/NSD_02.PNG "Nassi-Shneiderman-Diagramm Beispiel 1") 

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

### 4.1.2. Variablentausch ohne Hilfsvariable 

Mathematikfüchse kommen ohne Hilfsvariable aus: 

```c 
int a, b; 
...
a=a+b;
b=a-b;
a=a-b;
```

## 4.2. Arithmetische Operatoren 

### 4.2.1. Vorzeichenoperatoren

Zur Darstellung der mathematischen Vorzeichen 'plus' und 'minus' werden die unären Vorzeichenoperatoren `+` und `–` verwendet.

```c
int z1, z2;
z1 = +5;
z2 = -9;
```
### 4.2.2. Binäre arithmetische  Operatoren

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
  
Sind die Operanden von unterschiedlichen Datentypen, so ist das Ergebnis vom größeren der beiden Datentypen.
* Der Modulooperator ist nur für ganzzahlige Operanden zulässig. Das Ergebnis ist der ganzzahlige Rest der Division: `17 % 5 = 2`.
Bei den Divisionsoperatoren (`/` und `%`) führt eine Divison durch `0` zu einem Laufzeitfehler.  

# 5. Datentypen

In C gibt es eine Menge Datentypen, wobei die fett markierten für unseren weiteren Unterricht ausreichend sein werden. Die Größe und Wertebereiche der Datentypen sind nicht normiert. Bei den meisten Systemen gelten aber folgende Werte: 

| Name | Datentyp | Bytes |	Minimalwert | Maximalwert | Formatzeichen |  
| --- | --- | :---: | --- | --- | --- |  
| **`char`** | Ein Zeichen | 1 | -128 (![2^{31}-1](./pictures/CodeCogsEqn-7.gif)) | 127 (![2^{31}-1](./pictures/CodeCogsEqn_7-1.gif)) | `%c`  
| **`char[]`** | Eine Zeichenkette (String) | - | - | - | `%s` |  
| **`int`** | Ganze Zahl | 4 | (![-2^{31}](./pictures/CodeCogsEqn-31.gif)) | (![2^{31}-1](./pictures/CodeCogsEqn_31-1.gif)) | `%d`  
| `float` |	Fließkommazahl, 6-stellige Genauigkeit | 4 | 1.2E-38 | 3.4E+38 | `%f` 
| **`double`** | Fließkommazahl, 15-stellige Genauigkeit | 8 | 2.3E-308 | 1.7E+308 | `%lf`
| `short`| Ganze Zahl | 2 | –32.768 | +32.767 | `%d`  
| `long`|  Ganze Zahl | 4 | (![-2^{31}](./pictures/CodeCogsEqn-31.gif)) | (![2^{31}-1](./pictures/CodeCogsEqn_31-1.gif)) | `%ld` 


In C existiert kein logischer Datentyp (Datentyp `boolean`). Stattdessen werden Variablen vom Datentyp `int` für Bedingungen verwendet werden, wobei folgende Regeln gelten:

Variablenwert gleich 0 -> `FALSE`  
Variablenwert ungleich 0 -> `TRUE`

Alle Variablen müssen vor ihrer Verwendung **deklariert** werden. Die Deklaration legt den Namen und den Typ fest. Deklarationen müssen immer am Anfang eines Programms stehen. 

Für ganzzahlige Datentypen als auch `char` können die Prefixe `signed` und `unsigned` verwendet werden. Insbesondere bei Bitoperationen ist das letztere Prefix von Bedeutung.  
Abhängig vom Betriebssystem (16-, 32- oder 64-bit) belegen die einzelnen Datentypen unterschiedlich viel Speicher. Wieviel Speicher sie nun tatsächlich verwenden lässt sich mit dem `sizeof(`*type name*`)`-Operator feststellen.  

# 6. `printf()`-Befehl: Formatierte Ausgabe 

Die formatierte Ausgabe auf der Konsole erfolgt mit dem `printf()`-Befehl, der in der Headerdatei `<stdio.h>` definiert ist: 

```c
int printf("Formatstring" [ , argument1, argument2 ...]); 
```

Der erste Parameter dient zur Übergabe eines Formatstrings. Die weiteren Parameter sind optional (eckige Klammern bedeuten optional) und sind die Argumente für den Formatstring. Die Formatierung erfolgt entsprechend den Angaben im Formatstring. Der Rückgabewert des `printf()`-Befehls ist die Anzahl der ausgegebenen Zeichen.

Der Formatstring enthält sowohl normalen Text als auch Platzhalter mit den jeweiligen Formatangaben. Die Syntax für einen Platzhalter sieht wie folgt aus:

``` 
%[flag][width][.precision]conversion
```

Der wichtigste und einzige nicht optionale Teil ist dabei das Umwandlungszeichen (conversion), das den Datentyp für die Umwandlung bestimmt:

| `conversion` | Datentyp | Bedeutung |
| --- | --- | --- | 
| `d`, `i` | int | Integer |
| `f` | float | Gleitkommazahl float - Default von 6 Kommastellen |
| `lf` | double	| Gleitkommazahl double - Default von 6 Kommastellen |
| `%` | | Ausgabe des % Zeichens |


Die Flags sind optional und werden unmittelbar nach dem `%`-Zeichen angegeben:


| `flag` | Bedeutung | 
| --- | --- |
| `-` |	Ausgabe linksbündig |
| `+` |	Ausgabe mit Vorzeichen |
| `0` |	Leerstellen werden mit Nullen gefüllt |

Die Anzahl der auszugebenden Zeichen ist optional und wird durch die Breite (`width`) festgelegt. 

Die Anzahl der Nachkommastellen ist optional und wird durch die Genauigkeit (`precision`) festgelegt. 

Beispiele von Formatangaben für ganzzahlige Werte (Datentyp `int`): 

```
%d 		Ausgabe der Zahl ohne zusätzliche Vorgabe 
%5d 	rechtsbündige Ausgabe der Zahl auf 5 Stellen 
%-5d 	linksbündige Ausgabe der Zahl auf 5 Stellen 
%05d 	Ausgabe der Zahl auf 5 Stellen mit führenden Nullen 
%+5d 	rechtsbündige Ausgabe der Zahl auf 5 Stellen mit Vorzeichen 
%+-5d   linksbündige Ausgabe der Zahl auf 5 Stellen mit Vorzeichen 
```

Beispiele von Formatangaben für Fließkommazahlen (Datentyp `float`):

```
%f 		    Ausgabe der Zahl ohne zusätzliche Vorgabe 
%10f 		rechtsbündige Ausgabe der Zahl auf 10 Stellen
%.2f 		rechtsbündige Ausgabe der Zahl mit 2 Nachkommastellen 
%-10.2f 	linksbündige Ausgabe auf 10 Stellen, davon 2 Nachkommastellen 
%010.2f 	Ausgabe der Zahl auf 10 Stellen mit führenden Nullen, davon 2       
            Nachkommastellen
%+10.2f 	rechtsbündige Ausgabe der Zahl auf 10 Stellen und Vorzeichen,  
            davon 2 Nachkommastellen  
%+-.2f 	    linksbündige Ausgabe der Zahl mit Vorzeichen und 2 Nachkommastellen
```  

# 7. Zufallszahlen 

Zum Erzeugen von ganzzahligen Zufallszahlen stehen in der C Standard Library `<stdlib.h>` folgende Funktionen zu Verfügung:

```c 
srand(<seed>)       // Anweisung zum Erzeugen eines Zufallszahlen-Seeds
srand(time(NULL))   // Erzeugen eines Zufallszahlen-Seeds,  
                    // initialisiert mit der aktuellen Systemzeit   
rand()              // Erzeugen einer ganzzahligen Zufallszahl
```

Für die Funktion `time()` muss zusätzlich die Header-Datei `<time.h>` inkludiert werden. Die Funktion `srand()` definiert den Startwert (Seed) zum Erzeugen der Zufallszahlen. Durch die Übergabe der Funktion `time()` an `srand()` wird sichergestellt, dass bei jedem Programmstart neue Zufallszahlen erzeugt werden. 
Die Funktion `rand()` gibt eine Zufallszahl im Bereich von `[0,RAND_MAX]` zurück. Durch Verwendung des Modulo-Operators (`%`) kann der Wertebereich eingeschränkt werden. 

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

# 8. Mathematische Funktionen – `<math.h>`

In der Headerdatei `<math.h>` sind folgende nützliche mathematische Funktionen und Konstanten deklariert: 

```
double pow(double x, double y)	// x hoch y
double sqrt(double x)	        // Wurzel aus x
double fabs(double z)           // Absolutwert von x
double sin(double x)	        // Sinus von x
double cos(double x)	        // Cosinus von x
double tan(double x)	        // Tangens von x
double exp(double x)	        // Exponentialfunktion e hoch x
double log(double x)	        // Natuerlicher Logarithmus von x

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

# 9. Kommentare 

Regeln für Kommentare:

* Mehrzeilige Kommentare werden mit `/*` eingeleitet und mit `*/` abgeschlossen.
* Einzeilige Kommentare beginnen mit `//` und erstrecken sich bis zum Ende der Zeile.
* Kommentare können an beliebiger Stelle stehen.

# 10. Character- und Stringliterale 

## 10.1. Characterliterale

Die Zuweisung erfolgt durch genau ein Zeichen, das in einfachen Anführungszeichen eingeschlossen wird. Auf der char-Variablen wird der entsprechende ASCII-Wert des Zeichens gespeichert. 

[ASCII-Tabelle](http://www.asciichars.com/)

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

## 10.2. Stringliterale

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
char str2[] = "Hallo";
char str3[100] = "Hallo"; 
char str4[] = {'H', 'a', 'l', 'l', 'o', '\0'};
char str5[] = {72, 97, 108, 108, 111, 0};
char str6[20] = "Teil 1\
Teil2"; // Der Zeilenumbruch ist auf dem String nicht sichtbar

str1 = "ungueltige Zuweisung";  // Compilerfehler!
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
strLaenge = strlen(str); // Laenge ist 6 ("Hallo" + '\0')
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

# 11. Operatoren – 2. Teil 

## 11.1. Arithmetische  Zuweisungsoperatoren

| Operator | Beispiel |	Bedeutung |
|:----:|:----:|:----:|
| += | a += 2; | a = a+2; | 
| -= | a -= 2; | a = a-2;
| *= | a *= 2; | a = a*2;
| /= | a /= 2; | a = a/2;
| %= | a %= 2; | a = a%2;

Achtung: Die Zuweisung:  
`z1 *= z2 +1;`  
entspricht der Anweisung:  
`z1 = z1 * (z2 +1);`           
und nicht:  
`z1 = z1*z2 +1;`  

Die verkürzte Schreibweise mit den arithmetischen Zuweisungsoperatoren ist dann sinnvoll, wenn dadurch komplexe Ausdrücke leichter lesbar werden:

`feld[2*i+j-4] = feld[2*i+j-4] + 2;` // normale Schreibweise  
`feld[2*i+j-4] += 2;`                // verkürzte Schreibweise  

## 11.2. Inkrement- und Dekrementoperatoren `++` und `--`  

Diese beiden unären Operatoren werden verwendet um das Ergebnis des Operanden um 1 zu erhöhen oder um 1 zu vermindern. Sie sind für alle Datentypen zulässig.
Sie können in Präfix- (vor dem Operanden) oder Postfixnotation (nach dem Operanden) verwendet werden.  

Präfixnotation: Der Wert des Operanden ändert sich **vor** seiner weiteren Verwendung.  
`++x`  
`--x`  

Postfixnotation: Der Wert des Operanden ändert sich **nach** seiner weiteren Verwendung.  
`x++`  
`x--`  

Die folgende Tabelle zeigt die unterschiedliche Bedeutung der Operatoren:

| a vorher | Ausdruck | a nachher | b nachher |  
|:----:|:----:|:----:|:----:|
| 10 | b = a++; | 11 | 10 |  
| 10 | b = ++a; | 11 | 11 |  
| 10 | b = a--; | 9 | 10 |  
| 10 | b = --a; | 9 | 9 |  

Die Inkrement- und Dekrementoperatoren können für einzelne Variablen, nicht aber für Zahlen oder Ausdrücke verwendet werden.

Beispiel:
```c  
    int i = 2, j, k = 3;
    j = i++ + k; // = i++ + k
    printf("%d %d %d\n", i, j, k);
    j = i++ + k--; // = i++ + k--
    printf("%d %d %d\n", i, j, k);
    j = i++ + ++k;
    printf("%d %d %d\n", i, j, k);
    j = i++ + ++i;
    printf("%d %d\n", i, j);
    j = (i + k)++; // Compilerfehler!!

    float z = 3.1;
    z++;
    printf("%f\n", z);
```  

Ausgabe:
```  
3 5 3
4 6 2
5 7 3
7 12
4.100000
```

## 11.3. Vergleichsoperatoren  

In C gibt es 6 Operatoren zum Vergleichen von numerischen Datentypen. Das Ergebnis eines Vergleichs ist immer vom Typ `int`, wobei 0 dem Wert falsch und 1 dem Wert wahr entspricht.

| Operator | Bedeutung |  
|:----:|:----:|  
| == | gleich |  
| != | ungleich |  
| < | kleiner |  
| <= | kleiner gleich |  
| > | größer |  
| >= | größer gleich |  

Beispiel:  

```c  
int a = 2, b = 3;
printf("%d == %d ist %d\n", a, b, a == b);
printf("%d != %d ist %d\n", a, b, a != b);
printf("%d == %d ist %d\n", ++a, b, a == b); // Achtung: Call by Value!
```  

Ausgabe:  

```
2 == 3 ist 0
2 != 3 ist 1
3 == 3 ist 0
```

## 11.4. Logische Operatoren  

Logische Operatoren verknüpfen Wahrheitswerte. Da in C die Wahrheitswerte durch ganzzahlige Werte beschrieben werden, können logische Operatoren für alle Datentypen verwendet werden.  

| Operator | Bedeutung |  
|:----|:----|  
| ! | logisches nicht - dreht den Wahrheitswert um |  
| && | logisches und - wahr wenn beide Operanden wahr sind |  
| \|\| | logisches oder - wahr wenn zumindest einer der beiden Operanden wahr ist |  

Die folgende Wertetabelle zeigt alle möglichen Kombinationen der Wahrheitswerte:  

| a | b | !a | a && b | a \|\| b |  
|:----:|:----:|:----:|:----:|:----:|  
| 0 | 0 | 1 | 0 | 0 |  
| 0 | 1 | 1 | 0 | 1 |  
| 1 | 0 | 0 | 0 | 1 |  
| 1 | 1 | 0 | 1 | 1 |  

Die logischen Operatoren `&&` und `||` arbeiten mit der sog. short-circuit-evaluation, d.h. der rechte Operand wird nur dann ausgewertet, wenn das zur Bestimmung eines Ergebnisses notwendig ist.  
Bei  `a && b` wird daher b nur ausgewertet, wenn a=1 ist.  
Bei  `a || b` dagegen wird b nur ausgewertet wenn a=0 ist. 

Der `&&` Operator hat Vorrang vor dem `||` Operator.  
Der Ausdruck  
`a || b && c`  
ist gleichbedeutet mit  
`a || (b && c)`  

Durch die short-circuit-evaluation kann es zu unerwünschten Nebeneffekten kommen, wenn im rechten Teil eines logischen Ausdrucks Variablenänderungen stehen, die durch die verkürzte Auswertung nicht ausgeführt werden.

Beispiel:

```c  
if (a < b && d++) { ... }	// Bedingung mit Nebeneffekt
if (d++ && a < b) { ... }	// Bedingung ohne Nebeneffekt
``` 

Bei der ersten if-Anweisung wird d nur dann erhöht wenn `a < b` wahr ist. Bei der zweiten if-Anweisung wird d in jedem Fall erhöht.  

## 11.5. Die Operatorenrangfolge

Die Rangfolge der Operatoren ist von oben nach unten angeordnet. Operatoren innerhalb derselben Zeilen sind gleichwertig und werden von links nach rechts abgearbeitet.
Durch Verwendung von runden Klammern kann der Vorrag der Operatoren geändert werden.

| Operator-Typ | Operator |  
|:----|:----|  
| unär Postfix | () [] ++ -- |  
| unär Präfix | ++ -- (cast) sizeof |  
| binär Arithmetisch | * / % |  
| binär Arithmetisch | + - |  
| Vergleich | < <= > >= |  
| Vergleich | == != |  
| logisch und | && |  
| logisch oder | \|\| |  
| Zuweisung | += -= *= /= %=  |  
| Komma | , |  
