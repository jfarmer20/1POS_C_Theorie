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
  - [1.1. Wichtige Begriffe](#11-wichtige-begriffe)
  - [1.2. Geschichte von C](#12-geschichte-von-c)
- [2. Installation](#2-installation)
  - [2.1. Installationsanleitung für **Visual Studio Code (VS Code)** auf **Windows 10** und **Windows Subsystem for Linux (WSL)**](#21-installationsanleitung-für-visual-studio-code-vs-code-auf-windows-10-und-windows-subsystem-for-linux-wsl)
  - [2.2. Erstes Programm mit Visual Studio Code (VS Code)](#22-erstes-programm-mit-visual-studio-code-vs-code)
  - [2.3. `helloworld.c` kompilieren](#23-helloworldc-kompilieren)
  - [2.4. `helloworld.c` starten/debuggen](#24-helloworldc-startendebuggen)
    - [2.4.1. Wichtige Tastenkombinationen](#241-wichtige-tastenkombinationen)
    - [2.4.2. Zugriff Dateisystem Windows <-> WSL](#242-zugriff-dateisystem-windows---wsl)
  - [2.5. Einführungsbeispiel](#25-einführungsbeispiel)

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

## 2.1. Installationsanleitung für **Visual Studio Code (VS Code)** auf **Windows 10** und **Windows Subsystem for Linux (WSL)**  

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

und mit der Tastenkombination Strg+Shift+b kompilieren. 

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

### 2.4.2. Zugriff Dateisystem Windows <-> WSL

Linux Shell: Zugriff aufs Benutzerverzeichnis in Windows:  
`/mnt/c/Users/<USERNAME>`

Windows-File-Explorer: Zugriffs aufs WSL home-Verzeichnis:  
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
