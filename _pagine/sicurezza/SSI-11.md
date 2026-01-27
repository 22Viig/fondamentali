---
layout: page
title: Sicurezza nei Sistemi Informatici 11
args: (Aggiornamenti, File system, Virtualizzazione)
permalink: /SSI-011/

---
Argomenti: 
- [1. Aggiornamenti](#aggiornamenti)
- [2. File system](#file-system)
- [3. Virtualizzazione](#Virtualizzazione)

La lezione si apre introducendo il concetto di hardening, ovvero l’insieme delle operazioni applicate a sistemi, servizi e dispositivi per ridurre la superficie d’attacco e limitare i rischi derivanti da configurazioni deboli o vulnerabilità note. L’obiettivo del hardening è minimizzare il numero di servizi esposti e potenziali punti di ingresso per un aggressore. In questo contesto viene introdotto il principio di Least Functionality, che prevede di fornire ai sistemi solo le funzionalità necessarie, disattivando componenti superflui. Si distingue inoltre tra Least Functionality e Least Privilege: il primo riguarda i servizi disponibili, il secondo i privilegi concessi agli utenti e ai processi.

Un elemento essenziale è la baseline di sicurezza, un modello standard replicabile su più sistemi che garantisce un livello uniforme di protezione. Per distribuire configurazioni e policy omogenee su larga scala si utilizzano strumenti come Microsoft Endpoint Configuration Manager (MECM), che permette di applicare impostazioni, controlli e aggiornamenti a intere flotte di macchine.

La sicurezza delle applicazioni viene gestita tramite due metodi principali: whitelist e blacklist. La whitelist è un approccio molto restrittivo che permette l’esecuzione solo delle applicazioni esplicitamente autorizzate, bloccando tutto il resto. La blacklist funziona in modo opposto: vieta solo applicazioni specifiche, consentendo implicitamente tutto il resto. Da un punto di vista operativo, la whitelist rappresenta il metodo più sicuro, sebbene richieda più gestione.

La lezione introduce inoltre il concetto di Trusted Operating System (TOS). Un TOS è un sistema operativo che rispetta criteri internazionali di sicurezza definiti dal Common Criteria, adottato da oltre 30 nazioni. Sistemi come Windows 7+, macOS 10.6+, RedHat Enterprise Linux e FreeBSD rientrano nelle piattaforme considerate “trustate”. Un TOS assicura sicurezza multilivello, gestione avanzata dei permessi e robustezza contro attacchi mirati.

## Aggiornamenti
La gestione delle patch è uno dei pilastri dell’hardening. Le patch risolvono vulnerabilità o problemi specifici, mentre gli aggiornamenti possono includere nuovi componenti funzionali. La lezione distingue tra Security Update, Critical Update, Service Pack, Windows Update e Driver Update. Per gestire correttamente il ciclo di vita delle patch si utilizza il Patch Management, che comprende pianificazione, test, distribuzione e verifica. Questo processo richiede inventari aggiornati degli asset, registri delle patch e verifiche della compatibilità. Esistono anche script utilizzati per verificare offline la patch compliance, specialmente in contesti aziendali.

Nei sistemi Windows, un ruolo chiave è svolto dalle Group Policy (criteri di gruppo). Queste consentono di applicare impostazioni di sicurezza a gruppi di utenti o computer, definendo regole come password, permessi, configurazioni di rete o restrizioni operative. I GPO (Group Policy Object) si compongono di due parti: configurazione utente e configurazione computer. Le GPO vengono spesso affiancate ai Security Template, modelli di sicurezza già pronti che possono essere importati e applicati facilmente. Anche in questo contesto ritorna il concetto di baseline, utile per individuare discrepanze rispetto allo standard previsto.

## File system
La sicurezza di un sistema passa anche dal modo in cui i file sono memorizzati. Vengono presentati i principali file system: NTFS, FAT32, ext4, HFS+ e APFS. NTFS è considerato il più sicuro tra quelli Microsoft perché supporta permessi avanzati, crittografia e compressione. L’hardening sui dischi rigidi consiste in attività ricorrenti: rimozione dei file temporanei, verifica e riparazione del file system, deframmentazione, backup e esercitazioni di ripristino.

Un capitolo importante riguarda la supply chain, cioè la catena di approvvigionamento tecnologico. La Due Diligence sui fornitori serve a verificare la solidità del loro programma di cybersecurity, la conformità a standard come ISO 27001, 31000 o 9001, le politiche di retention e privacy dei dati, la capacità di gestire incidenti e il loro livello di reputazione. La sicurezza dell'hardware è un punto critico della supply chain: la lezione parla delle trusted foundry, fonderie affidabili che producono microprocessori in ambienti sicuri, evitando rischi di compromissione.

Un ruolo importante è ricoperto dal concetto di Root of Trust (ROT), un insieme di componenti hardware e firmware progettati per garantire un avvio e una gestione sicura del sistema. Tra questi troviamo:

- TPM (Trusted Platform Module), un microchip che memorizza chiavi, hash, certificati e dati crittografici usati per il secure boot e la cifratura completa del disco.
- HSM (Hardware Security Module), dispositivo esterno che gestisce generazione e protezione delle chiavi crittografiche.
- Approcci come BYOK (Bring Your Own Key) e HYOK (Hold Your Own Key), che definiscono chi controlla fisicamente e logicamente le chiavi di cifratura.

La sicurezza si estende anche al firmware, con tecnologie come UEFI, Secure Boot, Measured Boot, Attestation ed eFuse. Le eFuse, ad esempio, sono piccoli circuiti che, una volta programmati, non possono essere modificati e forniscono un livello di antimanomissione. A ciò si aggiunge la protezione dell’esecuzione tramite enclavi sicure, esecuzione atomica e crittografia del bus.

## Virtualizzazione
La parte finale della lezione affronta il tema della virtualizzazione, sempre più presente nei contesti aziendali. Una macchina virtuale (VM) è un computer emulato che può essere un sistema completo o un’applicazione isolata. Le VM vengono gestite tramite gli hypervisor, che assegnano risorse come CPU, memoria e disco ai vari sistemi guest. La lezione distingue tra:

- VM di sistema, che emulano un intero sistema operativo e sono persistenti;
- VM di processo, che eseguono solo una singola applicazione e sono non persistenti.

Gli hypervisor possono essere di:

- Tipo 1 (bare-metal), installati direttamente sull’hardware;
- Tipo 2, installati come applicazioni dentro un sistema operativo host.

La virtualizzazione introduce però nuove minacce. Una delle più pericolose è il VM Escape, ovvero la possibilità per un attaccante di evadere dalla VM e interagire con l’hypervisor o altre VM. Esistono anche rischi legati a:

- Elasticità e scalabilità, se la gestione non è sicura;
- Dati residui, che possono rimanere in una VM dopo il deprovisioning;
- Privilege escalation, che può sfruttare vulnerabilità dell’hypervisor;
- Migrazione live delle VM, durante la quale un attacco Man-in-the-Middle potrebbe intercettare i dati.

Per mettere in sicurezza le VM occorre aggiornare costantemente l’hypervisor, limitare la connettività tra guest e host, applicare il principio di least functionality anche alle macchine virtuali, distribuire le VM su più server per evitare il VM sprawl e cifrare i file che contengono le VM.
