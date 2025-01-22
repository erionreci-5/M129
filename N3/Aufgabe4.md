# N3 Expert - Auftrag 4

## Aufgabenstellung 3.4

**Theorie und Praxis kombiniert**

Zuerst erstellen Sie das Netzwerk-Design. Danach setzen Sie die Umgebung mit CISCO Packet Tracer um (Vorlage weiter unten)


## Ausgangslage
Die **IT-Grow Holding** hat ihren **Hauptsitz** in Glattbrugg (Management und Verwaltung). Sie verwaltet zwei Tochterunternehmen. Die Tochter **Global** ist im gleichen Gebäude untergebracht, wie das Management. Die Tochter **Local** ist auf der anderen Strassenseite einquartiert. 


| Produkt:   | Site **Global** | Site **Local** | 
|:-----------|:---------------:|:--------------:|
| PCs        | 30              | 8              | 
| Laptops    | 60              | 7              |
| Drucker    | 7               | 2              |
| **Total**  | **97**          | **17**         |


Die beiden Teilfirmen sind über eine Standleitung miteinander verbunden. Die **beiden Häuser haben getrennte Netze**. Der Hauptsitz ist über einen **DSL-Router mit dem Internet** verbunden. Die IT-Verwaltung wird intern geführt. Sie sind verantworlich für das Netzwerkmanagement der gesamten Holding.

### Vorgaben:

Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:

- Vom ISP erhalten sie den IP-Range: **178.19.22.0 /24**
- Erstellen Sie **unterschiedlich grosse Subnetze** - für jede Abteilung eines, plus noch die **Transfernetze**.



**Situations- und Netzwerkplan**

![Netzwerkplan](https://github.com/erionreci-5/M129/blob/main/Bilder/P3_4_netzwerk_800.jpg)

## 1. Teilauftrag (Theorie)

Erstellen Sie für die **IT-Grow Holding** einen IP-Plan mit folgenden Teil-Aufgaben. Bei jeder Tabelle unten ist **die erste Zeile** als Beispiel ausgefüllt. Wenn sie [**DIESE Excel-Tabelle**](https://github.com/erionreci-5/M129/blob/main/Bilder/P3_4_Netzwerk-Einteilung.xlsx) vorher korrekt ausfüllen, fällt es Ihnen einfacher. Und; Sie haben eine hervorragende Hilfe bei der späteren Umsetzung.  

1.  Teilen Sie das erhaltene Netz in passende **Subnetze** auf.
2.  Bestimmen Sie die **Netzadressen**, **Netzmasken** und **Broadcastadressen**.
3.  Teilen Sie den **Routerinterfaces IP-Adressen** zu.
4.  Erstellen Sie die **Routingtabellen** für **Router Haus A** und **Router
    Haus B**.


### Netzgrössen

| Netz   | Benötigte Adressen                      | Gewählte  Netzgrösse |
|--------|-----------------------------------------|----------------------|
| Netz I | 0 PCs + 0 LTs + 0 DR + 2 RT + 2 = 4     |    4                 |
| Netz T | 0 PCs + 0 LTs + 0 DR + 2 RT + 2 = 4     | 4                    |
| Netz A | 30 PCs + 60 LTs + 7 DR + 1 RT + 2 = 100 | 128                  |
| Netz B | 8 PCs + 7 LTs + 2 DR + 1 RT + 2         | 32                   |

### Netzadressen

| Netz   | Grösse | Netzadresse/Netzmaske (Bit) | Dezimale Schreibweise der Netzmaske | Broadcastadresse |
|--------|--------|-----------------------------|-------------------------------------|------------------|
| Netz I |  4     | 178.19.22.252 /30           | 255.255.255.252                     | 178.19.22.255    |
| Netz T | 4      | 178.19.22.248 /30           | 255.255.255.252                     | 178.19.22.251    |
| Netz A | 128    | 178.19.22.0 /25             | 255.255.255.128                     | 178.19.22.127    |
| Netz B | 32     | 178.19.22.128 /27           | 255.255.255.224                     | 178.19.22.159    |

---

### Grafische Darstellung (Kreis)

![Diagramm](https://github.com/erionreci-5/M129/blob/main/Bilder/Diagramm.png)

---

<br>

### Router-Interfaces

| **Router**      | **Interfaceadresse** | **Interface** |
|-----------------|----------------------|---------------|
| Router A Netz I | 178.19.22.253 /30    | s1            |
| Router A Netz A | 178.19.22.1   /25    | e0            |
| Router A Netz T | 178.19.22.249 /30    | s0            |
| Router B Netz B | 178.19.22.129 /27    | e0            |
| Router B Netz T | 178.19.22.250 /30    | s0            |

### Routingtabelle Router A

| **Destination Network** (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|------------------------------------------------|-----------------------------------------------------|------------------------------|-----------------------------------|
| (A) 178.19.22.0 /25                            |-----------------------------------------------------| 0                            | e0                                |
| (T) 178.19.22.248 /30                          |-----------------------------------------------------| 0                            | s0                                |
| (I) 178.19.22.252 /30                          |-----------------------------------------------------| 0                            | s1                                |
| (B) 178.19.22.128 /27                          | 178.19.22.250 /30                                   | 1                            | s0                                |
| (Default) 0.0.0.0 / 0                          | 178.19.22.254 /30                                   |------------------------------| s1                                |

### Routingtabelle Router B

| **Destination Network**  (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|-------------------------------------------------|-----------------------------------------------------|------------------------------|-----------------------------------|
| (T) 178.19.22.248 /30                           |-----------------------------------------------------| 0.0.0.0                      | s0                                |
| (B) 178.19.22.128 /27                           |-----------------------------------------------------| 0.0.0.0                      | e0                                |
| (Default) 0.0.0.0 / 0                           | 178.19.22.249 /30                                   |------------------------------| s0                                |

### Routingtabelle Router ISP

| **Destination Network**  (Zielnetz + Netzmaske) | **Next Hop** (Nächster Router auf dem Weg zum Ziel) | **Metric** (hier Hop Count)  | **Interface** (auf diesem Router) |
|-------------------------------------------------|-----------------------------------------------------|------------------------------|-----------------------------------|
| (I) 178.19.22.0 /24                             | 178.19.22.253                                       | 0                            | s0                                |


## Abgabe:
- Dokumentation mit allen Angaben zum Netzwerk
- Live-Demo bei der LP - Doku und CISCO PT (10’)

Dies ist mein gelöstes [File]([N3_4-Auftrag.pkt](https://github.com/erionreci-5/M129/blob/main/Bilder/Vorlage%20(3).pkt)).



## Quellen

- ChatGPT zur IP überprüfung

