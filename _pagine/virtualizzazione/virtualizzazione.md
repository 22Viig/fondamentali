---
layout: page
title: Virtualizzazione 
args: (virtualizzazione, hypervisor, container)
permalink: /virtualizzazione-01/

---

## La virtualizzazione

Nella sua forma più elementare, la virtualizzazione è il concetto di incapsulamento delle capacità e delle caratteristiche di una macchina fisica in un ambiente virtuale, noto come macchina virtuale .

Ma perché è necessaria la virtualizzazione? Per la maggior parte delle organizzazioni e degli individui, la virtualizzazione nasce dalle seguenti esigenze:

- **Riduzione delle spese**: i server fisici possono essere costosi e la virtualizzazione può ridurre il numero di server o di altro hardware, o addirittura eliminare completamente l’hardware fisico dall’infrastruttura di un’azienda.

- **Scalabilità**: senza una corretta implementazione di DevOps , potrebbe essere difficile per un’azienda scalare le risorse con l’aumento dell’utilizzo dei server. La virtualizzazione semplifica questo processo e consente di delegare le risorse di un server a macchine virtuali in base alle esigenze e all’utilizzo. 

- **Efficienza**: come la scalabilità, anche la virtualizzazione può semplificare la riduzione delle risorse assegnate a una macchina virtuale in caso di utilizzo ridotto.

### Tecnologia di virtualizzazione

A questo punto, potreste chiedervi come sia possibile la virtualizzazione; sebbene si tratti di una questione complessa, in questa sala analizzeremo le diverse tecnologie e piattaforme, esaminando brevemente come interagiscono con il sistema operativo host sottostante.

Per rispondere alla domanda precedente, è necessario ampliare la definizione di virtualizzazione. Formalmente, la virtualizzazione astrae o crea un  livello di astrazione  sull'hardware del computer. Un livello di astrazione consente di suddividere un singolo dispositivo in più computer virtuali, noti anche come macchine virtuali (VM).

In termini più semplici, ciò significa che la macchina virtuale avrà accesso a  risorse logiche  astratte dalle  risorse fisiche .

## Hypervisor

Un hypervisor offre la possibilità di creare il livello di astrazione tra hardware e software. Generalmente, un hypervisor include anche un'applicazione o un software di gestione che fornisce un'interfaccia tra l'utente finale e il livello di astrazione per creare o caricare macchine virtuali.

Gli hypervisor si dividono in due categorie, determinate dalla loro posizione rispetto all'hardware. Possono creare direttamente un sistema operativo leggero sull'hardware che funge da hypervisor oppure aggiungere un hypervisor come applicazione su un sistema operativo preesistente.

### Hypervisor tipo 1

Gli hypervisor di tipo 1, noti anche come  hypervisor bare metal, creano un livello di astrazione direttamente tra hardware e macchine virtuali, senza un sistema operativo comune. L'hypervisor è invece il sistema operativo ed è spesso  headless , con solo un portale di gestione basato sul web accessibile da remoto. Questi hypervisor sono progettati per la scalabilità e per distribuire un gran numero di macchine virtuali contemporaneamente. Sono estremamente leggeri per dedicare la maggior parte delle risorse alle macchine virtuali. 

Esempi di hypervisor di tipo 1 sono VMware ESXi, Proxmox, VMware vSphere, Xen e KVM.

### Hypervisor tipo 2

Gli hypervisor di tipo 2 , noti anche come hypervisor ospitati , creano un livello di astrazione da un'applicazione software basata su un sistema operativo preesistente. A differenza degli hypervisor di tipo 1, gli hypervisor di tipo 2 sono spesso gestiti direttamente dall'applicazione tramite un'interfaccia grafica utente (GUI) . Questi hypervisor sono spesso progettati per utenti finali o singoli individui come gli sviluppatori e non sono specificamente progettati per eseguire un gran numero di macchine virtuali per garantire la scalabilità. Di seguito è riportato un diagramma di un'architettura di hypervisor di tipo 2.

Esempi di hypervisor di tipo 2 sono VMware Workstation, VMware Fusion, VirtualBox, Parallels e QEMU.

