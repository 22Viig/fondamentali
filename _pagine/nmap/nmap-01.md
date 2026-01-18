---
layout: page
title: Nmap 1
args: (Scansione della rete locale, Scansione di una rete remota, Scansione delle porte TCP, Scansione SYN, Scansione delle porte UDP)
permalink: /nmap-01/

---

Argomenti: 
- [1. Scansione della rete locale](#scansione-della-rete-locale)
- [2. Scansione di una rete remota](#scansione-di-una-rete-remota)
- [3. Scansione SYN](#scansione-syn)
- [4. Scansione delle porte UDP](#scansione-delle-porte-udp)


## Scansione della rete locale

In questo contesto, utilizziamo il termine "locale" per riferirci alla rete a cui siamo direttamente connessi, come una rete Ethernet o WiFi. Nella prima dimostrazione, analizzeremo la rete WiFi a cui siamo connessi. 

Il nostro indirizzo IP è 192.168.66.89, e stiamo eseguendo la scansione della 192.168.66.0/24rete. 

Il comando da eseguire è `nmap -sn 192.168.66.0/24` . 

Nmap utilizza diversi modi per specificare i suoi obiettivi:

- Intervallo IP utilizzando `-`: se si desidera eseguire la scansione di tutti gli indirizzi IP da 192.168.0.1 a 192.168.0.10, è possibile scrivere192.168.0.1-10

- Sottorete IP utilizzando `/`: se si desidera eseguire la scansione di una sottorete, è possibile esprimerla come 192.168.0.1/24, e ciò equivarrebbe a192.168.0.0-255

Poiché eseguiamo la scansione della rete locale, a cui siamo connessi tramite Ethernet o WiFi, possiamo cercare gli indirizzi MAC dei dispositivi. Di conseguenza, possiamo risalire ai produttori delle schede di rete, un'informazione utile in quanto può aiutarci a indovinare il tipo di dispositivo di destinazione.

Durante la scansione di una rete connessa direttamente, Nmap inizia inviando richieste ARP. Quando un dispositivo risponde alla richiesta ARP, Nmap lo etichetta con la dicitura "Host is up" (Host attivo).

## Scansione di una rete remota

onsideriamo il caso di una rete "remota". In questo contesto, "remota" significa che almeno un router separa il nostro sistema da questa rete. Di conseguenza, tutto il traffico verso i sistemi di destinazione deve passare attraverso uno o più router. A differenza della scansione di una rete locale, non possiamo inviare una richiesta ARP al sistema di destinazione.

Il nostro sistema ha l'indirizzo IP 192.168.66.89e appartiene alla 192.168.66.0/24rete. Possiamo eseguire la scansione della rete di destinazione, 192.168.11.0/24 dove due o più router (hop) separano il nostro sistema locale dagli host di destinazione con questo comando: `nmap -sn 192.168.11.0/24` .

## Scansione delle porte TCP

Il modo più semplice ed elementare per sapere se una porta TCP è aperta è tentare di telnetaccedervi. Se si preferisce eseguire una scansione con un client Telnet, provare a stabilire una connessione TCP con ogni porta di destinazione. In altre parole, si tenta di completare l' handshake TCP a tre vie con ogni porta di destinazione; tuttavia, solo le porte TCP aperte risponderanno in modo appropriato e consentiranno di stabilire una connessione TCP . Questa procedura non è molto diversa dalla scansione di connessione di Nmap.

La scansione di connessione può essere attivata tramite `-sT`. Tenta di completare l'handshake TCP a tre vie con ogni porta TCP di destinazione. Se la porta TCP risulta aperta e Nmap si connette correttamente, Nmap interromperà la connessione stabilita.

## Scansione SYN

A differenza della scansione di connessione, che tenta di connettersi alla porta TCP di destinazione , ovvero di completare un handshake a tre vie, la scansione SYN esegue solo il primo passaggio: invia un pacchetto TCP SYN. ​​Di conseguenza, l'handshake a tre vie TCP non viene mai completato. Il vantaggio è che si prevede che ciò comporti un minor numero di log poiché la connessione non viene mai stabilita, e quindi è considerata una scansione relativamente furtiva. È possibile selezionare la scansione SYN utilizzando il flag `-sS`.

## Scansione delle porte UDP

Sebbene la maggior parte dei servizi utilizzi TCP per la comunicazione, molti utilizzano UDP. Tra gli esempi figurano DNS, DHCP, NTP (Network Time Protocol), SNMP (Simple Network Management Protocol) e VoIP (Voice over IP). UDP non richiede di stabilire una connessione e di interromperla in seguito. Inoltre, è molto adatto per le comunicazioni in tempo reale, come le trasmissioni in diretta. Tutti questi sono motivi per considerare la scansione e l'individuazione di servizi in ascolto sulle porte UDP.

Nmap offre la possibilità `-sU` per scansionare i servizi UDP.