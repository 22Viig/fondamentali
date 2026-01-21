---
layout: page
title: Human-centred - Approaches and Tecnologies 4
args: (Ricerca su HCAI, Legal AI ed Explainability)
permalink: /HCAT-04/

---

Argomenti
- [1. Ricerca su HCAI](#ricerca-su-hcai)

## Ricerca su HCAI

La ricerca sulle applicazioni di IA che pongono l’essere umano al centro, con particolare attenzione al tema dell’algorithmic fairness.

### Radici della non equità algoritmica
Le cause principali dell’iniquità nei sistemi di machine learning sono due:

- Dati distorti o sbilanciati, che riflettono pregiudizi o disuguaglianze storiche.
- Algoritmi che amplificano tali distorsioni, soprattutto quando utilizzano modelli complessi come le Graph Neural Networks (GNN).

Si evidenzia come le GNN — modelli sempre più utilizzati per compiti come il recommendation o l’analisi di social graph — siano particolarmente esposte al rischio di apprendere bias presenti nei dati.

### User profiling e valutazione della fairness

Il profiling degli utenti mira a inferire interessi, preferenze o comportamenti attraverso dati generati dagli stessi. I modelli di user profiling vengono spesso trattati come problemi di classificazione, e la fairness viene valutata utilizzando metriche tradizionali quali:

- Statistical Parity (SP)
- Equal Opportunity (EO)

Entrambe mirano a misurare eventuali disparità nei risultati tra gruppi sensibili, come genere o etnia.

### Criticità degli approcci binari alla fairness
Le slide riportano due importanti implicazioni etiche:

- L’uso della sola differenza assoluta tra gruppi può nascondere quali siano realmente i gruppi svantaggiati, rendendo difficile implementare interventi mirati.
- Ridurre classi e gruppi sensibili a categorie binarie semplificate distorce la realtà, portando a valutazioni non accurate della fairness dei modelli e contribuendo alla riproduzione di discriminazioni.

## Legal AI ed Explainability

Anche qui la sfida è duplice: costruire sistemi capaci di recuperare conoscenza normativa e casi giuridici, e allo stesso tempo renderne spiegabili i risultati agli utenti, che possono essere studenti, giuristi o professionisti del settore.

### RQ1 – Estrazione della conoscenza dai manuali giuridici

Un metodo per estrarre conoscenza relativa alle norme dai libri di testo, con l’obiettivo di creare un riferimento intermedio tra documenti molto diversi fra loro, come manuali, codici e commentari.
Il processo di estrazione prevede varie fasi: conversione del PDF, pulizia del testo, ricostruzione delle parole spezzate, identificazione dei titoli delle sezioni, segmentazione gerarchica del documento e applicazione di regole per riconoscere riferimenti a articoli di legge in diverse forme.
L’obiettivo è associare porzioni di testo esplicativo agli articoli del Codice Civile, generando così una banca dati navigabile e adatta alla creazione di sistemi di recupero informativo.

### RQ2 – Explainability e performance nel retrieval legale
La ricerca viene poi applicata ai task della competizione COLIEE, focalizzata sull’estrazione e il recupero di informazione giuridica.
L’obiettivo del gruppo è competere adottando un metodo non solo performante, ma anche spiegabile, dimostrando che trasparenza e prestazioni possono coesistere.

### RQ3 – Presentare la conoscenza in modo comprensibile
Il tema della progettazione dell’interfaccia per la consultazione legale.
Sono previsti tre modi di interagire con la base di conoscenza:

- Top‑down, esplorando manuali e concetti dall’alto;
- Middle‑out, ricercando un concetto presente in varie fonti;
- Bottom‑up, partendo da un singolo articolo o elemento normativo.

La sfida consiste nell’aiutare l’utente a trovare ciò di cui ha bisogno senza essere sopraffatto dalla complessità del materiale giuridico, come mostrano analisi tramite eye‑tracking e survey.


