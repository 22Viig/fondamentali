---
layout: page
title: Sicurezza nei Sistemi Informatici 6
args: (Software Development Life Cycle, Linee guida, Principali vulnerabilità)
permalink: /ssi-06/

---
Argomenti: 
- [1. Software Development Life Cycle](#software-development-life-cycle)
- [2. Linee guida](#linee-guida)
- [3. Principali vulnerabilità](#Principali-vulnerabilità)

## Software Development Life Cycle

Alla base di un software sicuro c’è la comprensione del Software Development Life Cycle (SDLC), il processo organizzato che guida la creazione, il mantenimento e il ritiro di un’applicazione. Il SDLC può essere strutturato secondo diversi modelli.

### Modello Waterfall

Il modello Waterfall segue un flusso sequenziale e lineare: si parte dall’analisi dei requisiti, si passa alla progettazione, all’implementazione, alla verifica e integrazione, fino alla distribuzione, manutenzione e infine al ritiro del prodotto. È un approccio adatto a progetti piccoli e ben definiti, con tempi e budget fissi, e in cui il cliente è poco presente durante lo sviluppo. Si rivela utile anche quando sono richiesti elevati livelli di sicurezza, poiché la rigidità del processo riduce la possibilità di introdurre modifiche tardive e potenziali vulnerabilità.

### Modello Agile

Al contrario, un approccio più dinamico è quello Agile, basato su cicli iterativi e incrementali. Agile privilegia la flessibilità e la capacità di adattarsi alle esigenze mutevoli del cliente o del mercato. Questo modello richiede continui rilasci, revisioni rapide e collaborazione continua tra gli attori del progetto, ma comporta anche la necessità di prestare maggiore attenzione agli aspetti di sicurezza, che devono essere integrati in ogni iterazione.

### DevOps e Secure DevOps

Un’evoluzione naturale di Agile è il paradigma DevOps, che favorisce un’interazione stretta tra sviluppo e operations, con l’obiettivo di rilasciare software in modo più rapido ed efficiente. A questo modello si affianca Secure DevOps, che integra anche i controlli di sicurezza nelle pipeline di lavoro, includendo automazione, integrazione continua, sistemi immutabili e infrastruttura come codice (IaC). Questo consente di anticipare la scoperta di vulnerabilità, riducendo costi e rischi.

## Linee guida

### Threat Modeling

Il Threat Modeling è un processo che identifica, classifica e analizza le potenziali minacce, valutandone il rischio e definendo le contromisure. È una fase strategica che permette di progettare il software tenendo conto dei potenziali attacchi e delle aree critiche da proteggere. 

### Security by Design

Il principio di Security by Design afferma che la sicurezza deve essere incorporata già nelle fasi iniziali di progettazione. A questo si affiancano diversi principi:

- Least Privilege: utenti e processi devono avere solo i privilegi strettamente necessari a svolgere le proprie funzioni.
- Defense in Depth: applicare controlli di sicurezza su più livelli per evitare che una singola vulnerabilità comprometta l’intero sistema.
- Input Validation: validare sempre gli input dell’utente per prevenire attacchi basati sull’inserimento di dati malevoli.
- Riduzione della superficie d’attacco: limitare tutte le aree in cui l’applicazione è esposta all’interazione esterna, riducendo così le possibilità di attacco.
- Security by Default: impostare configurazioni predefinite sicure, poiché gli utenti raramente le modificano.
- Code Signing: firmare digitalmente il software per verificarne l’integrità.
- Fail Securely: assicurarsi che, in caso di errore, l’applicazione fallisca in modo sicuro, senza esporre vulnerabilità.

Oltre a questi principi, è fondamentale rilasciare rapidamente le patch di sicurezza, utilizzare SDK e librerie affidabili e adottare strumenti di test adeguati.

### Metodi di testing

La lezione presenta vari metodi di testing per individuare vulnerabilità o comportamenti anomali:

- Test di sistema: include test black‑box (senza conoscere il codice), white‑box (con visione completa del codice) e grey‑box (con conoscenza parziale).
- Structured Exception Handling (SEH): definisce come l’applicazione deve reagire in presenza di errori a runtime o sintattici.
- Analisi statica: studia il codice senza eseguirlo, individuando vulnerabilità logiche o di programmazione.
- Analisi dinamica: verifica il comportamento dell’applicazione durante l’esecuzione, includendo tecniche come il fuzzing, che introduce dati casuali per stressare il sistema.
- Stress testing: simula condizioni estreme, come elevato traffico, per verificare la resistenza dell’applicazione, ad esempio contro attacchi DDoS.

Il testing è essenziale per identificare vulnerabilità prima del rilascio del software.

## Principali vulnerabilità

### Buffer overflow

Il buffer overflow si verifica quando un processo memorizza dati al di fuori del buffer allocato, sovrascrivendo aree di memoria adiacenti. Gli attaccanti sfruttano la vulnerabilità per inserire codice malevolo, come avviene nello stack buffer overflow, possibile quando il buffer si trova nello stack. La tecnica “Smash the Stack” prevede il riempimento del buffer con una lunga sequenza di NOP, al fine di facilitare l’esecuzione del payload. Per mitigare questa vulnerabilità, vengono utilizzate tecniche come l’Address Space Layout Randomization (ASLR), che randomizza la posizione delle zone di memoria, rendendo più difficile prevedere dove iniettare il codice.

### XSS (Cross‑Site Scripting)
L’attacco XSS consiste nell’inserire codice HTML o JavaScript in un sito considerato affidabile, che verrà poi eseguito dal browser dell’utente. Si distinguono tre tipi principali:

- Stored XSS, in cui il codice malevolo è permanentemente inserito nel server;
- Reflected XSS, che viene eseguito solo dopo aver cliccato un link contenente il payload;
- DOM‑based XSS, che sfrutta la manipolazione del Document Object Model.

Le contromisure includono la codifica dell’output, la validazione degli input e l’utilizzo di impostazioni di sicurezza del browser.

### XSRF (Cross‑Site Request Forgery)
Nell’XSRF l’attaccante sfrutta la fiducia che un sito web ripone nel browser dell’utente già autenticato, inducendolo ad eseguire azioni involontarie. Le difese principali includono l’uso di token univoci, cookie a breve durata e cifratura.

### SQL Injection

Si tratta di una delle vulnerabilità più diffuse e pericolose. Consiste nell’inserire comandi SQL malevoli tramite campi input dell’utente, manipolando query legittime. Gli attaccanti possono ottenere accessi non autorizzati, eliminare tabelle (come nel caso della query DROP TABLE USERS), o estrarre dati sensibili usando operatori come UNION SELECT. Per difendersi è fondamentale validare gli input, applicare il principio del least privilege, cifrare i dati e mantenere aggiornati i database.

### Vulnerabilità XML

Gli attacchi XML includono:

- XML Bomb, che sfrutta entità espandibili per creare file enormi che consumano memoria fino al crash del sistema.
- XXE (XML External Entity), che permette di accedere a file locali del server tramite entità esterne.

Le contromisure prevedono limitazioni sulla dimensione dei documenti XML, sanitizzazione degli input e disabilitazione delle entità esterne.

### Race Conditions

Si verificano quando due o più processi accedono contemporaneamente alla stessa risorsa, causando comportamenti non previsti. Tra gli esempi spiccano il bug Dirty COW, che consentiva escalation di privilegi tramite accessi simultanei, o vulnerabilità legate al Time of Check to Time of Use (TOCTTOU). Le soluzioni includono meccanismi di blocco, check finali immediatamente prima dell’uso e progettazione non sequenziale delle operazioni.