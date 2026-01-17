---
layout: page
title: Reti 1
args: (modello OSI, TCP/IP)
permalink: /reti-01/

---
Argomenti: 
- [1. Modello OSI](#1-modello-OSI)
- [2. TCP/IP](#2-tcp/ip)
- [3. UDP](#3-udp)

## Modello OSI

Al fine di comprendere il funzionamento delle reti è necessario conoscere il [modello OSI](https://it.wikipedia.org/wiki/Modello_OSI). Nella tabella sottostante si riassumono i livelli che costituiscono il modello e le loro funzioni.


| Numero di livello | Nome del livello             | Funzione principale                                       | Esempi di protocolli e standard       |   |
|------------------|------------------------------|-----------------------------------------------------------|---------------------------------------|---|
| Livello 7        | Livello applicativo          | Fornitura di servizi e interfacce alle applicazioni       | HTTP , FTP , DNS , POP3 , SMTP , IMAP |   |
| Livello 6        | Livello di presentazione     | Codifica, crittografia e compressione dei dati            | Unicode, MIME , JPEG, PNG, MPEG       |   |
| Livello 5        | Livello di sessione          | Creazione, mantenimento e sincronizzazione delle sessioni | NFS, RPC                              |   |
| Livello 4        | Livello di trasporto         | Comunicazione end-to-end e segmentazione dei dati         | UDP , TCP                             |   |
| Livello 3        | Livello di rete              | Indirizzamento logico e routing tra reti                  | IP, ICMP, IPSec                       |   |
| Livello 2        | Livello di collegamento dati | Trasferimento dati affidabile tra nodi adiacenti          | Ethernet (802.3), Wi-Fi (802.11)      |   |
| Livello 1        | Livello fisico                | Mezzi fisici di trasmissione dei dati                     | Segnali elettrici, ottici e wireless  |   |

### Livello 1 - Physical

Questo livello è uno dei più facili da comprendere. In parole povere, fa riferimento ai componenti fisici dell'hardware utilizzato nelle reti ed è il livello più basso che si possa trovare. I dispositivi utilizzano segnali elettrici per trasferire dati tra loro in un sistema di numerazione binario (1 e 0).

### Livello 2 - Data link

Il livello di collegamento dati si concentra sull'indirizzamento fisico della trasmissione. Riceve un pacchetto dal livello di rete (incluso l'indirizzo IP del computer remoto) e aggiunge l' indirizzo MAC (Media Access Control) fisico dell'endpoint ricevente. All'interno di ogni computer abilitato alla rete è presente una scheda di interfaccia di rete ( NIC ) dotata di un indirizzo MAC univoco per identificarlo.

Gli indirizzi MAC sono impostati dal produttore e letteralmente impressi sulla scheda; non possono essere modificati, sebbene possano essere falsificati. Quando le informazioni vengono inviate attraverso una rete, è in realtà l'indirizzo fisico a essere utilizzato per identificare esattamente dove inviare le informazioni.

Inoltre, è compito del livello di collegamento dati presentare i dati in un formato adatto alla trasmissione.

### Livello 3 - Network

Routing Information Protocol

Il terzo livello del modello OSI (livello di rete) è dove avviene la magia del routing e del riassemblaggio dei dati (da questi piccoli blocchi a quelli più grandi). In primo luogo, il routing determina semplicemente il percorso ottimale in cui questi blocchi di dati devono essere inviati.

Mentre alcuni protocolli a questo livello determinano esattamente qual è il percorso "ottimale" che i dati dovrebbero seguire per raggiungere un dispositivo, dovremmo conoscerne l'esistenza solo in questa fase del modulo di rete. In breve, questi protocolli includono OSPF (Open Shortest Path First) e RIP ( Routing Information Protocol ) . I fattori che determinano il percorso da seguire sono i seguenti:

Qual è il percorso più breve? Cioè quello che prevede il minor numero di dispositivi che il pacchetto deve attraversare.
Qual è il percorso più affidabile? Ci sono mai stati pacchetti persi su quel percorso?
Quale percorso ha la connessione fisica più veloce? Ad esempio, un percorso utilizza una connessione in rame (più lenta) o una fibra (considerevolmente più veloce)?
A questo livello, tutto viene gestito tramite indirizzi IP come 192.168.1.100. Dispositivi come i router in grado di recapitare pacchetti utilizzando indirizzi IP sono noti come dispositivi di Livello 3, perché sono in grado di operare al terzo livello del modello OSI.

### Livello 4 - Trasport

Il Livello 4 del modello OSI svolge un ruolo fondamentale nella trasmissione dei dati in rete e può essere un po' difficile da comprendere. Quando i dati vengono inviati tra dispositivi, seguono uno dei due protocolli disponibili, che vengono decisi in base a diversi fattori:

TCP
UDP
Cominciamo con TCP . Il Transmission Control Protocol ( TCP ). Come suggerisce il nome, questo protocollo è progettato pensando all'affidabilità e alla garanzia. Questo protocollo riserva una connessione costante tra i due dispositivi per il tempo necessario all'invio e alla ricezione dei dati .

Non solo, ma il TCP integra il controllo degli errori nella sua progettazione. Il controllo degli errori è il modo in cui il TCP può garantire che i dati inviati dai piccoli blocchi nel livello di sessione (livello 5) siano stati ricevuti e riassemblati nello stesso ordine.

Passiamo ora allo User Data Protocol (o UDP in breve). Questo protocollo  non è avanzato quanto il suo fratello, il protocollo TCP . Non vanta le numerose funzionalità offerte dal TCP , come il controllo degli errori e l' affidabilità. Infatti, tutti i dati inviati tramite UDP vengono inviati al computer, indipendentemente dal fatto che arrivino o meno. Non c'è sincronizzazione tra i due dispositivi né garanzia; speriamo solo per il meglio e incrociamo le dita.

UDP è utile in situazioni in cui vengono inviati piccoli frammenti di dati. Ad esempio, protocolli utilizzati per la rilevazione dei dispositivi ( ARP e DHCP di cui abbiamo parlato nella lezione 2 - Introduzione alle LAN) o file di grandi dimensioni come lo streaming video (in cui è accettabile che una parte del video sia pixelata. I pixel sono solo frammenti di dati persi!).

### Livello 5 - Session

Una volta che i dati sono stati correttamente tradotti o formattati dal livello di presentazione (livello 6), il livello di sessione (livello 5) inizierà a creare e mantenere la connessione con l'altro computer a cui i dati sono destinati. Quando viene stabilita una connessione, viene creata una sessione. Finché questa connessione è attiva, lo è anche la sessione.

Il livello di sessione è anche responsabile della chiusura della connessione se non viene utilizzata per un certo periodo di tempo o se viene persa. Inoltre, una sessione  può  contenere dei "checkpoint", in base ai quali, in caso di perdita di dati, è necessario inviare solo i dati più recenti, risparmiando larghezza di banda. 

Ciò che vale la pena notare è che le sessioni sono uniche, il che significa che i dati non possono essere trasmessi tra sessioni diverse, ma solo tra ogni sessione.

### Livello 6 - Presentation

Il livello 6 del modello OSI è il livello in cui inizia la standardizzazione. Poiché gli sviluppatori software possono sviluppare in modo diverso qualsiasi software, come un client di posta elettronica, i dati devono comunque essere gestiti allo stesso modo, indipendentemente dal funzionamento del software.

Questo livello funge da traduttore per i dati da e verso il livello applicativo (livello 7). Il computer ricevente comprenderà anche i dati inviati a un computer in un formato e destinati a un altro formato. Ad esempio, quando si invia un'e-mail, l'altro utente potrebbe utilizzare un client di posta elettronica diverso dal tuo, ma il contenuto dell'e-mail dovrà comunque essere visualizzato nello stesso modo.

A questo livello si verificano funzionalità di sicurezza come la crittografia dei dati (come HTTPS quando si visita un sito sicuro).


### Livello 7 - Application

Il livello applicativo del modello OSI è quello con cui avrete più familiarità. Questa familiarità è dovuta al fatto che il livello applicativo è il livello in cui sono definiti protocolli e regole per determinare come l'utente deve interagire con i dati inviati o ricevuti.

Le applicazioni di uso quotidiano , come i client di posta elettronica, i browser o i software di navigazione dei file server come FileZilla, forniscono un'interfaccia utente grafica (GUI) intuitiva che consente agli utenti di interagire con i dati inviati o ricevuti. Altri protocolli includono il DNS (Domain Name System ) , che è il  modo in cui gli indirizzi dei siti web vengono tradotti in indirizzi IP.

## TCP/IP

TCP  (o  T rasmission  C ontrol  Protocol in breve) è un'altra di queste regole utilizzate nelle reti.


Questo protocollo è molto simile al modello OSI di cui abbiamo già parlato nella terza aula di questo modulo. Il protocollo TCP /IP è costituito da quattro livelli e si può sostenere che sia solo una versione riassunta del modello OSI. Questi livelli sono: Applicazione, Trasporto, Internet, Interfaccia di rete.

Una caratteristica distintiva del TCP è che è  basato sulla connessione , il che significa che il TCP deve stabilire una connessione tra un client e un dispositivo che funge da server prima che i dati vengano inviati.

I pacchetti TCP contengono diverse sezioni di informazioni, note come intestazioni, che vengono aggiunte tramite incapsulamento. Nell'elenco seguente, spieghiamo alcune delle intestazioni più importanti:

- **Source Port**: 	Questo valore è la porta aperta dal mittente per inviare il pacchetto TCP . Questo valore viene scelto casualmente (tra le porte da 0 a 65535 che non sono già in uso al momento).

- **Destination Port**:	Questo valore è il numero di porta su cui un'applicazione o un servizio è in esecuzione sull'host remoto (quello che riceve i dati); ad esempio, un server web in esecuzione sulla porta 80. A differenza della porta di origine, questo valore non viene scelto casualmente.

- **Source IP**:	Questo è l'indirizzo IP del dispositivo che invia il pacchetto.
IP di destinazione	Questo è l'indirizzo IP del dispositivo a cui è destinato il pacchetto.

- **Destination IP**: Quando si verifica una connessione, al primo dato trasmesso viene assegnato un numero casuale. Spiegheremo questo concetto più in dettaglio più avanti.

- **Sequence Number**: Dopo che a un dato è stato assegnato un numero di sequenza, il numero del dato successivo avrà il numero di sequenza + 1. Più avanti spiegheremo questo concetto in modo più approfondito.

- **Acknowledgement Number**: Questo valore è ciò che garantisce l'integrità TCP . Viene eseguito un calcolo matematico in cui l'output viene memorizzato. Quando il dispositivo ricevente esegue il calcolo matematico, i dati devono essere corrotti se l'output è diverso da quello inviato.

- **Checksum**: Questo valore è ciò che garantisce l'integrità TCP . Viene eseguito un calcolo matematico in cui l'output viene memorizzato. Quando il dispositivo ricevente esegue il calcolo matematico, i dati devono essere corrotti se l'output è diverso da quello inviato.

- **Data**	In questa intestazione vengono memorizzati i dati, ovvero i byte di un file che viene trasmesso.

- **Flag**: Questa intestazione determina come il pacchetto deve essere gestito da entrambi i dispositivi durante il processo di handshake. Flag specifici determineranno comportamenti specifici, che spiegheremo più avanti.

Il Three-way handshake comunica utilizzando alcuni messaggi speciali: la tabella seguente ne evidenzia i principali:

- 1	**SIN**	Un messaggio SYN è il pacchetto iniziale inviato da un client durante l'handshake. Questo pacchetto viene utilizzato per avviare una connessione e sincronizzare i due dispositivi (ne parleremo più avanti).
- 2	**SYN/ACK**	Questo pacchetto viene inviato dal dispositivo ricevente (server) per confermare il tentativo di sincronizzazione da parte del client.
- 3	**ACK**	Il pacchetto di conferma può essere utilizzato dal client o dal server per confermare che una serie di messaggi/pacchetti è stata ricevuta correttamente.
- 4	**DATI**	Una volta stabilita la connessione, i dati (ad esempio i byte di un file) vengono inviati tramite il messaggio "DATA".
- 5	**FIN**	Questo pacchetto viene utilizzato per chiudere in modo pulito (corretto) la connessione dopo che è stata completata.
- 6	**RST**	Questo pacchetto interrompe bruscamente tutte le comunicazioni. Questa è l'ultima risorsa e indica che si è verificato un problema durante il processo. Ad esempio, se il servizio o l'applicazione non funziona correttamente o se il sistema presenta guasti, come risorse insufficienti. 

A tutti i dati inviati viene assegnata una sequenza numerica casuale e i dati vengono ricostruiti utilizzando questa sequenza numerica e incrementandola di 1. Entrambi i computer devono concordare sulla stessa sequenza numerica affinché i dati vengano inviati nell'ordine corretto. Questo ordine viene concordato in tre fasi:

* **SYN** - Cliente: ecco il mio numero di sequenza iniziale (ISN) da  cronometrare SYN con (0)
* **SYN/ACK** - Server: ecco il mio numero di sequenza iniziale (ISN) con cui  effettuare la sincronizzazione (5.000) e  riconosco la tua sequenza numerica iniziale (0)
* **ACK** - Cliente:  riconosco il tuo numero di sequenza iniziale (ISN) di (5.000), ecco alcuni dati che corrispondono al mio ISN+1 (0 + 1)

### UDP

L'  User Datagram  Protocol ( UDP ) è un altro protocollo  utilizzato per comunicare dati tra dispositivi .

A differenza del suo fratello TCP , UDP è un  protocollo stateless  che non richiede una connessione costante tra i due dispositivi per l'invio dei dati. Ad esempio, non si verifica l'handshake a tre vie, né vi è alcuna sincronizzazione tra i due dispositivi.

 In particolare, UDP viene utilizzato in situazioni in cui le applicazioni possono tollerare la perdita di dati (come lo streaming video o la chat vocale) o in scenari in cui una connessione instabile non è la soluzione definitiva.

