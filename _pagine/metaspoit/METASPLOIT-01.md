---
layout: page
title: Metasploit 1
args: ()
permalink: /METASPLOIT-01/

---

Argomenti: 
- [1. Metasploit](#metasploit)


## Metasploit

Metasploit Framework è un insieme di strumenti che consentono la raccolta di informazioni, la scansione, lo sfruttamento, lo sviluppo di exploit, il post-sfruttamento e altro ancora. Sebbene l'utilizzo principale di Metasploit Framework si concentri sul dominio dei penetration test, è utile anche per la ricerca di vulnerabilità e lo sviluppo di exploit.



I componenti principali del Metasploit Framework possono essere riassunti come segue;

- msfconsole : l'interfaccia principale della riga di comando.

- Modules : moduli di supporto quali exploit, scanner, payload, ecc.

- Tools : strumenti autonomi che facilitano la ricerca di vulnerabilità, la valutazione delle vulnerabilità o i penetration test. Alcuni di questi strumenti sono msfvenom, pattern_create e pattern_offset. Tratteremo msfvenom in questo modulo, ma pattern_create e pattern_offset sono strumenti utili nello sviluppo di exploit, il che esula dallo scopo di questo modulo.

## msfconsole

Utilizzando Metasploit Framework, interagirai principalmente con la console di Metasploit . Puoi avviarla dal terminale utilizzando il comando `msfconsole` . La console sarà la tua interfaccia principale per interagire con i diversi moduli di Metasploit Framework. I moduli sono piccoli componenti all'interno del framework Metasploit, progettati per eseguire un'attività specifica, come lo sfruttamento di una vulnerabilità, la scansione di un obiettivo o l'esecuzione di un attacco brute-force.

Prima di addentrarci nei moduli, sarebbe utile chiarire alcuni concetti ricorrenti: vulnerabilità, exploit e payload.

- **Exploit**: un frammento di codice che sfrutta una vulnerabilità presente nel sistema di destinazione.

- **Vulnerabilità**: difetto di progettazione, codifica o logica che colpisce il sistema di destinazione. Lo sfruttamento di una vulnerabilità può comportare la divulgazione di informazioni riservate o consentire all'aggressore di eseguire codice sul sistema di destinazione.

- **Payload**: un exploit sfrutta una vulnerabilità. Tuttavia, se vogliamo che l'exploit ottenga il risultato desiderato (ottenere l'accesso al sistema di destinazione, leggere informazioni riservate, ecc.), dobbiamo utilizzare un payload. I payload sono il codice che verrà eseguito sul sistema di destinazione.
