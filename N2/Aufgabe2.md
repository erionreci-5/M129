# N2 Advanced - Auftrag 2

## Anforderungen:
- Dokumentieren Sie ihr Vorgehen simpel, aber möglichst sinnvoll und nachvollziehbar gemäss den unten aufgeführten Anforderungen. 
- Bauen Sie mit Cisco Packet Tracer ein funktionierendes Netzwerk. Halten Sie sich dabei an folgende Vorgaben und den Netzwerkplan und halten Sie die Namenskonvention ein.
    - 16 Computer
    - 8 Switches
    - 1 Router

**Netzwerkplan**


![Netzwerkplan](https://github.com/erionreci-5/M129/blob/main/Bilder/P2_2_netzwerkplan_800.jpg)


**Vorgaben:**

Folgende Bedingungen sind vorgegeben und **müssen** eingehalten werden:

- Vom ISP erhalten sie den IP-Range: **37.105.96.0 /22**
- Erstellen Sie **acht gleichgrosse Subnetze** - für jede Abteilung eines.

## Konzept

Das Konzept sieht wie folgt aus:

|            | Netz ID       | Subnet          | Erste IP*     | Letzte IP     | Broadcast     |
|------------|---------------|-----------------|---------------|---------------|---------------|
| **Netz 1** | 37.105.96.0   | 255.255.255.128 | 37.105.96.1   | 37.105.96.126 | 37.105.96.127 |
| **Netz 2** | 37.105.96.128 | 255.255.255.128 | 37.105.96.129 | 37.105.96.254 | 37.105.96.255 |
| **Netz 3** | 37.105.97.0   | 255.255.255.128 | 37.105.97.1   | 37.105.97.126 | 37.105.97.127 |
| **Netz 4** | 37.105.97.128 | 255.255.255.128 | 37.105.97.129 | 37.105.97.254 | 37.105.97.255 |
| **Netz 5** | 37.105.98.0   | 255.255.255.128 | 37.105.98.1   | 37.105.98.126 | 37.105.98.127 |
| **Netz 6** | 37.105.98.128 | 255.255.255.128 | 37.105.98.129 | 37.105.98.254 | 37.105.98.255 |
| **Netz 7** | 37.105.99.0   | 255.255.255.128 | 37.105.99.1   | 37.105.99.126 | 37.105.99.127 |
| **Netz 8** | 37.105.99.128 | 255.255.255.128 | 37.105.99.129 | 37.105.99.254 | 37.105.99.255 |

Ebenfalls ersichtlich ist das Konzept auch unter dem [folgendem Excel File.](https://github.com/erionreci-5/M129/blob/main/Bilder/P2_2_Netzwerk-Einteilung.xlsx)

*Router hat die erste IP

### CISCO Packet Tracer File

Das funktionierende Packet Tracer File finden Sie [hier.](https://github.com/erionreci-5/M129/blob/main/Bilder/Vorlage%20(1).pkt)

Geräte sind wie folgt konfiguriert:

#### 1. Subnetz - Verkauf
| Gerät               | IP             | Subnetmask       |
|---------------------|----------------|------------------|
| Router Interface 01 |  37.105.96.1   | 255.255.255.128  |
| PC-6002             |  37.105.96.2   | 255.255.255.128  |
| PC-6003             |  37.105.96.3   | 255.255.255.128  |

#### 2. Subnetz - Einkauf
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 02 |  37.105.96.129   | 255.255.255.128  |
| PC-6130             |  37.105.96.130   | 255.255.255.128  |
| PC-6131             |  37.105.96.131   | 255.255.255.128  |

#### 3. Subnetz - Logistik
| Gerät               | IP             | Subnetmask       |
|---------------------|----------------|------------------|
| Router Interface 03 |  37.105.97.1   | 255.255.255.128  |
| PC-7002             |  37.105.97.2   | 255.255.255.128  |
| PC-7003             |  37.105.97.3   | 255.255.255.128  |

#### 4. Subnetz - Marketing
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 04 |  37.105.97.129   | 255.255.255.128  |
| PC-7130             |  37.105.97.130   | 255.255.255.128  |
| PC-7131             |  37.105.97.131   | 255.255.255.128  |

#### 5. Subnetz - Administration
| Gerät               | IP             | Subnetmask       |
|---------------------|----------------|------------------|
| Router Interface 05 |  37.105.98.1   | 255.255.255.128  |
| PC-8002             |  37.105.98.2   | 255.255.255.128  |
| PC-8003             |  37.105.98.3   | 255.255.255.128  |

#### 6. Subnetz - Transport
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 06 |  37.105.98.129   | 255.255.255.128  |
| PC-8130             |  37.105.98.130   | 255.255.255.128  |
| PC-8131             |  37.105.98.131   | 255.255.255.128  |

#### 7. Subnetz - Support
| Gerät               | IP             | Subnetmask       |
|---------------------|----------------|------------------|
| Router Interface 07 |  37.105.99.1   | 255.255.255.128  |
| PC-9002             |  37.105.99.2   | 255.255.255.128  |
| PC-9003             |  37.105.99.3   | 255.255.255.128  |

#### 8. Subnetz - Management
| Gerät               | IP               | Subnetmask       |
|---------------------|------------------|------------------|
| Router Interface 08 |  37.105.99.129   | 255.255.255.128  |
| PC-9130             |  37.105.99.130   | 255.255.255.128  |
| PC-9131             |  37.105.99.131   | 255.255.255.128  |

#### Netze

| Netz             | Genutzte IPs | Freie IPs |
|------------------|--------------|-----------|
| Verkauf          |      3       |    123    |
| Einkauf          |      3       |    123    |
| Logistik         |      3       |    123    |
| Marketing        |      3       |    123    |
| Administration   |      3       |    123    |
| Transport        |      3       |    123    |
| Support          |      3       |    123    |
| Management       |      3       |    123    |

### Check: Topics, die in der Doku festgehalten sein sollten:

- [x] Das Excel-Sheet ist korrekt ausgefüllt (Beweis gemäss Angaben oben)
- [x] Die IPs inkl. CIDR sämtlicher PCs (z.B. in einer Tabelle)
- [x] Die Netzwerk-ID's aller Subnetze (z.B. in einer Tabelle)
- [x] Anteil oder Anzahl genutzter und freier IP-Adressen pro Subnetz.
- [x] Die Konfigurationen sämtlicher Geräte.
- [x] Beweis der Funktionalität (Ping, Datentransfer).

### Weitere formative Fragen, auf die in der Doku eingegangen werden kann:
- [x] Wieviele freie IP-Adressen gibt es in der Abteilung **Marketing**?
- [x] Eine neue Mitarbeiterin wird in der Abteilung **Marketing** eingestellt. Welche Netzwerkkonfiguration erhält sie?
  - Eine neue Mitarbeiterin in der Abteilung Marketing würde folgende IP erhalten: 37.105.97.132
- [x] Ist das Netzwerk-Design sinnvoll?
  - Dieses Netzwerk hat viel zu viele IPs. Ein Netzwerk mit weniger IPs wäre sinnvoller
- [x] Gibt es Verbesserungsvorschläge bzgl. Netzwerk-Design?
  - Einen zusätzlichen Router für die Redundanz

