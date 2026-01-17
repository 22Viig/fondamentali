---
layout: page
title: Reti 2
args: (DHCP, ARP, Traceroute, Instradamento, NAT)
permalink: /reti-02/

---
Argomenti: 
- [1. DHCP](#dhcp)
- [2. ARP](#arp)
- [3. Traceroute](#traceroute)
- [4. Instradamento](#instradamento)
- [5. NAT](#nat)


## DHCP

Ogni volta che vogliamo accedere a una rete, dobbiamo almeno configurare quanto segue:

- Indirizzo IP insieme alla maschera di sottorete
- Router (o gateway)
- server DNS

Ogni volta che colleghiamo il nostro dispositivo a una nuova rete, le configurazioni di cui sopra devono essere impostate in base alla nuova rete. Configurare manualmente queste impostazioni è una buona opzione, soprattutto per i server. Non è previsto che i server cambino rete; non è necessario portare con sé il controller di dominio e collegarlo al Wi-Fi del bar. Inoltre, altri dispositivi devono connettersi ai server e aspettarsi di trovarli a indirizzi IP specifici.

Avere un modo automatizzato per configurare i dispositivi connessi offre numerosi vantaggi. In primo luogo, ci eviterebbe di dover configurare manualmente la rete, un aspetto estremamente importante, soprattutto per i dispositivi mobili. In secondo luogo, ci eviterebbe di dover gestire conflitti di indirizzo, ovvero quando due dispositivi sono configurati con lo stesso indirizzo IP. Un conflitto di indirizzi IP impedirebbe agli host coinvolti di utilizzare le risorse di rete; questo vale sia per le risorse locali che per Internet. La soluzione risiede nell'utilizzo del protocollo DHCP (Dynamic Host Configuration Protocol ). DHCP è un protocollo a livello di applicazione che si basa su UDP ; il server è in ascolto sulla porta UDP 67 e il client invia dati dalla porta UDP 68. Smartphone e laptop sono configurati per utilizzare DHCP per impostazione predefinita.

DHCP segue quattro fasi: Scoperta, Offerta, Richiesta e Riconoscimento (DORA):

- **DHCP Discover** : il client trasmette un messaggio DHCPDISCOVER alla ricerca del server DHCP locale , se presente.
- **Offerta DHCP** : il server risponde con un messaggio DHCPOFFER con un indirizzo IP disponibile per l'accettazione da parte del client.
- **Richiesta DHCP** : il client risponde con un messaggio DHCPREQUEST per indicare che ha accettato l'IP offerto.
- **DHCP Acknowledge** : il server risponde con un messaggio DHCPACK per confermare che l'indirizzo IP offerto è ora assegnato a questo client.

## ARP

Quando due host comunicano su una rete, un pacchetto IP viene incapsulato in un frame di collegamento dati durante il suo percorso attraverso il livello 2. Ricordiamo che i due livelli di collegamento dati più comuni che utilizziamo sono Ethernet (IEEE 802.3) e WiFi (IEEE 802.11). 

Ogni volta che un host deve comunicare con un altro host sulla stessa rete Ethernet o WiFi, deve inviare il pacchetto IP all'interno di un frame di livello di collegamento dati. Sebbene conosca l'indirizzo IP dell'host di destinazione, deve cercarne l'indirizzo MAC per poter creare l'intestazione di collegamento dati corretta.

Un indirizzo MAC è un numero a 48 bit solitamente rappresentato in notazione esadecimale; ad esempio,  ```7C:DF:A1:D3:8C:5Ce ```  ```44:DF:65:D8:FE:6C ``` sono due indirizzi MAC sulla mia rete.

Tuttavia, i dispositivi sulla stessa rete Ethernet non hanno bisogno di conoscere costantemente i rispettivi indirizzi MAC; devono solo conoscerli durante la comunicazione. Tutto ruota attorno agli indirizzi IP. Consideriamo questo scenario: colleghi il tuo dispositivo a una rete e, se la rete dispone di un server DHCP, il dispositivo viene automaticamente configurato per utilizzare un gateway (router) e un server DNS specifici. Di conseguenza, il dispositivo conosce l'indirizzo IP del server DNS per risolvere qualsiasi nome di dominio; inoltre, conosce l'indirizzo IP del router quando deve inviare pacchetti su Internet. In tutti questi scenari, non viene rivelato alcun indirizzo MAC. Tuttavia, due dispositivi sulla stessa rete Ethernet non possono comunicare senza conoscere i rispettivi indirizzi MAC.

Il protocollo ARP (Address Resolution Protocol) consente di trovare l'indirizzo MAC di un altro dispositivo sulla rete Ethernet. Un host con l'indirizzo IP  ```192.168.66.89 ``` desidera comunicare con un altro sistema con lo stesso indirizzo IP  ```192.168.66.1 ```. Invia una richiesta ARP chiedendo all'host con l'indirizzo IP  ```192.168.66.1 ``` di rispondere. La richiesta ARP viene inviata dall'indirizzo MAC del richiedente all'indirizzo MAC broadcast,  ```ff:ff:ff:ff:ff:ff ```. La risposta ARP è arrivata poco dopo e l'host con l'indirizzo IP  ```192.168.66.1 ``` ha risposto con il proprio indirizzo MAC. Da questo punto, i due host possono scambiarsi frame a livello di collegamento dati.

Una richiesta ARP o una risposta ARP non sono incapsulate in un pacchetto UDP o IP, ma direttamente in un frame Ethernet.

## ICMP

L'Internet Control Message Protocol (ICMP) è utilizzato principalmente per la diagnostica di rete e la segnalazione degli errori. Due comandi molto diffusi si basano su ICMP e sono fondamentali per la risoluzione dei problemi di rete e la sicurezza della rete. I comandi sono:

- ```ping```: Questo comando utilizza ICMP per testare la connettività a un sistema di destinazione e misura il tempo di andata e ritorno (RTT). In altre parole, può essere utilizzato per verificare se il sistema di destinazione è attivo e se la sua risposta può raggiungere il nostro sistema.

- ```traceroute```: Questo comando viene eseguito ```traceroute``` su sistemi Linux e UNIX-like e ```tracert``` su sistemi MS Windows. Utilizza ICMP per scoprire il percorso dall'host alla destinazione.

### Ping

Il ping comando invia una richiesta di eco ICMP (tipo ICMP 8). Il computer sul lato ricevente risponde con una risposta ICMP Echo (tipo ICMP 0).

### Traceroute

Come possiamo fare in modo che ogni router tra il nostro sistema e un sistema di destinazione si riveli?

Il protocollo Internet ha un campo chiamato Time-to-Live ( TTL ) che indica il numero massimo di router che un pacchetto può attraversare prima di essere scartato. Il router decrementa il TTL del pacchetto di uno prima di inviarlo. Quando il TTL raggiunge zero, il router scarta il pacchetto e invia un messaggio ICMP Time Exceeded (ICMP Type 11). (In questo contesto, il "tempo" è misurato in numero di router, non in secondi.)


## Instradamento

Internet è composta da milioni di router e miliardi di dispositivi. Un utente può raggiungere un server web, ma affinché ciò avvenga, ogni router lungo il percorso deve inviare i pacchetti tramite il collegamento appropriato. Ovviamente, esiste più di un percorso, ovvero una rotta, che collega l'utente al server web. Abbiamo bisogno di un algoritmo di routing che consenta al router di determinare quale collegamento utilizzare.
- 
**OSPF (Open Shortest Path First)** : OSPF è un protocollo di routing che consente ai router di condividere informazioni sulla topologia di rete e di calcolare i percorsi più efficienti per la trasmissione dei dati. Ciò avviene tramite lo scambio di aggiornamenti sullo stato dei link e delle reti connesse tra i router. In questo modo, ogni router dispone di una mappa completa della rete e può determinare i percorsi migliori per raggiungere qualsiasi destinazione.

- **EIGRP (Enhanced Interior Gateway Routing Protocol)** : EIGRP è un protocollo di routing proprietario di Cisco che combina aspetti di diversi algoritmi di routing. Consente ai router di condividere informazioni sulle reti che possono raggiungere e sui costi (come larghezza di banda o ritardo) associati a tali percorsi. I router utilizzano quindi queste informazioni per scegliere i percorsi più efficienti per la trasmissione dei dati.

- **BGP (Border Gateway Protocol)** : BGP è il protocollo di routing principale utilizzato su Internet. Consente a diverse reti (come quelle degli Internet Service Provider) di scambiare informazioni di routing e stabilire percorsi per il trasferimento dei dati tra queste reti. BGP contribuisce a garantire che i dati possano essere instradati in modo efficiente su Internet, anche quando attraversano più reti.

- **RIP (Routing Information Protocol)** : RIP è un protocollo di routing semplice, spesso utilizzato nelle reti di piccole dimensioni. I router che eseguono RIP condividono informazioni sulle reti che possono raggiungere e sul numero di hop (router) necessari per raggiungerle. Di conseguenza, ogni router crea una tabella di routing basata su queste informazioni, scegliendo i percorsi con il minor numero di hop per raggiungere ciascuna destinazione.

## NAT

Con l'aumento del numero di dispositivi connessi a Internet, dai computer e smartphone alle telecamere di sicurezza e alle lavatrici, era chiaro che lo spazio di indirizzamento IPv4 si sarebbe esaurito rapidamente. Una soluzione all'esaurimento degli indirizzi è il Network Address Translation (NAT).

L'idea alla base del NAT è quella di utilizzare un unico indirizzo IP pubblico per fornire accesso a Internet a molti indirizzi IP privati . In altre parole, se si collega un'azienda con venti computer, è possibile fornire accesso a Internet a tutti i venti computer utilizzando un unico indirizzo IP pubblico anziché venti. (Nota: tecnicamente parlando, il numero di indirizzi IP è sempre espresso come una potenza di due. Per essere tecnicamente precisi, con il NAT si riservano due indirizzi IP pubblici anziché trentadue. Di conseguenza, si sarebbero risparmiati trenta indirizzi IP pubblici. )

A differenza del routing, che è il modo naturale per instradare i pacchetti verso l'host di destinazione, i router che supportano NAT devono trovare un modo per tracciare le connessioni in corso. Di conseguenza, i router che supportano NAT mantengono una tabella che traduce gli indirizzi di rete tra reti interne ed esterne. Generalmente, la rete interna utilizza un intervallo di indirizzi IP privati, mentre la rete esterna utilizza un indirizzo IP pubblico.

