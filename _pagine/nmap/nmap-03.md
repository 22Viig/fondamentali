---
layout: page
title: Nmap 3
args: (Tempistica, Verbosità e debug, Salvataggio della scansione)
permalink: /nmap-03/

---

Argomenti: 
- [1. Tempistica](#tempistica)
- [2. Verbosità e debug](#verbosità-e-debug)
- [3. Salvataggio della scansione](#salvataggio-della-scansione)


## Tempistica

Nmap offre diverse opzioni per controllare la velocità e la tempistica della scansione.

Eseguire la scansione alla velocità normale potrebbe attivare un IDS o altre soluzioni di sicurezza. È ragionevole controllare la velocità di una scansione. Nmap offre sei modelli di temporizzazione, i cui nomi dicono tutto: paranoico (0), furtivo (1), educato (2), normale (3), aggressivo (4) e folle (5). È possibile selezionare il modello di temporizzazione tramite il nome o il numero. Ad esempio, è possibile aggiungere `-T0` (o `-T 0`) o `-T paranoid` per optare per la velocità più lenta.

Una seconda opzione utile è il numero di sonde di servizio parallele. Il numero di sonde parallele può essere controllato con `--min-parallelism <numprobes>` e `--max-parallelism <numprobes>`. Queste opzioni possono essere utilizzate per impostare un minimo e un massimo per il numero di sonde di porta TCP e UDP attive simultaneamente per un gruppo host. Per impostazione predefinita, nmapcontrollerà automaticamente il numero di sonde parallele. Se la rete ha prestazioni scadenti, ad esempio perde pacchetti, il numero di sonde parallele potrebbe scendere a uno; inoltre, se la rete funziona in modo impeccabile, il numero di sonde parallele può raggiungere diverse centinaia.

Un'opzione utile simile è la funzione `--min-rate <number>` e `--max-rate <number>`. Come indicano i nomi, possono controllare la velocità minima e massima di nmapinvio dei pacchetti. La velocità è espressa come numero di pacchetti al secondo . Vale la pena ricordare che la velocità specificata si applica all'intera scansione e non a un singolo host.

L'ultima opzione che tratteremo in questa attività è `--host-timeout <time>`. Questa opzione specifica il tempo massimo che si è disposti ad attendere ed è adatta per host lenti o con connessioni di rete lente.

## Verbosità e debug

In alcuni casi, la scansione impiega molto tempo per completarsi o per produrre un output che verrà visualizzato sullo schermo. Inoltre, a volte potrebbe essere interessante avere maggiori informazioni in tempo reale sullo stato di avanzamento della scansione. Il modo migliore per ottenere maggiori aggiornamenti su ciò che sta accadendo è abilitare l'output dettagliato aggiungendo `-v`. Si consideri il seguente output del terminale che mostra la scansione di rete ripetuta due volte. Nel primo caso, abbiamo optato per il livello di dettaglio predefinito.

Molto probabilmente, l' -vopzione è più che sufficiente per un output dettagliato; tuttavia, se non sei ancora soddisfatto, puoi aumentare il livello di verbosità aggiungendo un'altra "v", ad esempio `-vv` o `-vvvv`. Puoi anche specificare direttamente il livello di verbosità, ad esempio `-v2` e `-v4`. Puoi persino aumentare il livello di verbosità premendo "v" dopo l'avvio della scansione.

Se tutta questa verbosità non soddisfa le tue esigenze, devi considerare l' output `-d` a livello di debug. Allo stesso modo, puoi aumentare il livello di debug aggiungendo una o più "d" o specificando direttamente il livello di debug. Il livello massimo è `-d9`; prima di sceglierlo, assicurati di essere pronto a migliaia di informazioni e righe di debug.

## Salvataggio della scansione

In molti casi, potremmo aver bisogno di salvare i risultati della scansione. Nmap ci fornisce diversi formati. I tre più utili sono l'output normale (di facile comprensione), l'output XML e l'output grepable, in riferimento al comando `grep`. È possibile selezionare il formato del report di scansione come segue:

- `-oN <filename>-` Uscita normale
- `-oX <filename>-` Output XML
- `-oG <filename>-` `grep` output -able (utile per grepe awk)
- `-oA <basename>-` Output in tutti i principali formati
