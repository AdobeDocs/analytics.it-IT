---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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