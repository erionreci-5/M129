# N1 Basic - Aufgabe 2


## Anforderungen:
- Dokumentieren Sie ihr Vorgehen simpel, aber möglichst sinnvoll und nachvollziehbar gemäss den unten aufgeführten Anforderungen. 
- Bauen Sie mit Filius ein funktionierendes Netzwerk. Halten Sie sich dabei an folgende Vorgaben und den Netzwerkplan und halten Sie die Namenskonvention ein.
    - 16 Computer
    -  8 Switches
    -  1 Router


**Netzwerkplan**


![Netzwerkplan](https://github.com/erionreci-5/M129/blob/main/Bilder/P1_2_Filius_800.jpg)


## Vorgaben:


Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:


- Vom ISP erhalten sie den IP-Range: **59.136.34.0 /24**
- Erstellen Sie **acht gleichgrosse Subnetze** - für jede Abteilung eines.


### Konzept

So sieht das Konzept aus:
|            | Netz ID       | Subnet          | Erste IP*     | Letzte IP     | Broadcast     |
|------------|---------------|-----------------|---------------|---------------|---------------|
| **Netz 1** | 59.136.34.0   | 255.255.255.224 | 59.136.34.1   | 59.136.34.30  | 59.136.34.31  |
| **Netz 2** | 59.136.34.32  | 255.255.255.224 | 59.136.34.33  | 59.136.34.62  |59.136.34.63   |
| **Netz 3** | 59.136.34.64  | 255.255.255.224 | 59.136.34.65  | 59.136.34.94  | 59.136.34.95  |
| **Netz 4** | 59.136.34.96  | 255.255.255.224 | 59.136.34.97  | 59.136.34.126 | 59.136.34.127 |
| **Netz 5** | 59.136.34.128 | 255.255.255.224 | 59.136.34.129 | 59.136.34.158 | 59.136.34.159 |
| **Netz 6** | 59.136.34.160 | 255.255.255.224 | 59.136.34.161 | 59.136.34.190 | 59.136.34.191 |
| **Netz 7** | 59.136.34.192 | 255.255.255.224 | 59.136.34.193 | 59.136.34.222 | 59.136.34.223 |
| **Netz 8** | 59.136.34.224 | 255.255.255.224 | 59.136.34.225 | 59.136.34.254 | 59.136.34.255 |



*Router hat immer die erste IP im Subnet


### Filius File


Das funktionierende Filius File finden Sie genau [hier.](Bilder/Screenshot 2025-01-08 152932.png)


Geräte sind wie folgt konfiguriert:


#### 1. Subnetz - Verkauf
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 01 | 59.136.34.1      | 255.255.255.224  |
| PC10                | 59.136.34.10     | 255.255.255.224  |
| PC20                | 59.136.34.20     | 255.255.255.224  |


#### 2. Subnetz - Einkauf
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 02 | 59.136.34.33    | 255.255.255.224  |
| PC40                | 59.136.34.40    | 255.255.255.224  |
| PC50                | 59.136.34.50    | 255.255.255.224  |


#### 3. Subnetz - Logistik
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 03 | 59.136.34.65    | 255.255.255.224  |
| PC70                | 59.136.34.70    | 255.255.255.224  |
| PC80                | 59.136.34.80    | 255.255.255.224  |


#### 4. Subnetz - Marketing
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 04 | 59.136.34.97    | 255.255.255.224  |
| PC110               | 59.136.34.110   | 255.255.255.224  |
| PC120               | 59.136.34.120   | 255.255.255.224  |


#### 5. Subnetz - Administration
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 05 | 59.136.34.129   | 255.255.255.224  |
| PC130               | 59.136.34.130   | 255.255.255.224  |
| PC140               | 59.136.34.140   | 255.255.255.224  |


#### 6. Subnetz - Transport
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 06 | 59.136.34.161   | 255.255.255.224  |
| PC170               | 59.136.34.170   | 255.255.255.224  |
| PC180               | 59.136.34.180   | 255.255.255.224  |


#### 7. Subnetz - Support
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 07 | 59.136.34.193   | 255.255.255.224  |
| PC200               | 59.136.34.200   | 255.255.255.224  |
| PC210               | 59.136.34.210   | 255.255.255.224  |


#### 8. Subnetz - Management
| Gerät               | IP              | Subnetmask       |
|---------------------|-----------------|------------------|
| Router Interface 08 | 59.136.34.225   | 255.255.255.224  |
| PC230               | 59.136.34.230   | 255.255.255.224  |
| PC240               | 59.136.34.240   | 255.255.255.224  |



### Check:   Topics, die in der Doku festgehalten sein sollten:
- [x] Das Excel-Sheet ist korrekt ausgefüllt (Beweis gemäss Angaben oben)
- [x] Die IPs inkl. CIDR sämtlicher PCs sind ersichtlich (z.B. in einer Tabelle)
- [x] Die Netzwerk-ID's aller Subnetze sind ersichtlich (z.B. in einer Tabelle)
- [x] Anteil oder Anzahl genutzter und freier IP-Adressen pro Subnetz.
- [x] Die Konfigurationen sämtlicher Geräte.
- [x] Beweis der Funktionalität (Ping, Datentransfer).


### Weitere formative Fragen, auf die in der Doku eingegangen werden kann:
- [x] Wieviele freie IP-Adressen gibt es in der Abteilung **Einkauf**
  - In der Abteilung Einkauf hat es, sowie in allen anderen Abteilungen auch, 30 freie IPs inkl. den beiden PCs und dem Router.
- [x] Wo liegt die Grenze bzgl. Zuweisung der IPs an Mitarbeiter? (Pro Abteilung)
  - Jede Abteilung hat 29 IPs für die Mitarbeiter frei.
- [x] Ist dieses Netzwerk-Design realistisch? (Kritische Begründung)
  - Es gibt einen Single Point of Failure. Dies wäre der Router, wenn dieser ausfällt, gibt es keine Netzwerkverbindung mehr zwischen allen Geräten.
  - Es ist zu wenig skalierbar. Falls mehr Geräte hinzugefügt werden sollten, kann es sein das die IPs irgendwann ausgehen.
  - Da alle Geräte über den gleichen Router gehen, ist eine hohe Netzwerklatenz möglich.
  - **Dieses Netzwerk ist nicht realistisch**
- [x] Gibt es Verbesserungsvorschläge bzgl. Netzwerk-Design?
  - Einen zweiten Router einbauen für Redundanz
- [x] Welche zusätzlichen Informationen wären nützlich, um für dieses Netzwerk-Design einen Optimierungsvorschlag auszuarbeiten?
  - Wieviel Netzwerkverkehr habe ich?
  - Wie sieht es für die Zukunft aus?
