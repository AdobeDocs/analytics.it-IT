---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.trackExternalLinks

Se è "true" e vengono utilizzati per determinare se un collegamento selezionato è un collegamento di uscita.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

La *`trackExternalLinks`* variabile deve essere impostata su "false" solo se sul sito non sono presenti collegamenti di uscita o se non si desidera tenere traccia del numero di clic su tali collegamenti di uscita. Un collegamento di uscita è qualsiasi collegamento che porta un visitatore fuori dal sito. Se *`trackExternalLinks`* 'true', quando fai clic su un collegamento di uscita i dati di tracciamento vengono inviati immediatamente. I dati inviati con un collegamento di uscita includono l’URL del collegamento, il nome del collegamento e i dati della mappa del clic del visitatore per tale collegamento. Se *`trackExternalLinks`* è 'false', è probabile che i dati della mappa di clic del visitatore per i collegamenti di uscita sul sito siano sotto segnalazione.

## Sintassi e valori possibili

La *`trackExternalLinks`* variabile deve essere 'true' o 'false'.

```
js
s.trackExternalLinks=true|false
```

## Esempi

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* Quando *`trackExternalLinks`* è 'false', i collegamenti che portano le persone lontano dal sito sono probabilmente sotto segnalati nella mappa clic del visitatore.

* Quando *`trackExternalLinks`* è "true", i dati vengono inviati ogni volta che un visitatore fa clic su un collegamento di uscita (prima del caricamento della destinazione del collegamento).

## Tracciamento automatico dei collegamenti di uscita e dei download dei file

Il file JavaScript può essere configurato per tenere traccia automaticamente dei download dei file e dei collegamenti di uscita, in base ai parametri che definiscono i tipi di file di download e i collegamenti di uscita.

I parametri che controllano il tracciamento automatico sono i seguenti:

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

I parametri `trackDownloadLinks` e `trackExternalLinks` determinare se sono abilitati il download automatico dei file e il tracciamento dei collegamenti di uscita. Quando attivato, qualsiasi collegamento con un tipo di file che corrisponda a uno dei valori in `linkDownloadFileTypes` viene tracciato automaticamente come download di file. Qualsiasi collegamento con un URL che non contiene uno dei valori in `linkInternalFilters` viene tracciato automaticamente come collegamento di uscita.

In JavaScript H.25.4 (rilasciato a febbraio 2013), il tracciamento automatico dei collegamenti di uscita è stato aggiornato per ignorare sempre i collegamenti con `HREF` gli attributi che iniziano con `#`, `about:`, o `javascript:`.

### Esempio 1

I tipi di file `.jpg` e `.aspx` non sono inclusi in `linkDownloadFileTypes` precedenza, pertanto nessun clic su di essi viene tracciato automaticamente e segnalato come download di file.

Il parametro `linkLeaveQueryString` modifica la logica utilizzata per determinare i collegamenti di uscita. Se `linkLeaveQueryString`=false, i collegamenti di uscita sono determinati utilizzando solo il dominio, il percorso e la parte file dell’URL del collegamento. Se `linkLeaveQueryString`=true, per determinare un collegamento di uscita viene utilizzata anche la porzione stringa della query dell’URL del collegamento.

### Esempio 2

Con le seguenti impostazioni, l'esempio seguente verrà conteggiato come collegamento di uscita:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### Esempio 3

Con le seguenti impostazioni, il collegamento seguente non viene conteggiato come collegamento di uscita:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*Nota: È possibile tenere traccia di un singolo collegamento solo come collegamento di download o uscita del file, con il download prioritario. Se un collegamento è un collegamento di uscita e un download di file basato sui parametri`linkDownloadFileTypes`e`linkInternalFilters`, viene tracciato e segnalato come download di file e non come collegamento di uscita.*