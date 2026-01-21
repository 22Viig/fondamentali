---
layout: page
title: Sicurezza nei Sistemi Informatici
args: (Public Key Infrastructure, Protocolli di sicurezza, VPN)
permalink: /ssi-03/

---
Argomenti: 
- [1. Public Key Infrastructure](#public-key-infrastructure)
- [2. Protocolli di sicurezza](#protocolli -di-sicurezza)

## Public Key Infrastructure

La PKI è un sistema complesso composto da hardware, software, regole e soggetti che lavorano insieme per gestire la crittografia asimmetrica, cioè l’uso della chiave pubblica e privata. In questo ecosistema operano le Certificate Authority (CA), entità che emettono, validano, gestiscono e revocano i certificati digitali. Il loro ruolo è cruciale perché garantiscono che la chiave pubblica contenuta in un certificato appartenga davvero all’identità dichiarata.

Un certificato digitale è quindi un documento elettronico firmato digitalmente che associa in modo univoco una chiave pubblica a una persona, a un server o a un dispositivo. Esistono certificati per la sola autenticazione (single-sided) o per l’autenticazione reciproca (dual-sided), usati ad esempio nelle VPN o nei sistemi più sensibili.

Alcuni certificati possiedono caratteristiche particolari, come i wildcard, che permettono a tutti i sottodomini di un sito di utilizzare lo stesso certificato, oppure i certificati con Subject Alternative Name (SAN), che possono includere più domini e indirizzi IP. Tutti questi certificati sono basati sullo standard X.509, il quale definisce struttura, campi e regole di codifica (BER, CER, DER).

Esistono diversi formati di certificato, come PEM, CER, CRT, oppure contenitori più complessi come P12/PFX, utili per trasportare chiavi private in modo protetto, ed P7B, formato tipico dello standard S/MIME.

Per stabilire la validità di un certificato, si utilizza la cosiddetta catena di fiducia, che parte da una CA radice (root), passa per CA intermedie e arriva al certificato finale. Se uno degli anelli della catena non è riconosciuto, il certificato non viene considerato valido.

## Certificate Authority

Le CA seguono procedure precise: verificano l’identità del richiedente (tramite la Registration Authority), emettono il certificato sulla base del Certificate Signing Request (CSR), pubblicano le chiavi pubbliche e mantengono i registri dei certificati revocati. La revoca può essere inserita in una Certificate Revocation List (CRL) o in una Certificate Suspension List (CSL).

Per accelerare la verifica dello stato di un certificato, invece della CRL si utilizza l’OCSP (Online Certificate Status Protocol), che consente una verifica immediata. Una sua evoluzione è il OCSP Stapling, in cui il server stesso conserva e fornisce la prova aggiornata della validità.

Un meccanismo ulteriore per aumentare la sicurezza è il Public Key Pinning, che permette a un sito web di specificare quali chiavi pubbliche sono ritenute affidabili, riducendo il rischio di attacchi basati su certificati falsi.

Il concetto di Key Escrow, ovvero la conservazione sicura di copie delle chiavi private in caso di necessità di recupero, e introduce un modello alternativo alle CA: il Web of Trust, su cui si basa ad esempio PGP. In questo modello, la fiducia non è centralizzata ma distribuita, e la reputazione deriva dal giudizio della comunità.

## Protocolli di sicurezza

### S/MIME

È uno standard che protegge la posta elettronica tramite firma digitale e cifratura. Offre autenticità, integrità e riservatezza del contenuto. Un effetto collaterale è che la cifratura protegge tutto, anche eventuale malware allegato, rendendo più difficile l’analisi antivirus.

### TLS/SSL

TLS (e il suo predecessore SSL) è il protocollo che protegge la maggior parte delle comunicazioni web, come HTTPS, messaggistica e VoIP. Utilizza certificati X.509 e una serie di algoritmi chiamati suite di cifratura. Le porte standard dei protocolli cambiano quando vengono cifrati (ad esempio HTTP 80 diventa HTTPS 443).

Esistono alcuni rischi, come i downgrade attack, in cui un aggressore forza l’uso di versioni più deboli del protocollo, e descrive come un web proxy possa ispezionare il traffico agendo come un attacco man-in-the-middle autorizzato.

### SSH

SSH è un protocollo che crea un tunnel cifrato tra due computer e permette il controllo remoto sicuro. Utilizza la porta 22 e segue il modello client–server. È fondamentale per l’amministrazione di sistemi e dispositivi a distanza.

## VPN

Le Virtual Private Network (VPN) consentono a due o più dispositivi, non appartenenti alla stessa rete, di comunicare come se fossero in una rete privata. Esistono vari protocolli:

### PPTP
Uno dei più vecchi. Utilizza il protocollo PPP incapsulato e tecniche di autenticazione come CHAP. Usa la porta 1723.

### L2TP e L2TP/IPsec

L2TP fornisce il tunneling, mentre IPsec offre autenticazione e cifratura. È più sicuro di PPTP e ampiamente utilizzato.

### IPsec

È una suite di protocolli per autenticazione, integrità e sicurezza dei pacchetti IP. Offre modalità Transport (cifra solo il payload) e Tunnel (cifra l’intero pacchetto), utilizzata soprattutto per VPN su Internet.

La gestione delle chiavi in IPsec avviene tramite il protocollo IKE, che opera in due fasi: negoziazione del tunnel iniziale e creazione delle Security Association, e successiva definizione dei parametri del tunnel di fase 2.


