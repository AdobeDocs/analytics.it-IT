---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackDownLoadLinks

Impostate su 'true' se desiderate tenere traccia dei collegamenti ai file scaricabili sul sito.

If  is 'true,'  is used to determine which links are downloadable files.*`trackDownloadLinks`**`linkDownloadFileTypes`*

| Dimensioni massime | Debugger Parameter | Reports Populated | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

La *`trackDownloadLinks`* variabile deve essere impostata su "false" solo se non sono presenti collegamenti ai file scaricabili sul sito, oppure se non si desidera tenere traccia del numero di clic sui file scaricabili. Se *`trackDownloadLinks`* è 'true', quando si fa clic su un collegamento per il download di un file, i dati vengono inviati immediatamente a [!DNL Analytics]. I dati inviati con un collegamento per il download includono l’URL del download del collegamento e il clic del visitatore sulla mappa dei dati per tale collegamento. If  is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.*`trackDownloadLinks`*

## Syntax and Possible Values

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

## Configuration Settings

Nessuno

## Insidie, domande e suggerimenti

* Quando *`trackDownloadLinks`* è 'false', i collegamenti che le persone usano per scaricare i file sul tuo sito sono probabilmente sotto segnalati nella mappa clic del visitatore.

* When  is 'true,' data is sent each time a visitor clicks a file download link.*`trackDownloadLinks`*