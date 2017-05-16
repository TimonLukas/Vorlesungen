# Grundbegriffe & Pseudocode

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Grundbegriffe der Programmierung](#grundbegriffe-der-programmierung)
- [Pseudocode](#pseudocode)

<!-- /TOC -->

## Grundbegriffe der Programmierung
* Ausdruck
  * Kombination von **Operanden** und **Operatoren** als "Vorschrift" zur Berechnung eines Wertes
  * Liefert immer einen Wert (Ergebniswert) ab
  * Beispiel: 1 / x
* Anweisung
  * Kombination von Ausdrücken und Methoden als "Vorschrift" zur Ausführung einer Aktion
  * Beispiele:
    * *x* = 5 Wertzuweisung
    * *y* = 1/x Wertzuweisung
    * *print(x)* Ausgabe
* Sequenz
  * bildet eine zeitliche Abfolge von Anweisungen
  * Einzelne Schritte werden durchnummeriert oder es wird zum Abschluss der Sequenz ein Semikolon gesetzt
* Bedingte Anweisungen
  * Es werden Bedingungen auf ihre Richtigkeit überprüft
  * Für wahre und falsche Aussagen in der Beidungen können unterschiedliche Anweisungen ausgeführt werden
* Schleifen
  * Bestimmte Anweisungen werden solange ausgeführt, bis etwas passiert
* Unterprogramme
  * Beinhaltet einen Teilalgorithmus
  * Dieser Teilalgorithmus kann in mehreren Algorithmen wieder verwendet werden
* Variablen
  * "Platzhalter" für einen konkreten Wert
  * Sind von einem bestimmten Datentyp
  * Können ihren Wert ändern
* Konstanten
  * Haben einen festen Wert
  * Sind von einem bestimmten Datentyp
  * Können ihren Wert **nicht** ändern
* Pseudocode
  * Programmieren ohne Programmiersprache
* Programmablaufpläne
  * Genormt nach DIN 66001
  * Ursprung in der linearen Programmierung
  * Nur für kleinere Programme geeignet (Übersichtlichkeit)
* Nassi-Schneiderman-Diagramme (Struktogramme)
  * Entstehung 1973
  * Darstellung genormt nach DIN 66261 im Jahr 1985
  * Überwiegender Einsatz in der prozeduralen Programmierung

## Pseudocode
  * Sequenz
    * Alternative 1: Schritte werden durchnummeriert: 1, 2, 3, ...
    * Alternative 2: Abschluss der Sequenz durch Semikolon
    * Vorteil Alternative 1: Verfeinerung einzelner Schritte: 2.1, 2.2, ...
  * Bedingte Anweisungen
    * Es werden Bedingungen auf ihre Richtigkeit geprüft
    * Alternative 1: **falls** Bedingung **dann** Schritt
    * Alternative 2: **falls** Bedingung **dann** Schritt A **sonst** Schritt B
  * Schleifen
    * Kopfgesteuert
    * Fußgesteuert
    * Zählschleife
  * Beispiel: GGT
    ```
    1. Falls Fahne geklickt
    2. Gib erste Zahl ein
    3. Weise Variable X den eingegebenen Wert zu
    4. Gib zweite Zahl ein
    5. Weise Variable y den eingegebenen Wert zu
    6. Wiederhole bis x = y
    6.1 Falls x > y dann
    6.1.1 Setze x auf Ergebnis von x - y
    6.1.2 Warte eine Sekunde
    6.2 Falls y > y dann
    6.2.1 Setze y auf Ergebnis von y - x
    6.2.2 Warte eine Sekunde
    7. Gib den größten gemeinsamen Teiler x aus
    ```
  * Übung: Beschreiben Sie einen Algorithmus zur Berechnung der Fakultät! Nutzen Sie dazu den Pseudocode.
    ```
    1. Gib Zahl ein
    2. Weise Variable x den eingebenen Wert zu
    3. Falls Zahl < 0
    3.1 Werfe Fehler
    3.2 Ende
    4. Falls Zahl = 0
    4.1 Gib 1 aus
    4.2 Ende
    5. Weise Variable y den Wert 1 zu
    6. Wiederhole bis x = 0
    6.1 Setze y auf Ergebnis von y * x
    6.2 Setze x auf Ergebnis von x - 1
    7. Gib y aus
    8. Ende
    ```
  * Übung: Beschreiben Sie im Pseudocode einen Algorithmus zur Bestimmung der Fibonacci-Folge
    ```
    1. Falls Fahne geklickt
    2. Gib Länge ein
    3. Weise Variable i den eingegebenen Wert zu
    4. Setze zahl1 auf 0
    5. Setze zahl2 auf 1
    6. Wiederhole bis i = 0
    6.1 Gebe zahl2 aus
    6.2 Setze Variable temp auf Wert zahl2
    6.3 Setze zahl2 auf zahl1 + zahl2
    6.4 Setze zahl1 auf temp
    ```

## Java
* Vollständig objektorientiert
* Unkompliziert - einfach und leicht erlernbar
  * Syntax aus der C-Familie
  * Beschränkung auf das notwendigste
    * Keine Pointer
    * Keine Header-Dateien
    * Kein Präprozessor
    * Keine Mehrfachvererbung
* Plattformunabhängig
  * Programme werden in Bytecode übersetzt
  * Auf jeder javafähigen Plattform ausführbar
  * Fest definierter Wertebereich für Zahlen
* Sicher
  * Keine direkten Speicherzugriffe
  * Strenge Typenprüfungen
  * Keine Programmierung mit Sprachverletzung
* Robust
  * Keine Rechnerabstürze durch Programmfehler
  * Überprüfung der Speicherzugriffe
  * Ausnahmeroutinen zur Fehlerbehandlung
* Multithreaded
  * Parallele Ausführung von Programmteilen

## Compiler
* Übersetzt Programm aus Quellcode in semantisch äquivalenten Maschinencode
* Zwei Phase
  * Analysephase
    * Lexikalische Analyse (Tokenizing)
    * Syntaktische Analyse (Formale Richtigkeit)
    * Semantische Analyse (Logische Rahmenbedingungen)
  * Synthesephase
    * Zwischencodeerzeugung für Optimierungen
    * Programmoptimierung
    * Codegenerierung
* Verschiedene Arten von Compilern
  * Native Compiler
  * Cross-Compiler
  * One-Pass-Compiler
  * Multi-Pass-Compiler
