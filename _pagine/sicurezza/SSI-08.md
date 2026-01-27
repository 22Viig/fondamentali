---
layout: page
title: Sicurezza nei Sistemi Informatici 8
args: (Attacchi di rete, Attacchi di manipolazione delle comunicazioni, Sicurezza perimetrale)
permalink: /SSI-08/

---
Argomenti: 
- [1. Attacchi di rete: panoramica generale](#1-attacchi-di-rete-panoramica-generale)
- [2.  Attacchi di manipolazione delle comunicazioni](#2-attacchi-di-manipolazione-delle-comunicazioni)
- [3. Sicurezza perimetrale: firewall, proxy e sistemi di rilevamento](#3-sicurezza-perimetrale-firewall-proxy-e-sistemi-di-rilevamento)


## **1. Attacchi di rete: panoramica generale**

Le reti informatiche sono costantemente esposte a una vasta gamma di minacce che mirano a comprometterne la disponibilità, l’integrità o la confidenzialità. La lezione introduce inizialmente il concetto di **porte di comunicazione** e **protocolli**, fondamentali per comprendere dove e come gli attaccanti possono colpire.

Le porte sono essenzialmente “punti logici” attraverso cui avviene lo scambio di dati; ogni porta è associata a un servizio noto (HTTP sulla porta 80, DNS sulla 53, SSH sulla 22, ecc.). La conoscenza delle porte permette di capire quali servizi risultano esposti e quindi potenzialmente vulnerabili.

Entra quindi in gioco il concetto di **porte non necessarie**, ossia servizi attivi che non servono realmente all’operatività. Disabilitarli riduce significativamente la superficie d’attacco.

Si passa poi agli **attacchi DoS e DDoS**, che rendono un servizio non disponibile saturandone le risorse. Tra le varianti illustrate:

- **Ping Flood**, **UDP Flood**  
- **Smurf**, **Fraggle**  
- **SYN Flood**  
- **Christmas Attack**  
- **Ping of Death**  
- **Teardrop**  
- **Permanent DoS** (il più distruttivo, può danneggiare hardware/firmware)

Il **DDoS** utilizza una rete di dispositivi compromessi (botnet). Esempi celebri includono l’attacco **Mirai del 2016** e quello contro **GitHub del 2018**. Le difese includono **blackholing**, sistemi cloud scalabili e architetture NOC distribuite.

---

## **2. Attacchi di manipolazione delle comunicazioni**

Questa categoria riguarda attacchi che sfruttano identità false, intercettazione o manipolazione di flussi comunicativi.

### **Spoofing**
Lo spoofing consiste nel falsificare l’identità di origine (IP, MAC o altri identificatori). Serve spesso come fase introduttiva per attacchi più avanzati. Le difese includono MFA, NAC, formazione e antimalware.

### **Hijacking**
L’hijacking è la presa di controllo di una sessione attiva. Le varianti trattate:

- **Furto di sessione** (session ID)
- **TCP/IP hijacking**
- **Blind hijacking**
- **Clickjacking**
- **Man-in-the-Middle**
- **Man-in-the-Browser**
- **Watering Hole**
- **XSS**

### **Replay Attack**
Consiste nella ripetizione di una trasmissione legittima.  
Contromisure: token usa-e-getta, timestamp, MFA, TOTP, WPA2/WPA3.

### **Attacchi transitivi e DNS**
Comprendono:

- **DNS poisoning**
- **Zone transfer non autorizzati**
- **Modifica del file hosts**
- **Pharming**
- **Domain Name Kiting**

### **ARP Poisoning**
Alterazione delle associazioni IP–MAC all’interno di una LAN, utile per MITM, DoS e intercettazione.

Contromisure: VLAN, DHCP snooping, ARP statici.

---

## **3. Sicurezza perimetrale: firewall, proxy e sistemi di rilevamento**

La seconda parte della lezione introduce i sistemi di difesa perimetrale.

### **Firewall**
I firewall separano reti diverse e applicano politiche di filtraggio.

Tipologie:
- Software
- Hardware
- Embedded

Tecniche di filtraggio:
- Packet Filtering (stateless / stateful)
- NAT Filtering
- Application Layer Gateway
- Circuit-Level Gateway
- MAC Filtering
- Implicit Deny
- WAF
- NGFW

### **Server Proxy**
Funzionano da intermediari tra client e server remoti.

Tipi:
- Proxy IP (anonimizzatori)
- Caching proxy
- Content filter
- Web security gateway

Modalità operative:
- **Trasparenti**
- **Non trasparenti**
- **Reverse proxy**
- **Forward proxy**

### **Honeypot e Honeynet**
Sistemi volutamente vulnerabili usati per studiare attaccanti o distrarli.

### **DLP**
Monitorano i dati in uscita per prevenire fughe di informazioni sensibili.

### **NIDS e NIPS**
- **NIDS**: rilevano attività sospette  
- **NIPS**: prevengono bloccando traffico dannoso

### **UTM**
I dispositivi Unified Threat Management combinano:

- firewall  
- proxy  
- IDS/IPS  
- antivirus  
- filtro contenuti  
- DLP  

in un’unica soluzione centralizzata.
