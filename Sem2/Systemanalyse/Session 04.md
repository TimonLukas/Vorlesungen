# Session 04


## Anforderungsanalyse
* Erstellt aus den Ideen, Wünschen, Bedürfnissen des Kunden das Anforderungsdokument "**Lastenheft**"
* Vorgehen sollte **strukturiert** und **wiederholbar** sein
* Vorgehen sollte jeder direkt oder mit kurzer Schulung anwenden können
* Jeder Arbeitsschritt sollte das Wissen eine Erkenntnisstufe weiterbringen
* Jedes Ergebnis (Artefakt) sollte
  * Einzigartig in seiner Erkenntnisstufe sein
  * Die Artefakte der vorherigen Stufen nicht duplizieren
* Formulierte Erkenntnisse sollten immer konkreter werden

## Freies Kundeninterview
* Nur eine Art der Analyse
* Mit dem Kunden über sein Projekt sprechen
* Möglichst Agenda formulieren & Themen im Auge behalten
* Aktives Zuhören
  * Bei Unklarheiten nachfragen
  * Aussagen mit eigenen Worten wiederholen (umschreiben)
* Eigene Ideen und Gedanken anbieten
* Durch gezielte Fragen den Kunden (Stakeholder) dazu bringen, alle Anforderungen anzusprechen
* Alle Anforderungen in einem Dokument zusammentragen

### Tipps
* Fragen, Grafiken, Modelle vorbereiten
  * Auch wenn sie falsch sind
  * Korrigieren ist einfacher als Erstellen
  * Auf Bestehendem Aufbauen setzt bereits viele Rahmenbedingungen
* Oft nach dem "Warum" fragen
  * Five-Why-Methode (Ursache >> Wirkung)
  * Aber: nicht übertreiben
* Konkrete Beispiele geben lassen
  * Formeln
  * Regeln
  * Zahlen- oder textbasierte Daten
* Die Beispiele live durchspielen und notieren
  * Gute Grundlage für automatisierte Tests
  * Beispiel:
    * Kunde: "Das Kleiner-Als-Zeichen soll Werte herausfiltern, die größer oder gleich groß sind"
    * Entwickler: "< 42 lässt also nur Werte bis 41 durch?"
    * Kunde: "Ja, genau!"
* Ein dedizierter Anforderungsanalyst
* Fachkundiger Stenografierer
* Rohe Notizen unmittelbar an den Kunden herausgeben

### Nach dem Interview
* Mitschrift "ins Reine schreiben"
* Zeit mit den Anforderungen verbringen
* Ein Bild sollte sich formen
  * Wenn nicht: Noch ein Interview!
* Anforderungsanalyse ist erst beendet, wenn die Anforderungen klar sind
  * Sie werden trotzdem nicht vollständig korrekt sein
* Anforderungsdokument enthält die Essenz aus den Interviews

## Anforderungsdokument
* Muss Folgen haben
* Direkt ableitbare Artefakte

## Kriterien für Anforderungen
* **AN-10**: Vollständig
  * Alle Anforderungen explizit beschrieben
  * Keine impliziten Annahmen
  * Offen für spätere Ergänzungen
* **AN-20**: Eindeutig definiert/abgegrenzt
  * Präsize Definitionen
  * Missverständliche und unscharfe Begriffe vermeiden
  * Gute Heuristik: Kann ich einen automatisierten Test dafür schreiben?
* **AN-30**: Verständlich beschrieben
  * Anforderungen lesbar und verstehbar (mit vertretbarem Aufwand)
  * Gilt für Entwickler und Kunden
* **AN-40**: Atomar
  * Nur eine Anforderung pro Satz oder Abschnitt
  * Atomizität = Entscheidbarkeit der Anforderung
    * Ja-Nein-Antwort auf die Frage "Anforderung erfüllt?"
  * Erfordert Trennen verschiedener Themen
    * Ähnlich der Seperation of Concerns im Source-Code
* **AN-50**: Identifizierbar
  * Jede Anforderung eindeutig Identifizierbar
  * Beispielsweise Anforderungs-ID
  * Eventuell durch Issue-Nummer vermittelbar
* **AN-60**: Einheitlich dokumentiert
  * Anforderungen alle im gleichen Dokument
  * Durchgängige Struktur
* **AN-70**: Nachprüfbar
  * Verknüpft mit prüfbaren Abnahmekriterien
  * Mit Quellenangabe (woher kam die Anforderung?)
  * Abnahme = Kunde akzeptiert die Software
  * Abnahmekriterien als Akzeptanztest automatisieren
  * Während der Entwicklung ständig prüfen
* **AN-80**: Nachvollziehbarkeit
  * **AN-81**: Vorwärtsverfolgbar
    * Nachverfolgbar, ob Anforderungen vollständig erfüllt
    * Anforderungen &rarr; Funktionalität (Code)
  * **AN-82**: Rückverfolgbar
    * Funktionalität (Code) &rarr; Anforderungen
    * Erkennbar, aufgrund welcher Anforderungen erstellt
    * Anforderungs-ID im Code und in den Tests
    * Sehr wichtig für Wartungsphase (nach Abnahme)
* **AN-90**: Konsistent
  * Untereinander widerspruchsfrei
  * Insbesondere bei mehreren Stakeholdern
  * Explitize und implizite Widersprüche

### Entstehendes Artefakt
* Liste mit Anforderungen
  * + Einzeln identifizierbar
  * - Ungeordnet
  * - Unzusammenhängend
