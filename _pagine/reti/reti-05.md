---
layout: page
title: Reti 5
args: (VPN)
permalink: /reti-05/

---
Argomenti: 

- [1. VPN](#vpn)


## VPN
onsideriamo un'azienda con uffici dislocati geograficamente in diverse sedi. È possibile connettere tutti i suoi uffici e le sue sedi alla filiale principale in modo che qualsiasi dispositivo possa accedere alle risorse condivise come se si trovasse fisicamente nella filiale principale? La risposta è sì; inoltre, la soluzione più economica sarebbe quella di configurare una rete privata virtuale ( VPN ) utilizzando l'infrastruttura Internet. In questo caso, l'attenzione si concentra sulla V di Virtual (Virtuale) in VPN .

Quando Internet è stata progettata, la suite di protocolli TCP /IP si concentrava sulla consegna dei pacchetti. Ad esempio, se un router va fuori servizio, i protocolli di routing possono adattarsi e scegliere un percorso diverso per inviare i pacchetti. Se un pacchetto non viene riconosciuto, TCP dispone di meccanismi integrati per rilevare questa situazione e reinviarlo. Tuttavia, non esiste alcun meccanismo per garantire che tutti i dati in uscita o in entrata da un computer siano protetti da divulgazione e alterazione. Una soluzione popolare era la configurazione di una connessione VPN . L'attenzione qui è rivolta alla P di Private in VPN .

Quasi tutte le aziende richiedono uno scambio di informazioni "privato" nella propria rete virtuale. Pertanto, una VPN offre una soluzione molto comoda e relativamente economica. I requisiti principali sono la connettività Internet e un server e un client VPN .

Il diagramma di rete sottostante mostra un esempio di un'azienda con due filiali remote connesse alla filiale principale. Un client VPN nelle filiali remote dovrebbe connettersi al server VPN nella filiale principale. In questo caso, il client VPN crittograferà il traffico e lo trasmetterà alla filiale principale tramite il tunnel VPN stabilito (mostrato in blu). Il traffico VPN è limitato alle linee blu; le linee verdi trasporteranno il traffico VPN decrittografato.

Una volta stabilito un tunnel VPN , tutto il nostro traffico Internet verrà solitamente instradato sulla connessione VPN , ovvero attraverso il tunnel VPN . Di conseguenza, quando proviamo ad accedere a un servizio Internet o a un'applicazione web, questi non vedranno il nostro indirizzo IP pubblico, ma quello del server VPN . Questo è il motivo per cui alcuni utenti Internet si connettono tramite VPN per aggirare le restrizioni geografiche. Inoltre, l'ISP locale vedrà solo il traffico crittografato, il che limita la sua capacità di censurare l'accesso a Internet.