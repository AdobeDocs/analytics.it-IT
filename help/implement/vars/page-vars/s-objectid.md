---
title: s_objectID
description: Aiutare Activity Map a identificare collegamenti univoci sul sito.
feature: Variables
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 1%

---

# s_objectID

La `s_objectID` fornisce un identificatore univoco per un collegamento. Viene utilizzato per creare rapporti in [Activity Map](/help/analyze/activity-map/activity-map.md) più accurato. Se in una pagina sono presenti collegamenti che si modificano frequentemente, puoi utilizzare la funzione `s_objectID` per comunicare ad Activity Map una posizione di collegamento univoca in modo che possa raggruppare correttamente i dati come desiderato.

Se la precisione di Activity Map è fondamentale per la tua organizzazione, Adobe consiglia di includere `s_objectID` nella variabile `onClick` evento di collegamenti sul sito. Vedi [Casi d’uso del tracciamento dei collegamenti di Activity Map](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) nella guida utente Analisi per ulteriori informazioni.

## ID oggetto utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s_objectID in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s_objectID` è una variabile globale, il che significa che opera indipendentemente dall&#39;oggetto di tracciamento di Analytics (`s` per impostazione predefinita). I valori validi per questa variabile possono essere stringhe di lunghezza massima di 100 byte. Se questa variabile non è definita, Activity Map utilizza l’URL del collegamento come identificatore del collegamento.

Questa variabile viene generalmente impostata nel `onClick` evento di un collegamento HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Includere sempre il punto e virgola che termina un&#39;istruzione JavaScript. Il punto e virgola è necessario per il funzionamento di Activity Map.

## Casi d’uso

La `s_objectID` è utile quando desideri una maggiore precisione nel reporting di Activity Map.

### Aggregazione di collegamenti da contenuti altamente dinamici

Alcuni siti hanno contenuti altamente dinamici, come i siti di notizie o i siti di vendita al dettaglio con articoli che ruotano di frequente. Poiché Activity Map utilizza l’URL del collegamento come identificatore per impostazione predefinita, è difficile comprendere le aree più selezionate nelle pagine in cui i collegamenti si modificano frequentemente. Se utilizzi `s_objectID` all’interno di questi collegamenti, Activity Map riconosce quali collegamenti possono essere aggregati, indipendentemente dagli URL a cui puntano.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Indipendentemente da dove i collegamenti puntano o dalla frequenza con cui vengono modificati, Activity Map aggrega i dati in base al valore in `s_objectID`.

### Mantieni i collegamenti separati in una pagina

Alcuni siti hanno collegamenti che puntano alla stessa posizione in luoghi diversi. Ad esempio, un collegamento alla home page nell’intestazione e nel piè di pagina del sito. Poiché questi collegamenti hanno lo stesso URL, Activity Map aggrega i loro dati. Puoi separarli utilizzando la `s_objectID` variabile:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Anche se i collegamenti puntano allo stesso URL, Activity Map può utilizzare la funzione `s_objectID` per distinguerli correttamente nel reporting.
