---
layout: page
title: Sicurezza nei Sistemi Informatici 9
args: (Sicurezza degli endpoint, Progettare una rete sicura)
permalink: /SSI-09/

---
Argomenti: 
- [1. Sicurezza degli endpoint](#sicurezza-degli-endpoint)
- [2. Progettare una rete sicura](#progettare-una-rete-sicura)


## Sicurezza degli endpoint
La lezione introduce innanzitutto i concetti fondamentali legati alla protezione degli endpoint, ovvero tutti quei dispositivi che si connettono alla rete aziendale: computer, laptop, smartphone, storage locali o remoti. La sicurezza dell’endpoint è cruciale perché rappresenta spesso l’elemento più vulnerabile della rete. Il primo strumento presentato è il firewall host-based, una versione locale del firewall installata direttamente sul sistema operativo: ad esempio Windows offre Windows Defender Firewall, macOS utilizza PF e Linux si affida a iptables. Questi firewall controllano il traffico in entrata e in uscita dal singolo dispositivo, permettendo di bloccare connessioni indesiderate.

Accanto ai firewall sono essenziali gli IDS (Intrusion Detection System), strumenti che monitorano il traffico o il comportamento del sistema per rilevare attività sospette. La lezione distingue gli HIDS (che operano sull’host) dai NIDS (che monitorano segmenti di rete). I metodi di rilevamento includono controlli basati su firme note, su policy definite oppure su analisi comportamentali e anomalie.

Un altro blocco tematico importante riguarda le tecnologie di Data Loss Prevention (DLP): sistemi progettati per prevenire la fuga di dati sensibili. Esistono DLP per l’endpoint, che monitorano file utilizzati localmente; DLP di rete, che controllano i dati in transito; DLP di storage, dedicati ai dati a riposo; e infine DLP basati su cloud, integrati direttamente nei servizi SaaS e negli strumenti dei provider cloud.

Il documento affronta poi la messa in sicurezza del BIOS e dei dispositivi di avvio. Poiché il BIOS determina il comportamento del computer già dalle prime fasi dell’accensione, comprometterlo rappresenta un rischio enorme. Le principali contromisure includono aggiornarlo correttamente, impostare password di accesso, configurare attentamente l’ordine di boot, disabilitare porte non necessarie e attivare il secure boot per garantire l’esecuzione di software autentico e verificato.

Segue una sezione dedicata alla protezione dei dispositivi di storage. Tra le soluzioni più diffuse troviamo BitLocker To Go per cifrare supporti rimovibili, oppure chiavette USB dotate di cifratura hardware integrata. La lezione distingue tra NAS (Network Attached Storage), spesso dotati di configurazioni RAID, e SAN (Storage Area Network), reti più avanzate per l’archiviazione a blocchi. Per rendere sicuri NAS e SAN è fondamentale usare crittografia, autenticazione forte e registrazione degli accessi.

La parte conclusiva del blocco dedicato agli endpoint analizza i principali strumenti di difesa moderna. L’antivirus rimane un elemento essenziale, sebbene non più sufficiente da solo. I sistemi HIDS/HIPS monitorano cambiamenti anomali nel sistema. Le soluzioni EPP (Endpoint Protection Platform) integrano antivirus, firewall, HIPS, DLP, protezione da attacchi fileless e controllo delle porte USB. Le tecnologie più evolute includono EDR (Endpoint Detection and Response), strumenti in grado di registrare log, analizzare comportamenti malevoli, attuare risposte automatiche e permettere attività di threat hunting. L’estensione di questo approccio porta allo XDR, che integra dati provenienti non solo dall’endpoint ma anche da server, rete e servizi cloud. Infine, le tecniche UEBA sfruttano analisi comportamentali basate su AI e machine learning per riconoscere attività anomale degli utenti.

## Progettare una rete sicura
La seconda parte della lezione introduce le basi per la progettazione di una rete sicura a partire dal modello OSI, che descrive il percorso dei dati attraverso i vari livelli: fisico, collegamento dati, rete, trasporto, sessione, presentazione e applicazione. A ogni livello corrispondono potenziali rischi e tecnologie specifiche. Al livello fisico rientrano cavi e onde radio, che possono essere potenziati tramite hub e ripetitori. Al livello data-link troviamo indirizzi MAC, frame e dispositivi come bridge e switch. Al livello network si gestiscono IP e routing tramite router o switch di livello 3. I livelli successivi riguardano il trasporto delle informazioni (TCP/UDP), la gestione delle sessioni, la traduzione dei formati dati e le applicazioni come HTTP, SMTP e FTP.

Si passa poi alle tipiche minacce che possono colpire gli switch: MAC flooding, con cui un attaccante riempie la tabella CAM provocando il passaggio in modalità non sicura; MAC spoofing, in cui si falsifica il proprio indirizzo MAC, spesso in combinazione con ARP spoofing; e la manomissione fisica, che mira a ottenere accesso diretto allo switch. Le contromisure includono limiti sugli indirizzi MAC, gestione della durata delle entry ARP e ispezioni ARP.

I router svolgono il ruolo di collegamento tra reti differenti e includono la gestione delle ACL (Access Control List), strumenti fondamentali per filtrare traffico in entrata e in uscita. Per strutturare reti più complesse si introducono le zone di rete, tra cui spicca la DMZ, un'area isolata che ospita server esposti verso l’esterno riducendo il rischio per la rete interna. Le extranet seguono lo stesso principio, ma forniscono accesso controllato a partner esterni.

Molto importanti sono anche i concetti di bastion host, ovvero macchine nella DMZ ridotte al minimo essenziale per ridurre il rischio di compromissione, e jumpbox, server induriti che fungono da unico punto di accesso verso la DMZ per gli amministratori, garantendo un ulteriore livello di isolamento.

Un altro pilastro della sicurezza è il Network Access Control (NAC), che verifica lo stato di sicurezza di ogni dispositivo prima di concedergli l’accesso alla rete. Il NAC può utilizzare agenti persistenti (installati stabilmente sul dispositivo) o non persistenti, attivati solo durante la procedura di verifica.

La gestione delle VLAN (Virtual LAN) permette di segmentare la rete migliorando prestazioni e sicurezza. Tuttavia, questa tecnologia introduce anche vulnerabilità come VLAN hopping, che può verificarsi tramite attacchi come lo switch spoofing (in cui un attaccante finge di essere uno switch) o il double tagging (che sfrutta tag VLAN multipli per attraversare le reti). La segmentazione è ulteriormente rafforzata tramite il subnetting, utile per ridurre broadcast, collisioni e migliorare la gestione degli indirizzi IP.

Il documento tratta anche il NAT (Network Address Translation) e la sua variante PAT, che permettono alle reti interne di utilizzare indirizzi privati, presentandosi all’esterno con un unico indirizzo pubblico. Questo meccanismo offre un ulteriore livello di sicurezza rendendo più difficile individuare i singoli dispositivi interni.

L’ultima sezione della lezione riguarda la telefonia, con riferimento ai sistemi PBX per la gestione delle linee interne e alle tecnologie VoIP, che sfruttano la rete dati per trasmettere comunicazioni vocali. Anche la telefonia, ormai integrata nella rete informatica, richiede accorgimenti di sicurezza per evitare intercettazioni, attacchi o manipolazioni del traffico vocale.

## Conclusioni
La lezione si conclude riepilogando i principali elementi affrontati: le tecnologie di sicurezza per gli endpoint (come firewall, IDS, DLP, BIOS sicuro, cifratura, EDR, EPP, UEBA) e i principi di progettazione di una rete sicura (modello OSI, gestione di switch e router, DMZ, NAC, VLAN, subnetting, NAT e sicurezza della telefonia). L’obiettivo complessivo è fornire una visione completa e integrata della sicurezza informatica, che unisce protezione degli utenti, dei dati e delle infrastrutture di rete.
