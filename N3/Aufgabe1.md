# N3 Expert - Auftrag 1


## Aufgabenstellung 3.1

## Situation

Sie erhalten mehrere virtuelle Netzwerke als Filiusdateien. In den Netzwerken ist jeweils ein Fehler vorhanden.  
Das Netzwerklayout ist für alle Aufgaben identisch:

![Netzwerkplan](netzwerk_800.png)

## Auftrag

-   Sie gehen strukturiert vor um die **Fehler zu finden** und zu
    **korrigieren**.
-   Ihre ausgeführten Schritte für die **Fehlersuche** halten Sie in Ihrer **Dokumentation** fest.
-   Zusätzlich halten Sie die **gefundenen Fehler und deren Behebung** in der separaten Tabelle fest.
- Nachdem Sie sämtliche Fehler gefunden haben, testen Sie Ihr Lösungsfile mit dem Coach/Lehrer (Live-Demo)


## Fehler zum Auftrag 

**Fehlerbeschrieb für die einzelnen Aufgaben**

| **Filename**          | **Fehlerbeschrieb** |
|-----------------------|-----------------------------------------------------------|
| Netzwerk-Fehler-1.fls | Das Pingen zwischen PC_NW1_4 und PC_NW3_2 kommunizieren   |
| Netzwerk-Fehler-2.fls | PC_NW1_4 kann nicht mit anderen Geräten Pingen            |
| Netzwerk-Fehler-3.fls | PC_NW1_1 kann nicht mit anderen Geräten Pingen            |
| Netzwerk-Fehler-4.fls | Ping in Netzwerk 3 nicht möglich                          |
| Netzwerk-Fehler-5.fls | Ping von PC_NW1_1 nicht möglich ausserhalb von Netzwerk 1 |


**Gefundene Fehler (und Korrekturen) für die einzelnen Aufgaben**

| **Filename**          | **Gefundener Fehler, ausgeführte Korrektur**    |
|-----------------------|-------------------------------------------------------------------------------------------------------|
| Netzwerk-Fehler-1.fls | Subnetzmaske von PC_NW1_4 ist 255.255.255.0 anstatt 255.255.255.192                                   |
| Netzwerk-Fehler-2.fls | Gateway von PC_NW1_4 ist 192.168.1.2 anstatt 192.168.1.1                                              |
| Netzwerk-Fehler-3.fls | IP-Adresse von PC_NW1_1 ist 169.254.1.1 anstatt 192.168.1.11                                          |
| Netzwerk-Fehler-4.fls | Router_NW2 hat falsche Route in das Netzwerk 3 (Subnetzmaske 255.255.255.252 anstatt 255.255.255.192) |
| Netzwerk-Fehler-5.fls | Router_NW2 mit Switch_NW1_2 verbunden anstatt Router_NW1                                              |


## Gelöste Files für das Troubleshooting

1. [Netzwerk-Fehler-1]()
2. [Netzwerk-Fehler-2]()
3. [Netzwerk-Fehler-3]()
4. [Netzwerk-Fehler-4]()
5. [Netzwerk-Fehler-5]()

### Quellen
- Fragen an Gabriel Marki
