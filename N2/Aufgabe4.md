# N2 Advanced - Auftrag 4

### Anforderungen:
- Dokumentieren Sie ihr Vorgehen simpel, aber möglichst sinnvoll und nachvollziehbar gemäss den unten aufgeführten Anforderungen.
- Berücksichtigen Sie, dass die Firma zwei Abteilungen (Produktion und Verkauf) mit unterschiedlich vielen Netzwerkgeräten besitzt. 
- Erstellen Sie zuerst eine passende Netzwerkeinteilung. Berücksichtigen Sie dabei auch das Transfernetz.
- Bauen Sie mit Cisco Packet Tracer ein funktionierendes Netzwerk. 
- Halten Sie sich an die Namenskonvention.

| Produkt:   | GL        | Betrieb | Verkauf | Einkauf |
|:-----------|:---------:|:-------:|:-------:|:-------:|
| PCs        | 3        | 44       | 6       | 29      | 
| Laptops    | 3        | 36       | 10      | 30      |
| Drucker    | 2        | 5        | 4       | 6       |
| **Total**  | 8        | 85       | 20      | 65      |

**Netzwerkplan**

![Netzwerkplan](P2_4_netzwerkplan_800.png)


**Vorgaben:**

Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:

- Vom ISP erhalten sie den IP-Range: **219.60.30.0 /23**
- Erstellen Sie **unterschiedlich grosse Subnetze** - für jede Abteilung eines, plus noch das **Transfernetz** (insgesamt 5).

### Diagramm Visio

![Visio Diagramm](Visio.png)

### Konzept

Das Konzept sieht wie folgt aus:

| | Netz ID | Subnet | Erste IP* | Letzte IP | Broadcast |
|-|---------|--------|----------|-----------|-----------|
| **Netz 1** | 219.60.30.0 | 255.255.255.128 | 219.60.30.1 | 219.60.30.126 | 219.60.30.127 |
| **Netz 2** | 219.60.30.128 | 255.255.255.128 | 219.60.30.129 | 219.60.30.254 | 219.60.30.255 |
| **Netz 3** | 219.60.31.0 | 255.255.255.224 | 219.60.31.1 | 219.60.31.30 | 219.60.31.31 |
| **Netz 4** | 219.60.31.32 | 255.255.255.240 | 219.60.31.33 | 219.60.31.46 | 219.60.31.47 |
| **Netz 5** | 219.60.31.252 | 255.255.255.252 | 219.60.31.253 | 219.60.31.254 | 219.60.31.255 |


Ebenfalls ersichtlich ist das Konzept unter [folgendem Excel File.](P2_4_Netzwerk-Einteilung.xlsx)

*Router hat die erste IP

### CISCO Packet Tracer File

Das funktionierende Packet Tracer File finden Sie [hier.](P2_4_Vorlage.pkt)

Geräte sind wie folgt konfiguriert:

#### 1. Subnetz - Betrieb
| Gerät | IP | Subnetmask |
|-----------|----------|---------|
| Router Interface 00 | 219.60.30.1 | 255.255.255.128 |
| PC-B002 | 219.60.30.2 | 255.255.255.128 |
| PC-B003 | 219.60.30.3 | 255.255.255.128 |

#### 2. Subnetz - Einkauf
| Gerät | IP | Subnetmask |
|-----------|----------|---------|
| Router Interface 01 | 219.60.30.129 | 255.255.255.128 |
| PC-E130 | 219.60.30.130 | 255.255.255.128 |
| PC-E131 | 219.60.30.131 | 255.255.255.128 |

#### 3. Subnetz - Verkauf
| Gerät | IP | Subnetmask |
|-----------|----------|---------|
| Router Interface 02 | 219.60.31.1 | 255.255.255.224 |
| PC-V002 | 219.60.31.2 | 255.255.255.224 |
| PC-V003 | 219.60.31.3 | 255.255.255.224 |

#### 4. Subnetz - GL
| Gerät | IP | Subnetmask |
|-----------|----------|---------|
| Router Interface 03  | 219.60.31.33 | 255.255.255.240 |
| PC-G034 | 219.60.31.34 | 255.255.255.240 |
| PC-G035 | 219.60.31.35 | 255.255.255.240 |

#### 5. Subnetz - Transfer
| Gerät | IP | Subnetmask |
|-----------|----------|---------|
| RT-01 Interface 04 | 219.60.31.253 | 255.255.255.252 |
| RT-ISP | 219.60.31.254 | 255.255.255.252 |

#### Routing Table

##### RT-01

| Netzwerk  | Mask      | Next Hop      |
|-----------|-----------|---------------|
|  0.0.0.0  |  0.0.0.0  | 219.60.31.254 | 

##### RT-ISP

| Netzwerk    | Mask            | Next Hop      |
|-------------|-----------------|---------------|
|  219.60.30.0  |  255.255.252.0  | 219.60.31.253 | 


#### Netze

| Netz | Genutzte IPs | Freie IPs |
|-----|----|----|
| Betrieb | 3 | 123 |
| Einkauf | 3 | 123 |
| Verkauf | 3 | 27 |
| GL | 3 | 11 |
| Transfer | 2 | 0 |

### Check: Topics, die in der Doku festgehalten sein sollten:

- [x] Das Excel-Sheet ist korrekt ausgefüllt (Beweis gemäss Angaben oben)
- [x] Die IPs inkl. CIDR sämtlicher PCs (z.B. in einer Tabelle)
- [x] Die Netzwerk-ID's aller Subnetze (z.B. in einer Tabelle)
- [x] Anteil oder Anzahl genutzter und freier IP-Adressen pro Subnetz.
- [x] Die Konfigurationen sämtlicher Geräte.
- [x] Beweis der Funktionalität (Ping, Datentransfer).
