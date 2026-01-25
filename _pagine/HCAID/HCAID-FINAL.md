---
layout: page
title: FINALE - Human-Centred Artificial Intelligence and Design
args: ()
permalink: /HCAT-FINALE/

---
Argomenti
- [1. HCAI](#hcai)
- [2. HCAI Framework](#hcai-framework)
- [3. Raccomender System](#raccomender-system)
- [4. Expleinability](#expleinability) ** 
- [5. Etica](#etica) **
- [6. HCD Teoria di Norman](#teoria-di-norman)
- [7. HCD User experiment](#eser-experiment)
- [8. Algorithmic Fairness](#elgorithmic-fairness)



## HCAI

La Human-Centred Artificial Intelligence si propone di sviluppare sistemi che non sostituiscano l’uomo, ma lo amplifichino, potenzino e supportino, mantenendo un equilibrio tra automazione e controllo umano.

Questo approccio nasce come risposta alla visione tradizionale dell’AI, focalizzata sull’autonomia delle macchine, e pone al centro valori umani quali diritti, giustizia e dignità, oltre a obiettivi individuali come creatività, responsabilità e connessioni sociali. Il design di HCAI si basa su metodologie di user experience, coinvolgendo stakeholder e garantendo affidabilità, sicurezza e trasparenza.

Affinché l’AI soddisfi bisogni reali, operi in modo trasparente, produca esiti equi e tuteli la privacy sono necessarie 3 condizioni:

- un **framework bidimensionale** che rompe la falsa dicotomia “più automazione = meno controllo umano” e invita a progettare alto livello di automazione e alto livello di controllo umano;
- lo spostamento **dall’emulazione all’empowerment**: non costruire macchine “come umani”, ma strumenti super‑potenzianti;
- una struttura di **governance** per tradurre principi etici in pratiche concrete (prodotti affidabili, sicuri e degni di fiducia lungo tutto il ciclo di vita). 

In sintesi: HCAI significa amplificare, responsabilizzare e potenziare le persone.

I rami di ricerca dell’HCAI:

- **Explainable & Interpretable AI**: strumenti e metodi per rendere comprensibili decisioni o predizioni, contrastando l’opacità dei “black box” e adattando le spiegazioni a contesti e pubblici diversi;

- **Approcci human‑centred al Design**: applicazione sistematica dei metodi HCI nella progettazione e nel testing;

- **Ethical AI**: allineamento a principi e diritti fondamentali (linee guida UE per una “AI affidabile”: lecita, etica, robusta; con principi di autonomia, prevenzione del danno, equità, spiegabilità).

- **Human–AI teaming**: collaborazione uomo‑macchina, ruoli “human‑in‑the‑loop”, supporti agli data scientist, simulazione di comportamenti umani e sfide del lavoro congiunto;



## HCAI Framework

La Human-Centred AI Framework evidenzia l’importanza di progettare sistemi che combinino alti livelli di automazione con alti livelli di controllo umano, critiando e discostandosi dai modelli a una dimensione dei livelli di automazione.. L’obiettivo è superare la visione tradizionale che vede più autonomia come meno controllo umano, proponendo un approccio che valorizzi la creatività, la responsabilità e le connessioni sociali. 

- Agenti Intelligenti vs Supertool 
- Teammates vs Tele-bots
- Assured Autonomy vs Control Center
- Social Robots vs Active Appliance


## Raccomender System
I sistemi di raccomandazione si distinguano dai classici sistemi di Information Retrieval: mentre questi ultimi rispondono a una richiesta esplicita dell’utente e devono recuperare tutti i documenti rilevanti, i recommender systems operano in modo proattivo. Non attendono una query formale, ma analizzano preferenze, cronologia e contesto per suggerire contenuti rilevanti. Questo passaggio da un modello pull a uno push caratterizza l’intero settore: l’obiettivo non è trovare ciò che l’utente cerca, ma scoprire ciò che potrebbe piacergli. È qui che entrano in gioco la personalizzazione, l’uso di informazioni della comunità (come comportamenti simili di altri utenti) e la capacità di riconoscere preferenze implicite, come clic, acquisti o visualizzazioni.

Il compito principale di un sistema di raccomandazione può assumere due forme: la **Top‑N** recommendation, che punta a selezionare un insieme ristretto di elementi rilevanti, e la **rating prediction**, orientata invece a stimare il grado di apprezzamento di un utente per un certo oggetto. Sebbene oggi prevalgano gli approcci Top‑N, anche la capacità di prevedere un rating rimane utile in applicazioni come film, prodotti o recensioni.

Esistono diverse tecniche di raccomandazione, raggruppabili in tre macro‑famiglie: metodi **content‑based**, **collaborative filtering** e soluzioni ibride.

Le strategie **content‑based** analizzano direttamente le caratteristiche degli oggetti, come parole nei testi, metadati, tag, o feature audiovisive. Per valutare la similarità fra documenti testuali, ad esempio, si utilizza spesso il modello vettoriale: un documento è trattato come un vettore di termini, ponderati attraverso tecniche come tf–idf. Il processo prevede la rimozione delle stop‑words, la normalizzazione e l’applicazione dello stemming per ricondurre le parole alla loro radice. Il risultato è uno spazio vettoriale in cui la distanza o l’angolo tra vettori rappresenta la similarità semantica tra gli oggetti.

In contrasto, il **collaborative filtering** ignora il contenuto degli item e analizza esclusivamente lo schema di valutazioni degli utenti. La logica è che due elementi sono simili se le stesse persone li apprezzano o li rifiutano. Due utenti sono simili se hanno gusti coerenti. Questa famiglia di metodi è particolarmente potente quando le caratteristiche degli oggetti sono difficili da estrarre (ad esempio, immagini, video, audio). Tuttavia, può soffrire della cosiddetta “cold start problem” per utenti o item nuovi, dato che richiede un numero sufficiente di interazioni pregresse per funzionare bene. Un esempio classico di collaborative filtering è il nearest‑neighbor, che usa la vicinanza fra utenti o item per calcolare una previsione. L’algoritmo analizza quali altri utenti simili hanno valutato un certo oggetto e deduce di conseguenza la probabile valutazione dell’utente corrente.

I sistemi di raccomandazione possono avere approcci user‑based e item‑based. Nel primo caso si calcolano somiglianze tra gli utenti e si deduce il rating di un nuovo item aggregando i giudizi degli utenti più affini. Nell’approccio item‑based si assumono invece relazioni di similarità fra gli oggetti. Questa seconda modalità è stata storicamente preferita da aziende come Amazon, perché gli item sono generalmente più stabili nel tempo rispetto agli utenti, le cui preferenze possono essere molto dinamiche.

Esistono tecniche ibride, che combinano contenuto e collaborazione per mitigare i limiti di entrambe le strategie. La fusione può avvenire in diversi modi: votazioni per aggregare risultati, medie pesate o modelli personalizzati che combinano le due fonti di informazione. Gli approcci ibridi risultano spesso più robusti, soprattutto in domini complessi dove sia i dati testuali sia il comportamento degli utenti forniscono segnali significativi.

C’è una sostanziale distinzione tra metodi **memory‑based** e **model‑based**. Gli approcci memory‑based utilizzano direttamente la matrice delle valutazioni, senza costruire modelli astratti: la similarità è calcolata al momento, basandosi sulle interazioni correnti. Sono semplici e sempre aggiornati, ma poco scalabili e sensibili alla sparsità. I model‑based costruiscono invece un modello latente, come ad esempio con la decomposizione in valori singolari (SVD). Questo permette di identificare dimensioni nascoste che rappresentano gusti o caratteristiche implicite. I vantaggi sono consistenza, riduzione del rumore e rapidità nelle raccomandazioni; lo svantaggio è la necessità di aggiornare periodicamente il modello.

In base al tipo di task, cambiano le metriche. Per i Top‑N, la precisione e il recall misurano rispettivamente quanti suggerimenti sono corretti e quanti elementi rilevanti sono stati trovati. L’F‑measure combina le due metriche per dare un valore unificato. Quando il ranking conta, si utilizzano misure come la Mean Average Precision (MAP), che considera la posizione dei risultati. La ROC curve, con l’AUC, è un’altra tecnica che visualizza il compromesso tra veri positivi e falsi positivi lungo diverse soglie. Infine, per i sistemi di rating prediction, è comune il ricorso alla Root Mean Squared Error (RMSE), che misura lo scarto medio tra valutazioni reali e previste.

## Expleinability

Gli utenti non sempre comprendono perché un modello prenda una decisione, e in mancanza di trasparenza possono perdere fiducia nel sistema.

A questo punto diventa chiaro che l’Explainable Artificial Intelligence (XAI) non è un lusso, ma una componente fondamentale di sistemi sicuri e affidabili. La XAI è il campo dell’intelligenza artificiale dedicato a **rendere interpretabili i modelli complessi**, in modo sistematico e human‑interpretable.

Nel panorama dell’interpretabilità vengono introdotte due grandi categorie: metodi model‑specific e metodi model‑agnostic. I primi funzionano solo con determinate classi di modelli, sfruttando la loro struttura interna (ad esempio DeepLIFT per reti neurali). I secondi invece operano come una sorta di “lente esterna”: trattano il modello come una black box e analizzano solo input e output, applicare euristiche di spiegazione a posteriori.

L’apparente successo di un modello – ad esempio un classificatore di immagini con un’accuratezza dell’83% – può nascondere dinamiche problematiche. Non è dunque il livello di accuratezza a garantire l’affidabilità del modello, ma la comprensione dei fattori che guidano le predizioni. È questo il cuore dell’Explainable AI: **non accontentarsi che un modello funzioni, ma verificare che funzioni per le ragioni giuste**.

## Etica

La **ethical decision-making** nell’AI è capacità di un sistema di valutare e scegliere tra alternative in modo coerente con norme sociali, etiche e legali. Questo implica che l’AI debba riconoscere le opzioni non etiche, scartarle e selezionare quella che, pur consentendo il raggiungimento di un obiettivo, rispetta l’azione più giusta o più “benefica” secondo i valori della società.

Da ciò derivano i criteri fondamentali di un’azione etica: il sistema deve avere una reale possibilità di scelta, deve essere in grado di identificare tra le alternative quella considerata socialmente buona e deve farlo consapevolmente, cioè proprio perché riconosce tale scelta come etica. Questo già suggerisce la complessità del problema: mentre la legge può essere imposta dall’esterno, l’etica richiede interiorizzazione, apprendimento, sensibilità al contesto. Per questo l’etica non può essere semplicemente “programmata” come una serie di regole assolute.

Considerando le teorie morali, gli esseri umani combinano differenti visioni: talvolta ragioniamo in base alle conseguenze (visione utilitaristica), talvolta in base ai principi (visione deontologica), altre volte in base alle virtù e al carattere (virtue ethics). Non seguiamo mai rigidamente un’unica teoria, e proprio questa flessibilità ci permette di evitare risultati paradossali e di adattarci a contesti complessi. Rendere computazionale una capacità così sfumata è estremamente difficile, esistono tre approcci mediante i quali si cerca di far ragionare eticamente un sistema di AI: top‑down, bottom‑up e approcci ibridi.

L’approccio **top‑dow**n parte da una teoria etica predefinita, trasformata in regole o principi che il sistema deve seguire. È un metodo che presuppone che l’AI sia in grado di ragionare esplicitamente sulle conseguenze delle proprie azioni, valutando ciò che è moralmente corretto sulla base di una rappresentazione formale di valori, norme e conoscenze del dominio. Questo approccio funziona bene in sistemi in cui è importante garantire coerenza e verificabilità, ma presenta due limiti: da un lato riduce la complessità dell’etica a un insieme rigido di regole, dall’altro rischia di confondere etica e legalità, assumendo che ciò che è conforme alla legge sia automaticamente etico.

L’approccio **bottom‑up**, invece, si basa sull’idea che il comportamento etico possa essere appreso dall’osservazione dei comportamenti umani, un po’ come accade nei modelli di machine learning tradizionali. La “moralità” è derivata dal consenso sociale, da ciò che la maggior parte delle persone ritiene giusto in un determinato contesto. Questo metodo però introduce nuove sfide: ciò che è considerato accettabile varia da cultura a cultura, e ciò che la società accetta non sempre coincide con ciò che è moralmente corretto. Anche dal punto di vista concettuale, basarsi solo sulla “forza della maggioranza” è rischioso, perché può rinforzare pregiudizi e discriminazioni già presenti.

Da qui nasce la necessità degli **approcci ibridi**, che combinano la stabilità dei principi top‑down con la sensibilità contestuale del bottom‑up. L’approccio MOOD si fonda sulla “intelligenza collettiva” e cerca di integrare molteplici prospettive, evitando allo stesso tempo il dominio della maggioranza. Le decisioni etiche, infatti, implicano anche riflessioni sulla distribuzione dei benefici e dei rischi, sulla possibile creazione di danni futuri, su potenziali situazioni di oppressione o squilibri di potere.

Nella ricerca dei così detti artificial moral agents, ossia sistemi capaci di prendere decisioni moralmente informate, è importante la partecipazione il coinvolgimento degli stakeholder nei processi decisionali. Per costruire sistemi morali serve una riflessione accurata su elementi come la composizione della “folla” da cui si apprende, la formulazione delle domande poste agli utenti, la modalità con cui questi vengono informati e coinvolti, il sistema elettorale adottato nei processi partecipativi e la legittimità dei risultati. 

L’etica di un agente AI può essere implementata nei sistemi autonomi per mezzo di un approccio strettamente algoritmico, in cui il sistema incorpora meccanismi per valutare autonomamente le conseguenze morali, a soluzioni che prevedono un human in command, cioè un essere umano che supervisiona, controlla o affianca la decisione del sistema. Seguono poi modelli basati sulla regolamentazione dell’ambiente – che impedisce all’AI di trovarsi in situazioni moralmente ambigue –, fino alla considerazione che, in casi estremi, un sistema potrebbe persino adottare una scelta casuale quando nessuna decisione è eticamente preferibile.

Nessun artefatto, per quanto avanzato, può essere considerato autonomo nel senso filosofico del termine, poiché non possiede volontà, intenzionalità o capacità normativa. Perciò non può essere equiparato a un essere umano né può avere una sua dignità morale. **L’etica resta sempre responsabilità dell’essere umano che progetta, controlla o utilizza il sistema.**

Come trasformare i principi etici in pratiche reali, attraverso strutture di governance, metodi ingegneristici e processi di verifica che rendano i sistemi affidabili, sicuri e allineati ai valori umani.

Per colmare questo divario tra etica e pratica, viene proposto un modello a quattro livelli di governance. Al livello più interno troviamo i **team di ingegneria**, responsabili del codice, del testing e delle buone pratiche tecniche. Attorno a loro c’è l’**organizzazione aziendale**, che deve promuovere una vera cultura della sicurezza: non bastano procedure astratte, serve un atteggiamento diffuso orientato alla responsabilità, alla prevenzione degli errori e alla trasparenza. Il terzo livello è quello dell’oversight indipendente: **gruppi esterni**, magari di settore, che monitorano più organizzazioni e diffondono le buone pratiche. Infine c’è la **regolamentazione pubblica**, che rappresenta il livello più ampio, quello orientato al bene comune. Qui non si tratta di limitare l’innovazione, ma di creare un quadro stabile e sicuro in cui essa possa svilupparsi senza danneggiare la società.

## HCD Teoria di Norman

**Don Norman applicò i principi della psicologia cognitiva al design degli oggetti e, per estensione, delle interfacce digitali.**

Norman cercò di spiegare come le persone interagiscono con i sistemi e perché talvolta falliscono, introducendo una teoria generale che risulta ancora oggi fortemente attuale nel design dell’esperienza utente. La sua riflessione parte dall’idea che ogni azione dell’utente sia guidata da un ciclo d’azione, nel quale si alternano fasi di esecuzione e di valutazione. L’utente stabilisce un obiettivo, lo traduce in un’intenzione, specifica una sequenza di azioni, la esegue, osserva i risultati e li interpreta per capire se lo hanno avvicinato al proprio scopo. Questo ciclo appare semplice, ma contiene molteplici punti critici nei quali possono nascere errori.

Norman individua due grandi categorie di difficoltà: la **gulf of execution**, cioè ciò che ostacola la traduzione dell’intento in un’azione, e la **gulf of evaluation**, cioè ciò che impedisce all’utente di interpretare correttamente gli effetti dell’azione.


Per approfondire tale dinamica, Norman introduce il concetto di **designer image**, **system image** e **user image**. Il progettista immagina un certo funzionamento del sistema; il sistema, attraverso la sua interfaccia, comunica una rappresentazione di sé; l’utente, a sua volta, costruisce un modello mentale basato su ciò che percepisce. **Quando queste tre immagini sono disallineate, il sistema diventa difficile da usare.**

Per ridurre questi fraintendimenti, Norman individua tre strumenti chiave: **vincoli**, **significatori** e **feedback**. I vincoli indicano ciò che è possibile o impossibile fare: possono essere fisici, culturali, semantici o logici, e aiutano l’utente a evitare errori. I significatori indicano invece come usare un elemento: un pulsante ben evidenziato suggerisce che è cliccabile, una maniglia suggerisce che può essere tirata. Il feedback, infine, informa l’utente su ciò che sta accadendo, idealmente in meno di un decimo di secondo: un clic sonoro, un’evidenziazione grafica, un messaggio di conferma. Questi elementi, se progettati con coerenza, aumentano fortemente la comprensibilità e la facilità d’uso di un’interfaccia.

## HCD User experiment

Un user experiment viene definito come un metodo scientifico per indagare come diversi fattori influenzano l’interazione degli utenti con sistemi che possono essere software, dispositivi hardware, altre persone, organizzazioni o persino politiche interne. Il primo passo consiste nel porre domande precise: non è sufficiente domandarsi se un nuovo sistema “è buono”, perché ciò richiede di chiarire cosa significa “buono”. 

Gli esperimenti vengono quindi costruiti creando più versioni del sistema, differenziate solo per gli aspetti che si intende studiare. L’utente interagisce con una di queste versioni, e il ricercatore osserva il comportamento o raccoglie giudizi soggettivi. Successivamente, si applicano tecniche statistiche per valutare se le differenze tra condizioni siano significative. Lo scopo è produrre una relazione causale fra manipolazione e risultati: se tutto il resto è mantenuto costante e i partecipanti sono assegnati in modo casuale alle condizioni, allora le variazioni osservate possono essere attribuite proprio alla manipolazione.

L’elemento centrale del disegno sperimentale sono le **manipolazioni**, cioè i fattori che si ipotizza possano avere un impatto.

Per misurare gli effetti delle manipolazioni si utilizzano le **osservazioni**, dette anche variabili dipendenti o outcome. 


I principi del disegno sperimentale mettono in guardia contro alcuni effetti cognitivi che possono distorcere i risultati. Uno di questi è il **placebo effect**, che si verifica quando gli utenti credono che una caratteristica del sistema funzioni in un certo modo e modificano il loro comportamento di conseguenza, anche se quella caratteristica non è attiva. Un altro fenomeno cruciale è il **Hawthorne effect**, in cui i partecipanti cambiano comportamento semplicemente perché sanno di essere osservati. Per ridurre questi bias è spesso utile triangolare i risultati, confrontando gli esperimenti di laboratorio con test sul campo, come gli **A/B test**.

## Algorithmic Fairness

All’apparenza, un sistema che elabora solo dati numerici dovrebbe evitare discriminazioni, poiché non ha emozioni, pregiudizi o intenzioni. È frequente sentir dire che, poiché l’algoritmo utilizza unicamente elementi “oggettivi”, non può discriminare. Ma questa è una conclusione fallace. Le persone, nella loro presa di decisione, combinano componenti oggettive e soggettive; **i sistemi algoritmici, invece, dipendono completamente dai dati che ricevono**. **Se i dati includono bias—come storici pregiudizi umani o misurazioni difettose—l’algoritmo non solo li replicherà, ma rischierà di amplificarli**. 

Le linee guida europee sull’AI affidabile (2019) identificano la fairness come un requisito essenziale: è un concetto sociale e culturale, che cambia nel tempo e nei contesti. **La fairness implica che le valutazioni siano proporzionate e non discriminatorie**. In contrapposizione, il termine bias indica un errore sistematico che colpisce gruppi diversi in modo differenziale. 

Quali sono cause principali dell’iniquità nei sistemi di machine learning? Una delle più importanti risiede nei **dataset**: se i dati usati per addestrare il modello derivano da decisioni umane già condizionate da pregiudizi, misurazioni sbagliate o campioni non rappresentativi, l’algoritmo imparerà questi pattern distorti.

**I criteri di fairness sono categorie concettuali che stabiliscono quando un algoritmo può essere considerato “giusto”**.Si distinguono la **fairness individuale** e la **fairness di gruppo**. La prima prevede che individui simili vengano trattati allo stesso modo; la seconda richiede che le statistiche di performance siano simili tra gruppi diversi. Le teorie legali introducono concetti come disparate impact, cioè **discriminazione indiretta**, che si verifica quando un modello danneggia sistematicamente un gruppo pur trattando tutti allo stesso modo; e disparate treatment, cioè **discriminazione diretta**, quando il modello utilizza esplicitamente attributi sensibili per prendere decisioni. Una terza categoria, il **disparate mistreatment**, si focalizza non sulle predizioni corrette, ma sul tasso di errori: se un algoritmo sbaglia più spesso con un gruppo rispetto a un altro, può essere ritenuto ingiusto.

Accanto ai criteri concettuali esistono delle metriche per individuare e misurare la presenza di bias. Alcune misurano la parità tra le percentuali di classificazione positiva nei diversi gruppi, come il disparate impact o la statistical parity. Tuttavia, queste metriche possono penalizzare modelli molto accurati se i gruppi hanno tassi di base diversi. Per questo sono stati introdotti criteri più raffinati come equalized odds—che richiede che i tassi di veri positivi e falsi positivi siano simili tra gruppi—oppure equal opportunity, che si concentra solo sui veri positivi. Altre metriche, come overall accuracy equality o treatment equality, considerano rispettivamente la parità dell’accuratezza complessiva o il rapporto tra errori. Ogni metrica evidenzia un diverso ideale di equità, e non esiste un criterio universale: in molti casi, soddisfarne uno significa violarne un altro.

Esistono strategie di bias mitigation, cioè strumenti tecnici con cui ricercatori e ingegneri cercano di rendere i sistemi più equi. Questi approcci possono intervenire in tre fasi distinte del processo di machine learning. I pre‑processing modificano i dati prima dell’addestramento, ad esempio riscrivendo alcune etichette vicino alla frontiera decisionale o bilanciando i pesi degli esempi. Altri metodi rimuovono gli attributi proxy o trasformano i dati in rappresentazioni più neutrali. Gli in‑processing intervengono durante l’addestramento, integrando nella funzione obiettivo termini di regolarizzazione che forzano il modello a rispettare un criterio di fairness. Adversarial debiasing, ad esempio, addestra un classificatore insieme a un discriminatore che tenta di indovinare il gruppo sensibile: il classificatore è penalizzato se il discriminatore riesce, forzandolo a produrre rappresentazioni più eque. Infine, i post‑processing operano sul modello già addestrato: modificano le soglie di decisione per gruppi diversi o applicano regole correttive come l’equalized odds post‑processing. Sono molto utili quando non si ha accesso al modello originale o ai dati di addestramento.
