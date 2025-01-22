# N3 Expert - Auftrag 3

## Aufgabenstellung 3.3

## Situation

Drei Subnetze im /24er Bereich werden mit zwei Routern getrennt. Leider funktioniert es nicht so wie es sollte.

Das Netzwerklayout sieht wie folgt aus

![Netzwerkplan](netzwerkplan_800.png)

## Auftrag

-   Sie gehen strukturiert vor, um die **Fehler zu finden** und zu
    **korrigieren**.
-   Ihre ausgeführten Schritte für die **Fehlersuche** halten Sie in Ihrer **Dokumentation** fest.
-   Zusätzlich halten Sie die **gefundenen Fehler und deren Behebung** in der separaten Tabelle fest.
- Nachdem Sie alles korrekt konfiguriert und erfolgreich getestet haben, zegen Sie Ihre finale Version dem Coach/Lehrer (Live-Demo).


## Genutzes Filius File

Für diese Aufgabe wurde folgendes [Filius File](01_bigmess.fls) genutzt.

### Gefundene Fehler

**Gefundene Fehler (und Korrekturen)**

| **Device**          | **Gefundener Fehler, ausgeführte Korrektur**                                                                                    |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Laptop 192.168.0.10 | Falsche Subnetmask und kein Gateway, 255.255.255.0 anstatt 255.0.0.0 und 192.168.0.1 als GW                                     |
| Laptop 192.168.0.20 | Falsche Subnetmask und kein Gateway, 255.255.255.0 anstatt 255.255.0.0 und 192.168.0.1 als GW                                   |
| Laptop 192.168.1.10 | GW fehlt, 192.168.1.1 als GW hinzugefügt                                                                                        |
| Laptop 192.168.2.10 | GW fehlt & Subnetmaske falsch, 192.168.2.1 als GW hinzugefügt und Subnetmaske 255.255.255.0 anstatt 255.255.0.0                 |
| Laptop 192.168.2.10 | GW fehlt & Subnetmaske falsch, 192.168.2.1 als GW hinzugefügt und Subnetmaske 255.255.255.0 anstatt 255.0.0.0                   |
| Router 1            | Beide Interfaces haben falsche Subnetmask und keine IP, 255.255.255.0 anstatt 255.0.0.0 und 192.168.0.1/192.168.1.1 als IP      |
| Router 1            | Route zu 192.168.2.0/24 Netz fehlt, Route hinzugefügt                                                                           |
| Router 2            | Beide Interfaces fehlen und Subnetmaske falsch, 192.168.1.254/192.168.2.1 hinzugefügt und 255.255.0.0 zu 255.255.255.0 geändert |
| Router 2            | Route zu 192.168.1.0/24 Netz fehlt, Route hinzugefügt                                                                           |


Das gelöste File finden Sie [hier.](01_bigmess-gelöst.fls)

## Quellen

- Keine
