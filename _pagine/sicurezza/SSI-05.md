---
layout: page
title: Sicurezza nei Sistemi Informatici 5
args: (Social engineering, Phishing, Fattori psicologici, Frodi digitali, Sicurezza del browser, Sicurezza delle applicazioni)
permalink: /ssi-05/

---
Argomenti: 
- [1. Social engineering](#social-engineering)
- [2. Phishing](#phishing)
- [3. Fattori psicologici](#fattori-psicologici)
- [4. Frodi digitali](#frodi-digitali)
- [5. Sicurezza del browser](#sicurezza-del-browser)
- [5. Sicurezza delle applicazioni](#sicurezza-delle-applicazioni)

## Social engineering

Il social engineering è definito come qualunque atto volto a manipolare gli utenti affinché rivelino informazioni confidenziali o compiano azioni dannose. A differenza degli attacchi tecnici, si fonda sulla vulnerabilità più difficile da correggere: il fattore umano. L’attaccante usa pretesti, persuasione e inganni per superare le difese di un’organizzazione, spesso senza dover sfruttare vere vulnerabilità software. 

Tra le tecniche principali troviamo il pretexting, che consiste nel creare un contesto artificiale e credibile per spingere la vittima a condividere dati sensibili. L’attaccante assume un ruolo fittizio, come quello di tecnico dell’assistenza o fornitore di servizi, e costruisce una narrazione plausibile per ottenere fiducia. 

Accanto al pretexting compare la figura dell’insider, la minaccia interna: dipendenti o ex dipendenti che, intenzionalmente o per negligenza, danneggiano l’organizzazione. Contro questa categoria di minacce vengono impiegati strumenti di Data Loss Prevention (DLP), progettati per monitorare e prevenire la perdita di informazioni sensibili e controllare l’accesso ai dati.

Oltre alle tecniche digitali, esistono molte forme fisiche e comportamentali di attacco:

- Shoulder surfing: osservare direttamente le credenziali digitare all’utente, spesso standogli alle spalle.
- Dumpster diving: rovistare fra i rifiuti alla ricerca di documenti contenenti informazioni utili.
- Eavesdropping: carpire conversazioni sensibili origliando.
- Baiting: lasciare oggetti come chiavette USB infette affinché l’utente le raccolga e le utilizzi.
- Piggybacking e tailgating: accedere fisicamente ad aree riservate approfittando del passaggio di una persona autorizzata.
- Diversion: dirottamento fisico di merci o materiali informatici.
- Watering hole: compromissione di siti web frequentemente visitati da un gruppo specifico di utenti.
- Hoax: diffusione di notizie false progettate per ingannare o manipolare il comportamento delle vittime.

Queste tecniche dimostrano come l’anello debole della sicurezza sia spesso il comportamento umano.

## Phishing

Il phishing è una delle tecniche più diffuse e consiste nell’inviare comunicazioni ingannevoli, tipicamente via email, per rubare dati sensibili o consegnare malware alla vittima. Le email di phishing spesso imitano comunicazioni di enti affidabili e includono link a siti contraffatti o allegati dannosi. 

Esistono varianti più mirate, come lo spear phishing, rivolto a individui specifici o a particolari ruoli aziendali. Una forma ancora più selettiva è il whaling, che prende di mira dirigenti e figure di alto livello, sfruttando la loro posizione e la maggiore quantità di dati sensibili accessibili.

Oltre all’email, il phishing può sfruttare canali diversi:

- lo smishing, tramite SMS;
- il vishing, tramite telefonate manipolatorie;
- il pharming, che induce la vittima a visitare siti falsi - attraverso manipolazioni DNS lato server o client.

In tutti questi casi, l’obiettivo resta quello di convincere l’utente a consegnare informazioni, credenziali o denaro.

## Fattori psicologici

Molti attacchi di social engineering si basano su specifici fattori motivazionali. La lezione evidenzia in particolare:

- Autorevolezza: l’attaccante finge di avere un ruolo ufficiale o di rappresentare un ente riconosciuto per indurre fiducia.
- Urgenza: si crea una situazione in cui la vittima deve reagire velocemente, senza riflettere.
- Riprova sociale (social proof): si sfrutta la tendenza delle persone a uniformarsi al comportamento degli altri.
- Scarsità: si propone un’offerta limitata nel tempo o nella quantità.
- Empatia: si utilizzano toni familiari o emotivi per instaurare un rapporto personale.
- Paura: si minaccia un rischio imminente per costringere la vittima ad agire impulsivamente.

Tutti questi elementi rendono il social engineering una tecnica estremamente efficace, perché agiscono su meccanismi psicologici radicati, indipendenti dalla competenza tecnica dell’utente.

## Frodi digitali

La lezione affronta anche le frodi digitali, nelle quali la vittima viene raggirata con l’obiettivo di ottenere un guadagno illecito. Un esempio è la truffa delle fatture, in cui vengono inviati documenti apparentemente legittimi che inducono la vittima a effettuare pagamenti non dovuti. 

Vengono inoltre trattate le campagne di influenza, che mirano a manipolare l'opinione pubblica su larga scala tramite propaganda, social network e diffusione di fake news. Tra i casi citati figurano scandali come Cambridge Analytica e operazioni condotte tramite profili falsi come quello noto come “Jenna Abrams”.

## Sicurezza del browser

Il punto di contatto principale tra l’utente e le minacce esterne spesso transita attraverso il browser. Le regole fondamentali per una buona sicurezza includono:

- Implementare policy di sicurezza coerenti e aggiornate.
- Educare gli utenti sui rischi durante la navigazione e le best practice.
- Utilizzare proxy e content filter per bloccare contenuti malevoli.
- Impedire l’esecuzione di codice dannoso tramite configurazioni e controlli adeguati. 

Particolare attenzione viene data ai cookie, piccoli file utilizzati per memorizzare informazioni relative alla sessione. Esistono cookie di tracciamento e cookie di sessione, e uno dei rischi principali è il session hijacking, ovvero l’acquisizione del Session ID da parte di un attaccante. Per mitigare questi pericoli, si utilizzano attributi come:

- Secure, che limita l’uso del cookie alle connessioni HTTPS.
- HttpOnly, che impedisce l’accesso ai cookie tramite script, riducendo l’impatto degli attacchi XSS.

## Sicurezza delle applicazioni

Le applicazioni lato client rappresentano un altro vettore di attacco critico. Le best practice includono:

- proteggere i documenti con password;
- disabilitare le macro non necessarie, spesso veicolo di malware;
- utilizzare certificati digitali per garantire autenticità e integrità;
- proteggere file sensibili come i PST dei client di posta;
implementare forme di contenimento delle applicazioni;
u- tilizzare sistemi come l’User Account Control (UAC) di Windows, che limita l’esecuzione di operazioni potenzialmente dannose senza autorizzazione dell’utente. 

Queste misure aiutano a ridurre la superficie d’attacco e limitano l’impatto di eventuali compromissioni.