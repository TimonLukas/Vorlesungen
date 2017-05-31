# Session 02

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Ein- und Ausgabe](#ein-und-ausgabe)
* [Interrupts](#interrupts)
  * [Konzepte](#konzepte)
  * [Ablauf](#ablauf)
* [Dateisysteme](#dateisysteme)
  * [Dateien](#dateien)
    * [Metadaten](#metadaten)
    * [Daten](#daten)

<!-- tocstop -->

## Ein- und Ausgabe
* Maschine zu Mensch
  * Tastatur
  * Maus
  * Spracheingabe
  * Scanner
  * Mikrofon
  * Kamera
  * Gamepad
  * Bildschirm
  * Lautsprecher
  * Braille-Zeilen
* Maschine zu Maschine
  * LAN (Ethernet)
  * WLAN
  * Bluetooth
  * NFC
* Maschine zu Speichermedium
  * Speichersticks/-karten
  * (Externe) Festplatten
  * Touchscreens
  * CD, DVD, Bluray

## Interrupts
* 3 Klassen:
  * Hardware-Interrupts
    * Taste gedrückt
    * Netzwerkpakete
    * Festplattenausgabe
  * Software-Interrupts
  * Fehler-Interrupts
    * Speicherzugriffsfehler
    * Busfehler

### Konzepte
* Maskierung
* Priorisierung
* Vektorisierung

### Ablauf
1. Interruptursache ermitteln
2. Entscheiden, ob Interrupt behandelt wird (siehe Interruptmaske/Prioritäten)
  * Nein: Programm läuft normal weiter
  * Ja: Dann 3.
3. PC (Program Counter) auf den **Stack** sichern
3.5 In privilegierten Modus umschalten
4. Interruptbehandlungsprogramm aufrufen (siehe Vektortabelle)
5. Register (nach Bedarf) auf Stapel sichern
6. Interrupt behandeln **(z. b. im Treiber)**
7. Register vom Stapel laden
7.5 Ggf. in nichtprivilegierten Modus umschalten
8. Program Counter mit Adresse vom Stack laden (= Sprung ins unterbrochene Programm)

## Dateisysteme
### Dateien
#### Metadaten
* Dateityp/-format
* Name
* Größe
* Erstellungs-/Änderungs-/Zugriffsdatum
* Benutzer
* Berechtigungen
#### Daten
* Inhalt
