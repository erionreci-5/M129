# N3 Expert - Auftrag 5
## Aufgabenstellung 3.5

**Theorie und Praxis kombiniert**

Zuerst erstellen Sie das Netzwerk-Design. Danach setzen Sie die Umgebung mit CISCO Packet Tracer um (Vorlage weiter unten)


## Ausgangslage
Die Firma Go-IT AG hat einen **Hauptsitz** im Zentrum von Zürich (Management und Verwaltung) und einen **Branch** in einem Aussenquartier (Betrieb).

**Hauptsitz:**  
- 23 PCs
- 20 Laptops  
- 7 Drucker

**Branch:**  
- 65 PCs
- 55 Laptops  
-  7 Drucker

Beide Firmensitze sind über eine Standleitung verbunden. Die **beiden Häuser haben getrennte Netze**. Der Hauptsitz ist über einen **DSL-Router mit dem Internet** verbunden.

Für die Netzwerke steht das **Netz 192.168.100.0/23**
zur Verfügung. Für die Internetleitung erhalten wir vom ISP die statische IP-Adresse **95.2.50.102/30**, der Router des ISP hat die IP-Adresse **95.2.50.101/30**.


**Situations- und Netzwerkplan**

![Netzwerkplan](https://github.com/erionreci-5/M129/blob/main/Bilder/P3_5_netzwerk_800.jpg)

## 1. Teilauftrag (Theorie)

Erstellen Sie für die Firma **Go-IT** einen IP-Plan mit folgenden Teil-Aufgaben. Bei jeder Tabelle ist **die erste Zeile** als Beispiel ausgefüllt.

1.  Teilen Sie das erhaltene Netz in passende **Subnetze** auf.

2.  Bestimmen Sie die **Netzadressen**, **Netzmasken** und **Broadcastadressen**.

3.  Teilen Sie den **Routerinterfaces IP-Adressen** zu.

4.  Erstellen Sie die **Routingtabellen** für **Router Haus A** und **Router
    Haus B**.


### Netzgrössen

| Netz | Benötigte Adressen | Gewählte  Netzgrösse |
|------|-----------|----------------|
| Netz T | 0 PCs + 0 LTs + 0 DR + 2 RT + 2 = 4  |  4  |
| Netz I | vom Provider | - |
| Netz A | 23 PCs + 20 LTs + 7 DR + 1 RT + 2 | 53 |
| Netz B | 65 PCs + 55 LTs + 7 DR + RT + 2 | 130 |

### Netzadressen

| Netz   | Grösse | Netzadresse/Netzmaske (Bit) | Dezimale Schreibweise der Netzmaske | Broadcastadresse |
|--------|-----|-----|-----|-----|
| Netz I |  4  | 92.2.50.100 /30  | 255.255.255.252 | 92.2.50.103 |
| Netz T | 4 | 192.168.101.64 /30 | 255.255.255.252 | 192.168.100.255 |
| Netz A | 64 | 192.168.101.0 /26 | 255.255.255.192 | 192.168.101.63 |
| Netz B | 255 | 192.168.100.0 /24 | 255.255.255.0 | 192.168.100.255 |


---

### Grafische Darstellung (Kreis)

![Diagramm](https://github.com/erionreci-5/M129/blob/main/Bilder/Diagramm%20(1).png)

---

<br>

### Router-Interfaces

| **Router**      | **Interfaceadresse** | **Interface** |
|-----------------|----------------------|---------------|
| Router A Netz I | 92.2.50.102 /30      | s1            |
| Router A Netz A | 192.168.101.1 /26    | e0            |
| Router A Netz T | 192.168.101.65 /30   | s0            |
| Router B Netz B | 192.168.100.1 /24    | e0            |
| Router B Netz T | 192.168.101.66 /30   | s0            |

### Routingtabelle Router A

| **Destination Network** (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|-----|------|----------|------|
| (A) 192.168.101.0 /26   | -- | 0 | e0 |
| (T) 192.168.101.64 /30 | -- | 0 | s0 |
| (I) 92.2.50.100 /30 | -- | 0 | s1 |
| (B) 192.168.100.0 /24 | 192.168.101.66 /30 | 1 | s0 |
| (Default) 0.0.0.0 / 0 | 92.2.50.101 /30 | -- | s1 |

### Routingtabelle Router B

| **Destination Network**  (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|--------|-------|-------|---------|
| (T) 192.168.101.66  | -- | 0 | s0 |
| (B) 192.168.100.1  | -- | 0 | e0 |
| (Default) 0.0.0.0 / 0 | 192.168.101.65 | -- | s0 |

### Routingtabelle Router ISP

| **Destination Network**  (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|--------|-------|-------|---------|
| (I) 192.168.100.0 /23  | 92.2.50.102 | 0 | s0 |


## Abgabe:
- Dokumentation mit allen Angaben zum Netzwerk
- Live-Demo bei der LP - Doku und CISCO PT (10’)

Dies ist mein gelöstes [File](https://github.com/erionreci-5/M129/blob/main/Bilder/N3_5-Auftrag.pkt).

## Quellen

- ChatGPT zur IP überprüfung

