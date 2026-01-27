---
layout: page
title: Sicurezza nei Sistemi Informatici 10
args: (Malware mobile, Furti fisici, Sicurezza delle app, Modelli BYOD e hardening)
permalink: /SSI-010/

---
Argomenti: 
- [1. Malware mobile](#malware-mobile)
- [2. Furti fisici](#furti-fisici)
- [3. Sicurezza delle app](#sicurezza-delle-app)
- [4. Modelli BYOD e hardening](#modelli-byod-e-hardening)

La lezione si apre introducendo le principali aree di rischio legate all’uso dei dispositivi mobili in ambito personale e aziendale. Questi dispositivi, ormai essenziali per la vita quotidiana e lavorativa, rappresentano un punto critico della sicurezza informatica poiché combinano capacità di memorizzazione, comunicazione wireless, accesso ai servizi cloud e installazione autonoma di applicazioni. I rischi derivano da molteplici fattori: vulnerabilità e cattiva configurazione del sistema, app malevole, attacchi di rete, clonazione delle SIM, furti fisici e politiche di gestione aziendale non adeguate. L'obiettivo è comprendere queste minacce e le principali tecniche di mitigazione.

La prima parte del contenuto si concentra sulla sicurezza delle comunicazioni wireless, fondamentali per smartphone e tablet. Vengono presentati gli standard WPA2 e WPA3, oggi considerati i metodi più sicuri per proteggere le reti Wi-Fi domestiche e aziendali. Un ruolo analogo è rivestito dal Bluetooth, la cui fase di accoppiamento può rappresentare un punto debole se gestita in modo errato. Per questo motivo, molti sistemi adottano funzionalità aggiuntive di difesa come le soluzioni di Mobile Threat Defense (MTD), che sorvegliano costantemente configurazioni, integrità del sistema e possibili minacce di rete. Le MTD si affiancano o si integrano con strumenti più ampi come UEM e MDM, che gestiscono aspetti organizzativi e amministrativi dei dispositivi.

## Malware mobile
Una parte significativa della lezione è dedicata alle minacce software e alle tecniche di attacco che coinvolgono direttamente gli utenti. I dispositivi mobili possono essere colpiti da malware attraverso diversi vettori: vulnerabilità non corrette, app non sicure, comportamenti imprudenti degli utenti o attacchi che sfruttano i servizi di accessibilità.

Gli aggiornamenti del sistema operativo rivestono un ruolo fondamentale nella difesa, in quanto risolvono vulnerabilità che possono essere sfruttate da attaccanti per ottenere accessi non autorizzati o eseguire codice malevolo. È consigliato installare app esclusivamente dagli store ufficiali, poiché strumenti come Google Play Protect svolgono scansioni preventive e riducono il rischio di installare software dannoso.

La lezione presenta anche un esempio reale di app vulnerabile: una violazione della privacy dei contatti che costituiva un problema in termini di GDPR, risolta solo con un aggiornamento. Questo sottolinea come la sicurezza delle app non dipenda esclusivamente dall’utente, ma anche dallo sviluppatore e dalla capacità dell’ecosistema di aggiornarsi rapidamente.

Le tecniche di social engineering costituiscono un ulteriore capitolo di rischio. Gli attaccanti approfittano della distrazione, della fretta o dell’ingenuità dell’utente, ricorrendo a richieste fraudolente di password, carte di credito o autorizzazioni avanzate ingannevoli. Alcuni malware sfruttano l'accesso ai servizi di Accessibilità per monitorare il comportamento dell’utente e lanciare l’attacco nel momento più opportuno. Le contromisure raccomandate includono evitare il jailbreak o il rooting del dispositivo, non utilizzare firmware non ufficiali o ROM personalizzate, limitare l’installazione di app al minimo indispensabile (principio di least functionality), mantenere aggiornati i sistemi e ricorrere a soluzioni MTD.

## Furti fisici
Nel documento viene poi affrontata la tematica della SIM e delle sue potenziali vulnerabilità. La SIM contiene informazioni critiche per l’identificazione dell’utente sulla rete mobile, come l’IMSI (International Mobile Subscriber Identity), il codice MNC e il MCC. La clonazione della SIM rappresenta una minaccia significativa perché permette a un attaccante di impersonare l’utente, accedere ai suoi servizi e compromettere la sua privacy o sicurezza finanziaria.

Un altro gruppo di attacchi riguarda il Bluetooth. Vengono illustrati tre principali metodi:

- **Bluejacking**, che consiste nell’invio non richiesto di messaggi;
- **Bluesnarfing**, che permette di accedere a informazioni private;
- **Bluebugging**, che consente addirittura di controllare completamente il dispositivo bersaglio tramite una backdoor.

Per mitigare i rischi sono fondamentali la crittografia completa del dispositivo, il backup dei dati e l’utilizzo di strumenti di gestione remota come UEM o MDM, che permettono di bloccare o cancellare lo smartphone in caso di furto o smarrimento. A questo scopo, servizi come Google “Find My Device” o Apple “Find My” offrono localizzazione e controlli da remoto. Quando i dispositivi sono gestiti tramite UEM/MDM, è possibile applicare misure di sicurezza più stringenti come blocco dello schermo obbligatorio, verifica di conformità e configurazioni centralizzate.

## Sicurezza delle app
Un aspetto centrale della lezione è la sicurezza delle app. Il rooting (Android) e il jailbreak (iOS) espongono il dispositivo a rischi enormi poiché rimuovono le protezioni integrate del sistema operativo. Le soluzioni MTD continuano a giocare un ruolo fondamentale anche in questo contesto, affiancate dai sistemi di Mobile Device Management (MDM), che permettono la gestione centralizzata dei dispositivi aziendali tramite policy, profili e controlli sulle app.

Sono introdotti vari acronimi relativi alla gestione della mobilità aziendale: **EMM** (Enterprise Mobility Management), che integra MDM, MAM (Mobile Application Management), MEM e MCM, e **UEM** (Unified Endpoint Management), che amplia il controllo anche a dispositivi IoT o desktop. Esistono inoltre sistemi come **AppConfig** e **OEMConfig**, che permettono configurazioni avanzate e standardizzate da remoto.

Il tema della localizzazione e del **geotagging** evidenzia l’importanza della privacy: foto e video possono contenere metadati GPS, potenzialmente utilizzabili per tracciare l’utente.

## Modelli BYOD e hardening
La lezione si conclude con un approfondimento sui principali modelli di gestione dei dispositivi in azienda:

- **COBO**: dispositivi aziendali utilizzati solo per lavoro;
- **COPE**: dispositivi aziendali con uso personale consentito;
- **BYOD**: dispositivi personali dell’utente utilizzati anche per lavoro;
- **CYOD**: l'utente sceglie un dispositivo approvato dall’azienda.

Il modello BYOD è quello più complesso dal punto di vista della sicurezza, e per questo vengono presentate soluzioni come Android Enterprise con diversi profili (work profile, fully managed, COSU) e i dispositivi Apple in modalità supervised, pensati per un controllo più rigido.

Le tecniche di hardening consistono in azioni preventive come aggiornare regolarmente il dispositivo, installare antivirus e strumenti MTD, educare gli utenti, evitare rooting/jailbreaking, utilizzare SIM recenti, disattivare funzionalità non necessarie, attivare la cifratura, usare autenticazioni biometriche e adottare policy UEM basate sul contesto o sull’autenticazione continua.
