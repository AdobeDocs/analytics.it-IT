---
title: s_objectID
description: Aiuta Activity Map a identificare collegamenti univoci sul tuo sito.
feature: Appmeasurement Implementation
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/20feFPXM4DBWp41J8WDrCgZmcrfnrhYFHL46MnNRtxE'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 6%

---

# s_objectID

La variabile `s_objectID` fornisce un identificatore univoco per un collegamento. Viene utilizzato per rendere più precisi i report in [Activity Map](/help/analyze/activity-map/overview.md). Se in una pagina sono presenti collegamenti che cambiano frequentemente, è possibile utilizzare la variabile `s_objectID` per indicare ad Activity Map la posizione di un collegamento univoco in modo che possa raggruppare correttamente i dati come desiderato.

Se la precisione di Activity Map è fondamentale per la tua organizzazione, Adobe consiglia di includere la variabile `s_objectID` nell&#39;evento `onClick` dei collegamenti sul sito.

## ID oggetto tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s_objectID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s_objectID` è una variabile globale, ovvero funziona indipendentemente dall&#39;oggetto di tracciamento di Analytics (`s` per impostazione predefinita). I valori validi per questa variabile possono essere costituiti da qualsiasi stringa della lunghezza massima di 100 byte. Se questa variabile non è definita, Activity Map utilizza il testo del collegamento come identificatore del collegamento.

Questa variabile viene in genere impostata nell&#39;evento `onClick` di un collegamento HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Includere sempre il punto e virgola che completa un&#39;istruzione JavaScript. Per il funzionamento di Activity Map è necessario il punto e virgola.

## Casi d’uso

La variabile `s_objectID` è utile quando desideri una maggiore precisione nei rapporti di Activity Map.

### Aggregazione di collegamenti da contenuti altamente dinamici

Alcuni siti presentano contenuti altamente dinamici, ad esempio siti di notizie o siti di vendita al dettaglio con articoli a rotazione frequente. Poiché Activity Map utilizza l’URL del collegamento come identificatore per impostazione predefinita, è difficile comprendere le aree più selezionate nelle pagine in cui i collegamenti cambiano frequentemente. Se utilizzi `s_objectID` all&#39;interno di questi collegamenti, Activity Map capisce quali collegamenti possono essere aggregati, indipendentemente dagli URL a cui puntano.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Indipendentemente da dove puntano i collegamenti o dalla frequenza con cui questi vengono modificati, Activity Map aggrega i dati in base al valore in `s_objectID`.

### Mantenere i collegamenti separati in una pagina

Alcuni siti dispongono di collegamenti che puntano alla stessa posizione in posizioni diverse. Ad esempio, un collegamento alla home page nell’intestazione e nel piè di pagina del sito. Poiché questi collegamenti hanno lo stesso URL, Activity Map aggrega i loro dati. È possibile separarli utilizzando la variabile `s_objectID`:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Anche se i collegamenti puntano allo stesso URL, Activity Map può utilizzare la variabile `s_objectID` per distinguerli nel reporting in modo corretto.
