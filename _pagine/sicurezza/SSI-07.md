---
layout: page
title: Sicurezza nei Sistemi Informatici 7
args: (Porte e protocolli, Attacchi DoS e DDoS, Attacchi DNS e ARP Poisoning, Sicurezza perimetrale)
permalink: /ssi-07/

---
Argomenti: 
- [1. Porte e protocolli](#Porte-e-protocolli)
- [2. Attacchi DoS e DDoS](#attacchi-dos-e-ddos)
- [3. Attacchi DNS e ARP Poisoning](#attacchi-dns-e-arp-poisoning)
- [4. Sicurezza perimetrale](#sicurezza-perimetrale)

## Porte e protocolli

Ogni servizio di rete comunica attraverso una porta, ovvero un canale logico numerato che permette a un protocollo di funzionare correttamente. Le porte sono suddivise in tre categorie: note, registrate e dinamiche. Tra le più comuni si trovano quelle legate a servizi fondamentali come HTTP (porta 80), HTTPS (443), FTP (20/21), SSH (22), DNS (53) e molte altre. Proprio la loro diffusione le rende bersaglio ideale per analisi, scansioni e tentativi di compromissione.

Un aspetto importante per la sicurezza è l’eliminazione delle porte non necessarie, cioè quelle associate a servizi non indispensabili al sistema: lasciarle aperte senza motivo aumenta la superficie d’attacco. Una buona pratica consiste nello spegnere o disabilitare i servizi superflui tramite appositi comandi di sistema, riducendo così le potenziali vulnerabilità.


## Attacchi DoS e DDoS
Una delle famiglie di attacchi più diffuse è quella dei Denial of Service (DoS), che mira a rendere non disponibile un servizio inondandolo di richieste o inviando pacchetti costruiti in modo da causarne il malfunzionamento. Il principio alla base del DoS è saturare le risorse di un host – CPU, RAM, banda o stack di rete – fino a impedirne il normale funzionamento.

Tra gli attacchi DoS più diffusi compaiono:

- Flood attack, in cui un'enorme quantità di pacchetti è inviata a un server per sovraccaricarlo.
- Ping Flood, basato sull’invio massivo di richieste ICMP.
- Smurf e Fraggle, varianti che sfruttano il broadcast della rete e protocolli come ECHO o CHARGEN per amplificare gli effetti dell’attacco.
- SYN Flood, che sfrutta la fase iniziale dell’handshake TCP, aprendo connessioni senza mai completarle.
- Christmas Attack, che invia pacchetti TCP con flag anomali per causare errori nel sistema target.
- Ping of Death e Teardrop, che usano pacchetti malformati o frammentati per causare crash o reboot.
- Permanent DoS, più grave, perché danneggia hardware o firmware del dispositivo.
- Fork bomb, tipicamente locale, che crea infiniti processi fino a bloccare il sistema.

Ancora più pericolosi sono gli attacchi Distributed Denial of Service (DDoS), condotti tramite un insieme coordinato di sistemi compromessi (botnet). Questi attacchi possono generare traffico enorme, come avvenuto nell’attacco del 2016 al provider Dyn o nell’attacco da 1,35 Tbps ai danni di GitHub. Un tipo diffuso di DDoS è quello basato su amplificazione DNS o NTP, in cui piccole richieste falsificate (spoofate) generano risposte molto più grandi verso la vittima, saturandone la banda.
Le contromisure includono tecniche come il blackholing o sinkholing, che instradano il traffico malevolo verso un’interfaccia nulla, l’uso di Intrusion Prevention Systems, infrastrutture cloud scalabili e architetture NOC-based specializzate per mitigare l’impatto di questi attacchi.

## Spoofing e Hijacking

Lo spoofing si verifica quando un attaccante falsifica la propria identità, assumendo l'aspetto di un’altra entità. Ciò può riguardare l’indirizzo IP, il MAC address, le email e altri elementi usati per l'autenticazione. La prevenzione richiede misure come l’autenticazione multifattore (MFA), il controllo degli accessi tramite NAC, software antimalware e un adeguato livello di formazione degli utenti.
L’hijacking consiste invece nel prendere il controllo di una sessione attiva tra due sistemi. Può assumere forme diverse:

- Furto di sessione, sfruttando il Session ID di una sessione web.
- TCP/IP hijacking, in cui l’attaccante si inserisce in una sessione TCP esistente.
- Blind hijacking, in cui l’attaccante invia dati senza poter vedere la risposta.
- Clickjacking, che inganna l’utente inducendolo a cliccare in punti non visibili o mascherati.
- Man-in-the-Middle (MITM), dove l’attaccante intercetta e può modificare i dati in transito.
- Man-in-the-Browser, variante MITM limitata alle sessioni del browser.
Watering hole, dove l’attaccante compromette un sito visitato dalle sue vittime tipiche.
- Cross-Site Scripting (XSS), che induce il browser a eseguire codice malevolo.
- Replay attack, dove l’attaccante ritrasmette comunicazioni valide per ottenere accessi non autorizzati.

Le difese includono token usa-e-getta, timestamp, MFA, protocolli sicuri come WPA2/WPA3 e sistemi di rilevamento come EDR.

## Attacchi DNS e ARP Poisoning

Gli attacchi ai DNS mirano a manipolare la risoluzione dei nomi per dirottare gli utenti verso siti malevoli. Tra questi:

- DNS poisoning, che altera la cache DNS.
- Trasferimenti di zona non autorizzati, utili a ottenere informazioni sulla rete.
- Modifica del file hosts, tramite malware.
- Pharming, che reindirizza il traffico verso server dannosi.
- Domain Name Kiting, pratica abusiva che sfrutta il periodo di cancellazione dei domini.

Una minaccia significativa a livello locale è l’ARP poisoning, in cui l’attaccante falsifica le associazioni IP–MAC, dirottando il traffico nella LAN. Può generare MITM o DoS. Le contromisure includono VLAN, DHCP snooping e ARP statici.

## Sicurezza perimetrale

Per proteggere una rete è fondamentale definire un perimetro di sicurezza affidabile. I principali strumenti sono:

### Firewall
I firewall filtrano il traffico in entrata e uscita secondo politiche definite e possono essere:

- Software
- Hardware
- Embedded

Le tecnologie includono:

Packet filtering (stateless o stateful)
NAT filtering
Application Layer Gateway
Circuit-level gateway
MAC filtering
Web Application Firewall (WAF)
Next-Generation Firewall (NGFW)

Il criterio di sicurezza spesso adottato è l’implicit deny, che blocca ogni traffico non esplicitamente autorizzato.

### Proxy server
I proxy fungono da intermediari tra utenti e rete esterna. 

Possono essere:

- Proxy IP (anonimizzazione)
- Caching proxy (ottimizzazione prestazioni)
- Content filter (blocco contenuti indesiderati)
- Web Security Gateway (scansione antivirus, DLP, controllo dello shadow IT)

Esistono proxy trasparenti o non trasparenti, forward o reverse, a seconda dell’architettura.

### Honeypot e honeynet
Un honeypot è un sistema deliberatamente vulnerabile progettato per attirare gli attaccanti e studiarne le tecniche. Più honeypot combinati formano una honeynet, utile per analisi avanzate e attività di cyber intelligence.

## Data Loss Prevention (DLP)
I sistemi DLP analizzano il contenuto dei dati in transito per impedire la perdita o l’esfiltrazione non autorizzata di informazioni sensibili.

## NIDS e NIPS
I Network Intrusion Detection System (NIDS) e Network Intrusion Prevention System (NIPS) monitorano la rete rilevando attività sospette. Possono operare in modalità inline o passiva, e utilizzano tecniche basate su firme, anomalie statistiche e analisi dei protocolli.
Unified Threat Management (UTM)
Le soluzioni UTM integrano firewall, antivirus, filtraggio contenuti, IDS/IPS e altre funzioni di sicurezza in un unico dispositivo semplificando la gestione.