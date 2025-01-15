# N2 Advanced - Auftrag 3

## Anforderungen:
- Dokumentieren Sie ihr Vorgehen simpel, aber möglichst sinnvoll und nachvollziehbar gemäss den unten aufgeführten Anforderungen.
- Berücksichtigen Sie, dass die Firma zwei Abteilungen (Produktion und Verkauf) mit unterschiedlich vielen Netzwerkgeräten besitzt. 
- Erstellen Sie zuerst eine passende Netzwerkeinteilung. Berücksichtigen Sie dabei auch das Transfernetz.
- Bauen Sie mit Cisco Packet Tracer ein funktionierendes Netzwerk. 
- Halten Sie sich an die Namenskonvention.

| Produkt:   | Produktion|  Verkauf
|:-----------|:---------:|:------------:|
| PCs        | 15        | 5            |
| Laptops    | 10        | 6            |
| Drucker    | 10        | 2            |



**Netzwerkplan**

![Netzwerkplan](https://github.com/erionreci-5/M129/blob/main/Bilder/P2_3_netzwerkplan_800.jpg)


**Vorgaben:**

Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:

- Vom ISP erhalten sie den IP-Range: **34.112.98.0 /24**
- Erstellen Sie **unterschiedlich grosse Subnetze** - für jede Abteilung eines, plus noch das **Transfernetz**.

### Diagramm Visio

Hier noch das Diagramm Visio

![Visio Diagramm](https://github.com/erionreci-5/M129/blob/main/Bilder/P2_3_subnetz-kreis_800.jpg)

### Konzept

Das Konzept sieht wie folgt aus:

|            | Netz ID       | Subnet          | Erste IP*     | Letzte IP     | Broadcast     |
|------------|---------------|-----------------|---------------|---------------|---------------|
| **Netz 1** | 34.112.98.0   | 255.255.255.192 | 34.112.98.1   | 133.95.48.126 | 133.95.48.127 |
| **Netz 2** | 34.112.98.64  | 255.255.255.240 | 34.112.98.65  | 34.112.98.78  | 34.112.98.79  |
| **Netz 3** | 34.112.98.252 | 255.255.255.252 | 34.112.98.253 | 34.112.98.254 | 34.112.98.255 |


Ebenfalls ersichtlich ist das Konzept auch unter dem [folgendem Excel File.](P2_3_Netzwerk-Einteilung.xlsx)

### CISCO Packet Tracer File

Das funktionierende Packet Tracer File finden Sie [hier.](P2_3_Vorlage.pkt)

Geräte sind wie folgt konfiguriert:


#### 1. Subnetz - Produktion
| Gerät               | IP          | Subnetmask      |
|---------------------|-------------|-----------------|
| Router Interface 01 | 34.112.98.1 | 255.255.255.192 |
| PC-P01              | 34.112.98.2 | 255.255.255.192 |
| PC-P02              | 34.112.98.3 | 255.255.255.192 |

#### 2. Subnetz - Verkauf
| Gerät               | IP           | Subnetmask      |
|---------------------|--------------|-----------------|
| Router Interface 02 | 34.112.98.65 | 255.255.255.240 |
| PC-V01              | 34.112.98.66 | 255.255.255.240 |
| PC-V02              | 34.112.98.67 | 255.255.255.240 |

#### 3. Subnetz - Transfer
| Gerät  | IP            | Subnetmask      |
|--------|---------------|-----------------|
| RT-01  | 34.112.98.253 | 255.255.255.252 |
| RT-ISP | 34.112.98.254 | 255.255.255.252 |

#### Routing Table

##### RT-01

| Netzwerk  | Mask      | Next Hop      |
|-----------|-----------|---------------|
|  0.0.0.0  |  0.0.0.0  | 34.112.98.254 | 

##### RT-ISP

| Netzwerk    | Mask            | Next Hop      |
|-------------|-----------------|---------------|
|34.112.98.0  |  255.255.255.0  | 34.112.98.253 | 

#### Netze

| Netz       | Genutzte IPs | Freie IPs |
|------------|--------------|-----------|
| Produktion | 3            | 59        |
| Verkauf    | 3            | 11        |
| Transfer   | 2            | 0         |


### Check: Topics, die in der Doku festgehalten sein sollten:

- [x] Das Excel-Sheet ist korrekt ausgefüllt (Beweis gemäss Angaben oben)
- [x] Die IPs inkl. CIDR sämtlicher PCs (z.B. in einer Tabelle)
- [x] Die Netzwerk-ID's aller Subnetze (z.B. in einer Tabelle)
- [x] Anteil oder Anzahl genutzter und freier IP-Adressen pro Subnetz.
- [x] Die Konfigurationen sämtlicher Geräte.
- [x] Beweis der Funktionalität (Ping, Datentransfer).

### Weitere formative Fragen, auf die in der Doku eingegangen werden kann:
- [x] Wieviele freie IP-Adressen gibt es in der Abteilung **Verkauf**
- [x] Ist ein mögliches Wachstum der Firma berücksichtigt?
  - Ein zugrosses Wachstum ist nicht berücksichtig, aber ein kleineres wäre möglich

