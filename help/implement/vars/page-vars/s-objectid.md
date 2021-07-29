---
title: s_objectID
description: Aiutare Activity Map a identificare collegamenti univoci sul sito.
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 1%

---

# s_objectID

La variabile `s_objectID` fornisce un identificatore univoco per un collegamento. Viene utilizzato per rendere i rapporti più precisi in [Activity Map](/help/analyze/activity-map/activity-map.md). Se in una pagina sono presenti collegamenti che si modificano frequentemente, è possibile utilizzare la variabile `s_objectID` per indicare ad Activity Map una posizione di collegamento univoca in modo che possa raggruppare correttamente i dati come desiderato.

Se la precisione di Activity Map è fondamentale per l’organizzazione, Adobe consiglia di includere la variabile `s_objectID` nell’evento `onClick` dei collegamenti sul sito. Per ulteriori informazioni, consulta [Casi di utilizzo del tracciamento dei collegamenti Activity Map](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) nella guida utente Analisi .

## ID oggetto utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s_objectID in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s_objectID` è una variabile globale, il che significa che funziona indipendentemente dall&#39;oggetto di tracciamento di Analytics (`s` per impostazione predefinita). I valori validi per questa variabile possono essere stringhe di lunghezza massima di 100 byte. Se questa variabile non è definita, Activity Map utilizza l’URL del collegamento come identificatore del collegamento.

Questa variabile viene generalmente impostata nell&#39;evento `onClick` di un collegamento HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Includere sempre il punto e virgola che termina un&#39;istruzione JavaScript. Il punto e virgola è necessario per il funzionamento di Activity Map.

## Casi di utilizzo

La variabile `s_objectID` è utile quando desideri una maggiore precisione nel reporting di Activity Map.

### Aggregazione di collegamenti da contenuti altamente dinamici

Alcuni siti hanno contenuti altamente dinamici, come i siti di notizie o i siti di vendita al dettaglio con articoli che ruotano di frequente. Poiché Activity Map utilizza l’URL del collegamento come identificatore per impostazione predefinita, è difficile comprendere le aree più selezionate nelle pagine in cui i collegamenti si modificano frequentemente. Se utilizzi il tag `s_objectID` all’interno di tali collegamenti, Activity Map è consapevole dei collegamenti che è possibile aggregare, indipendentemente dagli URL a cui punta.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Indipendentemente da dove i collegamenti puntano o dalla frequenza con cui vengono modificati, Activity Map aggrega i dati in base al valore in `s_objectID`.

### Mantieni i collegamenti separati in una pagina

Alcuni siti hanno collegamenti che puntano alla stessa posizione in luoghi diversi. Ad esempio, un collegamento alla home page nell’intestazione e nel piè di pagina del sito. Poiché questi collegamenti hanno lo stesso URL, Activity Map aggrega i loro dati. Puoi separarli utilizzando la variabile `s_objectID` :

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Anche se i collegamenti puntano allo stesso URL, Activity Map può utilizzare la variabile `s_objectID` per distinguerli correttamente nel reporting.
