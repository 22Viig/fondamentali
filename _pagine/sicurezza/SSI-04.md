---
layout: page
title: Sicurezza nei Sistemi Informatici 4
args: (Malaware, Virus informatici, Worm, Trojan, Ransomware, Spyware, Spam)
permalink: /ssi-04/

---
Argomenti: 
- [1. Malaware](#malaware)
- [2. Virus informatici](#virus-informatici)
- [3. Worm](#worm)
- [4. Trojan](#trojan)
- [5. Ransomware](#ransomware)
- [6. Spyware](#spyware)
- [6. Spam](#spyware)

## Malaware

Il termine malware deriva dall’unione di malicious e software e indica qualsiasi programma dannoso progettato per alterare, interrompere o compromettere il corretto funzionamento di un computer o di un sistema informatico. Il malware può assumere forme diverse e può agire con finalità differenti: dal danneggiamento dei dati alla sottrazione di informazioni sensibili, fino all’estorsione economica. In qualunque caso, ciò che accomuna tutte le varianti è la capacità di operare all’insaputa dell’utente, sfruttando vulnerabilità del sistema o comportamenti imprudenti.

Il malware può raggiungere le vittime tramite:

- software scaricato da fonti non sicure,
- email e sistemi di messaggistica,
- supporti rimovibili come USB o DVD,
- tecniche come il watering hole, in cui siti legittimi vengono compromessi per infettare i visitatori,
- exploit kit presenti su server compromessi,
- typosquatting, che sfrutta errori di digitazione degli URL per reindirizzare a siti malevoli.

### Botnet, DDoS e attacchi connessi

Le botnet sono reti di dispositivi infettati controllati come un’unica entità. Ogni dispositivo compromesso è definito bot o zombie. Le botnet vengono spesso utilizzate per eseguire attacchi DDoS, cioè sovraccaricare un server con un numero enorme di richieste per renderlo inaccessibile.

### Intercettazione attiva, escalation dei privilegi e backdoor

L’intercettazione attiva (MITM) avviene quando un attaccante si inserisce nella comunicazione tra due sistemi, intercettando o modificando i dati trasmessi.
L’escalation dei privilegi consiste nell’ottenere accesso a risorse protette tramite vulnerabilità o configurazioni errate.
Le backdoor sono accessi nascosti al sistema, spesso inseriti dagli stessi sviluppatori, mentre le logic bomb sono porzioni di codice che si attivano al verificarsi di condizioni specifiche.

### Sintomi di infezione, rimozione e prevenzione

Fra i sintomi più comuni di un’infezione troviamo rallentamenti improvvisi, malfunzionamenti, apertura di finestre indesiderate, utilizzo anomalo delle risorse o comportamenti strani del sistema.
La rimozione del malware richiede vari passaggi: identificare i sintomi, isolare il dispositivo, disattivare il ripristino, eseguire scansioni, riparare il sistema e programmare verifiche periodiche.
La prevenzione si basa su:

- aggiornamento costante dei sistemi,
- uso di antivirus e antimalware moderni,
- filtri antispam,
- formazione degli utenti,
- soluzioni basate su AI/ML per il rilevamento comportamentale,
- scansioni periodiche per individuare rootkit.

### APT

Le APT rappresentano una forma di attacco avanzato e continuativo, tipica dei gruppi criminali o di cyber-spionaggio. Operano in modo silenzioso per lunghi periodi e seguono fasi precise: infezione iniziale tramite dropper, mantenimento e rafforzamento dell’accesso, movimento laterale nella rete e infine esecuzione degli obiettivi (furto dati, sabotaggio, ecc.). Utilizzano tecniche come masquerading, DLL sideloading, process hollowing e strumenti già presenti nel sistema (LOTL – Living Off The Land).


## Virus informatici

I virus rappresentano una delle prime e più note forme di malware. Si tratta di codice maligno che viene eseguito inconsapevolmente dall’utente e che infetta un computer ogni volta che il programma ospite viene avviato. Un virus, infatti, non è un programma autonomo: necessita di un file o di un’applicazione che lo “trasporti”.
Esistono molte varianti:

- Boot sector virus: si insedia nel primo settore del disco rigido e viene caricato all’avvio del sistema. È particolarmente dannoso poiché agisce in una fase critica del caricamento del sistema operativo.
- Macrovirus: si diffonde tramite documenti Office contenenti macro malevole, spesso inviate per email o scaricate inconsapevolmente.
- Program virus: infetta file eseguibili o applicazioni.
- Multipartite virus: combinano le tecniche dei boot virus e dei program virus, rendendo più complessa la rimozione.
- Virus criptati, polimorfi e metamorfici: evoluzioni sofisticate che mirano a evitare la rilevazione da parte degli antivirus. I virus polimorfi modificano la propria firma a ogni replica, mentre quelli metamorfici riescono addirittura a riscrivere il proprio codice per ogni iterazione.
- Stealth e armored virus: presentano funzionalità avanzate di autoprotezione, offuscamento e resistenza alla rimozione.
- Hoax: forma particolare che non è un vero virus, ma un inganno volto a convincere l’utente a eseguire azioni dannose sulla propria macchina.

## Worm

Diversamente dai virus, i worm sono malware che si autoreplicano senza necessità di intervento umano e senza richiedere un programma ospite. La loro caratteristica principale è la capacità di diffondersi attraverso la rete sfruttando vulnerabilità dei sistemi o protocolli. La rapidità di propagazione può generare congestioni di rete e provocare un impatto significativo su infrastrutture critiche. Worm noti come Nimda o Conficker hanno causato danni su scala globale sfruttando debolezze dei sistemi Windows.

## Trojan

I trojan sono programmi malevoli che si presentano sotto forma di software legittimo o desiderabile. L’utente viene indotto a installarli volontariamente, pensando di eseguire un’applicazione innocua. Una volta attivi, i trojan possono compiere varie azioni: aprire backdoor, rubare dati, installare ulteriori malware.
Tra le varianti principali:

- Rogueware: falsi antivirus che simulano minacce inesistenti e spingono l’utente ad acquistare licenze fraudolente.
- Remote Access Trojan (RAT): strumenti che forniscono all’attaccante il controllo remoto del sistema compromesso, spesso tramite un server dedicato di Command & Control (C2).

## Ransomware

Ransomware e modelli di business criminale
Il ransomware è oggi una delle minacce più diffuse e pericolose. Agisce bloccando l’accesso al sistema o cifrando i file della vittima, richiedendo poi un riscatto per il loro recupero. Le forme più moderne includono:

- Doxing: minaccia di divulgare dati personali rubati per aumentare la pressione psicologica.
- Eliminazione delle Shadow Copy: tecnica usata per impedire il ripristino dei file tramite copie locali.
- Ransomware-as-a-Service (RaaS): modello commerciale in cui sviluppatori di malware affittano programmi a criminali meno competenti, abbassando la barriera d’ingresso al cybercrimine.

Il ransomware si sta diffondendo anche verso dispositivi IoT, solitamente meno protetti, diventando così una minaccia trasversale a molti ambiti.

## Spyware

Gli spyware raccolgono informazioni sull’utente, monitorandone attività, abitudini o dati sensibili senza consenso.
Un caso particolare è il keylogger, che registra tutto ciò che viene digitato sulla tastiera, incluso credenziali e messaggi privati.

L’adware, invece, mostra pubblicità invasive e può tracciare il comportamento dell’utente per finalità di marketing. Il grayware rappresenta una categoria intermedia: non è esplicitamente malevolo, ma può ridurre la sicurezza del sistema.

## Spam

Lo spam è la diffusione incontrollata di messaggi indesiderati, spesso tramite server SMTP mal configurati (open mail relay). Si parla di spim quando lo stesso fenomeno riguarda la messaggistica istantanea.

Il cryptojacking è una minaccia crescente: il sistema della vittima viene usato segretamente per attività di mining di criptovalute. Tra i sintomi figurano rallentamenti improvvisi, uso anomalo della CPU, surriscaldamento e traffico di rete insolito verso siti di mining. Tecnologie come l’Intel TDT supportano la rilevazione tramite telemetria hardware.

