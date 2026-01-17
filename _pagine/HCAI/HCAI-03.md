---
layout: page
title: Human-Centred Artificial Intelligence 3
args: (Recommender System)
permalink: /HCAI-03/

---

Argomenti
- [1. Recommender System](#1-Recommender-System)


I sistemi di raccomandazione si distinguano dai classici sistemi di Information Retrieval: mentre questi ultimi rispondono a una richiesta esplicita dell’utente e devono recuperare tutti i documenti rilevanti, i recommender systems operano in modo proattivo. Non attendono una query formale, ma analizzano preferenze, cronologia e contesto per suggerire contenuti rilevanti. Questo passaggio da un modello pull a uno push caratterizza l’intero settore: l’obiettivo non è trovare ciò che l’utente cerca, ma **scoprire ciò che potrebbe piacergli**. È qui che entrano in gioco la personalizzazione, l’uso di informazioni della comunità (come comportamenti simili di altri utenti) e la capacità di riconoscere preferenze implicite, come clic, acquisti o visualizzazioni.

Il compito principale di un sistema di raccomandazione può assumere due forme: la **Top‑N recommendation**, che punta a selezionare un insieme ristretto di elementi rilevanti, e la **rating prediction**, orientata invece a stimare il grado di apprezzamento di un utente per un certo oggetto. Sebbene oggi prevalgano gli approcci Top‑N, anche la capacità di prevedere un rating rimane utile in applicazioni come film, prodotti o recensioni.

Esistono diverse tecniche di raccomandazione, raggruppabili in tre macro‑famiglie: metodi content‑based, collaborative filtering e soluzioni ibride. 

Le strategie **content‑based** analizzano direttamente le caratteristiche degli oggetti, come parole nei testi, metadati, tag, o feature audiovisive. Per valutare la similarità fra documenti testuali, ad esempio, si utilizza spesso il modello vettoriale: un documento è trattato come un vettore di termini, ponderati attraverso tecniche come tf–idf. Il processo prevede la rimozione delle stop‑words, la normalizzazione e l’applicazione dello stemming per ricondurre le parole alla loro radice. Il risultato è uno spazio vettoriale in cui la distanza o l’angolo tra vettori rappresenta la similarità semantica tra gli oggetti.

In contrasto, il **collaborative filtering** ignora il contenuto degli item e analizza esclusivamente lo schema di valutazioni degli utenti. La logica è che due elementi sono simili se le stesse persone li apprezzano o li rifiutano. Due utenti sono simili se hanno gusti coerenti. Questa famiglia di metodi è particolarmente potente quando le caratteristiche degli oggetti sono difficili da estrarre (ad esempio, immagini, video, audio). Tuttavia, può soffrire della cosiddetta “cold start problem” per utenti o item nuovi, dato che richiede un numero sufficiente di interazioni pregresse per funzionare bene. Un esempio classico di collaborative filtering è il nearest‑neighbor, che usa la vicinanza fra utenti o item per calcolare una previsione. L’algoritmo analizza quali altri utenti simili hanno valutato un certo oggetto e deduce di conseguenza la probabile valutazione dell’utente corrente.

I sistemi di raccomandazione possono avere approcci user‑based e item‑based. Nel primo caso si calcolano somiglianze tra gli utenti e si deduce il rating di un nuovo item aggregando i giudizi degli utenti più affini. Nell’approccio item‑based si assumono invece relazioni di similarità fra gli oggetti. Questa seconda modalità è stata storicamente preferita da aziende come Amazon, perché gli item sono generalmente più stabili nel tempo rispetto agli utenti, le cui preferenze possono essere molto dinamiche.

Esistono tecniche ibride, che combinano contenuto e collaborazione per mitigare i limiti di entrambe le strategie. La fusione può avvenire in diversi modi: votazioni per aggregare risultati, medie pesate o modelli personalizzati che combinano le due fonti di informazione. Gli approcci ibridi risultano spesso più robusti, soprattutto in domini complessi dove sia i dati testuali sia il comportamento degli utenti forniscono segnali significativi.

C'è una sostanziale distinzione tra metodi **memory‑based** e **model‑based**. Gli approcci memory‑based utilizzano direttamente la matrice delle valutazioni, senza costruire modelli astratti: la similarità è calcolata al momento, basandosi sulle interazioni correnti. Sono semplici e sempre aggiornati, ma poco scalabili e sensibili alla sparsità. I model‑based costruiscono invece un modello latente, come ad esempio con la decomposizione in valori singolari (SVD). Questo permette di identificare dimensioni nascoste che rappresentano gusti o caratteristiche implicite. I vantaggi sono consistenza, riduzione del rumore e rapidità nelle raccomandazioni; lo svantaggio è la necessità di aggiornare periodicamente il modello.

In base al tipo di task, cambiano le metriche. Per i Top‑N, la **precisione** e il **recall** misurano rispettivamente quanti suggerimenti sono corretti e quanti elementi rilevanti sono stati trovati. L’**F‑measur**e combina le due metriche per dare un valore unificato. Quando il ranking conta, si utilizzano misure come la **Mean Average Precision** (MAP), che considera la posizione dei risultati. La ROC curve, con l’AUC, è un'altra tecnica che visualizza il compromesso tra veri positivi e falsi positivi lungo diverse soglie. Infine, per i sistemi di rating prediction, è comune il ricorso alla **Root Mean Squared Error** (RMSE), che misura lo scarto medio tra valutazioni reali e previste.