---
title: s_objectID
description: Aiuta gli Activity Map a identificare collegamenti univoci sul tuo sito.
feature: Variables
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 6%

---

# s_objectID

Il `s_objectID` La variabile fornisce un identificatore univoco per un collegamento. Viene utilizzato per creare rapporti in [Activity Map](/help/analyze/activity-map/activity-map.md) più accurata. Se in una pagina sono presenti collegamenti che cambiano frequentemente, puoi utilizzare `s_objectID` variabile per indicare all’Activity Map la posizione di un collegamento univoco in modo da poter raggruppare correttamente i dati come desiderato.

Se la precisione Activity Map è fondamentale per la tua organizzazione, Adobe consiglia di includere `s_objectID` variabile in `onClick` evento dei collegamenti sul sito. Consulta [Casi di utilizzo del tracciamento dei collegamenti in Activity Map](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) nella guida utente Analizza per ulteriori informazioni.

## ID oggetto tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s_objectID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s_objectID` è una variabile globale, il che significa che funziona indipendentemente dall&#39;oggetto di tracciamento di Analytics (`s` per impostazione predefinita). I valori validi per questa variabile possono essere costituiti da qualsiasi stringa della lunghezza massima di 100 byte. Se questa variabile non è definita, Activity Map utilizza l’URL di collegamento come identificatore del collegamento.

Questa variabile è in genere impostata in `onClick` evento di un collegamento HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Includere sempre il punto e virgola che completa un&#39;istruzione JavaScript. Il punto e virgola è obbligatorio per il funzionamento dell&#39;Activity Map.

## Casi d’uso

Il `s_objectID` La variabile è utile quando desideri una maggiore precisione nei rapporti Activity Map.

### Aggregazione di collegamenti da contenuti altamente dinamici

Alcuni siti presentano contenuti altamente dinamici, ad esempio siti di notizie o siti di vendita al dettaglio con articoli a rotazione frequente. Poiché l’Activity Map utilizza l’URL di collegamento come identificatore per impostazione predefinita, è difficile comprendere le aree più selezionate nelle pagine in cui i collegamenti cambiano frequentemente. Se si utilizza `s_objectID` all’interno di questi collegamenti, Activity Map comprende quali collegamenti possono essere aggregati, indipendentemente dagli URL a cui puntano.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Indipendentemente da dove puntano i collegamenti o dalla frequenza con cui li modifichi, Activity Map aggrega i dati in base al valore in `s_objectID`.

### Mantenere i collegamenti separati in una pagina

Alcuni siti dispongono di collegamenti che puntano alla stessa posizione in posizioni diverse. Ad esempio, un collegamento alla home page nell’intestazione e nel piè di pagina del sito. Poiché questi collegamenti hanno lo stesso URL, Activity Map aggrega i loro dati. È possibile separarli utilizzando `s_objectID` variabile:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Anche se i collegamenti puntano allo stesso URL, l’Activity Map può utilizzare `s_objectID` per distinguerli correttamente nel reporting.
