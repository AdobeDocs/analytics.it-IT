---
title: s_objectID
description: Help Activity Map identifica i collegamenti univoci sul sito.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

La `s_objectID` variabile fornisce un identificatore univoco per un collegamento. Viene utilizzato per rendere più precisi i rapporti nella Mappa [](/help/analyze/activity-map/activity-map.md) attività. Se in una pagina sono presenti collegamenti che si modificano di frequente, è possibile utilizzare la `s_objectID` variabile per indicare la Activity Map di una posizione di collegamento univoca in modo che possa raggruppare correttamente i dati come desiderato.

Se la precisione della Activity Map è fondamentale per la vostra organizzazione, Adobe consiglia di includere la `s_objectID` variabile in `onClick` caso di collegamenti sul sito. Per ulteriori informazioni, consulta la sezione relativa al tracciamento dei collegamenti nella guida per l’analisi dei casi [di utilizzo della mappa di](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) attività.

## ID oggetto in Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s_objectID in AppMeasurement e Launch, editor di codice personalizzato

La `s_objectID` variabile è una variabile globale, il che significa che opera indipendentemente dall&#39;oggetto di tracciamento di Analytics (per impostazione`s` predefinita). I valori validi per questa variabile possono essere stringhe di lunghezza massima di 100 byte. Se questa variabile non è definita, Activity Map utilizza l&#39;URL del collegamento come identificatore del collegamento.

Questa variabile viene generalmente impostata in `onClick` caso di collegamento HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] Includere sempre il punto e virgola che termina un&#39;istruzione JavaScript. Il punto e virgola è richiesto per il funzionamento della Activity Map.

## Casi di utilizzo

La `s_objectID` variabile è utile ogni volta che si desidera una maggiore precisione nei rapporti Activity Map.

### Aggrega collegamenti da contenuti altamente dinamici

Alcuni siti presentano contenuti altamente dinamici, come siti di notizie o siti di vendita al dettaglio con articoli che vengono spesso ruotati. Poiché Activity Map utilizza l&#39;URL del collegamento come identificatore per impostazione predefinita, è difficile comprendere le aree su cui si fa clic di più sulle pagine in cui i collegamenti cambiano spesso. Se utilizzate i collegamenti `s_objectID` all&#39;interno di tali collegamenti, Activity Map comprende quali collegamenti possono essere aggregati, indipendentemente dagli URL a cui fanno riferimento.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Indipendentemente da dove punti i collegamenti o dalla frequenza con cui li si modifica, Activity Map aggrega i dati in base al valore in `s_objectID`.

### Separare i collegamenti in una pagina

Alcuni siti dispongono di collegamenti che puntano alla stessa posizione in luoghi diversi. Ad esempio, un collegamento alla pagina principale nell’intestazione e nel piè di pagina del sito. Poiché questi collegamenti hanno lo stesso URL, Activity Map aggrega i loro dati. Potete separarli utilizzando la `s_objectID` variabile:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Anche se i collegamenti fanno riferimento allo stesso URL, Activity Map può utilizzare la `s_objectID` variabile per distinguerli correttamente nel reporting.
