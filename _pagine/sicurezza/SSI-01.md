---
layout: page
title: Sicurezza nei Sistemi Informatici
args: (Cybersecurity)
permalink: /ssi-01/

---
Argomenti: 
- [1. Cybersecurity](#Cybersecurity)

## Cybersecurity

La cybersecurity rientra all’interno della più ampia “sicurezza informatica”, ossia la disciplina che protegge informazioni e sistemi da accessi non autorizzati, modifiche, interruzioni o distruzioni. La cybersecurity si concentra in particolare sugli aspetti digitali di questa protezione.

Uno dei primi pilastri affrontati è il modello CIA: Confidenzialità, Integrità e Disponibilità. La confidenzialità garantisce che le informazioni non vengano divulgate impropriamente; l’integrità assicura che non siano alterate senza autorizzazione; la disponibilità fa sì che dati e servizi siano sempre accessibili quando necessari. 

A questo si affianca la triade AAA: Autenticazione, Autorizzazione e Accounting. L’autenticazione verifica l’identità di un utente, l’autorizzazione stabilisce a quali risorse può accedere, mentre l’accounting assicura la tracciabilità delle attività (come con i file di log), includendo anche il principio del non ripudio.

Le principali minacce informatiche sono i malware, l’accesso non autorizzato ai sistemi, i guasti di sistema (come crash improvvisi) e il social engineering, cioè le tecniche psicologiche volte a manipolare un utente per ottenere informazioni sensibili o convincerlo a compiere azioni dannose.

Per ridurre l’impatto di queste minacce, esistono tre tipi di controlli di sicurezza: quelli fisici (barriere nel mondo reale, come serrature o guardiani), quelli tecnologici (software o hardware che implementano protezioni automatiche) e quelli amministrativi (politiche, regole e procedure interne di un’organizzazione).

I white hat sono hacker etici che aiutano a individuare vulnerabilità, mentre i black hat operano con fini dannosi. I grey hat si collocano in una zona intermedia, senza affiliazioni criminali ma potenzialmente oltre i limiti legali. Esistono anche figure come i blue hat (che possono agire per vendetta personale), i green hat (principianti, spesso detti “script kiddies”), i red hat (contro-hacker aggressivi) e gli hacker “elite”, particolarmente esperti. A questi si aggiungono gli hacktivist, spinti da cause politiche o sociali, la criminalità organizzata e i gruppi sponsorizzati dagli Stati, noti come APT (Advanced Persistent Threat).

La **Threat Intelligence** è la raccolta e l’analisi continua di informazioni sugli attacchi potenziali. Le fonti di intelligence possono essere proprietarie, closed-source o open-source, e vengono valutate in base a tempestività, pertinenza, efficacia e credibilità. Tra le piattaforme open-source più citate compare MISP, che consente di condividere indicatori di compromissione (IOC). Sono menzionati anche i CERT nazionali, strumenti OSINT e piattaforme come VirusTotal.

Il **Threat hunting** consiste la ricerca proattiva di minacce che non sono state rilevate dai normali sistemi di sicurezza. Il processo parte dalla formulazione di ipotesi basate sulla threat intelligence e continua con l’analisi di attori e possibili attività (TTP), proseguendo poi con l’indagine attraverso strumenti di monitoraggio. Tra le attività tipiche troviamo l’analisi del traffico di rete, la verifica dei processi attivi sugli host e l’identificazione di eventuali ulteriori sistemi compromessi. Il threat hunting è dispendioso in termini di tempo e risorse, ma contribuisce a ridurre la superficie di attacco e a individuare asset critici.

La Kill Chain di Lockheed Martin è un modello di attacco che descrive le fasi operative di un attaccante: dalla ricognizione iniziale alla weaponization, alla delivery del payload, sfruttamento (exploit), installazione, comando e controllo, fino alle azioni finali sugli obiettivi. A ciascuna fase corrispondono possibili contromisure, note come le “sei D”: detect, deny, disrupt, degrade, deceive e destroy.

Il framework MITRE ATT&CK, un catalogo dettagliato delle tattiche e tecniche usate dagli avversari, e il modello Diamond, che analizza un incidente collegando quattro elementi: avversario, vittima, infrastruttura e capacità. I due modelli possono essere combinati per ottenere un approccio più completo all’analisi delle intrusioni.
