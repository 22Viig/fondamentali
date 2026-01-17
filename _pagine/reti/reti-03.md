---
layout: page
title: Reti 3
args: (DNS, WHOIS, HTTP/S, FTP, SMTP, POP3, IMAP)
permalink: /reti-03/

---
Argomenti: 
- [1. DNS](#dns)
- [2. WHOIS](#whois)
- [3. HTTP/S](#https)
- [4. FTP](#ftp)
- [5. SMTP](#smtp)
- [6. POP3](#pop3)
- [7. IMAP](#imap)

## DNS

Il Domain Name System ( DNS ) è responsabile della corretta mappatura di un nome di dominio a un indirizzo IP.

Il DNS opera a livello applicativo, ovvero il livello 7 del modello ISO-OSI. Il traffico DNS utilizza la porta UDP 53 per impostazione predefinita e la porta TCP 53 come fallback predefinito. Esistono molti tipi di record DNS ; tuttavia, in questa attività ci concentreremo sui seguenti quattro:

- **Record A** : il record A (indirizzo) mappa un nome host a uno o più indirizzi IPv4. Ad esempio, è possibile impostare example.comla risoluzione in 172.17.2.172.

- **Record AAAA** : il record AAAA è simile al record A, ma è per IPv6. Ricorda che è AAAA (quad-A), poiché AA e AAA si riferiscono alle dimensioni di una batteria; inoltre, AAA si riferisce ad Autenticazione, Autorizzazione e Accounting ; nessuno dei due rientra nel DNS.

- **Record CNAME** : il record CNAME (Canonical Name) mappa un nome di dominio a un altro nome di dominio. Ad esempio, www.example.compuò essere mappato a example.como anche a example.org.

- **Record MX** : il record MX (Mail Exchange) specifica il server di posta responsabile della gestione delle email per un dominio.

Se vuoi cercare l'indirizzo IP di un dominio dalla riga di comando, puoi usare uno strumento come ```nslookup```.

## WHOIS

Abbiamo visto come un nome di dominio viene risolto in un indirizzo IP. Tuttavia, affinché ciò avvenga, è necessario che qualcuno abbia l'autorità di impostare i record A, AAAA e MX, tra gli altri record DNS per il dominio. Chiunque registri un nome di dominio ha questo potere. Pertanto, se si registra example.com, è possibile impostare qualsiasi record DNS valido per example.com.

Puoi registrare qualsiasi nome di dominio disponibile per uno o più anni. Devi pagare la quota annuale e sei tenuto a fornire informazioni di contatto accurate in qualità di registrante. Queste informazioni fanno parte dei dati disponibili tramite i record WHOIS e sono accessibili al pubblico. (Sebbene scritto in maiuscolo, WHOIS non è un acronimo; si pronuncia who is ). Tuttavia, non preoccuparti se desideri registrare un dominio senza rivelare pubblicamente le tue informazioni di contatto; puoi utilizzare uno dei servizi di privacy che nascondono tutte le tue informazioni dai record WHOIS.

## HTTP/S

Quando apri il tuo browser, utilizzi principalmente i protocolli HTTP e HTTPS. HTTP sta per Hypertext Transfer Protocol; la S di HTTPS sta per Secure. Questo protocollo si basa su TCP e definisce il modo in cui il tuo browser web comunica con i server web.

Alcuni dei comandi o metodi che il browser web invia comunemente al server web sono:

- **GET** recupera dati da un server, ad esempio un file HTML o un'immagine.
- **POST** ci consente di inviare nuovi dati al server, ad esempio inviando un modulo o caricando un file.
- **PUT** viene utilizzato per creare una nuova risorsa sul server e per aggiornare e sovrascrivere le informazioni esistenti.
- **DELETE**, come suggerisce il nome, viene utilizzato per eliminare un file o una risorsa specificata sul server.

HTTP e HTTPS utilizzano comunemente rispettivamente le porte TCP 80 e 443 e, meno comunemente, altre porte come 8080 e 8443.

## FTP

A differenza di HTTP , progettato per recuperare pagine web, il File Transfer Protocol ( FTP ) è progettato per trasferire file. Di conseguenza, FTP è molto efficiente per il trasferimento di file e, a parità di condizioni, può raggiungere velocità superiori a HTTP .

sempi di comandi definiti dal protocollo FTP sono:

- **USER** viene utilizzato per inserire il nome utente
- **PASS** serve per inserire la password
- **RETR**(recupera) viene utilizzato per scaricare un file dal server FTP al client.
- **STOR** (store) viene utilizzato per caricare un file dal client al server FTP .

Per impostazione predefinita, il server FTP ascolta sulla porta TCP 21; il trasferimento dei dati avviene tramite un'altra connessione dal client al server.


## SMTP

Come per la navigazione sul web e il download di file, anche l'invio di e-mail necessita di un protocollo specifico. Il Simple Mail Transfer Protocol ( SMTP ) definisce il modo in cui un client di posta comunica con un server di posta e come un server di posta comunica con un altro.

L'analogia con il protocollo SMTP è quando ci si reca all'ufficio postale locale per spedire un pacco. Si saluta l'impiegato, si indica dove si desidera spedire il pacco e si forniscono le informazioni del mittente prima di consegnarglielo. A seconda del Paese in cui ci si trova, potrebbe essere richiesto di mostrare un documento d'identità. Questo processo non è molto diverso da una sessione SMTP .

Presentiamo alcuni dei comandi utilizzati dal tuo client di posta quando trasferisce un'e-mail a un server SMTP :

- **HELO o EHLO** avvia una sessione SMTP
- **MAIL** FROMspecifica l'indirizzo email del mittente
- **RCPT TO** specifica l'indirizzo email del destinatario
- **DATA** indica che il client inizierà a inviare il contenuto del messaggio di posta elettronica
- **.** viene inviato su una riga a sé stante per indicare la fine del messaggio di posta elettronica

## POP3

Hai ricevuto un'e-mail e desideri scaricarla sul tuo client di posta locale. Il protocollo POP3 (Post Office Protocol versione 3 ) è progettato per consentire al client di comunicare con un server di posta e recuperare i messaggi di posta elettronica.

Senza entrare nei dettagli tecnici, un client di posta elettronica invia i messaggi tramite SMTP e li recupera tramite POP3 . SMTP è simile alla consegna di una busta o di un pacco all'ufficio postale, mentre POP3 è simile alla verifica della presenza di nuove lettere o pacchi nella casella di posta locale.

Alcuni comandi POP3 comuni sono:

- **USER username** identifica l'utente
- **PASS password** fornisce la password dell'utente
- **STAT** richiede il numero di messaggi e la dimensione totale
- **LIST** elenca tutti i messaggi e le loro dimensioni
- **RETR** message_number recupera il messaggio specificato
- **DELE** message_number contrassegna un messaggio per l'eliminazione
- **QUIT** termina la sessione POP3 applicando modifiche, come le eliminazioni

## IMAP

POP3 è sufficiente quando si lavora da un solo dispositivo, ad esempio il proprio client di posta elettronica preferito sul computer desktop. Tuttavia, cosa succede se si desidera controllare la posta elettronica dal computer desktop dell'ufficio e dal laptop o dallo smartphone? In questo scenario, è necessario un protocollo che consenta la sincronizzazione dei messaggi anziché eliminarli dopo averli scaricati. Una soluzione per mantenere una casella di posta sincronizzata su più dispositivi è l'Internet Message Access Protocol ( IMAP ).

IMAP consente di sincronizzare i messaggi letti, spostati ed eliminati. IMAP è molto comodo quando si controlla la posta elettronica tramite più client. A differenza di POP3 , che tende a ridurre al minimo lo spazio di archiviazione del server poiché la posta elettronica viene scaricata ed eliminata dal server remoto, IMAP tende a utilizzare più spazio di archiviazione poiché la posta elettronica viene conservata sul server e sincronizzata tra i client di posta elettronica.

I comandi del protocollo IMAP sono più complessi di quelli del protocollo POP3 . Di seguito riportiamo alcuni esempi:

- **LOGIN username password** autentica l'utente
- **SELECT mailbox** seleziona la cartella della cassetta postale con cui lavorare
- **FETCH mail_number data_item_name** Esempio fetch 3 body[]per recuperare il messaggio numero 3, intestazione e corpo.
- **MOVE sequence_set mailbox** sposta i messaggi specificati in un'altra casella di posta
- **COPY sequence_set data_item_name** copia i messaggi specificati in un'altra casella di posta
- **LOGOUT** si disconnette