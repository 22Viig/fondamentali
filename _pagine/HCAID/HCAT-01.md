---
layout: page
title: Human-centred - Approaches and Tecnologies 1
args: (Human‑Centred Workflow, Knowledge Graph, XUI)
permalink: /HCAT-01/

---

Argomenti
- [1. Human‑Centred Workflow](#human-centred-workflow)
- [2. Knowledge Graph](#knowledge-graph)
- [3. XUI](#xui)
- [4. Algorithmic Fairness](#algorithmic-fairness)

## Human‑Centred Workflow

Il workflow human‑centred descrive una struttura articolata in cui convivono tre dimensioni:

- **System Component** – le tecnologie, i modelli computazionali, gli strumenti di raccolta e analisi dati (come Matomo, Knowledge Graph, machine learning o NLP).
- **User Component** – gli utenti, i loro profili, le loro interazioni e i loro contesti d’uso.
- **User Experience (UX)** – ciò che gli utenti sperimentano realmente nell’interazione con il sistema.

Il processo prevede attività sia qualitative (interviste, studi sugli utenti, analisi comportamentali) sia quantitative (monitoraggi, valutazioni basate su dati, modelli statistici).
L’obiettivo è arrivare a definire:

- Human‑Centred Patterns – modelli ricorrenti di comportamento e interazione;
- Human‑Centred Profiles – rappresentazioni adattive dell’utente basate su item, contesto, attività e preferenze.

Il workflow è alla base sia del design (HCD) sia dello sviluppo di sistemi di IA centrati sull’essere umano (HCAI), poiché consente di comprendere e monitorare come le persone interagiscono con i sistemi, di adattarne il comportamento e di migliorarne costantemente l’usabilità.

### Human‑Centred Design

Si tratta di una metodologia di problem‑solving che mette le persone al centro dell’intero ciclo di vita del prodotto. Significa progettare non solo interfacce, ma sistemi, servizi e processi che rispondano realmente ai bisogni, alle capacità e alle aspettative degli utenti.
HCD secondo lo standard ISO 9241‑210 richiede:

- comprensione del contesto d’uso,
- coinvolgimento continuo degli utenti,
- iterazioni ripetute di progettazione e valutazione,
- bilanciamento tra tecnologia, organizzazione, ruoli e qualità.

### Human‑Centred Artificial Intelligence (HCAI)
L’intelligenza artificiale, in questa visione, non sostituisce l’uomo ma lo amplifica, potenzia e supporta.
La definizione si basa su un framework a due dimensioni:

- livello di automazione del sistema,
- livello di controllo umano.

La combinazione desiderabile è alta automazione + alto controllo umano, poiché consente sistemi potenti ma allo stesso tempo sicuri, affidabili e governabili.
HCAI richiede:

- trasparenza,
- sicurezza e affidabilità,
- comprensibilità,
- equità algoritmica,
- possibilità per l’utente di intervenire nelle decisioni.

## Knowledge Graph

I Knowledge Graph sono strumenti che rappresentano la conoscenza attraverso nodi e relazioni.

Tre sottografi principali vengono generati:

- Topic subgraph – collega persone, output di ricerca e argomenti generati.
- Research interest and activity subgraph – unisce ricercatori, interessi e attività svolte.
- Department subgraph – mette in relazione output, persone e unità organizzative.

Questi grafi consentono una comprensione più profonda delle dinamiche interne ai sistemi, dei contenuti e degli utenti. Sono fondamentali anche per il systematic monitoring, cioè l’osservazione continua del comportamento degli utenti attraverso dati di navigazione, sistemi come Matomo e tecniche di annotazione automatica delle sessioni (es. TAASG).

## XUI

Per rendere l’IA comprensibile agli utenti è necessaria una progettazione che renda visibili, interpretabili e giustificabili le decisioni prese dal sistema. Le slide mostrano come interviste mirate e analisi qualitative permettano di migliorare la trasparenza percepita.

### User Profiling

Il profiling può essere:

- esplicito, basato su dati dichiarati dall’utente (form, preferenze);
- implicito o comportamentale, ottenuto analizzando azioni e interazioni.

I Graph Neural Networks (GNN) sono perfette per modellare relazioni complesse ma esposte al rischio di apprendere i bias presenti nei dati.

Sono analizzati due modelli:

- CatGCN
- RHGN (Relation‑aware Heterogeneous Graph Network)

Le osservazioni principali:

- RHGN produce modelli più equi rispetto a CatGCN.
- Nonostante ciò, entrambi richiedono processi di debiasing.
- In scenari sensibili è necessaria anche una valutazione della disparate mistreatment, non solo della parità di trattamento.


