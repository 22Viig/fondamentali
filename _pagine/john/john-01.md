---
layout: page
title: John the Ripper 1
args: (Gli hash, Sintesi di base, Cracking automatico)
permalink: /john-01/

---

Argomenti: 
- [1. Gli Hash](#gli-hash)
- [2. Sintesi di base](#sintesi-di-base)
- [3. Cracking automatico](#cracking-automatico)



## Gli Hash

Un hash è un modo per prendere un dato di qualsiasi lunghezza e rappresentarlo in un'altra forma di lunghezza fissa. Questo processo maschera il valore originale dei dati. Il valore hash si ottiene eseguendo sui dati originali un algoritmo di hashing. Esistono molti algoritmi di hashing popolari, come MD4, MD5 , SHA1 e NTLM . Proviamo a dimostrarlo con un esempio:

Se prendiamo "polo", una stringa di quattro caratteri, e la eseguiamo attraverso un algoritmo di hashing MD5 , otteniamo un output di b53759f3ce692de7aff1b5779d3964da, un hash MD5 standard di 32 caratteri.

Allo stesso modo, se prendiamo "polomints", una stringa di 9 caratteri, e la eseguiamo attraverso lo stesso algoritmo di hashing MD5, otteniamo un output di , un altro hash MD5584b6e4f4586e136bc280f27f9c64f3b standard di 32 caratteri .

Cosa rende sicuri gli hash?
Le funzioni di hash sono progettate come funzioni unidirezionali. In altre parole, è facile calcolare il valore hash di un dato input; tuttavia, trovare l'input originale dato il valore hash è un problema arduo. In parole povere, un problema difficile diventa rapidamente computazionalmente irrealizzabile in informatica. Questo problema computazionale affonda le sue radici nella matematica, come P vs NP.

In informatica, P e NP sono due classi di problemi che ci aiutano a comprendere l'efficienza degli algoritmi:

- P (Tempo Polinomiale) : la Classe P comprende i problemi la cui soluzione può essere trovata in tempo polinomiale. Si consideri l'ordinamento di una lista in ordine crescente. Più lunga è la lista, più tempo ci vorrebbe per ordinarla; tuttavia, l'aumento del tempo non è esponenziale.
- NP (Tempo Polinomiale Non Deterministico) : i problemi di classe NP sono quelli per i quali una data soluzione può essere verificata rapidamente, anche se trovare la soluzione stessa potrebbe essere difficile. Infatti, non sappiamo se esista un algoritmo veloce per trovare la soluzione in primo luogo.


### Dove entra in gioco John

Anche se l'algoritmo non è facilmente reversibile, ciò non significa che sia impossibile decifrare gli hash. Se, ad esempio, si dispone della versione hash di una password e si conosce l'algoritmo di hashing, è possibile utilizzarlo per eseguire l'hashing di un gran numero di parole, chiamato dizionario. È quindi possibile confrontare questi hash con quello che si sta cercando di decifrare per vedere se corrispondono. In tal caso, si sa quale parola corrisponde a quell'hash: l'hai decifrato!

Questo processo è chiamato attacco a dizionario e John the Ripper , o John come viene comunemente abbreviato, è uno strumento per condurre rapidi attacchi brute force su vari tipi di hash.


## Sintesi di base

Sintassi di base di John
La sintassi di base dei comandi di John the Ripper è la seguente. Analizzeremo le opzioni e i modificatori specifici utilizzati man mano che li utilizzeremo.

`john [options] [file path]`

`john`: Richiama il programma John the Ripper
`[options]`: Specifica le opzioni che vuoi usare
`[file path]`: Il file contenente l'hash che stai cercando di decifrare; se si trova nella stessa directory, non dovrai indicare un percorso, ma solo il file.

## Cracking automatico

John ha funzionalità integrate per rilevare il tipo di hash fornito e selezionare le regole e i formati appropriati per decifrarlo; questa non è sempre la soluzione migliore, in quanto può essere inaffidabile, ma se non riesci a identificare il tipo di hash con cui stai lavorando e vuoi provare a decifrarlo, può essere una buona opzione! Per farlo, utilizziamo la seguente sintassi:

`john --wordlist=[path to wordlist] [path to file]`

- `--wordlist=`: Specifica l'utilizzo della modalità wordlist, leggendo dal file fornito nel percorso fornito
- `[path to wordlist]`: Il percorso verso l'elenco di parole che stai utilizzando, come descritto nell'attività precedente

Esempio di utilizzo:

`john --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt`

### Cracking specifico del formato

Una volta identificato l'hash con cui hai a che fare, puoi dire a John di usarlo mentre cracca l'hash fornito utilizzando la seguente sintassi:

`john --format=[format] --wordlist=[path to wordlist] [path to file]`

`--format=`: Questo è il flag per dire a John che gli stai assegnando un hash di un formato specifico e di usare il seguente formato per decifrarlo
`[format]`: Il formato in cui si trova l'hash

Esempio di utilizzo:

`john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt`

Nota sui formati:

Quando dici a John di usare i formati, se hai a che fare con un tipo hash standard, ad esempio  md5 come nell'esempio precedente, devi anteporre il prefisso raw-per indicare a John che stai semplicemente gestendo un tipo hash standard, anche se questo non è sempre valido. Per verificare se è necessario aggiungere il prefisso o meno, puoi elencare tutti i formati di John usando `john --list=formats` e verificare manualmente o cercare il tuo tipo hash con grep usando qualcosa come `john --list=formats | grep -iF "md5"`.