* Zielsetzung
  * Sammlung aller Anforderungen
  * Erster Überblick über die Domäne
  * Aussagen über die erwartete Projektgröße

## Strukturierung der Anforderungen
* Beziehungen zwischen Anforderungen
  * **S-10**: Abhängigkeiten
    * Nur wenige Anforderungen sind vollständig unabhängig
    * Zu prüfen ist:
      * Gibt es Voraussetzungen für die Anforderung?
        * Erstellt eine topologische Sortierung
      * Bedingen sich Anforderungen gegenseitig?
        * Zirkuläre Abhängigkeiten
        * Nicht einzeln umsetzbar
  * **S-20**: Zusammengehörigkeit
    * Manche Anforderungen liegen semantisch nahe beieinander
      * Fachlich-logischer Zusammenhang
    * Sollten im Verbund umgesetzt werden
    * Bleiben aber eigenständig und können auch eigenständig umgesetzt werden
  * **S-30**: Rollenbezogenheit
    * Jede Benutzerrolle hat ihre eigene Sicht auf die Anforderungen
    * Typische Benutzerrollen
      * Administrator
      * Benutzer
      * Gast
    * Anforderungen nach Rollenzugehörigkeit gruppieren
    * Ziel: Benutzerspezifische Teilsysteme erstellen können
      * Beispiel: iFood
      * Produktsuche für Besteller muss vorhanden sein
      * Spezielles Klassifikationssystem für Lieferanten kann (eventuell) warten
* Typ der Anforderungen
  * **S-40**: Funktionale vs. Nicht-Funktionale Anforderungen
    * Funktionale Anforderungen
      * Definieren das Verhalten des Systems (Was soll das System machen?)
      * Eingabe &rarr; Verhalten &rarr; Ausgabe
    * Nicht-funktionale Anforderungen
      * Definieren die Eigenschaften des Systems (Wie soll das System sein?)
      * Qualitätsmerkmale
        * Leistungscharakteristik (z. B. Skalierbarkeit/Benutzer)
        * Ressourcenbedarf während des Betriebs (z. B. Speicherverbrauch)
* Motivation der Anforderung
  * **S-50**: Fachlich vs. Technisch motivierte Anforderungen
    * Fachliche Anforderungen = "Aus der Domäne stammend"
    * Technische Anforderungen = Durch den aktuellen Stand der Technik bedingt
    * Domäne und Technik ändern sich mit jeweils eigenem Tempo
    * **Ziel**: Anforderungen aus Domäne unabhängig von technischer Umsetzung realisieren

### Entstehendes Artefakt
* Topologisch sortierter Abhängigkeitsgraph
* Gruppen- bzw. Regionsbildung (Sub-Graphen)
* Zielsetzung
  * Unmögliche Konstellationen ausschließen
  * "Nebenwirkungen" aufzeigen
  * Identifikation von Subsystemen bzw. Modulen
    * Bei serviceorientierter Struktur (SOA) vor allem Services
  * Erwartete Nachweismittel festlegen

## Bewertung der Anforderungen
* Jede Anforderung sollte fünf Qualitätsmerkmale aufweisen
* **Q-10**: Korrekt
  * Untereinander widerspruchsfrei
  * Vom Kunden bestätigt
* **Q-20**: Machbar
  * Unter Berücksichtigung der anderen Anforderungen umsetzbar
  * Mit dem aktuellen Stand der Technik realisierbar
* **Q-30**: Notwendig
  * Vom Kunden explizit gefordert
  * Kein "Nice-to-Have"-Feature
* **Q-40**: Priorisiert
  * Einschätzung der Wichtigkeit der Anforderungen
    * Erwartete Business-Value
    * Eventuell auch nur Häufigkeit der Verwendung
  * Vom Kunden vorgenommen
  * Ziel: "Business Value First"-Ansatz
* **Q-50**: Nutzbringend
  * Produktives System auch bei nur teilweiser Umsetzung
  * Durch Abhängigkeitsanalyse müssen eventuell weniger hochpriore Anforderungen trotzdem früh umgesetzt werden
  * Ziel: Inkrementell-iterative Systemerstellung
    * Einsatzbereites System am Ende jeder Iteration
    * Pro Iteration neue Funktionalität mit zusätzlichem Nutzen

### Entstehendes Artefakt
* Topologisch sortierter Abhängigkeitsraph
* Priorisierung der Einsteigsknoten
* **Zielsetzung**
  * Maximaler Business Value in minimaler Zeit
  * Dauerhafte Einsatzbereitschaft
  * Teilweise Umsetzung möglich

## Grundlegende Artefakt-Regeln
* Jedes Anforderungsartefakt muss konkreter sein als die Vorgänger
  * Analysearbeit bewegt das Projekt in Richtung Code
* Anforderungen müssen referenzierbar sein
  * Nachvollziehbarkeit als Gegenmittel zu "Chaos"
* Jede Anforderung muss konkrete und nachvollziehbare Artefakte im Projekt produzieren
  * Automatisierte Tests
  * Manuelle Überprüfungen
  * Source Code

## Qualität des Anforderungsdokumentes
* Leser-Einschätzung ist wichtig und richtig
  * Anforderungsdokumente werden für den Leser geschrieben
  * Wenn es nicht verständlich ist, ist es nicht gut
* Anforderungsdokumente zu schreiben ist sehr schwierig (und aufwendig)
  * Viel Geduld und Mithilfe notwendig
  * "Den Kunden entwickeln"
* Wichtig: Bewusster Perspektivwechsel
  * Entwickler denken aus einer anderen Richtung
