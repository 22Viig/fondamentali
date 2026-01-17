---
layout: page
title: Human-Centred Artificial Intelligence 6
args: (Human‑Centred AI, Human‑Centred Quality e Human‑Centred Design, Human‑Centred Workflow, Interdipendenza HCD–HCAI e monitoraggio, Scenario applicativo i LLM)
permalink: /HCAI-06/

---

Argomenti
- [1. Human‑Centred AI](#Human‑Centred-AI)
- [2. Human‑Centred Quality e Human‑Centred Design](#Human‑Centred-Quality-e-Human‑Centred-Design)
- [3. Human‑Centred Workflow](#Human‑Centred-Workflow)
- [4. Interdipendenza HCD–HCAI e monitoraggio](#Interdipendenza-HCD–HCAI-e-monitoraggio)
- [5. Scenario applicativo: i LLM](#Scenario-applicativo:-i-LLM)
- [6. Conclusioni](#Conclusioni)

## Human‑Centred AI

Affinché l’AI soddisfi bisogni reali, operi in modo trasparente, produca esiti equi e tuteli la privacy sono necessarie 3 condizioni:

- **(1) un framework bidimensionale** che rompe la falsa dicotomia “più automazione = meno controllo umano” e invita a progettare alto livello di automazione e alto livello di controllo umano;
- **(2) lo spostamento dall’emulazione all’empowerment**: non costruire macchine “come umani”, ma strumenti super‑potenzianti;
- **(3) una struttura di governance** per tradurre principi etici in pratiche concrete (prodotti affidabili, sicuri e degni di fiducia lungo tutto il ciclo di vita). In sintesi: HCAI significa amplificare, responsabilizzare e potenziare le persone.

I rami di ricerca dell’HCAI:

- Explainable & Interpretable AI: strumenti e metodi per rendere comprensibili decisioni o predizioni, contrastando l’opacità dei “black box” e adattando le spiegazioni a contesti e pubblici diversi;

- Approcci human‑centred al design e alla valutazione dell’AI: applicazione sistematica dei metodi HCI nella progettazione e nel testing;

- Human–AI teaming: collaborazione uomo‑macchina, ruoli “human‑in‑the‑loop”, supporti agli data scientist, simulazione di comportamenti umani e sfide del lavoro congiunto;

- Ethical AI: allineamento a principi e diritti fondamentali (linee guida UE per una “AI affidabile”: lecita, etica, robusta; con principi di autonomia, prevenzione del danno, equità, spiegabilità). 


## Human‑Centred Quality e Human‑Centred Design

Per ottenere usabilità, accessibilità, user experience positiva e assenza di danni d’uso, l’approccio è l’HCD: un processo iterativo che può avviarsi da qualunque stadio, ma che in ogni caso richiede di: pianificare il processo human‑centred; comprendere e specificare il contesto d’uso; tradurre il contesto in requisiti utente; produrre soluzioni di design; e valutare le soluzioni rispetto ai requisiti, reiterando fino al soddisfacimento degli obiettivi. Questa architettura metodologica è la base su cui si innesta l’HCAI.

## Human‑Centred Workflow

Lo **Human‑Centred Workflow**  connette HCAI e HCD e integra due ingredienti cruciali:

- **monitoraggio sistematico** (un approccio multimodale che combina metodi quantitativi e qualitativi per leggere i comportamenti d’uso);

- **una prospettiva economica del valore** (valutare l’“expanded value” generato per le persone che interagiscono con l’AI).

Il workflow è articolato in quattro fasi decisionali e sei processi, specchiati per la parte HCD e per la parte HCAI, ciascuno con ciclo di feedback per la rifinitura iterativa.

Le quattro fasi sono:

- Decidere la ricerca necessaria: identificare i bisogni degli utenti e le “susceptibilities” del sistema (punti deboli, rischi), tramite raccolta informativa;

- Decidere i requisiti degli stakeholder: collegare requisiti derivati dai bisogni, sia per sistemi nuovi sia per sistemi in esercizio;

- Decidere quali idee realizzare: selezione guidata da fattibilità e idoneità a soddisfare i requisiti;

- Decidere i requisiti nel roadmap: pianificare l’implementazione dei requisiti accettati in una roadmap.

I sei processi corrono in parallelo tra HCD e HCAI, con andate e ritorni:

- Aspettative / Valori e leggi: da un lato si indagano aspettative di utenti e stakeholder; dall’altro si leggono sistemi di valori e cornici normative per ispezionare il sistema e scovarne vulnerabilità.
- Bisogni / Susceptibilities: i bisogni nascono dalla conoscenza del contesto d’uso; dal lato sistema si osservano interazioni reali per identificare pattern comportamentali e quantificare rischi e severità dei punti deboli.
- Requisiti stakeholder / Analisi dei comportamenti: i requisiti descrivono condizioni e capacità della soluzione futura; simmetricamente, si valutano potenzialità di miglioramento sulla base di pattern d’uso e debolezze del sistema.
- Idee di soluzione / Approcci AI: si generano idee per soddisfare i requisiti; sul lato AI, si valutano approcci per automatizzare compiti o supportare l’uso del sistema, stimando il valore atteso per le persone e validando i rischi futuri.
- Requisiti di sistema / Approcci AI valutati: dalle idee si derivano requisiti implementabili; a specchio, si consolidano gli approcci AI selezionati in base al valore atteso.
- Soluzione implementata / Soluzione AI implementata: si realizza e si verifica/valida con gli stakeholder; si controllano fattibilità e idoneità nel contesto previsto, alla luce del sistema di valori e dei pattern d’interazione. L’esito confluisce nella roadmap per il miglioramento continuo. 

## Interdipendenza HCD–HCAI e monitoraggio

Il monitoraggio è una la sinergia tra:

- un **User component**, focalizzato su interessi, esperienza, competenze e aspetti attitudinali (raccolti qualitativamente “ascoltando le parole degli utenti”);
- un **System component**, responsabile di registrare, raccogliere, aggiornare e cancellare i dati che descrivono l’interazione (base per analisi quantitative).

La combinazione produce una base di conoscenza capace di guidare decisioni progettuali etiche, coinvolgenti e focalizzate sulla soddisfazione d’uso.

## Scenario applicativo: i LLM

Large Language Models (LLM) hanno introddotto un cambio di paradigma che hanno introdotto in NLP e HCI, in quanto sono modelli scalabili con capacità testuali “quasi umane” (precisione sintattica, coerenza semantica, consapevolezza del contesto), utili per migliorare l’interazione, personalizzare i contenuti e automatizzare attività.

Gli utenti si aspettano dialoghi naturali e risposte affidabili, cortesi, accurate, ma che spesso i LLM faticano ad aderire pienamente a vincoli e regole d’uso, motivo per cui vengono impiegate tecniche di Reinforcement Learning from Human Feedback. Per ridurre bias, contenuti dannosi e allucinazioni, compaiono anche strategie come PEFT (Parameter‑Efficient Fine‑Tuning) e Direct Preference Optimization (DPO).

Un’altra dimensione centrale è il **contesto**: LLM generalisti non possiedono consapevolezza di dominio e considerano solo porzioni limitate della conversazione come contesto d’input. Due leve progettuali proposte sono:

- l’integrazione con Knowledge Graphs per guidare la generazione verso contenuti personalizzati e coerenti;
- la progettazione di meccanismi per contesti lunghi/infiniti, in grado di mantenere memoria estesa nelle conversazioni. In termini di requisiti, le soluzioni LLM vanno spesso integrate con algoritmi task‑specific (es. recommender o information retrieval) e con schemi RAG (Retrieval Augmented Generation), che combinano generazione testuale e recupero informativo su basi aggiornate.

I LLM si prestano a apprendimento continuo e richiedono strategie di valutazione robuste (dataset di QA come MMLU, HellaSwag, DROP, ecc.), oltre a una roadmap che scandisca gli avanzamenti: il settore evolve con nuove release periodiche (famiglie GPT, Llama, Mistral), e il miglioramento continuo è parte costitutiva del ciclo di vita. Tutto questo è perfettamente coerente con l’idea di Human‑Centred Workflow: una pratica che garantisce evoluzione naturale dei modelli e miglioramento costante guidato da requisiti etici, d’uso e di valore per le persone.

## Conclusioni
Sviluppare HCAI significa anche seguire l’HCD, perché solo così si ottengono sistemi usabili, accessibili, sicuri e orientati alla dignità dell’utente. 

Il workflow human‑centred integra fasi decisionali e processi specchiati (per HCD e HCAI), introduce monitoraggio sistematico e valutazione del valore per gli umani, e si dimostra applicabile a casi reali come i LLM, dove questioni di equità, trasparenza, governance e personalizzazione sono cruciali. In questo approccio, l’automazione è invocata dalle persone e resta prevedibile e controllabile: i computer non sono persone, e proprio per questo le persone rimangono responsabili.