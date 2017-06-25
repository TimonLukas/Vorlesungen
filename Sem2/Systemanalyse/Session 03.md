# Session 03

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Phasen des Entwicklungsprozesses](#phasen-des-entwicklungsprozesses)
  * [Analyse](#analyse)
    * [Lastenheft](#lastenheft)
    * [Probleme](#probleme)
    * [Erste Schritte](#erste-schritte)
    * [Systemidee](#systemidee)
      * [Bestandteile](#bestandteile)
      * [Beispiel](#beispiel)
    * [Interessenshalter (Stakeholder)](#interessenshalter-stakeholder)
      * [Beispiel: Interessen](#beispiel-interessen)
    * [Systemkontext](#systemkontext)

<!-- tocstop -->

## Phasen des Entwicklungsprozesses
### Analyse
#### Lastenheft
* Zielbestimmungen
  * Welche Ziele sollen durch den Einsatz der Software erreicht werden?
* Produkteinsatz
  * Welche Anwendungsfälle, -bereiche und Zielgruppen hat die Software?
* Produktfunktionen (Funktionale Anforderungen)
  * Was sind die Hauptfunktionen des Produktes aus Sicht des Auftraggebers?
* Produktdaten (Funktionale Anforderungen)
  * Was sind die (permanent gespeicherten) Hauptdaten des Produktes?
* Produktleistungen (Nicht-Funktionale Anforderungen)
  * Werden für bestimmte Funktionen besondere Ansprüche in Bezug auf Zeit, Datenumfang und Genauigkeit gestellt?
  * Wenn ja, welche?
* Qualitätsanforderungen (Nicht-Funktionale Anforderungen)
  * Aufzählung der wichtigsten Qualitätsanforderungen
    * Zuverlässigkeit
    * Robustheit
    * Benutzerfreundlichkeit
    * Effizienz
* Ergänzungen
  * Gibt es außergewöhnliche Anforderungen, die nicht durch obige Punkte abgedeckt werden?
  * Wenn ja, welche?

#### Probleme
* Abgrenzung
  * Was sind die Grenzen des Systems?
  * Was soll vom System unterstützt werden?
* Verständlichkeit
  * Interessenshalter erwähnen nicht das für sie offensichtliche
  * Interessenshalter kennen häufig nur einen Ausschnitt des Ganzen
* Änderungen
  * Anforderungen können sich über die Zeit ändern (durch neue Erfahrungen, Ideen)

#### Erste Schritte
* Systemidee entwickeln
  * Gemeinsame Beschreibung (Auftraggeber/-nehmer) der wesentlichen Eigenschaften eines Systems
* Interessenshalter identifizieren
  * Personen/Gruppen mit Erwartungen bzw. Anforderungen an das zu erstellende System  
* Systemkontext modellieren
  * Definition der Schnittstellen und Akteure des zu entwickelnden Systems

#### Systemidee
* Die erste Beschreibung der wesentlichen Eigenschaften eines Systems
* Kurze schriftliche Formulierung (max. halbe bis eine Seite)
* Entwicklung einer gemeinsamen Systemidee mit Auftraggeber/Auftragnehmer
  * Lösung von ersten Konflikten/Widersprüchen
* Wichtigste Voraussetzung für Projekterfolg!

##### Bestandteile
* Name des Produktes (Projektname)
* Kurzbeschreibung: Was soll mit dem System erreicht werden?
* Auflistung der wichtigsten Funktionalitäten/Leistungsmerkmale (5-15 Punkte)
* Auflistung der wichtigsten Voraussetzungen (5-15 Punkte)
* Abgrenzung welche Eigenschaften nicht oder erst später im Fokus sind (5-15 Punkte)

##### Beispiel
* Name: iFood
* Kurzbeschreibung: Eine Web-basierte Plattform über die lokale Erzeuger ihre Produkte (z. B. im Bereich Lebensmittel) direkt vertreiben
* Funktionen
  * Kunden können nach Erzeugern/Produkten (in bestimmten Gebieten) suchen und diese bestellen
  * Der Versand der Produkte ist über unterschiedliche Wege möglich (z. B. Kurier, Abholung, Sammelabholung)
  * Die Bezahlung ist auf unterschiedlichen Wegen möglich (PayPal, Direktbezahlung bei Abholung)
  * Eine Bewertung der Produkte, Kunden und Abholer ist möglich
  * Bestellungen sollen auch telefonisch möglich sein
* Voraussetzungen (Anwender und Anbieter)
  * Internetzugang
  * Web-Browser (Version?)
  * Registrierung bei PayPal
* Weitere geplante Module
  * Monatsabschluss (Anbieter)
  * CRM-Funktionen (Anbieter)

#### Interessenshalter (Stakeholder)
* Personen/Gruppen mit **Erwartungen** bzw. **Anforderungen** an das zu erstellende System
* Typische Gruppen
  * Auftraggeber/Geschäftspartner
  * Geldgeber
  * Anwender/Kunden
  * Gesetzgeber/Standards
  * Administratoren/Entwickler
  * Marketing/Vertrieb
  * Mögliche Projektgegner
* Interessenshalter sollten **priorisiert** und **klassifiziert** werden
  * Priorisierung
    * Risiko (1 = sehr klein, 6 = sehr groß), wenn Interessenshalter nicht berücksichtigt werden
    * Aufwand (1 = sehr groß, 6 = sehr klein), um Interessenshalter zu berücksichtigen
  * Klassifikation
    * Einteilung bzgl. der obigen Priorisierung in Muss-, Soll- und Kann-Interessenshalter
* Ansprechpartner
  * Für jede Stakeholder-Gruppe sollte ein **konkreter Ansprechpartner** definiert werden
  * Zuordnung von Rollen zu Ansprechpartner
    * Anwender
    * Fachlicher Experte
    * Technischer Experte
    * Entscheidungsverantwortlicher
    * ...
  * Ein Ansprechpartner kann **mehrere Rollen** besitzen
* Für jeden Stakeholder sollten die **Ziele** und **Interessen** ermittelt werden
  * Ziele und Interessen können durch **Interviews** oder **Fragebögen** ermittelt werden
  * Ziele und Interessen sind für **Definition der Anwendungsfälle** wichtig
  * **Probleme und Schwachstellen** aus Sicht der Interessenshalter sollten auch ermittelt werden

##### Beispiel: Interessen
* Direkterzeuger
  * Erweiterung des Kundenbereichs
  * Höhere Gewinnmargen, da kein Zwischenhändler
  * Direkten Kontakt zu Kunden halten (durch gezielte Werbekampagnen)
* Kunde
  * Qualitativ hochwertige Produkte zu niedrigen Preisen
  * Finden von "besonderen" Produkten
  * Problemlose Lieferung der Produkte statt Abholung
  * Einfache Bezahlmöglichkeiten

#### Systemkontext
* Definiert **Akteure** und **Schnittstellen**
* Mögliche Akteure
  * Benutzer
  * Fremdsysteme
* Benutzer interagieren über **Dialogschnittstellen** mit dem System
* Fremdsysteme interagieren über **Datenschnittstellen** mit dem System
* Systemkontext ist wichtig für die Definition der durch das System unterstützten Anwendungsfälle
