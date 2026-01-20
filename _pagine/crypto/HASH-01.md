---
layout: page
title: Basi di Hashing 1
args: (Funzioni di HASH, Collisione HASH)
permalink: /HASH-01/

---

Argomenti
- [1. Funzioni di HASH](#funzioni-di-hash)
- [2. Collisione HASH](#collisione-hash)

## Funzioni di HASH
Le funzioni hash sono diverse dalla crittografia. Non esiste una chiave e sono concepite per rendere impossibile (o computazionalmente poco pratico) il passaggio dall'output all'input.

Una funzione hash prende dati di input di qualsiasi dimensione e crea un riepilogo o digest di tali dati. L'output ha una dimensione fissa. È difficile prevedere l'output per qualsiasi input e viceversa. I buoni algoritmi di hashing saranno relativamente veloci da calcolare e proibitivamente lenti da invertire, ovvero partire dall'output e determinare l'input. Qualsiasi piccola variazione nei dati di input, anche un singolo bit, dovrebbe causare una variazione significativa nell'output.

L'hashing svolge un ruolo fondamentale nel nostro utilizzo quotidiano di Internet. Come altre funzioni crittografiche, l'hashing rimane nascosto all'utente. L'hashing aiuta a proteggere l'integrità dei dati e a garantire la riservatezza delle password.

Considera questo esempio di come l'hashing venga utilizzato per proteggere la tua sicurezza informatica. Quando accedi ad un sito web, il server utilizza l'hashing per verificare la tua password. Infatti, secondo le buone pratiche di sicurezza, un server non registra la tua password, ma ne registra il valore hash. Ogni volta che desideri accedere, calcolerà il valore hash della password che hai inserito con il valore hash registrato. Allo stesso modo, quando accedi al tuo computer, l'hashing gioca un ruolo nella verifica della tua password. Interagisci con l'hashing in modo più indiretto di quanto pensi, e quasi quotidianamente nel contesto delle password.

## Collisione HASH

Una collisione di hash si verifica quando due input diversi producono lo stesso output. Le funzioni hash sono progettate per evitare le collisioni il più possibile. Inoltre, le funzioni hash sono progettate per impedire a un aggressore di creare, ovvero progettare, una collisione intenzionalmente. Tuttavia, poiché il numero di input è praticamente illimitato e il numero di output possibili è limitato, ciò porta a un effetto "pigeonhole".

L' **effetto pigeonhole** afferma che il numero di elementi ( pigeons ) è maggiore del numero di contenitori ( pigeonhole ); alcuni contenitori devono contenere più di un elemento. In altre parole, in questo contesto, esiste un numero fisso di valori di output diversi per la funzione hash, ma è possibile assegnarle un input di qualsiasi dimensione. Poiché ci sono più input che output, alcuni input devono inevitabilmente fornire lo stesso output. Se si hanno 21 piccioni e 16 pigeonhole, alcuni piccioni condivideranno i pigeonhole. Di conseguenza, le collisioni sono inevitabili. Tuttavia, una buona funzione hash garantisce che la probabilità di una collisione sia trascurabile.

