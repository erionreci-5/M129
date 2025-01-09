# N2 Advanced - Auftrag 1


## Anforderungen:

- Dokumentieren Sie ihr Vorgehen simpel, aber möglichst sinnvoll und nachvollziehbar gemäss den unten aufgeführten Anforderungen. 
- Bauen Sie mit Cisco Packet Tracer ein funktionierendes Netzwerk. Halten Sie sich dabei an folgende Vorgaben und den Netzwerkplan und halten Sie die Namenskonvention ein.
    - 8 Computer
    - 4 Switches
    - 1 Router


**Netzwerkplan**


![Netzwerkplan](https://github.com/erionreci-5/M129/blob/main/Bilder/P2_1_netzwerkplan_800.jpg)


**Vorgaben:**


Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:


- Vom ISP erhalten sie den IP-Range: **133.95.48.0 /23**
- Erstellen Sie **vier gleichgrosse Subnetze** - für jede Abteilung eines.


## Konzept


Das Konzept sieht wie folgt aus:


|            | Netz ID       | Subnet          | Erste IP*     | Letzte IP     | Broadcast     |
|------------|---------------|-----------------|---------------|---------------|---------------|
| **Netz 1** | 133.95.48.0   | 255.255.255.128 | 133.95.48.1   | 133.95.48.126 | 133.95.48.127 |
| **Netz 2** | 133.95.48.128 | 255.255.255.128 | 133.95.48.129 | 133.95.48.254 | 133.95.48.255 |
| **Netz 3** | 133.95.49.0   | 255.255.255.128 | 133.95.49.1   | 133.95.49.126 | 133.95.49.127 |
| **Netz 4** | 133.95.49.128 | 255.255.255.128 | 133.95.49.129 | 133.95.49.254 | 133.95.49.255 |


Ebenfalls ersichtlich ist das Konzept unter dem [folgendem Excel File.](https://github.com/erionreci-5/M129/blob/main/Bilder/P2_1_Netzwerk-Einteilung.xlsx)

*Router hat die erste IP


### CISCO Packet Tracer File


Das funktionierende Packet Tracer File finden Sie [hier.](https://github.com/erionreci-5/M129/blob/main/Bilder/Reci..pkt)


Geräte sind wie folgt konfiguriert:


#### 1. Subnetz - GL


| Gerät               | IP           | Subnetmask      |
|---------------------|--------------|-----------------|
| Router Interface 01 | 133.95.48.1  | 255.255.255.128 |
| PC-8050             | 133.95.48.50 | 255.255.255.128 |
| PC-8080             | 133.95.48.51 | 255.255.255.128 |


#### 2. Subnetz - Buchhaltung


| Gerät               | IP            | Subnetmask      |
|---------------------|---------------|-----------------|
| Router Interface 02 | 133.95.48.129 | 255.255.255.128 |
| PC-8130             | 133.95.48.150 | 255.255.255.128 |
| PC-8140             | 133.95.48.151 | 255.255.255.128 |


#### 3. Subnetz - Verkauf


| Gerät               | IP           | Subnetmask      |
|---------------------|--------------|-----------------|
| Router Interface 03 | 133.95.49.1  | 255.255.255.128 |
| PC-9050             | 133.95.49.50 | 255.255.255.128 |
| PC-9080             | 133.95.49.51 | 255.255.255.128 |


#### 4. Subnetz - Einkauf


| Gerät               | IP            | Subnetmask      |
|---------------------|---------------|-----------------|
| Router Interface 04 | 133.95.49.129 | 255.255.255.128 |
| PC-9130             | 133.95.49.130 | 255.255.255.128 |
| PC-9140             | 133.95.49.140 | 255.255.255.128 |


#### Netze


| Netz        | Genutzte IPs | Freie IPs |
|-------------|--------------|-----------|
| GL          | 3            | 123       |
| Buchhaltung | 3            | 123       |
| Verkauf     | 3            | 123       |
| Einkauf     | 3            | 123       |


### Check: Topics, die in der Doku festgehalten sein sollten:
- [x] Das Excel-Sheet ist korrekt ausgefüllt (Beweis gemäss Angaben oben)
- [x] Die IPs inkl. CIDR sämtlicher PCs (z.B. in einer Tabelle)
- [x] Die Netzwerk-ID's aller Subnetze (z.B. in einer Tabelle)
- [x] Anteil oder Anzahl genutzter und freier IP-Adressen pro Subnetz.
- [x] Die Konfigurationen sämtlicher Geräte.
- [x] Beweis der Funktionalität (Ping, Datentransfer).


### Weitere formative Fragen, auf die in der Doku eingegangen werden kann:
- [x] Wieviele freie IP-Adressen gibt es in der Abteilung **Einkauf**
  - IM einkauf und in den anderen Abteilungen gibt es nur noch 123 freie IP-Adresse
- [x] Ist ein mögliches Wachstum der Firma berücksichtigt?
  - Das Firma hat viele freie IPs, deshalb ist das Wachstum der Firma hier möglich.
- [x] Ist das Netzwerk-Design sinnvoll?
  - Bei Ausfall des Routers hat man mehr Netzwerk.
- [x] Gibt es Verbesserungsvorschläge bzgl. Netzwerk-Design?
  - Zusätzlichen Router für Redundanz, ist aber nicht unbedingt nötig hier
- [x] Welche zusätzlichen Informationen wären nützlich, um für dieses Netzwerk-Design einen Optimierungsvorschlag auszuarbeiten?
  - Man sollte wissen für was die Umgebung benötigt wird, da man das besser einplanen kann.
    hier merkt man, dass die Umgebung für eine grössere Firma genutzt wird.

