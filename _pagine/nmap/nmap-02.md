---
layout: page
title: Nmap 2
args: (Rilevamento del sistema operativo, Rilevamento del servizio e della versione, Forzare la scansione)
permalink: /nmap-02/

---

Argomenti: 
- [1. Rilevamento del sistema operativo](#rilevamento-del-sistema-operativo)
- [2. Rilevamento del servizio e della versione](#rilevamento-del-servizio-e-della-versione)
- [3. Forzare la scansione](#forzare-la-scansione)



## Rilevamento del sistema operativo

È possibile abilitare il rilevamento del sistema operativo aggiungendo l' opzione `-O`. Come suggerisce il nome, l'opzione di rilevamento del sistema operativo fa sì che Nmap si basi su vari indicatori per formulare un'ipotesi plausibile sul sistema operativo di destinazione.

## Rilevamento del servizio e della versione

Hai scoperto diverse porte aperte e vuoi sapere quali servizi sono in ascolto su di esse. `-sV` abilita il rilevamento della versione. Questa funzione è molto utile per raccogliere più informazioni sul tuo target con meno tasti.

E se fosse possibile avere entrambe le cose `-O`, `-sV` e anche di più, in un'unica opzione? Sarebbe `-A`. Questa opzione consente il rilevamento del sistema operativo, la scansione delle versioni e il traceroute, tra le altre cose.

## Forzare la scansione

Quando eseguiamo la nostra scansione delle porte, ad esempio usando `-sS`, c'è la possibilità che l'host di destinazione non risponda durante la fase di individuazione dell'host (ad esempio, un host non risponde alle richieste ICMP). Di conseguenza, Nmap contrassegnerà questo host come inattivo e non avvierà una scansione delle porte su di esso. Possiamo chiedere a Nmap di considerare tutti gli host come online ed eseguire la scansione delle porte su ogni host, compresi quelli che non hanno risposto durante la fase di individuazione dell'host. Questa scelta può essere attivata aggiungendo l' opzione `-Pn`.
