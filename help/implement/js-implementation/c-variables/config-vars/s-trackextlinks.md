---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

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
