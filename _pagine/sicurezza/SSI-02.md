---
layout: page
title: Sicurezza nei Sistemi Informatici 2
args: (Concetti introduttivi di crittografia, Crittografia simmetrica e asimmetrica, Firma digitale, Tecniche avanzate, Funzioni hash)
permalink: /ssi-2/

---
Argomenti: 
- [1. Concetti introduttivi di crittografia](#Concetti-introduttivi-di-crittografia)
- [2. Crittografia simmetrica e asimmetrica](#crittografia-simmetrica-e-asimmetrica)
- [3. Firma digitale](#firma-digitale)

## Concetti introduttivi di crittografia

La crittografia è la disciplina che studia metodi per proteggere il contenuto di un messaggio, rendendolo illeggibile a chi non è autorizzato. Il suo obiettivo principale è garantire la riservatezza, ma nel tempo ha assunto un ruolo più ampio, integrando autenticazione, integrità e non ripudiabilità. La crittografia si affianca alla crittoanalisi, che invece studia tecniche per attaccare o violare sistemi crittografici.

Alla base di ogni sistema di cifratura ci sono due elementi: il **cifrario**, cioè l’algoritmo che trasforma il testo in chiaro in testo cifrato, e la **chiave**, che rappresenta il vero segreto e determina la robustezza di un algoritmo. Poiché la maggior parte degli algoritmi è pubblica, la sicurezza non deriva dall’oscurità del metodo, ma dalla segretezza e complessità della chiave. La cifratura può essere applicata ai dati statici (archiviati su disco), ai dati in transito (che viaggiano in rete) e ai dati in uso (caricati in RAM ed elaborati).

Per comprendere l’evoluzione moderna, si parte dai cifrari più semplici, come il Cifrario di Cesare o il ROT13, che si basano su rotazioni di caratteri. Questi metodi, oggi puramente didattici, mostrano come la sicurezza sia legata alla dimensione dello spazio delle chiavi e alla complessità dell’algoritmo.


## Crittografia simmetrica e asimmetrica

### Crittografia simmetrica

Nella crittografia simmetrica la stessa chiave viene usata sia per cifrare sia per decifrare. Questo implica grande velocità ed efficienza, ma anche la necessità di disporre di un canale sicuro per condividere la chiave. Gli algoritmi più importanti sono:

- DES: utilizza chiavi da 56 bit e blocchi da 64 bit; oggi è considerato insicuro.
- 3DES: applica DES tre volte per aumentare la sicurezza.
- AES: standard moderno con chiavi da 128, 192 e 256 bit; molto sicuro ed efficiente.
- Blowfish e Twofish: algoritmi open source con struttura a blocchi, variabili ed efficienti.
- Famiglia RC (RC4, RC5, RC6): comprendono cifrari a flusso e a blocchi, alcuni storicamente utilizzati ma oggi parzialmente deprecati.

Gli algoritmi simmetrici possono usare due approcci diversi: cifratura a flusso (elaborano i bit uno alla volta, ideali per stream audio/video) e cifratura a blocchi (elaborano gruppi di bit più grandi, tipicamente 64 o 128).

Per la cifratura a blocchi, esistono diverse modalità operative:

- ECB: semplice ma insicura, perché produce pattern ripetuti nel ciphertext.
- CBC: usa una XOR tra blocco corrente e precedente, migliorando la sicurezza.
- CTR/CTM: converte il blocco in flusso tramite contatori e vettori casuali; veloce e molto usato.
- GCM: combina CTR con un metodo di autenticazione basato su funzioni hash, garantendo integrità oltre alla riservatezza.

### Crittografia asimmetrica

La crittografia asimmetrica utilizza una coppia di chiavi: una pubblica e una privata. Con la chiave pubblica si cifra, mentre con la chiave privata si decifra (o viceversa, per la firma). Gli algoritmi principali sono:

- Diffie–Hellman: usato per lo scambio sicuro delle chiavi.
- RSA: basato sulla difficoltà di fattorizzare numeri molto grandi; ampiamente usato per cifratura, firma e distribuzione delle chiavi.
- ECC: sfrutta le curve ellittiche ed è molto più efficiente di RSA a parità di sicurezza, ideale per dispositivi mobili o risorse limitate.

Nella pratica, si usa un’implementazione ibrida: l’asimettrica serve per scambiare una chiave di sessione sicura, mentre la simmetrica cifra i dati effettivi.

## Firma digitale

La firma digitale consente di garantire integrità, autenticità e non ripudiabilità. Il processo avviene così:

- si calcola l’hash del messaggio;
- l’hash viene cifrato con la chiave privata del mittente: questo è la firma;
- il destinatario verifica la firma decifrando con la chiave pubblica del mittente.

La gestione delle chiavi si basa sulla PKI (Public Key Infrastructure), che definisce certificati digitali, CA, revoche, e procedure di validazione delle identità.
Strumenti come PGP e GPG permettono cifratura, firma e scambio chiavi in un modello più distribuito basato sul concetto di web of trust, in cui gli utenti certificano reciprocamente l’autenticità delle chiavi.

## Tecniche avanzate

### One-Time Pad e RNG
 
Il One-Time Pad è teoricamente perfetto: usa una chiave casuale lunga quanto il messaggio e non riutilizzabile. Tuttavia, è difficile da applicare perché richiede un generatore di numeri realmente casuali. Per questo spesso si utilizzano PRNG (pseudorandom number generator) in ambiti come OTP e autenticazione (2FA).

### Steganografia

La steganografia non cifra il messaggio, ma lo nasconde all’interno di altri file (immagini, audio, documenti). Sebbene non garantisca riservatezza da sola, è un utile strumento di offuscamento. Gli strumenti di steganalisi usano hash e confronti per individuare anomalie o alterazioni.

### Blockchain e applicazioni crittografiche moderne

La blockchain è una struttura dati condivisa, immutabile e decentralizzata, progettata per registrare transazioni in modo sicuro e verificabile. I blocchi sono concatenati tramite hash e non possono essere modificati retroattivamente. Esistono versioni pubbliche e private; tra le applicazioni correlate figurano anche gli NFT, basati su token unici.

### Computazione quantistica e crittografia post-quantistica

I computer quantistici sfruttano qubit, sovrapposizione ed entanglement, permettendo di risolvere rapidamente problemi matematici complessi. Questo minaccia algoritmi come RSA e Diffie–Hellman. Per questo sono nati:

- la crittografia quantistica, che usa i fotoni per scambi sicuri di chiavi;
- la crittografia post-quantistica, con nuovi algoritmi resistenti agli attacchi quantistici (lattice-based, SIDH, ecc.).

La Perfect Forward Secrecy, usata ad esempio in WPA3 e TLS, assicura che la compromissione di una chiave a lungo termine non comprometta le sessioni passate.

## Funzioni hash

Una funzione hash è una trasformazione non invertibile che produce un output a lunghezza fissa, utile per verificare integrità, firme digitali e gestione delle password. Gli algoritmi principali includono:

- MD5, oggi insicuro per via delle collisioni;
- SHA-0, SHA-1, considerati deboli;
- SHA-2 e SHA-3, moderni e robusti;
- RIPEMD e HMAC, che aggiungono integrità e autenticazione tramite chiavi segrete.

### Attacchi alle funzioni hash

- Pass-the-hash: un attaccante usa l’hash di una password per autenticarsi.
- Birthday attack: sfrutta la probabilità di collisione per ottenere messaggi diversi con lo stesso hash.
- Rainbow tables: tabelle precomputate per decifrare password dai loro hash.

### Contromisure

- Key stretching (PBKDF2, bcrypt): rende più costoso ogni tentativo di attacco ripetuto.
- Salting: aggiunge dati casuali alla password prima di applicare l’hash.
- Nonce e limiti sui tentativi falliti: prevengono attacchi automatizzati e replay.



