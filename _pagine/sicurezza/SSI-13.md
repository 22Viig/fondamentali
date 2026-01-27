---
layout: page
title: Sicurezza nei Sistemi Informatici 13
args: (Autenticazione e Controlli d’Accesso)
permalink: /SSI-012/

---
Argomenti: 
- [1. Autenticazione e Controlli d’Accesso](#autenticazione-e-controlli-d-accesso)


## Autenticazione e Controlli d’Accesso

La lezione dedicata all’**autenticazione** e ai **controlli d’accesso** analizza in maniera organica tutti gli elementi che consentono di verificare l’identità di un utente o di un dispositivo e di autorizzarlo all’uso di risorse specifiche in un sistema informatico. Fin dalle prime slide si affronta il concetto di **autenticazione a più fattori (Multi‑Factor Authentication – MFA)**, uno dei metodi più affidabili per garantire la sicurezza degli accessi digitali. La **MFA** si basa sull’impiego congiunto di più categorie di verifica, tra cui **ciò che l’utente conosce**, **ciò che possiede**, **ciò che è**, **dove si trova** oppure **ciò che fa**.

Le slide mostrano come questi criteri vengano combinati in maniera flessibile per innalzare il livello di sicurezza oltre la semplice **password**, che da sola rappresenta un meccanismo sempre più debole e vulnerabile. L’autenticazione a un solo fattore è infatti spesso limitata a **username e password**, mentre sistemi più evoluti adottano password temporanee come **TOTP** e **HOTP**, generate dinamicamente tramite un segreto condiviso. Altri modelli più moderni includono la **continuous authentication**, che non si limita alla verifica iniziale ma prosegue nel tempo analizzando costantemente il comportamento dell’utente attraverso tecniche basate su **AI** e **machine learning**.

A questo punto, la lezione introduce i **modelli di autenticazione**, tra cui quello **context‑aware**, che valuta fattori ambientali come posizione, orario o dispositivo prima di concedere l’accesso. Il modello **Single Sign‑On (SSO)** semplifica l’esperienza dell’utente collegando un unico profilo a molteplici servizi, mentre il **Federated Identity Management (FIM)** estende questo principio tra organizzazioni diverse.

All'interno delle federazioni, i meccanismi di **trust** possono essere basati su **cross‑certification** o su un **trusted third party**, mentre uno dei linguaggi più comuni per lo scambio di informazioni di identità è **SAML**, un formato basato su XML che consente al **service provider** di delegare l’autenticazione all’**identity provider**. Le slide presentano anche **OAuth** e **OpenID Connect (OIDC)**, tecnologie fondamentali per l’autorizzazione e l’autenticazione nelle applicazioni web moderne.

In ambito di rete si affrontano protocolli come **802.1X**, un framework IEEE che regola l’accesso a LAN e WLAN attraverso l’autenticazione di **supplicant** e **authenticator** mediante server **RADIUS** o **TACACS+**. Grazie a **EAP** ed alle sue varianti – tra cui **EAP‑TLS**, **EAP‑FAST**, **PEAP** – è possibile negoziare chiavi sicure e stabilire connessioni protette. A questo si aggiungono due pilastri dell’autenticazione aziendale: **LDAP**, protocollo di interrogazione delle directory, e **Kerberos**, un sistema basato su **ticket** e sicurezza bidirezionale utilizzato da **Active Directory**.

Le slide proseguono con un approfondimento sui servizi di accesso remoto, come il **Remote Desktop Protocol (RDP)** e il **Virtual Network Computing (VNC)**, che permettono il controllo di macchine remote tramite interfaccia grafica. L’autenticazione remota può basarsi su protocolli come **PAP**, ormai obsoleto perché invia le password in chiaro, e **CHAP**, che migliora la sicurezza evitando l’invio diretto della password.

Per rendere sicura la connessione a reti aziendali da remoto vengono utilizzate le **VPN**, che creano tunnel cifrati tramite tecnologie come **PPTP** o **L2TP** e con il supporto di **VPN concentrator**. Il traffico può essere gestito con approcci come lo **split tunneling**, che separa il traffico interno da quello esterno.

All’interno delle infrastrutture aziendali la gestione dell’autenticazione avviene spesso tramite sistemi come **RADIUS** e **TACACS+**, che svolgono funzioni centralizzate di **autenticazione**, **autorizzazione** e **accounting (AAA)**. RADIUS opera tramite **UDP** sulle porte 1812/1813, mentre TACACS+, proprietario Cisco, usa **TCP** e fornisce un controllo più granulare e sicuro.

Le slide si soffermano anche sulle principali **forme di attacco** relative all’autenticazione: **spoofing**, **Man‑in‑the‑Middle**, **password spraying**, **credential stuffing** e **broken authentication**. Questi attacchi vengono contrastati attraverso misure come **autenticazione forte**, **NAC**, formazione degli utenti e controlli sui meccanismi di **session management**.

La seconda parte della lezione è dedicata al **controllo degli accessi**, cioè ai meccanismi che regolano chi può accedere a quali risorse. Si parte dal modello **Discretionary Access Control (DAC)**, dove il proprietario dell’oggetto definisce le autorizzazioni, per poi passare al **Mandatory Access Control (MAC)**, in cui è il sistema a gestire rigidamente i privilegi tramite **etichette** e livelli di riservatezza, seguendo i principi di **minimum level** e **need‑to‑know**.

Il modello **Role‑Based Access Control (RBAC)** assegna i diritti in base al ruolo dell’utente, mentre l’**Attribute‑Based Access Control (ABAC)** permette un controllo dinamico basato su regole contestuali che combinano attributi dell’utente, della risorsa e dell’ambiente. L’approccio ABAC consente un livello di precisione elevato, permettendo scenari come accessi condizionati a orari, sedi o tipologie di dispositivo.

La lezione sottolinea alcune **best practice** fondamentali per una gestione sicura degli accessi: il principio di **implicit deny**, secondo cui tutto è vietato finché non viene esplicitamente consentito; il concetto di **least privilege**; la **separation of duties**; il **job rotation**, utile per scoprire attività anomale.

In ambienti Windows, strumenti come **Active Directory Users and Computers (ADUC)** permettono di gestire utenti, gruppi e diritti. I permessi in Windows includono **full control**, **modify**, **read & execute**, mentre in Linux i permessi si articolano su **owner**, **group** e **others**, con il comando **chmod** che consente la gestione numerica delle autorizzazioni.

Un rischio importante è il **privilege creep**, l’accumulo incontrollato di privilegi nel tempo, contrastabile tramite **User Access Recertification**. Infine, si discutono le buone pratiche sulle **password**, come complessità minima, cambio periodico, disabilitazione degli account guest e uso di **UAC** per limitare l’esecuzione con privilegi amministrativi.
