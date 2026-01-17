---
layout: page
title: Reti 4
args: (TLS, HTTPS, SMTPS POP3S IMAPS, SSH, SFTP FTPS)
permalink: /reti-04/

---
Argomenti: 
- [1. DNS](#dns)
- [2. HTTPS](#https)
- [3. SMTPS POP3S IMAPS](#smtps-pop3s-imaps)
- [4. SSH](#ssh)
- [5. SFTP FTPS](#sftp-ftps)



## TLS

Un tempo, per leggere tutte le chat, le email e le password degli utenti della rete era sufficiente uno strumento di cattura dei pacchetti. Non era raro che un aggressore impostasse la propria scheda di rete in modalità promiscua, ovvero catturasse tutti i pacchetti, compresi quelli non destinati a essa. In seguito, analizzava tutte le catture dei pacchetti e otteneva le credenziali di accesso di vittime ignare. Non c'era nulla che un utente potesse fare per impedire che la propria password di accesso venisse inviata in chiaro. Oggigiorno, è diventato raro imbattersi in un servizio che invia credenziali di accesso in chiaro.

All'inizio degli anni '90, Netscape Communications riconobbe la necessità di comunicazioni sicure sul World Wide Web. Sviluppò quindi SSL (Secure Sockets Layer) e rilasciò SSL 2.0 nel 1995 come prima versione pubblica. Nel 1999 , l'Internet Engineering Task Force ( IETF ) sviluppò TLS (Transport Layer Security). Sebbene molto simile, TLS 1.0 era un aggiornamento di SSL 3.0 e offriva diverse misure di sicurezza migliorate. Nel 2018 , TLS ha subito una revisione significativa del suo protocollo ed è stato rilasciato TLS 1.3. Lo scopo non è ricordare le date esatte, ma comprendere la quantità di lavoro e tempo impiegati nello sviluppo della versione attuale di TLS , ovvero TLS 1.3. In oltre due decenni, ci sono state molte cose da imparare e da migliorare con ogni versione.

Come SSL, il suo predecessore, TLS è un protocollo crittografico che opera a livello di trasporto del modello OSI. Consente comunicazioni sicure tra un client e un server su una rete non sicura. Per sicurezza, intendiamo riservatezza e integrità; TLS garantisce che nessuno possa leggere o modificare i dati scambiati. Pensate a cosa significherebbe fare shopping online, servizi bancari online o persino inviare messaggi ed e-mail online senza poter garantire la riservatezza e l'integrità dei pacchetti di rete. Senza TLS , non saremmo in grado di utilizzare Internet per molte applicazioni che ormai fanno parte della nostra routine quotidiana.

Oggigiorno, decine di protocolli hanno ricevuto aggiornamenti di sicurezza con la semplice aggiunta di TLS . Tra gli esempi figurano HTTP , DNS , MQTT e SIP, che sono diventati HTTPS, DoT ( DNS over TLS ), MQTTS e SIPS, dove la "S" aggiunta sta per "sicuro" grazie all'utilizzo di SSL/ TLS . Nei prossimi articoli, esamineremo HTTPS, SMTPS, POP3S e IMAPS.

Il primo passo per ogni server (o client) che deve identificarsi è ottenere un certificato TLS firmato . Generalmente, l'amministratore del server crea una richiesta di firma del certificato (CSR) e la invia a un'autorità di certificazione ( CA ); la CA verifica la CSR ed emette un certificato digitale. Una volta ricevuto il certificato (firmato), può essere utilizzato per identificare il server (o il client) ad altri, che possono confermare la validità della firma. Affinché un host confermi la validità di un certificato firmato, i certificati delle autorità di firma devono essere installati sull'host. Nel mondo non digitale, questo è simile al riconoscimento dei timbri di varie autorità. Lo screenshot seguente mostra le autorità attendibili installate in un browser web.

In genere, per ottenere un certificato firmato è necessario pagare una quota annuale. Tuttavia, Let's Encrypt consente di ottenere il certificato firmato gratuitamente.

Infine, va sottolineato che alcuni utenti scelgono di creare un certificato autofirmato. Un certificato autofirmato non può dimostrare l'autenticità del server, poiché non è stato confermato da terze parti.

## HTTPS

HTTP si basa su TCP e utilizza la porta 80 per impostazione predefinita. Abbiamo anche visto come tutto il traffico HTTP venisse inviato in chiaro, in modo che chiunque potesse intercettarlo e monitorarlo. 

HTTPS è l'acronimo di Hypertext Transfer Protocol Secure. Si tratta sostanzialmente di HTTP su TLS. Di conseguenza, la richiesta di una pagina tramite HTTPS richiederà i seguenti tre passaggi (dopo aver risolto il nome di dominio):

Stabilire un handshake TCP a tre vie con il server di destinazione
Stabilire una sessione TLS
Comunicare utilizzando il protocollo HTTP; ad esempio, inviare richieste HTTP, come GET / HTTP/1.1

L'aggiunta di TLS a HTTP comporta la crittografia di tutti i pacchetti. Non possiamo più vedere il contenuto dei pacchetti scambiati a meno che non otteniamo l'accesso alla chiave privata. 

## SMTPS POP3S IMAPS

Aggiungere TLS a SMTP , POP3 e IMAP non è diverso dall'aggiungerlo a HTTP . Analogamente a come HTTP aggiunge una S per Secure e diventa HTTPS, SMTP , POP3 e IMAP diventano rispettivamente SMTPS, POP3S e IMAPS. L'utilizzo di questi protocolli su TLS non è diverso dall'utilizzo di HTTP su TLS ; pertanto, quasi tutti i punti della discussione su HTTPS si applicano a questi protocolli .

Le versioni sicure, ovvero tramite TLS , utilizzano per impostazione predefinita i seguenti numeri di porta TCP :

- HTTPS	443
- SMTPS	465 e 587
- POP3S	995
- IMAPS	993

## SSH

Sebbene sia molto comodo accedere e amministrare sistemi remoti, è rischioso quando tutto il traffico viene inviato in chiaro. È facile per chiunque monitori il traffico di rete entrare in possesso delle credenziali di accesso una volta che si utilizza telnet. Questo problema richiedeva una soluzione. Tatu Ylönen sviluppò il protocollo Secure Shell (SSH) e rilasciò SSH-1 nel 1995 come freeware. (È interessante notare che fu lo stesso anno in cui Netscape Communications rilasciò il protocollo SSL 2.0.) Una versione più sicura, SSH-2, fu definita nel 1996. Nel 1999 , gli sviluppatori di OpenBSD rilasciarono OpenSSH, un'implementazione open source di SSH. Oggigiorno, quando si utilizza un client SSH, è molto probabile che sia basato sulle librerie e sul codice sorgente di OpenSSH.

OpenSSH offre diversi vantaggi. Elencheremo alcuni punti chiave:

- Autenticazione sicura : oltre all'autenticazione basata su password, SSH supporta l'autenticazione a chiave pubblica e a due fattori.
- Riservatezza : OpenSSH fornisce crittografia end-to-end, proteggendo dalle intercettazioni. Inoltre, notifica le nuove chiavi server per proteggere dagli attacchi man-in-the-middle.
- Integrità : oltre a proteggere la riservatezza dei dati scambiati, la crittografia protegge anche l'integrità del traffico.
- Tunneling : SSH può creare un "tunnel" sicuro per instradare altri protocolli attraverso SSH. Questa configurazione crea una connessione simile a una VPN.
- Inoltro X11 : se ci si connette a un sistema simile a Unix con un'interfaccia utente grafica, SSH consente di utilizzare l'applicazione grafica sulla rete.

## SFTP FTPS

SFTP è l'acronimo di SSH File Transfer Protocol e consente il trasferimento sicuro di file. Fa parte della suite di protocolli SSH e condivide lo stesso numero di porta, 22. Se abilitato nella configurazione del server OpenSSH, è possibile connettersi utilizzando un comando come sftp username@hostname. Una volta effettuato l'accesso, è possibile impartire comandi come get filenamee put filenameper scaricare e caricare file, rispettivamente. In generale, i comandi SFTP sono di tipo Unix e possono differire dai comandi FTP .

SFTP non deve essere confuso con FTPS. Hai ragione a pensare che FTPS stia per File Transfer Protocol Secure. Come è protetto FTPS? Sì, hai ragione a ritenere che sia protetto tramite TLS , proprio come HTTPS. Mentre FTP utilizza la porta 21, FTPS di solito utilizza la porta 990. Richiede la configurazione di un certificato e può essere difficile da gestire anche con firewall rigidi, poiché utilizza connessioni separate per il controllo e il trasferimento dei dati.

Configurare un server SFTP è semplice come abilitare un'opzione nel server OpenSSH. Come HTTPS, SMTPS, POP3S, IMAPS e altri protocolli che si basano su TLS per la sicurezza, FTPS richiede un certificato TLS appropriato per funzionare in modo sicuro.