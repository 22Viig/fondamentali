---
layout: page
title: Reti 1
args: ()
permalink: /reti-01/

---

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

## TCP/IP 

Internet è l'interconnessione globale tra reti di telecomunicazioni e informatiche di natura e di estensione diversa, resa possibile da una suite di protocolli di rete comune chiamata "TCP/IP" dal nome dei due protocolli principali, il TCP e l'IP, che costituiscono la "lingua" comune con cui i computer connessi a Internet (gli host) sono interconnessi e comunicano tra loro a un livello superiore indipendentemente dalla loro sottostante architettura hardware e software, garantendo così l'interoperabilità tra sistemi e sottoreti fisiche diverse.

Il TCP/IP si basa sul modello OSI ed è composto dai seguenti livelli:

- Livello applicativo : i livelli di applicazione, presentazione e sessione del modello OSI, ovvero i livelli 5, 6 e 7, sono raggruppati nel livello applicativo nel modello TCP /IP.
- Livello di trasporto : questo è il livello 4.
- Livello Internet : questo è il livello 3. Il livello di rete del modello OSI è chiamato livello Internet nel modello TCP /IP.
- Livello di collegamento : questo è il livello 2.

## Indirizzi IP e subnet

Ogni host sulla rete necessita di un identificativo univoco per consentire agli altri host di comunicare con lui. Senza un identificativo univoco, l'host non può essere trovato senza ambiguità. Quando si utilizza la suite di protocolli TCP /IP, è necessario assegnare un indirizzo IP a ciascun dispositivo connesso alla rete.

Un indirizzo IP è composto da quattro ottetti, ovvero 32 bit. Essendo composto da 8 bit, un ottetto ci permette di rappresentare un numero decimale compreso tra 0 e 255. 

Gli indirizzi IP possono essere di due tipi:

- IPv4: formato più comune, composto da 4 numeri separati da punti (es. 192.168.1.1).
- IPv6: formato più recente, usato per superare la limitazione degli indirizzi IPv4 (es. 2001:0db8:85a3:0000:0000:8a2e:0370:7334).

Inoltre di indirizzi IP possono essere pubblici o privati.

RFC 1918 definisce i seguenti tre intervalli di indirizzi IP privati:

- 10.0.0.0- 10 255.255.255( 10/8)
- 172.16.0.0- 172.31.255.255( 172.16/12)
- 192.168.0.0- 192.168.255.255( 192.168/16)

I numeri 0 e 255 dell'ultimo ottetto di bit degli ip privati sono riservati rispettivamente agli indirizzi di rete e broadcast. In altre parole, 0 192.168.1.0è l'indirizzo di rete, mentre 255 192.168.1.255è l'indirizzo di broadcast. L'invio all'indirizzo di broadcast ha come target tutti gli host della rete. 