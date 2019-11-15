---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackDownLoadLinks

Impostate su 'true' se desiderate tenere traccia dei collegamenti ai file scaricabili sul sito.

Se *`trackDownloadLinks`* è 'true', *`linkDownloadFileTypes`* viene utilizzato per determinare quali collegamenti sono file scaricabili.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

La *`trackDownloadLinks`* variabile deve essere impostata su "false" solo se non sono presenti collegamenti ai file scaricabili sul sito, oppure se non si desidera tenere traccia del numero di clic sui file scaricabili. Se *`trackDownloadLinks`* è 'true', quando si fa clic su un collegamento per il download di un file, i dati vengono inviati immediatamente a [!DNL Analytics]. I dati inviati con un collegamento per il download includono l’URL del download del collegamento e il clic del visitatore sulla mappa dei dati per tale collegamento. Se *`trackDownloadLinks`* è 'false', il visitatore fa clic sui dati della mappa per i collegamenti ai file scaricabili sul sito probabilmente non sarà incluso nei rapporti.

## Sintassi e valori possibili

La *`trackDownloadLinks`* variabile deve essere 'true' o 'false'.

## Esempi

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* Quando *`trackDownloadLinks`* è 'false', i collegamenti che le persone usano per scaricare i file sul tuo sito sono probabilmente sotto segnalati nella mappa clic del visitatore.

* Quando *`trackDownloadLinks`* è "true", i dati vengono inviati ogni volta che un visitatore fa clic su un collegamento per il download di un file.

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