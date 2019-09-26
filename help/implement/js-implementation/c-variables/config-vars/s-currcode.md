---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.currencyCode

La variabile determina il tasso di conversione da applicare alle entrate.

Tutti gli importi monetari sono memorizzati in una valuta di vostra scelta. Se la valuta è la stessa specificata in *`currencyCode`*, o *`currencyCode`* è vuota, non viene applicata alcuna conversione.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | cc | Conversione &gt; Acquisti &gt; Ricavi Tutti i rapporti Conversione che mostrano i valori di ricavi o monetari | "USD" |

Se il sito consente ai visitatori di acquistare in più valute, è necessario utilizzare la *`currencyCode`* variabile per assicurarsi che le entrate siano memorizzate nella valuta appropriata. Ad esempio, se la valuta di base per la suite di rapporti è USD e si vende un articolo per 40 Euro, è necessario compilare il *`currencyCode`* campo con "EUR" nella pagina HTML. Non appena la raccolta dei dati riceve i dati, utilizza il tasso di conversione corrente per convertire i 40 euro nel suo equivalente in USD.

La compilazione della *`currencyCode`* variabile sulla pagina HTML invece che nel file JavaScript è consigliabile se si vende in più valute. Se si desidera utilizzare i tassi di conversione personalizzati invece che quelli utilizzati da Adobe, impostare l'opzione su un valore pari *`currencyCode`* alla valuta di base della suite di rapporti. Quindi tutte le entrate vengono convertite prima di inviarle [!DNL Analytics].

La conversione della valuta è valida sia per i ricavi che per eventuali eventi di valuta. Si tratta di eventi che vengono utilizzati per sommare valori simili alle entrate, come tasse e spedizioni. Gli eventi relativi alle entrate e alla valuta sono specificati nella stringa products. Per ulteriori informazioni sui prodotti, vedere [Eventi](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html).

## Sintassi e valori possibili

```js
s.currencyCode="currency_code"
```

## Esempi

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## Impostazioni di configurazione

Adobe [!DNL Customer Care] può modificare l'impostazione della valuta predefinita per la suite di rapporti. Quando si modifica la valuta di base per una suite di rapporti, i ricavi esistenti nel sistema non vengono convertiti. Tutti i nuovi valori delle entrate verranno convertiti di conseguenza.

## Insidie, domande e suggerimenti

* Se notate sorprendentemente grandi quantità di ricavi nei report, accertatevi che la *`currencyCode`* variabile e la valuta di base della suite per report siano impostate correttamente.
* La *`currencyCode`* variabile non è persistente, il che significa che deve essere passata nella stessa richiesta di immagine come qualsiasi altro dato relativo alle entrate o alla valuta.
* Gli eventi valutari non devono essere utilizzati a fini non valutari. Se è necessario contare valori arbitrari o dinamici che non sono valuta, utilizzare il tipo di [!UICONTROL numeric] evento.
* Se la *`currencyCode`* variabile è vuota, non viene applicata alcuna conversione.

Per ulteriori informazioni, vedere Codici [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html)valuta.
