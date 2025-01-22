# N3 Expert - Auftrag 2

## Aufgabenstellung 3.2

## Situation

Sie erhalten mehrere virtuelle Netzwerke als Filiusdateien. In den Netzwerken sind jeweils Fehler vorhanden.
Das Netzwerklayout ist für alle Aufgaben identisch:

![Netzwerkplan](https://github.com/erionreci-5/M129/blob/main/Bilder/netzwerk_800%20(1).png)

## Auftrag

-   Sie gehen strukturiert vor um die **Fehler zu finden** und zu
    **korrigieren**.
-   Ihre ausgeführten Schritte für die **Fehlersuche** halten Sie in Ihrer **Dokumentation** fest.
-   Zusätzlich halten Sie die **gefundenen Fehler und deren Behebung** in der separaten Tabelle fest.
- Nachdem Sie sämtliche Fehler gefunden haben, testen Sie Ihr Lösungsfile mit dem Coach/Lehrer (Live-Demo)


## Fehler

**Fehlerbeschrieb für die einzelnen Aufgaben**

| **Filename**          | **Fehlerbeschrieb**                                                          |
|-----------------------|------------------------------------------------------------------------------|
| Netzwerk-Fehler-1.fls | Geräte aus Netz 4 können nicht mit Geräten aus anderen Netzen kommunizieren  |
| Netzwerk-Fehler-1.fls | Geräte aus Netz 4 kommen nicht in das WAN                                    |
| Netzwerk-Fehler-2.fls | Geräte aus Netz 1 & 2 können  nicht mit Netzen 3 & 4 kommunizieren           |
| Netzwerk-Fehler-2.fls | Netz 3 kann mit keinen anderen Geräten kommunizieren                         |
| Netzwerk-Fehler-3.fls | Netz 1 & 2 können mit niemandem kommunizieren                                |
| Netzwerk-Fehler-3.fls | Nur Netz 4 bekommt Antwort auf Ping im WAN                                   |
| Netzwerk-Fehler-4.fls | Keine Kommunikation von oder in Netzen 1 und 2 möglich                       |


**Gefundene Fehler (und Korrekturen) für die einzelnen Aufgaben**

| **Filename**          | **Gefundener Fehler, ausgeführte Korrektur**                                                                                                |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| Netzwerk-Fehler-1.fls | Gateway fehlt bei beiden Geräten, Gateway 192.168.4.1 hinzugefügt                                                                           |
| Netzwerk-Fehler-1.fls | Keine Route für 192.168.4.1 bei RT-1, Route für 192.168.4.1 hinzugefügt                                                                     |
| Netzwerk-Fehler-2.fls | RT-2 hat Kabel von RT-1 und RT-3 vertauscht, Kabel wieder vertauscht                                                                        |
| Netzwerk-Fehler-2.fls | Switch von Netz 3 ist an falscher Schnittstelle angeschlossen, Switch umgesteckt                                                            |
| Netzwerk-Fehler-3.fls | Allgemeine IP von RT-3 ist falsch, Anstelle von 192.168.2.1 sollte die IP 10.1.0.2 sein                                                     |
| Netzwerk-Fehler-3.fls | Im RT-1 in der Route für Netze 1, 2 & 3 ist ein falsches "Nächstes Gateway (Weiterungstabelle)", anstelle 10.2.1.1 sollte die IP 10.2.0.1   |
| Netzwerk-Fehler-3.fls | Im RT-1 in der Route für Netze 1, 2 & 3 ist ein falsches "Über Schnittstelle (Weiterungstabelle)", anstelle 10.2.9.2 sollte die IP 10.2.0.2 |
| Netzwerk-Fehler-4.fls | RT-3 ist ein Switch und kein Router, Router mit richtigen Interfaces eingebaut, Wartungstabelle angepasst                                   |


## Gelöste Files für das Troubleshooting

1. [Netzwerk-Fehler-1](https://github.com/erionreci-5/M129/blob/main/Bilder/netzwerk-fehler-1%20(1).fls)
2. [Netzwerk-Fehler-2](https://github.com/erionreci-5/M129/blob/main/Bilder/netzwerk-fehler-2%20(1).fls)
3. [Netzwerk-Fehler-3](https://github.com/erionreci-5/M129/blob/main/Bilder/netzwerk-fehler-3%20(1).fls)
4. [Netzwerk-Fehler-4](https://github.com/erionreci-5/M129/blob/main/Bilder/netzwerk-fehler-4%20(1).fls)

## Quellen

- Chat GBT
