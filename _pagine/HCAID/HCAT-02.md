---
layout: page
title: Human-centred - Approaches and Tecnologies 2
args: (Language Engineering, I corpora )
permalink: /HCAT-02/

---

Argomenti
- [1. Language Engineering](#language-engineering)
- [2. I corpora](i-corpora)

## Language Engineering 

L’obiettivo generale è comprendere come i sistemi linguistici vengano progettati, costruiti e migliorati mediante dati linguistici strutturati e annotati, che costituiscono la base per applicazioni come il Natural Language Processing (NLP), il machine learning e i sistemi di recupero dell’informazione.

Due motivazioni principali: da un lato la crescente centralità delle risorse linguistiche nelle applicazioni informatiche moderne, e dall’altro l’importanza delle annotazioni ai diversi livelli dell’analisi linguistica.

Il linguaggio è presentato come il più naturale mezzo di comunicazione umana, in grado di veicolare idee complesse, negoziare, persuadere, raccontare e registrare la cultura. Tuttavia, per permettere alle macchine di comprendere o manipolare il linguaggio è necessario formalizzarlo e strutturarlo. L’ingegneria del linguaggio si occupa proprio di sviluppare sistemi software per il trattamento automatico delle lingue naturali. Per poter funzionare, tali sistemi necessitano di language resources, ovvero risorse linguistiche che includono corpora, lessici, dizionari elettronici, thesauri e altre basi di dati contenenti informazioni linguistiche di varia complessità.

I corpora e le risorse lessicali sono fondamentali per addestrare, valutare e migliorare sistemi di NLP, IR (Information Retrieval) e tecniche di data mining. Le slide includono anche un modello di “Language Enabled System” che illustra come i componenti di input linguistico, risorse, algoritmi e moduli di elaborazione interagiscano in un sistema linguistico basato su dati.

### I dati in linguistica

Le caratteristiche dei dati linguistici possono essere classificati in categorie come naturally occurring data (dati naturali), evoked data (indotti) e invented data (inventati). La distinzione tra dati “reali” e “non reali” non coincide necessariamente con la loro naturalità: anche grandi corpora contenenti testi autentici possono presentare frasi poco naturali, mentre esempi creati da linguisti possono essere naturali dal punto di vista dell’uso.

I dati linguistici vengono classificati secondo numerosi parametri, tra cui:

- lingua, registro e varietà (dialetti, socioletti, linguaggi specialistici);
- tipo di testo (articoli, discorsi politici, comandi di controllo, notizie);
- dominio (finanza, medicina, trasporti);
- produttore del testo (giornalista, utente medio, bambino);
- modalità e mezzo di produzione (scritto/orale, PC, telefono, web);
- condizioni di produzione (spontaneo, con pressione temporale, preparato);
- codifica, mezzi di trasmissione e presentazione.

Tale ricchezza di parametri dimostra quanto sia complessa la raccolta e classificazione dei dati usati per creare corpora rappresentativi. Per essere utili, i dati devono rappresentare in modo adeguato un fenomeno linguistico, un tipo di testo o l’input/output necessario per una specifica applicazione tecnologica.

## I corpora


Un corpus consiste in un insieme finito di testi autentici, leggibili da macchina e selezionati secondo criteri specifici per rappresentare una lingua o una sua varietà. La corpus linguistics si occupa dello studio della lingua basandosi su questi insiemi di testi reali.

I corpora possono essere:

- paralleli, quando i testi sono tradotti in una o più lingue (es. EuroParl);
- comparabili, quando raccolgono testi simili in diverse lingue (es. ICE);
- mono-, bi- o multilingui, a seconda del numero di lingue rappresentate;
- annotati, cioè arricchiti con informazioni morfologiche, sintattiche, semantiche, pragmatiche ecc.

Esistono anche risorse basate sul Web, come le directory tematiche che associano categorie semantiche a insiemi di termini, esempi storici essendo Yahoo Directory e l’Open Directory Project.
Viene menzionato anche il ChatGPT corpus, a sottolineare che corpora complessi e di grande scala stanno diventando centrali nell’addestramento dei moderni modelli linguistici.

### Annotazione dei corpora

L’annotazione consiste nell’aggiungere informazioni ai testi, ai diversi livelli dell’analisi linguistica. Il termine deriva dal latino annotare, ovvero “aggiungere note”. Le annotazioni possono riguardare informazioni linguistiche (morfologia, sintassi, semantica, discorso, pragmatica) oppure metadati (autore, data, genere, formato, caratteristiche editoriali).

Esistono diversi livelli di annotazione:

- *Part-of-Speech (PoS) tagging*
Il PoS tagging suddivide il testo in token, seleziona un tagset e applica tag alle parole. Alcuni problemi tipici riguardano:

* multi-parole come in spite of;
* fusioni (clitici, contrazioni);
ambiguità morfologica (es. come in inglese).

Il tagging richiede criteri, un lessico di riferimento e procedure per risolvere l’ambiguità.

- *Annotazione sintattica*
Consiste nel costruire parsed corpora, spesso sotto forma di treebanks che rappresentano la struttura ad albero delle frasi. Le finalità includono:

* addestramento di parser automatici;
* analisi linguistica e studio delle costruzioni sintattiche.

Vengono citati alcuni treebank importanti come il Penn Treebank e il Susanne Corpus, ciascuno con strutture, criteri e complessità differenti.

- *Annotazione semantica*
Si concentra sul significato delle parole e dei concetti. Le sfide principali sono:

* Problema 1: più parole possono riferirsi allo stesso concetto (abdomen/tummy).
* Problema 2: la stessa parola può avere significati diversi (boot).

L’annotazione semantica richiede tassonomie gerarchiche (es. WordNet) e linee guida dettagliate per il tagging dei “semantic fields”. Può essere manuale, assistita o automatica, anche se l’automazione totale non è ancora realistica.

### Annotazione del discorso

Tratta aspetti come coesione e coerenza, anafore, sostituzioni, ellissi e relazioni logiche. Le slide mostrano esempi di annotazione anaforica (es. UCREL) e strumenti dedicati come XANADU.

### Annotazione pragmatica

Analizza elementi oltre la frase e il discorso, come segnali conversazionali e atti linguistici. Sono forniti esempi di studi sulle interazioni conversazionali in ambito medico, con categorie come disclosure, acknowledgment, edification. L’annotazione pragmatica richiede spesso un lavoro manuale e grande interpretazione da parte di esperti.




