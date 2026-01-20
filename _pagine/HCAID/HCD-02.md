---
layout: page
title: Human-Centred Design 2
args: (User Needs e User Requirements)
permalink: /HCD-02/

---

Argomenti
- [1. User Needs e User Requirements](#user-needs-e-user-requirements)
- [2. Conclusioni](#conclusioni)

## User Needs e User Requirements

Dopo aver osservato utenti, analizzato i loro compiti e compreso obiettivi, difficoltà e risorse, il primo passo è identificare ciò che a loro “serve” per raggiungere i propri obiettivi. Questa è la definizione di user need: una condizione indispensabile affinché un utente o un gruppo di utenti possa raggiungere un obiettivo all’interno del proprio contesto d’uso. 

Un punto fondamentale è che il bisogno dell’utente non deve mai fare riferimento alla soluzione, quindi non bisogna citare sistemi, siti o interfacce. I bisogni non descrivono “come” risolvere un problema, ma “cosa” manca all’utente per riuscire in qualcosa. Per esempio, dire “l’utente deve poter vedere la schermata del medico” è scorretto, perché introduce una soluzione. È corretto invece dire: “Il paziente ha bisogno di sapere quando inizierà l’appuntamento”. 

Gli user needs derivano da tecniche come interviste, osservazioni, questionari e valutazioni di usabilità. In genere rappresentano la distanza tra ciò che succede oggi e ciò che dovrebbe succedere.
Il documento offre vari esempi: il paziente che ha bisogno di un’informazione sui tempi dell’appuntamento, oppure che deve avere una risorsa come un appuntamento confermato. Allo stesso modo, un panettiere ha bisogno di possedere la competenza per cucinare una cheesecake se il suo obiettivo è venderla con successo. 

### Come formulare correttamente gli user needs

Ogni user need deve contenere:

- un solo prerequisito (sapere, avere, saper fare qualcosa);
- un solo scopo espresso con "in modo da…" / "per …";
- nessuna tautologia o ripetizione;
- nessuna duplicazione: se lo stesso bisogno emerge più volte, lo si registra una sola volta e poi si fa riferimento alla versione esistente.

Queste regole servono a evitare confusione e a garantire che i bisogni siano chiari, specifici, non ambigui. In questo modo, quando saranno trasformati in requisiti, risulteranno più facili da progettare e soprattutto da verificare.

Il documento distingue anche diversi tipi di user need, legati a informazioni necessarie, risorse mancanti o competenze richieste. Questi tre elementi (informazioni, risorse, capacità) rappresentano le forme base di ciò che può mancare all’utente all’interno di un’attività.

### Dai bisogni ai requisiti:

Dopo aver individuato i bisogni, il passo successivo consiste nel tradurli in user requirements. Un requisito è definito come una condizione o capacità che deve essere soddisfatta dal sistema per rispettare standard o accordi, ma soprattutto per rispondere ai bisogni degli utenti.

I requisiti devono essere determinabili, cioè devono poter essere verificati. La lezione distingue:

- requisiti di mercato,
- requisiti organizzativi,
- requisiti utente.

Questi ultimi sono ulteriormente divisi in qualitativi e quantitativi.

#### Requisiti qualitativi
Descrivono ciò che l’utente deve poter riconoscere, capire, selezionare o inserire.

Non descrivono funzioni, ma condizioni d’uso.

Ad esempio, non è corretto dire “l’utente deve poter acquistare un biglietto”, perché è troppo generico e descrive l’intero compito. È invece corretto scomporre in requisiti elementari come:

- l’utente deve poter inserire la destinazione,
- l’utente deve poter visualizzare tutte le possibili connessioni,
- l’utente deve riconoscere le tariffe per ogni tratta. 

Questo livello di astrazione permette di usare i requisiti come base chiara e solida per la progettazione dell’interfaccia.


#### Requisiti quantitativi

Hanno natura misurabile: si riferiscono a efficacia, efficienza, soddisfazione, accessibilità o sicurezza.
Sono, di fatto, criteri di accettazione del progetto.
Esempi:

“L’utente deve poter completare una procedura in meno di X secondi.”
“Il sistema deve permettere non più di Y errori in un compito.”

Sono requisiti verificabili tramite test di usabilità. Il documento raccomanda di:

- confrontarsi con sistemi esistenti,
- considerare le aspettative degli stakeholder,
validare i requisiti quantitativi con gli utenti stessi. 

Un aspetto cruciale è che i requisiti non devono derivare da soluzioni preesistenti, perché ciò bloccherebbe l’innovazione.

L’esempio del miscelatore della doccia chiarisce bene questo rischio: non bisogna dire che devono esserci cinque livelli di calore; bisogna esprimere il bisogno astratto (selezionare la temperatura desiderata) e lasciare che il design trovi la soluzione migliore.

### Le relazioni tra bisogni, requisiti e obiettivi di qualità

- contesto d’uso,
- bisogni dell’utente,
- requisiti utente,
- requisiti di sistema,
- obiettivi di qualità,
- aspettative degli stakeholder.

Il messaggio principale è che questi elementi formano una catena logica.
Per esempio:

- Osservazione → l’utente ha difficoltà a capire quando è il suo turno.
- User need → l’utente deve conoscere l’orario effettivo dell’appuntamento.
- User requirement → il sistema deve permettere all’utente di riconoscere l’orario aggiornato.
- System requirement → il sistema deve aggiornare automaticamente i tempi.
- Test di verifica → controllare che l’utente riconosca realmente l’informazione.

In questo modo si ha un percorso verificabile dalla realtà fino al design finale.

### Metodo pratico per derivare bisogni e requisiti

- Identificare gli obiettivi dell’utente nelle informazioni raccolte.
- Capire cosa manca all’utente per raggiungere tali obiettivi (informazione, risorsa, competenza).
- Formulare gli user needs con la struttura “L’utente ha bisogno di X per fare Y”.
- Derivare gli user requirements descrivendo ciò che l’utente deve poter riconoscere, selezionare o inserire.
- Formulare i requisiti secondo la sintassi corretta (“Con il sistema, l’utente deve poter…”).
- Assegnare i requisiti ai sottocompiti del task model, così da integrare tutto nel processo di progettazione.

## Conclusione

Gli **user needs**, cioè prerequisiti indispensabili affinché gli utenti possano compiere un’azione o prendere una decisione. Un user need può riguardare il bisogno di sapere qualcosa (informazione), avere qualcosa (risorsa) o saper fare qualcosa (competenza). È fondamentale che tali bisogni siano formulati senza fare riferimento a soluzioni tecnologiche, perché descrivono un “mancato presupposto”, non una funzionalità del sistema. Questa distinzione mantiene il focus sugli utenti e non sui prodotti esistenti, evitando di “incatenare” la progettazione a scelte premature o imitazioni di soluzioni note.

Una volta definiti con precisione i bisogni, si passa alla loro trasformazione in **user requirements**, che descrivono cosa il sistema dovrà permettere all’utente di riconoscere, selezionare o inserire per soddisfare quei bisogni. I requisiti possono essere qualitativi, quando definiscono aspetti dell’interazione, oppure quantitativi, quando stabiliscono misure verificabili di efficacia, efficienza, soddisfazione, accessibilità o sicurezza. I requisiti quantitativi diventano veri criteri di accettazione del progetto e devono essere verificabili tramite test, osservazioni o confronti con sistemi già esistenti. Inoltre, devono essere formulati a un livello sufficientemente astratto da non imporre soluzioni predefinite, preservando così la libertà progettuale e l’innovazione.

La progettazione centrata sull’utente è un processo logico e sequenziale: si parte dalla comprensione profonda del contesto reale, si identificano i bisogni fondamentali degli utenti e si trasformano tali bisogni in requisiti chiari e verificabili. Solo seguendo questo percorso il sistema finale potrà essere realmente utile, utilizzabile e coerente con le necessità delle persone a cui è destinato. Questa metodologia non produce solo prodotti migliori, ma garantisce anche che le decisioni progettuali siano motivate, tracciabili e orientate al valore reale per gli utenti.