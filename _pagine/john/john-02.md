---
layout: page
title: John the Ripper 2
args: (NTHash / NTLM, /etc/shadow, Single Crack Mode, Regole personalizzate)
permalink: /john-02/

---

Argomenti: 
- [1. NTHash / NTLM](#nthash-/-ntlm)
- [2. /etc/shadow](#/etc/shadow)
- [3. R personalizzate](#regole-personalizzate)

## NTHash / NTLM

NThash è il formato hash utilizzato dai moderni sistemi operativi Windows per memorizzare le password utente e di servizio. È anche comunemente noto come NTLM , che fa riferimento alla versione precedente del formato Windows per l'hashing delle password, noto come LM, da cui NT/LM.

Un po' di storia: la designazione NT per i prodotti Windows originariamente significava "Nuova Tecnologia". Fu utilizzata a partire da Windows NT per indicare prodotti non basati sul sistema operativo MS- DOS . Col tempo, la linea "NT" divenne il tipo di sistema operativo standard rilasciato da Microsoft e il nome fu abbandonato, ma sopravvive ancora nei nomi di alcune tecnologie Microsoft.

In Windows, SAM (Security Account Manager) viene utilizzato per archiviare le informazioni sugli account utente, inclusi nomi utente e password con hash. È possibile acquisire hash NTHash/ NTLM scaricando il database SAM su un computer Windows, utilizzando uno strumento come Mimikatz o il database di Active Directory: NTDS.dit. Potrebbe non essere necessario decifrare l'hash per continuare l'escalation dei privilegi, poiché spesso è possibile condurre un attacco "pass the hash", ma a volte il cracking dell'hash è un'opzione praticabile in presenza di una policy per le password debole.

Per crackare hash di algoritmi di tipo NTLM bisogna usare il formato NT di con il comando `john --format=nt ...`

## /etc/shadow

Il /etc/shadow file è il file sui computer Linux in cui vengono memorizzati gli hash delle password. Contiene anche altre informazioni, come la data dell'ultima modifica della password e la data di scadenza. Contiene una voce per riga per ogni utente o account utente del sistema. Questo file è solitamente accessibile solo dall'utente root, quindi è necessario disporre di privilegi sufficienti per accedere agli hash. Tuttavia, in tal caso, è possibile decifrare alcuni degli hash.

### Unshadowing

John può essere molto esigente riguardo ai formati in cui i dati devono essere elaborati; per questo motivo, per decifrare /etc/shadow password, è necessario combinarle con il /etc/passwd file affinché John possa comprendere i dati che gli vengono forniti. Per fare questo, utilizziamo uno strumento integrato nella suite di strumenti John chiamato unshadow. La sintassi di base di unshadow è la seguente:

`unshadow [path to passwd] [path to shadow]`

- `unshadow`: richiama lo strumento unshadow
- `[path to passwd]`: Il file che contiene la copia del /etc/passwd file che hai preso dalla macchina di destinazione
- `[path to shadow]`: Il file che contiene la copia del /etc/shadow file che hai preso dalla macchina di destinazione

Esempio di utilizzo:

`unshadow local_passwd local_shadow > unshadowed.txt`

### Cracking

Possiamo quindi inviare l'output da `unshadow`, nel nostro caso d'uso di esempio chiamato `unshadowed.txt`, direttamente a John. Non dovremmo aver bisogno di specificare una modalità qui, poiché abbiamo creato l'input specificamente per John; tuttavia, in alcuni casi, sarà necessario specificare il formato come abbiamo in precedenza utilizzando: `--format=sha512crypt`

`john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt unshadowed.txt`

## Single Crack Mode
Finora abbiamo utilizzato la modalità wordlist di John per forzare brute force hash semplici e non così semplici. Ma John dispone anche di un'altra modalità, chiamata modalità Single Crack . In questa modalità, John utilizza solo le informazioni fornite nel nome utente per cercare di ricavare euristicamente possibili password modificando leggermente le lettere e i numeri contenuti nel nome utente.

### Word Mangling

Il modo migliore per spiegare la modalità Single Crack e la manipolazione delle parole è attraverso un esempio:

Prendiamo in considerazione il nome utente "Markus".

Alcune possibili password potrebbero essere:

- Markus1, Markus2, Markus3 (ecc.)
- MArkus, MARkus, MARKus (ecc.)
- Markus!, Markus$, Markus* (ecc.)

Questa tecnica è chiamata "word mangling". John costruisce il suo dizionario in base alle informazioni che gli vengono fornite e utilizza un insieme di regole chiamate "regole di mangling", che definiscono come può mutare la parola con cui inizia per generare un elenco di parole basato su fattori rilevanti per il target che si sta cercando di decifrare. Questa tecnica sfrutta il fatto che le password possono essere deboli in base a informazioni sul nome utente o sul servizio a cui si sta effettuando l'accesso.

### GECOS

L'implementazione di John del word mangling è compatibile anche con il campo GECOS del sistema operativo UNIX, così come con altri sistemi operativi simili a UNIX come Linux . GECOS sta per General Electric Comprehensive Operating System. Nell'ultimo esercizio, abbiamo esaminato le voci per e /etc/shadow. /etc/passwdOsservando attentamente, noterete che i campi sono separati da due punti :. Il quinto campo nel record dell'account utente è il campo GECOS. Memorizza informazioni generali sull'utente, come il nome completo, il numero di ufficio e il numero di telefono, tra le altre cose. John può utilizzare le informazioni memorizzate in questi record, come il nome completo e il nome della directory home, per aggiungerle alla wordlist generata durante la decifratura /etc/shadowdegli hash in modalità di decifratura singola.

### Utilizzo della modalità Single Crack

Per utilizzare la modalità di cracking singolo, utilizziamo più o meno la stessa sintassi che abbiamo utilizzato finora; ad esempio, se volessimo crackare la password dell'utente chiamato "Mike", utilizzando la modalità singola, useremmo:

`john --single --format=[format] [path to file]`

- `--single`: Questo flag fa sapere a John che vuoi usare la modalità di cracking hash singolo
- `--format=[format]`:Come sempre, è fondamentale identificare il formato corretto.

Esempio di utilizzo:

`john --single --format=raw-sha256 hashes.txt`

Nota sui formati di file in modalità crack singolo:

Se si craccano hash in modalità "single crack", è necessario modificare il formato del file che si sta fornendo a John affinché capisca da quali dati creare una wordlist. Per farlo, si antepone all'hash il nome utente a cui appartiene l'hash, quindi, secondo l'esempio precedente, dovremmo modificare il file.hashes.txt

- Da 1efee03cdcb96d90ad48ccc7b8666033

- A mike:1efee03cdcb96d90ad48ccc7b8666033

## Regole personalizzate

Le regole personalizzate sono definite nel john.conffile. Questo file si trova in /opt/john/john.confsu TryHackMe Attackbox. Di solito si trova in `/etc/john/john.conf` se John è stato installato utilizzando un gestore di pacchetti o compilato dal codice sorgente con make.

Esaminiamo la sintassi di queste regole personalizzate, utilizzando l'esempio precedente come modello di riferimento. Nota che è possibile definire un livello di controllo granulare molto elevato in queste regole. Ti consiglio di consultare la wiki qui per una panoramica completa dei modificatori che puoi utilizzare e altri esempi di implementazione delle regole.

La prima riga:

`[List.Rules:MyRule]` viene utilizzato per definire il nome della regola; questo è ciò che utilizzerai per chiamare la tua regola personalizzata un argomento John.

Utilizziamo quindi un pattern di corrispondenza in stile regex per definire dove verrà modificata la parola; ancora una volta, qui tratteremo solo i modificatori principali e più comuni:

- `Az`: Prende la parola e la aggiunge con i caratteri che definisci
- `A0`: Prende la parola e le aggiunge i caratteri che definisci
- `c`: Mette in maiuscolo il carattere posizionalmente
Possono essere utilizzati in combinazione per definire dove e cosa nella parola si desidera modificare.

Infine, dobbiamo definire quali caratteri devono essere aggiunti, anteposti o altrimenti inclusi. Lo facciamo aggiungendo set di caratteri tra parentesi quadre [ ]dove devono essere utilizzati. Questi seguono gli schemi dei modificatori tra virgolette doppie " ". Ecco alcuni esempi comuni:

- `[0-9]`: Includerà i numeri da 0 a 9
- `[0]`: Includerà solo il numero 0
- `[A-z]`: Includerà sia maiuscole che minuscole
- `[A-Z]`: Includerà solo lettere maiuscole
- `[a-z]`: Includerà solo lettere minuscole

Si prega di notare che:

- `[a]`: Includerà soloa
- `[!£$%@]`: Includerà i simboli !, £, $, %, e@


### Utilizzo di regole personalizzate

Potremmo quindi chiamare questa regola personalizzata un argomento John utilizzando il  `--rule=MyRule`.
