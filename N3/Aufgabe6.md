# N3 Expert - Auftrag 6
## Aufgabenstellung 3.6

**Theorie und Praxis kombiniert**

Zuerst erstellen Sie das Netzwerk-Design. Danach setzen Sie die Umgebung mit CISCO Packet Tracer um (Vorlage weiter unten)


## Ausgangslage
Die weltweit tätige Firma **Global Tech AG** hat ihren **Hauptsitz** in Zürich (Management und Verwaltung) und betreibt zwei Tochtergesellschaften. Eine mit Sitz in Boston (USA) und eine weitere in Paris (EMEA).

| Produkt:   | HQ       | USA     | EMEA    | 
|:-----------|:--------:|:-------:|:-------:|
| PCs        | 25       | 290     | 120     |
| Laptops    | 50       | 510     | 200     | 
| Drucker    | 5        | 20      | 10      | 
| **Total**  | **80**   | **820** | **330** | 


Die Firma hat ihre IT-Infrastruktur bereits erfolgreich in die Cloud migriert und nutzt die globale Infrastruktur des Providers. Die **Lokationen haben getrennte Netze**. Der Hauptsitz ist über einen **DSL-Router mit dem Internet** verbunden.

Für die Netzwerke steht das **Netz 135.233.176.0 /21**
zur Verfügung. Die Adressen zum  ISP sind ebenfalls darin enthalten und sollen von Ihnen bestimmt werden. Achten Sie hier darauf, dass sie dafür die **letzten zwei verfügbaren IP-Adressen des obigen Ranges** nutzen.


**Situations- und Netzwerkplan**

![Netzwerkplan](P3_6_netzwerk_1000.jpg)

## 1. Teilauftrag (Theorie)

Erstellen Sie für die Firma **Global Tech AG** zuerst einen klaren und fehlerfreien IP-Plan mit folgenden Teil-Aufgaben. Bei jeder Tabelle weiter unten ist **die erste Zeile** als Beispiel ausgefüllt.

- Laden Sie [**DIESES Excel-Sheet**](P3_6_Netzwerk-Einteilung.xlsx) runter und...
    - Teilen Sie das erhaltene Netz in passende **Subnetze** auf.
    - Füllen Sie es gemäss den Vorgaben elektronisch korrekt aus, indem Sie die **Netzadressen**, **Netzmasken** und **Broadcastadressen** bestimmen (Tabelle unten).
    - Schiessen Sie einen Screenshot der Subnetze von **Netzwerk B** (US) und **Netzwerk C** (EMEA). Ergänzen Sie diesen in Ihrer Dokumentation mit entsprechendem Text.
    - Teilen Sie den **Routerinterfaces IP-Adressen** zu (Tabelle unten).
    - Erstellen Sie die **Routingtabellen** für **Router A**, **Router B**, **Router C** und **Router ISP** (Tabelle unten)


### Netzgrössen

| Netz    | Benötigte Adressen | Gewählte  Netzgrösse |
|---------|--------------------|----------------------|
| Netz I  | 0 PCs + 0 LTs + 0 DR + 2 RT + 2 = 4  |    4  |
| Netz T1 | 0 PCs + 0 LTs + 0 DR + 2 RT + 2 = 4  |    4  |
| Netz T2 | 0 PCs + 0 LTs + 0 DR + 2 RT + 2 = 4  |    4  |
| Netz A  | 25 PCs + 50 LTs + 5 DR + 1 RT + 2 = 83 | 128 |
| Netz B  | 290 PCs + 510 LTs + 20 DR + 1 RT + 2 = 823 | 1024 |
| Netz C  | 120 PCs + 200 LTs + 10 DR + 1 RT + 2 = 333| 512 |

### Netzadressen

