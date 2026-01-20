---
layout: page
title: Human-Centred Design 3
args: (Designing solutions, First Drafts, Refined Design)
permalink: /HCD-03/

---

Argomenti
- [1. Designing solutions](#designing-solutions)
- [2. Early Design](#earlyd-esign)
- [3. First Drafts](#first-drafts)
- [4. Refined Design](#refined-design)
- [5. Conclusione](#conclusione)

##  Designing solutions

La progettazione delle soluzioni è la trasformazione dei bisogni e dei requisiti degli utenti in idee concrete, strutture informative, prototipi e interfacce sempre più definite. Questa fase non consiste solo nel “disegnare schermate”, ma in un processo complesso e strutturato che parte dalla comprensione profonda del contesto d’uso e arriva alla definizione dettagliata dell’interfaccia e dei suoi elementi. L’intero percorso è caratterizzato da iterazione continua e verifica costante con gli utenti e gli stakeholder.

##  Early Design

La prima fase della progettazione è chiamata Early Design e rappresenta il momento in cui si iniziano a trasformare conoscenze teoriche e dati raccolti nel contesto reale in una possibile visione futura del sistema. L’obiettivo non è ancora definire l’aspetto finale dell’interfaccia, ma chiarire come utenti e sistema interagiranno e quali informazioni dovranno essere scambiate tra le due parti.

Questa fase ruota attorno a un concetto chiave: il conceptual modelling, una forma di modellazione concettuale che permette di:

- analizzare i task degli utenti alla luce dei requisiti progettuali,
- adattare i task model in base a restrizioni, nuove tecnologie o ottimizzazioni,
- individuare i task objects (gli oggetti che l’utente crea, modifica o osserva) e le loro proprietà,
- definire le funzioni eseguibili dal sistema,
- costruire use scenarios che descrivono casi d’uso futuri realistici.

Il **task model for design** può differire dal task model osservato nel contesto d’uso, perché nella progettazione si può decidere di semplificare attività, automatizzarne alcune, o adattarle a un sottoinsieme specifico di utenti.

Un altro elemento centrale in questa fase è l’**interaction specification**, cioè la definizione precisa delle sequenze di azioni e reazioni tra l’utente e il sistema. Ogni dialogue step descrive cosa l’utente fa, come il sistema risponde, e da chi parte l’iniziativa (utente o sistema). Tutte queste specificazioni devono essere collegate esplicitamente ai task, ai sottotask e ai requisiti utente.

I criteri di qualità impongono che l’interaction specification sia completa, coerente, non limitata da soluzioni tecniche premature e priva di riferimenti a dettagli d’interfaccia ancora da definire. L’obiettivo è modellare ciò che deve accadere, non ancora come appare visivamente.

Da questa base si costruiscono i **use scenarios**, cioè racconti testuali che descrivono come un utente (spesso rappresentato da una persona) utilizzerà il sistema in un contesto realistico. I use scenarios servono per stimolare dialogo, chiarire aspettative e valutare alternative prima di passare alla prototipazione.

## First Drafts

Dopo aver definito cosa deve succedere a livello concettuale, si passa alla fase dei First Drafts, in cui si inizia a strutturare l’informazione e il flusso dell’interazione in modo più tangibile.

Il prodotto principale di questa fase è la **Information Architecture (IA)**, ovvero la struttura logica di task objects, funzioni e percorsi di navigazione.

L’information architecture ha lo scopo di:

- rispecchiare il mental model degli utenti,
- organizzare task objects e funzioni in modo comprensibile e accessibile,
- rendere visibile e valutabile la struttura informativa,
chiarire i percorsi necessari a raggiungere funzioni e contenuti.

Gli elementi fondamentali dell’IA sono:

### Signposts
Sono gli indicatori di percorso, come:

- calls to action (collegamenti verso funzioni o altri task objects),
- trigger words (etichette che permettono di raggiungere un task object da un altro punto del sistema).

### Connection Paths
Definiscono i collegamenti tra i task objects e vengono usati per costruire la navigazione.

## Navigation Structure

È la struttura che organizza gli accessi ai contenuti e alle funzioni, spesso rappresentata come un albero di navigazione. Deve essere basata sulle priorità degli utenti (top tasks) e non su preferenze dei progettisti o convenzioni arbitrarie.
Durante questa fase possono essere utilizzati metodi come il card sorting per validare se la struttura proposta è intuitiva e coerente con la rappresentazione mentale dell’utente.

Dalla IA si passa a definire le prime interaction sequences, ovvero la traduzione dei dialogue steps in una sequenza ordinata di viste e interazioni. A questo punto si iniziano a creare le prime rappresentazioni visive:

- sketches, schizzi rapidi per esplorare alternative;
- wireframes, rappresentazioni a bassa fedeltà che mostrano layout, contenuti e primi percorsi.

Il principio guida è: fail early and often, cioè sbagliare presto, perché i prototipi iniziali sono facili, veloci ed economici da modificare.

## Refined Design

La terza fase, chiamata Refined Design, è dedicata alla definizione precisa dell’interfaccia e a tutti i dettagli necessari per costruire un sistema chiaro, coerente e percorribile dagli utenti.

### Interface Design
Qui si decide:

- quali elementi dell’interfaccia utilizzare,
- come combinarli e disporli,
- quali comportamenti devono avere (es. stati default, interazioni dinamiche),
- come implementare il flusso delle interazioni.



### Prototipi ad Alta Fedeltà

Una volta definito lo stile dell’interfaccia, si passa ai prototipi high‑fidelity, versioni digitali molto simili al prodotto finale, dotate di interazione e navigazione. Sono essenziali per valutare:

- usabilità,
- estetica,
- coerenza del design,
- qualità dell’esperienza utente.

### Information Design
Questa parte del design riguarda la presentazione dell’informazione: testi, etichette, icone, simboli, immagini. L’obiettivo è rendere l'informazione:

- rilevabile (detectable),
- non disturbata da elementi superflui (freedom from distraction),
- distinguibile,
- interpretabile,
- concisa,
- coerente.

Sono importanti anche i principi di lettura (scanning, skimming, reading), lo schema di lettura e la tecnica dell’inverted pyramid, che parte sempre dalle informazioni più importanti.

### Sensory Design e Gestalt Laws
L’ultima parte del documento affronta il tema della percezione visiva e sensoriale:

- leggi della Gestalt (vicinanza, similarità, continuità, chiusura, buona forma, destino comune),
- uso appropriato di colori, contrasti e dimensioni dei caratteri,
- importanza del white space per leggibilità, organizzazione e estetica.

Questi principi aiutano a creare interfacce chiare, equilibrate e intuitive, riducendo il carico cognitivo e migliorando la comprensione immediata.

## Conclusione 

La progettazione di una soluzione non è un atto creativo isolato, ma un processo rigoroso, iterativo e guidato da principi di ergonomia, psicologia cognitiva, percezione visiva e ingegneria dell’informazione. Si parte da modelli concettuali e task rielaborati, si costruisce una struttura informativa coerente e navigabile, si traducono questi elementi in interazioni visualizzate tramite prototipi, e infine si definiscono tutti i dettagli dell’interfaccia, rispettando principi percettivi, visivi e comunicativi.
Il risultato è una soluzione progettata davvero attorno agli utenti: un sistema che permette loro di riconoscere, comprendere e usare le informazioni in modo efficace, efficiente e soddisfacente. In questo senso, “designing solutions” è la fase in cui la visione strategica dell’HCD diventa concreta, tangibile e valutabile.