# N1 Basic - Aufgabe 1
 
## Anforderungen:
- Dokumentieren Sie ihr Vorgehen simpel, aber möglichst sinnvoll und nachvollziehbar gemäss den unten aufgeführten Anforderungen.
- Bauen Sie mit Filius ein funktionierendes Netzwerk. Halten Sie sich dabei an folgende Vorgaben und den Netzwerkplan und halten Sie die Namenskonvention ein.
    - 4 Computer
    - 2 Switches
    - 1 Router
 
**Netzwerkplan**
 
![Netzwerkplan](P1_1_Filius_800.png)
 
## Vorgaben:
 
 
Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:
 
- Vom ISP erhalten sie den IP-Range: **160.160.250.0 /24**
- Erstellen Sie **zwei gleichgrosse Subnetze** - für jede Abteilung eines.
- Die erste IP-Adresse jedes Subnets ist für den Router reserviert.
- Die Endgeräte erhalten die nächsthöheren IP-Adressen (z.B. PC-01 160.160.250.2)
- Namenskonvention (gemäss Netzwerkplan)
 
### Konzept
 
Das Konzept sieht wie folgt aus:
 
|            | Netz ID         | Subnet          | Erste IP*       | Letzte IP       | Broadcast       |
|------------|-----------------|-----------------|-----------------|-----------------|-----------------  |
| **Netz 1** | 160.160.250.0   | 255.255.255.128 | 160.160.250.1   | 160.160.250.126 | 160.160.250.127 |
| **Netz 2** | 160.160.250.128 | 255.255.255.128 | 160.160.250.129 | 160.160.250.254 | 160.160.250.255 |
 
Ebenfalls ersichtlich ist das Konzept unter [folgendem Excel File.](P1_1_Netzwerk-Einteilung.xlsx)
 
*Router hat die erste IP
 
### Filius File
 
Das funktionierende Filius File finden Sie [hier.](P1_1_Vorlage.fls)
 
Geräte sind wie folgt konfiguriert:
 
| Gerät               | IP              | Subnetmask      |
|---------------------|-----------------|-----------------|
| Router Interface 01 | 160.160.250.1   | 255.255.255.128 |
| PC01                | 160.160.250.2   | 255.255.255.128 |
| PC02                | 160.160.250.3   | 255.255.255.128 |
| Router Interface 02 | 160.160.250.129 | 255.255.255.128 |
| PC11                | 160.160.250.130 | 255.255.255.128 |
| PC12                | 160.160.250.131 | 255.255.255.128 |