## Containers

I container hanno molto in comune con le macchine virtuali, ma anziché essere completamente astratti dal sistema operativo host, condividono alcune proprietà con quest'ultimo. I container hanno un proprio file system, una porzione di risorse di elaborazione ( CPU , RAM ), uno spazio di elaborazione e altro ancora. 

Oltre agli ovvi vantaggi derivanti dalla leggerezza, i container sono anche portatili e robusti perché non sono completamente astratti. 

I container engine rappresentano il nostro secondo tipo di virtualizzazione. Così come le macchine virtuali utilizzano un hypervisor per creare un livello di astrazione per la virtualizzazione, i container utilizzano un container engine per creare un livello di astrazione utilizzando risorse logiche.

### Docker

Se qualcuno ha familiarità con i container, Docker è probabilmente il primo nome che viene in mente. Docker è una piattaforma e un motore per container utilizzato per eseguire le "immagini" Docker come container.

Ogni immagine Docker è costituita da un'immagine base, come Alpine o Ubuntu, specificamente progettata per l'uso in container e leggera. Per creare un'immagine Docker, è necessario creare un Dockerfile, che definisce l'immagine base per un container e tutti i comandi da eseguire

### Esecuzione e interazione con un contenitore Docker

Docker Hub è un repository remoto per immagini Docker, simile a GitHub, un repository remoto per Git . Utilizzando Docker Hub, possiamo caricare immagini Docker create da altri o caricare le nostre.

 ***`docker pull <user>/<image>`***

In alternativa, è possibile estrarre automaticamente un'immagine del container al primo avvio del container. Una volta estratto, il container verrà memorizzato nella cache locale e Docker lo cercherà localmente prima di tentare di scaricarlo.

 ***`docker run <user>/<image>`***

 Una volta avviata l'immagine, possiamo verificare che il motore Docker stia eseguendo il contenitore elencando i processi in esecuzione in Docker utilizzando il comando seguente.

 ***`docker ps`***

 Dal comando precedente, puoi notare che al contenitore verranno assegnati un identificatore casuale, un indirizzo IP e un'interfaccia di rete.

### Kubernetes


Grazie all'utilizzo di hypervisor e container, la maggior parte dei problemi associati all'elaborazione tradizionale, come  costi ed efficienza viene risolta. Resta però aperta la questione: cosa succederebbe se avessimo bisogno di una soluzione più veloce e scalabile? In altre parole, al variare del carico o di altri criteri, le risorse o il numero di istanze allocate all'applicazione o al servizio aumentano o diminuiscono al volo, a seconda delle necessità.

Kubernetes, abbreviato anche in " K8s ", è una di queste soluzioni, nota come  piattaforma di orchestrazione . Una piattaforma di orchestrazione mira a integrarsi in altri prodotti, come Docker, estendendone le capacità o "sincronizzandoli" con altri prodotti o applicazioni.

Kubernetes si basa su modelli di virtualizzazione tradizionali come hypervisor e container e ne amplia gli utilizzi, le funzionalità e le capacità.

Queste capacità e caratteristiche includono quanto segue:

- Scalabilità orizzontale : a differenza della tradizionale scalabilità "verticale", la scalabilità "orizzontale" si riferisce all'aggiunta di dispositivi o macchine per gestire un carico di lavoro maggiore, anziché all'aggiunta di risorse logiche come CPU o RAM .
- Estensibilità : i cluster possono essere modificati dinamicamente senza influire sui contenitori esterni al gruppo previsto.
- Auto-riparazione : K8s può riavviare, sostituire, riprogrammare ed eliminare automaticamente i contenitori che non funzionano correttamente in base ai controlli di integrità definiti dall'utente.
- Rollout e rollback automatizzati : K8s può implementare progressivamente le modifiche ai container. Man mano che vengono apportate modifiche, monitorerà lo stato dell'applicazione e deciderà se proseguire con il rollout o il rollback. Ciò garantisce un uptime costante del cluster anche in caso di errore di alcuni container.





