# N1 Basic - Aufgabe 4


## Situation


Sie erhalten ein virtuelles Netzwerk als Filiusdatei. Auf den ersten Blick kommt ihnen die Aufgabe bekannt vor.
**Aber vorsicht.** Bei einer genaueren Betrachtung ist zu erkennen, dass hier einiges anders ist und auch vieles nicht stimmt.
Beim Re-Design haben sich mindestens **10 Fehler** eingeschlichen. ...Vielleicht sogar noch mehr.


**Netzwerkplan**
![Netzwerkplan](P1_4_Filius_800.png)


## Auftrag
-   Sie gehen strukturiert vor, um die **Fehler zu finden** und zu **korrigieren**.
-   Ihre ausgeführten Schritte für die **Fehlersuche** halten Sie in Ihrer **Dokumentation** fest.
-   Zusätzlich halten Sie die **gefundenen Fehler und deren Behebung** in der separaten Tabelle fest.
-   Nachdem Sie sämtliche Fehler gefunden haben, testen Sie Ihr Lösungsfile mit dem Coach/Lehrer (Live-Demo)


### Konzept
Das Konzept sieht wie folgt aus:


|            | Netz ID      | Subnet          | Erste IP*    | Letzte IP    | Broadcast    |
|------------|--------------|-----------------|--------------|--------------|--------------|
| **Netz 1** | 170.11.83.0  | 255.255.255.248 | 170.11.83.1  | 170.11.83.6  | 170.11.83.7  |
| **Netz 2** | 170.11.83.8  | 255.255.255.248 | 170.11.83.9  | 170.11.83.14 | 170.11.83.15 |
| **Netz 3** | 170.11.83.16 | 255.255.255.248 | 170.11.83.17 | 170.11.83.22 | 170.11.83.23 |
| **Netz 4** | 170.11.83.24 | 255.255.255.248 | 170.11.83.25 | 170.11.83.30 | 170.11.83.31 |
| **Netz 5** | 170.11.83.32 | 255.255.255.248 | 170.11.83.33 | 170.11.83.38 | 170.11.83.39 |
| **Netz 6** | 170.11.83.40 | 255.255.255.248 | 170.11.83.41 | 170.11.83.46 | 170.11.83.47 |
| **Netz 7** | 170.11.83.48 | 255.255.255.248 | 170.11.83.49 | 170.11.83.54 | 170.11.83.55 |
| **Netz 8** | 170.11.83.56 | 255.255.255.248 | 170.11.83.57 | 170.11.83.62 | 170.11.83.63 |


Ebenfalls ersichtlich ist das Konzept unter [folgendem Excel File.](P1_4_Netzwerk-Einteilung.xlsx)
*Router hat die erste IP


### Filius File
Das funktionierende Filius File finden Sie [hier.](P1_4_FEHLRER.fls)


**Gefundene Fehler (und Korrekturen) für die einzelnen Aufgaben**


| **Gerät** | **Gefundener Fehler, ausgeführte Korrektur**                                        |
|-----------|-------------------------------------------------------------------------------------|
| PC-3      | Gateway falsch: 170.11.82.1, geändert zu 170.11.83.1                                |
| PC-10     | Falsche IP 170.11.83.11, geändert zu 170.11.83.10                                   |
| PC-10     | Falsches Gateway: 170.11.83.8, geändert zu 170.11.83.9                              |
| PC-26     | Falsche Netzmaske: 255.252.255.248, geändert zu 255.255.255.248                     |
| PC-27     | Falsches Gateway: 107.11.83.25, geändert zu 170.11.83.25                            |
| PC-43     | Gateway fehlt, geändert zu 170.11.83.41                                             |
| PC-50     | Falsche IP-Adresse: 170.11.83.250, geändert zu 170.11.83.50                         |
| PC-51     | Falsche Netzmaske: 255.255.248.0, geändert zu 255.255.255.248                       |
| PC-59     | Falsches Gateway: 170.11.83.59, geändert zu 170.11.83.57                            |
| RT-1      | Falsche IP Interface Subnetz 4: 170.11.83.27, geändert zu 170.11.83.25              |
| RT-1      | Falsche Netzmaske Interface Subnetz 4: 255.255.252.248, geändert zu 255.255.255.248 |


**Fehlersuche Journal**


| **Ausgeführter Test** | **Beobachtetes Resultat/ (Ausgeführte Korrektur)**                                         |
|-----------------------|--------------------------------------------------------------------------------------------|
| Test 1                | Alle IPs überprüft, alle Fehler verbessert (Tabelle oben)                                  |
| Test 2                | Von PC02 alle anderen gepingt, Subnetz 2 funktionierte nicht sonst alles                   |
| Test 3                | Subnetz 2 nochmal genau angeschaut, Fehler wurde vorhin schon gefunden, aber nicht behoben |
Das funktionierende Filius File finden Sie [hier.](P1_4_FEHLRER.fls)
