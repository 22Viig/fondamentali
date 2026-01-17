---
layout: page
title: Reti 3
args: (DNS, WHOIS)
permalink: /reti-03/

---
Argomenti: 
- [1. DNS](#dns)
- [2. WHOIS](#whois)
- [3. HTTPS/S](#https)

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