| Netz   | Grösse | Netzadresse/Netzmaske (Bit) | Dezimale Schreibweise der Netzmaske | Broadcastadresse |
|--------|-----|-----|-----|-----|
| Netz I |  4  | 135.233.183.252 /30  | 255.255.255.252 | 135.233.183.255 |
| Netz T1 | 4 | 135.233.183.248 /30 | 255.255.255.252 | 135.233.183.251 |
| Netz T2 | 4 | 135.233.183.244 /30 | 255.255.255.252 | 135.233.183.247 |
| Netz A  | 128 | 135.233.183.0 /25 | 255.255.255.128 | 135.233.183.127 |
| Netz B  | 1024 | 135.233.176.0 /22 | 255.255.252.0 | 135.233.179.255 |
| Netz C  | 512 | 135.233.180.0 /23 | 255.255.254.0 | 135.233.181.255 |

---


### Grafische Darstellung (Kreis)

![Diagramm](Diagramm.png)


---

<br>

### Router-Interfaces

| **Router**        | **Interfaceadresse** | **Interface** |
|-------------------|----------------------|---------------|
| Router A Netz I   | 135.233.183.254 /30  | s0            |
| Router A Netz A   | 135.233.183.1   /25  | e0            |
| Router A Netz T1  | 135.233.183.249 /30  | s0            |
| Router B Netz T1  | 135.233.183.250 /30  | s0            |
| Router B Netz T2  | 135.233.183.245 /30  | s1            |
| Router B Netz B   | 135.233.176.1   /22  | e0            |
| Router C Netz T2  | 135.233.183.246 /30  | s0            |
| Router C Netz C   | 135.233.180.1   /23  | e0            |
| Router ISP Netz I | 135.233.183.253 /30  | s0            |


### Routingtabelle Router A

| **Destination Network** (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|-----|------|----------|------|
| (I) 135.233.183.252 /30 | -- | 0 | s0 |
| (A) 135.233.183.0 /25  | -- | 0 | e0 |
| (T1) 135.233.183.248 /30 | -- | 0 | s1 |
| (T2) 135.233.183.244 /30 | 135.233.183.250 | 1 | s1 |
| (B) 135.233.176.0 /22  | 135.233.183.250 | 1 | s1 |
| (C) 135.233.180.0 /23  | 135.233.183.250 | 2 | s1 |
| (Default) 0.0.0.0 / 0 | 135.233.183.253 /30 | -- | s0 |

### Routingtabelle Router B

| **Destination Network**  (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|--------|-------|-------|---------|
| (T1) 135.233.183.248 /30  | -- | 0 | s0 |
| (T2) 135.233.183.244 /30  | -- | 0 | s1 |
| (B)  135.233.176.0 /22   | -- | 0 | e0 |
| (C)  135.233.180.0 /23   | 135.233.183.246 | 0 | s1 |
| (Default) 0.0.0.0 / 0 | 135.233.183.249 /30 | -- | s0 |


### Routingtabelle Router C

| **Destination Network**  (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|--------|-------|-------|---------|
| (T2) 135.233.183.244 /30 | -- | 0 | s0 |
| (C) 135.233.180.0 /23  | -- | 0 | e0 |
| (Default) 0.0.0.0 / 0 | 135.233.183.245 /30 | -- | s0 |

### Routingtabelle Router ISP

| **Destination Network**  (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|--------|-------|-------|---------|
| (Default) 0.0.0.0 / 0 | 135.233.183.253 /30 | -- | s0 |



## 2. Teilauftrag (Praxis)
Setzen Sie diese Netzwerkumgebung mit dem CISCO Packet Tracer um. Nutzen Sie dabei die unten verlinkte Vorlage. Sie müssen **keine** weiteren Geräte anschliessend. Die Namen der Geräte sind bereits eingetragen. Sämtliche Konfigurationen fehlen noch. Achten Sie ausserdem darauf, dass diverse Netzwerkkarten noch eingeschaltet werden müssen, damit sie überhaupt funktionieren.
- [CISCO Packet Tracer Vorlage](Vorlage.pkt)



### Abgabe:
- Dokumentation mit allen Angaben zum Netzwerk
- Live-Demo bei der LP - Doku und CISCO PT (10’)


Dies ist mein gelöstes [File](N3_6-Auftrag.pkt).

Das gelöste Excel File ist [hier](P3_6_Netzwerk-Einteilung-gelöst.xlsx).

## Quellen

- ChatGPT zur IP überprüfung
