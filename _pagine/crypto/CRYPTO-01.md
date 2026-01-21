---
layout: page
title: Basi di Crittografia 1
args: (Crittografia Simmetrica, Crittografia Asimmetrica, RSA, Scambio di chiavi Diffie-Hellman, openssl, chiave pubblica)
permalink: /CRYPTO-01/

---

Argomenti
- [1. Crittografia Simmetrica](#crittografia-simmetrica)
- [2. Crittografia Asimmetrica](#crittografia-asimmetrica)
- [3. RSA](#rsa)
- [4. Scambio di chiavi Diffie-Hellman](#scambio-di-chiavi-diffie-hellman)

## Crittografia Simmetrica

La crittografia simmetrica , nota anche come crittografia simmetrica , utilizza la stessa chiave per crittografare e decrittografare i dati, come mostrato nella figura seguente. Mantenere segreta la chiave è fondamentale; è anche chiamata crittografia a chiave privata . Inoltre, comunicare la chiave alle parti interessate può essere complicato, poiché richiede un canale di comunicazione sicuro. Mantenere la segretezza della chiave può rappresentare una sfida significativa, soprattutto in presenza di numerosi destinatari. Il problema diventa ancora più grave in presenza di un avversario potente; si pensi, ad esempio, alla minaccia dello spionaggio industriale.

Consideriamo il semplice caso in cui hai creato un documento protetto da password per condividerlo con un tuo collega. Puoi facilmente inviare via email il documento crittografato al tuo collega, ma molto probabilmente non puoi inviargli la password. Il motivo è che chiunque abbia accesso alla sua casella di posta elettronica avrebbe accesso sia al documento protetto da password che alla sua password. Pertanto, devi pensare a un modo diverso, ovvero un canale, per condividere la password. A meno che tu non pensi a un canale sicuro e accessibile, una soluzione potrebbe essere quella di incontrarti di persona e comunicare la password al collega.

Esempi di crittografia simmetrica sono DES (Data Encryption Standard), 3DES (Triple DES ) e AES (Advanced Encryption Standard).

- Il DES è stato adottato come standard nel 1977 e utilizza una chiave a 56 bit. Con l'aumento della potenza di calcolo, nel 1999 una chiave DES è stata violata con successo in meno di 24 ore, spingendo il passaggio al 3DES.
- 3DES è il DES applicato tre volte; di conseguenza, la dimensione della chiave è di 168 bit, sebbene la sicurezza effettiva sia di 112 bit. 3DES era più una soluzione ad hoc quando DES non era più considerato sicuro. 3DES è stato deprecato nel 2019 e dovrebbe essere sostituito da AES ; tuttavia, potrebbe ancora essere presente in alcuni sistemi legacy.
- AES è stato adottato come standard nel 2001. La dimensione della sua chiave può essere di 128, 192 o 256 bit.

Esistono molti altri cifrari simmetrici utilizzati in varie applicazioni; tuttavia, non sono stati adottati come standard.


## Crittografia Asimmetrica

A differenza della crittografia simmetrica, che utilizza la stessa chiave per la crittografia e la decrittografia, la crittografia asimmetrica utilizza una coppia di chiavi, una per la crittografia e l'altra per la decrittografia, come mostrato nell'illustrazione seguente. Per proteggere la riservatezza, la crittografia asimmetrica, o crittografia asimmetrica, crittografa i dati utilizzando la chiave pubblica; per questo motivo, è anche chiamata crittografia a chiave pubblica.

Esempi sono RSA , Diffie-Hellman e crittografia a curve ellittiche ( ECC ). Le due chiavi coinvolte nel processo sono chiamate chiave pubblica e chiave privata . I dati crittografati con la chiave pubblica possono essere decrittografati con la chiave privata. La chiave privata deve essere mantenuta privata, da cui il nome.

La crittografia asimmetrica tende a essere più lenta e molti cifrari asimmetrici utilizzano chiavi più grandi rispetto alla crittografia simmetrica. Ad esempio, RSA utilizza chiavi a 2048 bit, 3072 bit e 4096 bit; 2048 bit è la dimensione minima consigliata per la chiave. Anche Diffie-Hellman ha una dimensione minima consigliata per la chiave di 2048 bit, ma utilizza chiavi a 3072 bit e 4096 bit per una maggiore sicurezza. D'altra parte, ECC può raggiungere un livello di sicurezza equivalente con chiavi più corte. Ad esempio, con una chiave a 256 bit, ECC fornisce un livello di sicurezza paragonabile a una chiave RSA a 3072 bit .

La crittografia asimmetrica si basa su un particolare gruppo di problemi matematici che sono facili da risolvere in una direzione, ma estremamente difficili da invertire. In questo contesto, "estremamente difficile" significa praticamente irrealizzabile. Ad esempio, possiamo fare affidamento su un problema matematico che richiederebbe molto tempo, ad esempio milioni di anni, per essere risolto utilizzando la tecnologia odierna.

## RSA

A è un algoritmo di crittografia a chiave pubblica che consente la trasmissione sicura dei dati su canali non sicuri. Con un canale non sicuro, ci aspettiamo che gli avversari possano intercettarlo.

## La matematica che rende RSA sicuro

RSA si basa sul problema matematicamente complesso di fattorizzare un numero grande. Moltiplicare due numeri primi grandi è un'operazione semplice; tuttavia, trovare i fattori di un numero enorme richiede una potenza di calcolo molto maggiore.

Moltiplicare due numeri primi tra loro è semplice anche sulla carta, ad esempio 113 × 127 = 14351. Anche per numeri primi più grandi, sarebbe comunque un lavoro fattibile, anche a mano. Consideriamo il seguente esempio numerico:

Numero primo 1: 982451653031
Numero primo 2: 169743212279
Il loro prodotto: 982451653031 × 169743212279 = 166764499494295486767649
D'altro canto, è piuttosto complicato determinare quali due numeri primi moltiplicati tra loro danno 14351 , ed è ancora più difficile trovare i fattori di 166764499494295486767649 .

In esempi reali, i numeri primi sarebbero molto più grandi di quelli in questo esempio. Un computer può facilmente fattorizzare 166764499494295486767649 ; tuttavia, non può fattorizzare un numero con più di 600 cifre. E converrete che la moltiplicazione dei due enormi numeri primi, ciascuno di circa 300 cifre, sarebbe più facile della fattorizzazione del loro prodotto.

Nel seguente esempio numerico semplificato, vediamo l' algoritmo RSA in azione:

- Bob sceglie due numeri primi: p  = 157 e q  = 199. Calcola n  =  p  ×  q  = 31243 .

- Con ϕ ( n ) =  n  −  p  −  q  + 1 = 31243 − 157 − 199 + 1 = 30888 , Bob seleziona e  = 163 in modo che e sia relativamente primo a ϕ ( n ) ; inoltre, seleziona d  = 379 , dove e  ×  d  = 1 mod ϕ ( n ) , ovvero e  ×  d  = 163 × 379 = 61777 e 61777 mod 30888 = 1 . La chiave pubblica è ( n , e ) , ovvero (31243,163) e la chiave privata è $(n,d), ovvero (31243,379) .

- Supponiamo che il valore che vogliono crittografare sia x  = 13 , allora Alice calcolerà e invierà y  =  x e mod n  = 13 163 mod 31243 = 16341 .

- Bob decifrerà il valore ricevuto calcolando x  =  y d mod n  = 16341 379 mod 31243 = 13. In questo modo, Bob recupera il valore inviato da Alice.
La dimostrazione del funzionamento dell'algoritmo sopra descritto si può trovare nell'aritmetica modulare e va oltre lo scopo di questo modulo. Vale la pena ripetere che in questo esempio abbiamo scelto un numero primo a tre cifre, mentre in un'applicazione reale, p e q sarebbero numeri primi di almeno 300 cifre ciascuno.

## Scambio di chiavi Diffie-Hellman

Lo scambio di chiavi mira a stabilire un segreto condiviso tra due parti. È un metodo che consente a due parti di stabilire un segreto condiviso su un canale di comunicazione non sicuro senza richiedere un segreto condiviso preesistente e senza che un osservatore possa ottenere questa chiave. Di conseguenza, questa chiave condivisa può essere utilizzata per la crittografia simmetrica nelle comunicazioni successive.

Consideriamo il seguente scenario. Alice e Bob vogliono comunicare in modo sicuro. Vogliono stabilire una chiave condivisa per la crittografia simmetrica, ma non vogliono utilizzare la crittografia asimmetrica per lo scambio di chiavi. È qui che entra in gioco lo scambio di chiavi Diffie-Hellman.

Alice e Bob generano segreti indipendentemente; chiamiamoli A e B. Hanno anche del materiale pubblico comune; chiamiamolo C.

Dobbiamo fare alcune ipotesi. In primo luogo, ogni volta che combiniamo i segreti, è praticamente impossibile separarli. In secondo luogo, l'ordine in cui vengono combinati non ha importanza. Alice e Bob combineranno i loro segreti con il materiale comune per formare AC e BC. Poi se li invieranno a vicenda e combineranno la parte ricevuta con il loro segreto per creare due chiavi identiche, entrambe ABC. Ora possono usare questa chiave per comunicare.

Lo scambio di chiavi Diffie-Hellman viene spesso utilizzato insieme alla crittografia a chiave pubblica RSA . Diffie-Hellman viene utilizzato per l'accordo sulle chiavi, mentre RSA viene utilizzato per le firme digitali, il trasporto delle chiavi e l'autenticazione, tra le altre cose. Ad esempio, RSA aiuta a dimostrare l'identità della persona con cui si sta parlando tramite la firma digitale, poiché è possibile confermarla in base alla sua chiave pubblica. Questo impedirebbe a qualcuno di attaccare la connessione con un attacco man-in-the-middle contro Alice, fingendo di essere Bob. In breve, Diffie-Hellman e RSA sono integrati in molti protocolli e standard di sicurezza per fornire una soluzione di sicurezza completa.

## openssl

La libreria software OpenSSL è un toolkit robusto, di livello commerciale e completo per la crittografia generica e la comunicazione sicura.

Comandi utili:

- `openssl genrsa -out private-key.pem 2048`: Con openssl, abbiamo utilizzato genrsaper generare una chiave privata RSA. Utilizzando -out, abbiamo specificato che la chiave privata risultante viene salvata come private-key.pem. Abbiamo aggiunto 2048per specificare una dimensione della chiave di 2048 bit.

- `openssl rsa -in private-key.pem -pubout -out public-key.pem`: Utilizzando openssl, abbiamo specificato che stiamo utilizzando l'algoritmo RSA con l' rsaopzione. Abbiamo specificato che volevamo ottenere la chiave pubblica utilizzando -pubout. Infine, abbiamo impostato la chiave privata come input utilizzando -in private-key.peme salvato l'output utilizzando -out public-key.pem.

- `openssl rsa -in private-key.pem -text -noout`: Siamo curiosi di vedere variabili RSA reali , quindi abbiamo usato -text -noout. I valori di p , q , N , e , e d sono rispettivamente prime1, prime2, modulus, publicExponent, e privateExponent.

- `openssl pkeyutl -encrypt -in plaintext.txt -out ciphertext -inkey public-key.pem -pubin`: se abbiamo già la chiave pubblica del destinatario, possiamo crittografarla con il comando

- `openssl pkeyutl -decrypt -in ciphertext -inkey private-key.pem -out decrypted.txt` : decifrazione del messaggio

## Esempio

Ccosa succede quando accediamo a un sito web tramite HTTPS.

- Il client richiede il certificato SSL/ TLS del server
- Il server invia il certificato SSL/ TLS al client
- Il cliente conferma che il certificato è valido

Il ruolo della crittografia inizia con la verifica del certificato. Affinché un certificato sia considerato valido, deve essere firmato. La firma implica che un hash del certificato venga crittografato con la chiave privata di una terza parte attendibile; l'hash crittografato viene aggiunto al certificato.

Se la terza parte è attendibile, il client utilizzerà la chiave pubblica della terza parte per decifrare l'hash crittografato e confrontarlo con l'hash del certificato. Tuttavia, se la terza parte non viene riconosciuta, la connessione non procederà automaticamente.

Una volta che il client conferma la validità del certificato, viene avviato un handshake SSL/ TLS . Questo handshake consente al client e al server di concordare, tra le altre cose, la chiave segreta e l'algoritmo di crittografia simmetrica. Da questo momento in poi, tutte le comunicazioni di sessione correlate saranno crittografate utilizzando la crittografia simmetrica.

Il passaggio finale consiste nel fornire le credenziali di accesso. Il client utilizza la sessione SSL/ TLS crittografata per inviarle al server. Il server riceve nome utente e password e deve confermare che corrispondano.

Seguendo le linee guida di sicurezza, ci aspettiamo che il server salvi una versione hash della password dopo avervi aggiunto un salt casuale. In questo modo, in caso di violazione del database, le password sarebbero difficili da recuperare.