# N1 Basic - Aufgabe 3


## Anforderungen:
- Dokumentieren Sie ihr Vorgehen simpel, aber möglichst sinnvoll und nachvollziehbar gemäss den unten aufgeführten Anforderungen. 
- Bauen Sie mit Filius ein funktionierendes Netzwerk. Halten Sie sich dabei an folgende Vorgaben und den Netzwerkplan und halten Sie die Namenskonvention ein.
    - 8 Computer
    - 4 Switches
    - 1 Router


**Netzwerkplan**


![Netzwerkplan]()


## Vorgaben:
Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:
- Vom ISP erhalten sie den IP-Range: **25.30.120.0 /26**
- Erstellen Sie **vier gleichgrosse Subnetze** - für jede Abteilung eines.
- Die erste IP-Adresse jedes Subnets ist für den Router reserviert.
- Die Endgeräte erhalten die nächsthöheren IP-Adressen
- Namenskonvention (gemäss Netzwerkplan)


### Konzept


Das Konzept sieht wie folgt aus:


| | Netz ID | Subnet | Erste IP* | Letzte IP | Broadcast |
|-|---------|--------|----------|-----------|-----------|
| **Netz 1** | 25.30.120.0 | 255.255.255.240 | 25.30.120.1 | 25.30.120.14 | 25.30.120.15 |
| **Netz 2** | 25.30.120.16 | 255.255.255.240 | 25.30.120.17 | 25.30.120.30 | 25.30.120.31 |
| **Netz 3** | 25.30.120.32 | 255.255.255.240 | 25.30.120.33 | 25.30.120.46 | 25.30.120.47 |
| **Netz 4** | 25.30.120.48 | 255.255.255.240 | 25.30.120.49 | 25.30.120.62 | 25.30.120.63 |

*Router hat die erste IP im Subnet
### Filius File



Geräte sind wie folgt konfiguriert:


#### 1. Subnetz - GL
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 01 | 25.30.120.1     | 255.255.255.240  |
| PC2                 | 25.30.120.2     | 255.255.255.240  |
| PC3                 | 25.30.120.3     | 255.255.255.240  |


#### 2. Subnetz - Buchhaltung
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 02 | 25.30.120.17     | 255.255.255.240  |
| PC18                | 25.30.120.18     | 255.255.255.240  |
| PC19                | 25.30.120.19     | 255.255.255.240  |


#### 3. Subnetz - Verkauf
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 03 | 25.30.120.33     | 255.255.255.240  |
| PC34                | 25.30.120.34     | 255.255.255.240  |
| PC35                | 25.30.120.35     | 255.255.255.240  |


#### 4. Subnetz - Einkauf
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 04 | 25.30.120.49     | 255.255.255.240  |
| PC50                | 25.30.120.50     | 255.255.255.240  |
| PC51                | 25.30.120.51     | 255.255.255.240  |


#### Anteil oder Anzahl genutzter und freier IP-Adressen pro Subnetz.
| Netz              | Genutzte IPs     | Freie IPs        |
|-------------------|------------------|------------------|
| GL                | 3                | 11               |
| Buchhaltung       | 3                | 11               |
| Verkauf           | 3                | 11               |
| Einkauf           | 3                | 11               |



### Check:  Topics, die in der Doku festgehalten sein sollten:
- [x] Das Excel-Sheet ist korrekt ausgefüllt (Beweis gemäss Angaben oben).
- [x] Die IPs inkl. CIDR sämtlicher PCs (z.B. in einer Tabelle).
- [x] Die Netzwerk-ID's aller Subnetze (z.B. in einer Tabelle)
- [x] Anteil oder Anzahl genutzter und freier IP-Adressen pro Subnetz.
- [x] Die Konfigurationen sämtlicher Geräte.
- [x] Beweis der Funktionalität (Ping, Datentransfer).


### Weitere formative Fragen, auf die in der Doku eingegangen werden kann:
- [x] Wieviele freie IP-Adressen gibt es in der Abteilung **Buchhaltung**.
- Es gibt noch 11 freie IP-Adressen in dieser Abteilung
- [x] Ist ein mögliches Wachstum der Firma berücksichtigt?
  - Es sieht so aus als wäre es eine kleinere Firma, weil es ein /26 Netz ist. Bis zu einer gewissen Anzahl ist das Wachstum der Firma berücksichtig, 
    aber ab einem Punkt benötigt man einen grösseren IP-Range, falls viele Mitarbeiter kommen sollten.
- [x] Ist das Netzwerk-Design sinnvoll?
  - Es ist gut aufgebaut.
- [x] Gibt es Verbesserungsvorschläge bzgl. Netzwerk-Design?
  - Ein zusätzlicher Router für die Redundanz wäre ein guter Vorschlag, um das Netzwerk zu verbesseren.
- [x] Welche zusätzlichen Informationen wären nützlich, um für dieses Netzwerk-Design einen Optimierungsvorschlag auszuarbeiten?
  - Es wäre eine nützliche Information, zu wissen für was diese Umgebung benötigt wird. So kann man die Umgebung auf das entsprechend anpassen.
