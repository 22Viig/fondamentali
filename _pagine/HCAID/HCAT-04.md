---
layout: page
title: Human-centred - Approaches and Tecnologies 4
args: (Ricerca su HCAI, Legal AI ed Explainability)
permalink: /HCAT-04/

---

Argomenti
- [1. Human-Centred AI e Explainable User Interfaces](#ricerca-su-hcai)

## Human-Centred AI e Explainable User Interfaces

l tema centrale della lezione riguarda la ricerca nell’ambito dell’Human-Centred Artificial Intelligence (HCAI), con particolare attenzione all’importanza dell’interpretabilià e delle interfacce utente spiegabili (Explainable User Interfaces, XUIs).
L’obiettivo è mostrare come le decisioni prodotte da sistemi complessi – in questo caso, sistemi di raccomandazione basati su knowledge graph – possano essere esposte agli utenti in modo chiaro, comprensibile e utile per creare fiducia.

Il punto di partenza è l’osservazione che, negli ultimi anni, i recommender systems hanno assunto un ruolo centrale nella selezione e presentazione di informazioni personalizzate in contesti molto diversi: dalla ricerca accademica alle piattaforme commerciali.

Nell’ambito scientifico, vengono citati sistemi per la raccomandazione di esperti e raccomandazione di articoli accademici, che mostrano come il supporto digitale possa agevolare la navigazione tra grandi quantità di contenuti.
Tuttavia, insieme alla crescita di questi sistemi è emersa un’esigenza altrettanto forte: capire come e perché vengono proposti certi risultati. La disciplina della Explainable AI (XAI) mira a rendere interpretabili i modelli di intelligenza artificiale “esponendo” il loro funzionamento all’utente in modo sistematico.

## Il ruolo delle interfacce nel rendere spiegabile l’IA

Il design delle interfacce utente sia spesso persino più determinante dell’algoritmo stesso nel riuscire a trasmettere la trasparenza di un sistema complesso.
Infatti, anche il miglior modello di IA diventa “non spiegabile” se non è accompagnato da un'interfaccia capace di comunicare in modo chiaro le logiche utilizzate.
La necessità di adattare le spiegazioni agli utenti deriva da diversi fattori:

- Caratteristiche individuali: ciò che un utente percepisce come trasparente può non esserlo per un altro.
- Obiettivi e capacità cognitive: la comprensione varia in base al background, al tipo di attività e alle competenze dell’utente.
- Livello di dettaglio richiesto: alcuni utenti preferiscono spiegazioni sintetiche, altri bisogno di dettagli approfonditi.

Questi elementi conducono alla transizione da spiegazioni statiche a spiegazioni adattive e personalizzate, coerenti con i principi dell’Human-Centred Design.

##  Il contributo della ricerca: un sistema di raccomandazione basato su Knowledge Graph

Il lavoro presentato introduce un contributo composto da due parti principali:

La costruzione di un sistema di raccomandazione basato su un knowledge graph, sviluppato a partire dai dati del gruppo di ricerca GEI.
La progettazione di due interfacce spiegabili, differenti nel modo in cui presentano risultati e spiegazioni agli utenti.

### Il GEI Knowledge Graph
Il knowledge graph è una rappresentazione strutturata che raccoglie informazioni sulle attività del gruppo GEI: membri, pubblicazioni, interessi di ricerca, progetti, eventi, collaborazioni esterne.
È composto da:

6921 entità
8988 relazioni

Le entità includono persone interne ed esterne, corsi, eventi, pubblicazioni, interessi di ricerca e altri elementi connessi. Le relazioni descrivono, per esempio, la co-autoria, la partecipazione ad attività, la gestione di progetti, l’appartenenza a unità organizzative, le pubblicazioni su riviste o presso editori.
Gli autori hanno poi generato tre sotto-grafi rilevanti per la raccomandazione:

Topic subgraph, basato su persone e pubblicazioni.
Research interest & activity subgraph, che lega interessi personali, attività e lavori prodotti.
Department subgraph, che mette in relazione ricercatori e unità organizzative.

Questa struttura consente al sistema di raccomandare articoli e ricercatori partendo da diversi tipi di collegamenti concettuali.

## Le interfacce spiegabili: System A e System B

Il sistema sviluppato prevede due versioni differenti di interfacce:
### System A

Presenta raccomandazioni insieme a visualizzazioni grafiche del knowledge graph.
Evidenzia i collegamenti tra elementi (persone, interessi, pubblicazioni) per permettere all’utente di capire come il sistema è arrivato a suggerire un certo contenuto.
Offre una spiegazione principalmente visuale, centrata sulle relazioni del grafo.

### System B

Fornisce spiegazioni più testuali e strutturate.
Mostra le connessioni in modo meno grafico ma più descrittivo.
Può risultare più accessibile per chi preferisce informazioni organizzate in forma di liste o testo.

## Valutazione con utenti
Lo studio ha coinvolto 23 ricercatori appartenenti a diverse aree disciplinari del GEI.
Il disegno sperimentale è stato:

within-subjects: ogni partecipante ha testato entrambe le interfacce;
con presentazione casuale dei sistemi;
valutazione tramite domande Likert a 5 punti.

L’obiettivo era capire:

quale interfaccia risultasse più comprensibile;
quale aumentasse maggiormente la fiducia nel sistema;
quale fosse percepita come più utile per esplorare e comprendere le raccomandazioni.

L’esperimento è stato arricchito da interviste qualitative per raccogliere impressioni e suggerimenti più approfonditi.


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


