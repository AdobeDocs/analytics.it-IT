---
title: s_objectID
description: Aiuta  Activity Map a identificare collegamenti univoci sul sito.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---


# s_objectID

La `s_objectID` variabile fornisce un identificatore univoco per un collegamento. Viene utilizzato per rendere i report più precisi in [Activity Map](/help/analyze/activity-map/activity-map.md) . Se in una pagina sono presenti collegamenti che si modificano di frequente, è possibile utilizzare la `s_objectID` variabile per indicare  Activity Map di una posizione di collegamento univoca in modo che possa raggruppare correttamente i dati come desiderato.

Se  precisione Activity Map è fondamentale per la vostra organizzazione, Adobe consiglia di includere la `s_objectID` variabile in caso di `onClick` collegamenti sul sito. Per ulteriori informazioni, consulta [casi](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) di utilizzo del tracciamento dei Activity Map nella guida per l’analisi degli utenti.

## ID oggetto  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s_objectID in AppMeasurement e Launch, editor di codice personalizzato

La `s_objectID` variabile è una variabile globale, il che significa che opera indipendentemente dall&#39;oggetto di tracciamento Analytics  (per impostazione predefinita`s` ). I valori validi per questa variabile possono essere stringhe di lunghezza massima di 100 byte. Se questa variabile non è definita,  Activity Map utilizza l’URL del collegamento come identificatore del collegamento.

Questa variabile viene generalmente impostata in `onClick` caso di collegamento HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Includere sempre il punto e virgola che termina un&#39;istruzione JavaScript. Il punto e virgola è richiesto per il funzionamento  Activity Map.

## Casi d’uso

La `s_objectID` variabile è utile ogni volta che si desidera una maggiore precisione nel reporting  Activity Map.

### Aggrega collegamenti da contenuti altamente dinamici

Alcuni siti presentano contenuti altamente dinamici, come siti di notizie o siti di vendita al dettaglio con articoli che vengono spesso ruotati. Poiché  Activity Map utilizza l’URL del collegamento come identificatore per impostazione predefinita, è difficile comprendere le aree su cui si fa clic di più sulle pagine in cui i collegamenti si modificano frequentemente. Se utilizzate i collegamenti `s_objectID` all&#39;interno di tali collegamenti,  Activity Map comprende quali collegamenti possono essere aggregati, indipendentemente dagli URL a cui fanno riferimento.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Indipendentemente da dove punti i collegamenti o dalla frequenza con cui li si modifica,  Activity Map aggrega i dati in base al valore in `s_objectID`.

### Separare i collegamenti in una pagina

Alcuni siti dispongono di collegamenti che puntano alla stessa posizione in luoghi diversi. Ad esempio, un collegamento alla pagina principale nell’intestazione e nel piè di pagina del sito. Poiché questi collegamenti hanno lo stesso URL,  Activity Map aggrega i loro dati. Potete separarli utilizzando la `s_objectID` variabile:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Anche se i collegamenti fanno riferimento allo stesso URL,  Activity Map può usare la `s_objectID` variabile per distinguerli correttamente nel reporting.
