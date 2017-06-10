# Session 02

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Software-Entwicklungsprozesse (Vorgehensmodelle)](#software-entwicklungsprozesse-vorgehensmodelle)
  * [Inhalte](#inhalte)
  * [Vorteile](#vorteile)
  * [Klassifikation](#klassifikation)
    * [Sequentiell](#sequentiell)
    * [Iterativ](#iterativ)
    * [Agil](#agil)
* [Modelle](#modelle)
  * ["Code and Fix"](#code-and-fix)
  * [Wasserfallmodell](#wasserfallmodell)
    * [Probleme](#probleme)
  * [Iteratives Wasserfallmodell](#iteratives-wasserfallmodell)
  * [Spiralmodell](#spiralmodell)
  * [V-Modell](#v-modell)
  * [Unified Process/Rational Unified Process](#unified-processrational-unified-process)
  * [Agile](#agile)
    * [Manifesto](#manifesto)
    * [Werte](#werte)
    * [Prinzipien](#prinzipien)
  * [Extreme Programming](#extreme-programming)
  * [Scrum](#scrum)
    * [Prozess](#prozess)
    * [Sprint](#sprint)
    * [Meetings](#meetings)
    * [Estimation Meeting](#estimation-meeting)
    * [Retrospektive](#retrospektive)
    * [3-4-3-Regel](#3-4-3-regel)
* [Auswahl des richtigen Modells](#auswahl-des-richtigen-modells)

<!-- tocstop -->

## Software-Entwicklungsprozesse (Vorgehensmodelle)
* Software-Entwicklungsprozesse sind Vorgehensmodelle (Prozessmodelle) und dienen der Steuerung der Software-Entwicklung

### Inhalte
* Durchzuführende Aktivitäten
* Reihenfolge des Arbeitsablaufes
* Definition von Teilprodukten/Ergebnissen
* Fertigstellungskriterien
* Verantwortlichkeiten (Rollen) und Kompetenzen
* Notwendige Mitarbeiterqualifikationen
* Anzuwendende Standards, Richtlinien, Methoden und Werkzeuge

### Vorteile
* Planbarkeit von Softwareprojekten durch definierte, strukturierte und standardisierte Vorgehensweise
* Bessere Kontrolle von Zeit, Budget und Qualität der Ergebnisse
* Optimierung des Entwicklungsprozesses
* Verbesserung der Kommunikation innerhalb des Projekts und nach außen
* Automatisierungsmöglichkeiten durch Werkzeuge (CASE = Computer Aided Software Engineering)

### Klassifikation
#### Sequentiell
* Einzelne Phasen (Analyse, Spezifikation, Entwurf, ...) folgen nacheinander
* Ende liefert fertiges Produkt

#### Iterativ
* Einzelne Phasen können mehrfach wiederholt werden
* Iterationen liefern Zwischenergebnisse/Prototypen

#### Agil
* Aktivitäten der Phasen werden bei Bedarf ausgeführt
* Ablauf nur "grob" vorgegeben

## Modelle
### "Code and Fix"
* Vor der Softwarekrise
* Entwickeln, betreiben, testen, Fehler beheben gleichzeitig
* 1950 - heute
* Kein Vorgehensmodell (da ad-hoc)
* Coden, fixen und testen werden ad-hoc durchgeführt
* Keine Trennung der Zuständigkeiten
  * Keine echte Teamarbeit
* Projekte sind nicht planbar
  * Keine Möglichkeit mit Komplexität umzugehen
* Resultat: Softwarekrise

### Wasserfallmodell
* 1968 - heute
* Original: Sequentielles Wasserfallmodell mit mehreren Phasen von Planung bis Betrieb
* Eine Phase **muss** abgeschlossen sein, bevor die nächste beginnen kann
* Jeder Schritt liefert ein oder mehrere Ergebnisse


|Abschnitt                    |Ergebnisse                     |
|-----------------------------|-------------------------------|
|Analyse                      |Lastenheft (Auftraggeber)      |
|Spezifikation                |Pflichtenheft (Auftragnehmer)  |
|Entwurf                      |Architektur, Modulentwurf      |
|Entwicklung                  |Coden und Modultests           |
|Validierung und Verifikation |Integrations- und Systemtest   |
|Betrieb und Wartung          |Abnahmetest und Modifikationen |

#### Probleme
* In der Praxis überlagern sich die einzelnen Phasen
* Rücksprünge sind notwendig
* Es gibt Übergangsprobleme, wenn Rücksprünge nicht (zeitnah) möglich sind
* Modell ist daher in der Praxis **kaum anwendbar**
* Fehler in frühen Phasen (z. B. Anforderungsanalyse) sind sehr teuer und später schwer zu beheben

### Iteratives Wasserfallmodell
* Eine Iteration legt nicht alle Details fest
* In jeder Iteration können bewusst neue Details dazukommen
  * Diese können die Ergebnisse vorheriger Iterationen verfeinern (oder auch invalidieren)

### Spiralmodell
* Einzelne Phasen (Anforderungsanalyse, Entwurf, ...) werden als "Windung" einer Spirale sequentiell nacheinander ausgeführt
* Hauptmerkmal: Explizite Risikoanalyse am Ende jeder Phase
* Jede "Windung" ist in vier Segmente eingeteilt
  * Ziele festlegen: Identifikation von Alternativen und Beschreibungen von Rahmenbedingungen
  * Evaluierung der Alternativen und Risikoanalyse: Erkennen, Abschätzen von Risiken, z. B. durch Prototypen
  * Realisierung: Umsetzung und Überprüfung des Zwischenprodukts
  * Planung der nächsten Iteration
* Ist wie Wasserfallmodell zunächst ein sequentielles Vorgehensmodell
* Kann aber auch als iteratives Modell ausgeführt werden

### V-Modell
|Stufe        |Übergang       |Test             |
|-------------|---------------|-----------------|
|Analyse      |Anwendungsfälle|Abnahmetest      |
|Spezifikation|Tests          |Systemtest       |
|Entwurf      |Tests          |Integrationstest |
|Entwicklung  |Tests          |Unit-Test        |

* Vom Bundesministerium für Verteidigung entwickelt und dort seit 1992 verbindlich vorgeschrieben
* Erweiterung des Wasserfallmodells durch Integration einer expliziten Qualitätssicherung
* Verifikation und Validierung der Teilprodukte sind Bestandteile des V-Modells
  * Verifikation: "Wird ein korrektes Produkt entwickelt?"
  * Validierung: "Wird das richtige Produkt entwickelt?"
* Verschiedene Varianten
  * V-Modell 97
  * V-Modell XT
* V-Modell kann in mehreren Iterationen angewendet werden (Iteratives Modell)
* In jeder Iteration entsteht eine verfeinerte Version des endgültigen Produktes
* V-Modell XT unterstützt durch "Tailoring" auch agile Vorgehensweisen

### Unified Process/Rational Unified Process
* 1999 - heute
* Komplexes Vorgehensmodell aus 4 Abschnitten mit unterschiedlichem Fokus pro Abschnitt
  * Inception: Anwendungsfälle
  * Ellaboration: Architektur, Designmodell und Testszenarien
  * Construction: Entwicklung und Test
  * Transition: Abnahme und Betrieb
* Varianten: Rational Unified Process (mit entsprechender Werkzeugunterstützung der Firma Rational/IBM)
* In jedem Abschnitt sind mehrere Iterationen möglich, um die Ergebnisse des Abschnittes zu verfeinern
* Jeder Abschnitt hat einen Anteil verschiedener Aktivitäten (Analyse, Spezifikation, Entwurf, Programmierung, Test)

### Agile
#### Manifesto
* Individuals and interactions over processes and tools
* Working software over comprehensive documentation
* Customer collaboration over contract negotiation
* Responding to change over following a plan

#### Werte
* Kommunikation
* Einfachheit
* Feedback
* Mut zur Wahrheit/Respekt

#### Prinzipien
* Keine starre Rollentrennung, vorhandene Ressourcen mehrfach verwenden
* KISS-Prinzip
* Zweckmäßigkeit der Anwendung beachten
* Kundennähe

### Extreme Programming
* 1999 - heute
* Agiler Entwicklungsprozess
* Schnelle Iterationen der folgenden Schritte
  * Analyse: Anforderungen werden in Form von User-Stories erfasst
  * Entwurf: CRC-Karten und Prototypen
  * Umsetzung
    * Unit-Test für jede User-Story
    * Implementierung in Zweier-Teams
  * Test: Ausführung der Unit-Tests und Analyse fehlender Funktionen


* Beispiel: Parkkartensystem an der Hochschule
  * "As a student I want to purchase a parking pass so that I can drive to school by car"
  * One pass for one month issued at a time
  * Student will not receive pass if payment isn't sufficient
  * Person buying the pass must be a currently enrolled student
  * Student may only buy one pass per month


* CRC-Karten
  * CRC = Class Responsibility-Collaboration
  * Vorderseite
    * Name der Klasse
    * Superklasse
    * Verantwortung der Klasse
    * Beziehungen zu den anderen Klassen
  * Rückseite
    * Verzeichnis über die Methoden (Name, Parameter)
    * Verzeichnis über die Attribute

### Scrum
* Vertreter des agilen Vorgehensmodells

#### Prozess
* Produkt-Backlog
* Sprint-Backlog
* Sprint
* Lauffähige, inkrementell verbesserte Software


* Scrum definiert den Entwicklungsprozess als eine Serie von Sprints (1 - 4 Wochen)
  * Lose Sammlung von Aktivitäten
  * Aktivitäten kombinieren bekannte Werkzeuge und Techniken
* Produkt-Backlog: Sammlung aller bisheriger Anforderungen
* Sprint-Backlog: Anforderungen während eines Sprints

#### Sprint
* Kleine Teams (< 10 Personen)
* Sichtbare und verwendbare Ergebnisse
* Regelmäßige kurze Meetings ("Daily Scrum") während eines Sprints (täglich)
* Fokussierung: Keine ungewollte Ablenkung
* Neue Ziele können durch das Team festgelegt werden  

#### Meetings
* Kurz (15 bis 30 Minuten)
* Regelmäßig
* Geleitet durch den Scrum-Master
* Alle! Teammitglieder sind dabei (auch Externe)
* 3 Fragen werden gestellt
  * Was hast du seit dem letzten Meeting erledigt?
  * Was hat dich dabei gestört?
  * Was wirst du bis zum nächsten Meeting erledigen?

#### Estimation Meeting
* Mindestens 1 mal pro Sprint
* Geleitet durch den Scrum Master
* Legt den Aufwand "Storypoints" pro Backlog-Item fest
* Velocity des Teams = Storypoints / Sprint

#### Retrospektive
* Letztes Meeting im Sprint
* Geleitet durch den Scrum-Master
* *Hens and Pigs* anwesend (Commited & Involved)

#### 3-4-3-Regel
* Drei wesentliche Rollen
  * Product Owner
    * Verantwortlich für die Business-Value des Projekts
  * Scrum Master
    * Kümmert sich um das Team
  * Team
    * Organisiert sich selbst, um die Arbeit zu erledigen
* Vier Meetings
  * Sprint planning
    * Team + Product Owner treffen sich
    * Vereinbaren, was in dem Sprint erledigt werden muss
  * Daily scrum
    * Team trifft sich jeden Tag
    * Tauschen Probleme und Fortschritte aus
  * Sprint reviews
    * Team zeigt Product Owner Ergebnisse
  * Sprint retrospectives
    * Team überlegt neue Wege Produkt und Prozesse zu verbessern
* Drei Artefakte
  * Product backlog
    * Liste der Ideen für das Produkt
  * Sprint backlog
    * Punkte, die im Sprint erledigt werden sollen
    * Team bestimmt diese
    * In einzelne Aufgaben unterteilt
  * Product increment
    * Benötigtes Ergebnis jedes Sprints
    * Version des Produkts, deren Qualität gut genug ist, um ausgeliefert zu werden

## Auswahl des richtigen Modells
* Schulung der Mitarbeiter auf das Model
* Aufgaben und Rollen müssen den Mitarbeitern bekannt sein
* Vorgehensmodell ist selbst Teil eines kontinuierlichen Verbesserungsprozesses
* Modell muss zu Aufgabe, Umfeld und Mitarbeitern passen
* **Modell ist nicht Selbstzweck!**
