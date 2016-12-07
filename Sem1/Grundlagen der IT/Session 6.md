# Session 6

## Von-Neumann-Architektur
* Speicher aufgeteilt in einzelne Register
* Steuerbefehle werden in Registern abgelegt
* Verschiedene Bus-Systeme zur Kommunikation zwischen Speicher und CPU
  * Steuerbus
  * Adressbus
  * Datenbus

|RISC| |CISC|
|----|-|----|
|Einfache Instruktionen (1 Takt)|**Instruktionen**|Komplexe Instruktionen (Mehrere Taktzyklen)|
|Nur Lade- und Speicherbefehle greifen auf den Speicher zu|**Speicherzugriff**|Jede Instruktion kann auf den Speicher zugreifen|
|Intensives Pipelining|**Pipelining**|Kein oder wenig Pipelining|
|Festverdrahtete Hardware|**Ausführung von Instruktionen**|Mikroprogramme|
|Instruktionen mit fester Länge|**Format**|Variable Länge|
|Code weniger kompakt|**Codeform**|Kompakter Code| 
