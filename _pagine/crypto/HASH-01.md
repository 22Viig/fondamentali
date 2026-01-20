---
layout: page
title: Basi di Hashing 1
args: (Funzioni di HASH, Collisione HASH, Hashing per l'archiviazione delle password)
permalink: /HASH-01/

---

Argomenti
- [1. Funzioni di HASH](#funzioni-di-hash)
- [2. Collisione HASH](#collisione-hash)
- [3. Hashing per l'archiviazione delle password](#hashing-per-l-archiviazione-delle-password)

## Funzioni di HASH
Le funzioni hash sono diverse dalla crittografia. Non esiste una chiave e sono concepite per rendere impossibile (o computazionalmente poco pratico) il passaggio dall'output all'input.

Una funzione hash prende dati di input di qualsiasi dimensione e crea un riepilogo o digest di tali dati. L'output ha una dimensione fissa. È difficile prevedere l'output per qualsiasi input e viceversa. I buoni algoritmi di hashing saranno relativamente veloci da calcolare e proibitivamente lenti da invertire, ovvero partire dall'output e determinare l'input. Qualsiasi piccola variazione nei dati di input, anche un singolo bit, dovrebbe causare una variazione significativa nell'output.

L'hashing svolge un ruolo fondamentale nel nostro utilizzo quotidiano di Internet. Come altre funzioni crittografiche, l'hashing rimane nascosto all'utente. L'hashing aiuta a proteggere l'integrità dei dati e a garantire la riservatezza delle password.

Considera questo esempio di come l'hashing venga utilizzato per proteggere la tua sicurezza informatica. Quando accedi ad un sito web, il server utilizza l'hashing per verificare la tua password. Infatti, secondo le buone pratiche di sicurezza, un server non registra la tua password, ma ne registra il valore hash. Ogni volta che desideri accedere, calcolerà il valore hash della password che hai inserito con il valore hash registrato. Allo stesso modo, quando accedi al tuo computer, l'hashing gioca un ruolo nella verifica della tua password. Interagisci con l'hashing in modo più indiretto di quanto pensi, e quasi quotidianamente nel contesto delle password.

## Collisione HASH

Una collisione di hash si verifica quando due input diversi producono lo stesso output. Le funzioni hash sono progettate per evitare le collisioni il più possibile. Inoltre, le funzioni hash sono progettate per impedire a un aggressore di creare, ovvero progettare, una collisione intenzionalmente. Tuttavia, poiché il numero di input è praticamente illimitato e il numero di output possibili è limitato, ciò porta a un effetto "pigeonhole".

L' **effetto pigeonhole** afferma che il numero di elementi ( pigeons ) è maggiore del numero di contenitori ( pigeonhole ); alcuni contenitori devono contenere più di un elemento. In altre parole, in questo contesto, esiste un numero fisso di valori di output diversi per la funzione hash, ma è possibile assegnarle un input di qualsiasi dimensione. Poiché ci sono più input che output, alcuni input devono inevitabilmente fornire lo stesso output. Se si hanno 21 piccioni e 16 pigeonhole, alcuni piccioni condivideranno i pigeonhole. Di conseguenza, le collisioni sono inevitabili. Tuttavia, una buona funzione hash garantisce che la probabilità di una collisione sia trascurabile.

## Hashing per l'archiviazione delle password

L'hashing ha molteplici utilizzi nella sicurezza informatica. In questa lezione, ci concentreremo su due aspetti: l'archiviazione delle password e l'integrità dei dati. Ci riferiamo all'archiviazione delle password quando viene utilizzata per l'autenticazione.

È importante notare che questo non si applica ai gestori di password, dove è necessario recuperare la password in chiaro . D'altra parte, i meccanismi di autenticazione devono solo confermare che l'utente conosca la password per potergli concedere l'accesso alla risorsa; pertanto, questo problema è diverso da quello dei gestori di password.

La maggior parte delle applicazioni web a un certo punto deve verificare la password di un utente. Memorizzare queste password in chiaro è una pratica di sicurezza molto rischiosa. Probabilmente avrete letto notizie di aziende i cui database sono stati violati. Sapendo che molte persone usano la stessa password per i loro vari account, incluso l'online banking, divulgare la password di un account mette a repentaglio la sicurezza di tutti gli altri.

Ci sono tre pratiche non sicure quando si tratta di password:

* Memorizzazione delle password in testo normale
* Memorizzazione delle password utilizzando una crittografia obsoleta
* Memorizzazione delle password tramite un algoritmo di hashing non sicuro

### Memorizzazione delle password in testo normale
