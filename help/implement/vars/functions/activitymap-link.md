---
title: ActivityMap.link
description: Personalizza il modo in cui Activity Map raccoglie il collegamento su cui è stato fatto clic.
feature: Variables
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 8%

---

# ActivityMap.link

La variabile `ActivityMap.link` consente di ignorare la logica utilizzata da Activity Map per impostare i valori di collegamento. Questa variabile è utile nelle aree in cui si desidera avere un controllo maggiore di quello fornito da [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md).

>[!CAUTION]
>Questa variabile sostituisce completamente la logica Activity Map. Impostando qui una funzione di sostituzione che restituisce valori errati si possono verificare problemi di raccolta dati con le dimensioni Activity Map e la sovrapposizione Activity Map.

## Sovrascrittura dei valori dei collegamenti tramite Web SDK

È possibile utilizzare il callback [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) per modificare il payload dell&#39;SDK Web o interrompere l&#39;invio dei dati.

## Sostituzione dei collegamenti tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## ActivityMap.link in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Assegna a questa variabile una funzione che:

* Riceve l’elemento HTML su cui è stato fatto clic; e
* Restituisce un valore stringa. Questo valore stringa è il valore finale utilizzato per la dimensione [Collegamento Activity Map](/help/components/dimensions/activity-map-link.md).

Se il valore restituito è [falsy](https://developer.mozilla.org/it-IT/docs/Glossary/Falsy), tutte le variabili di dati di contesto Activity Map vengono cancellate e non vengono tracciati dati di collegamento.

## Esempi

Utilizzare solo l&#39;attributo title dei tag `<a>`. Se l’attributo title non è presente, non viene tracciato alcun collegamento.

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

Restituire il nome del collegamento impostato manualmente in `s.tl` se esiste, altrimenti restituire l&#39;URL del collegamento.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

Invece di sostituire completamente la logica di collegamento predefinita, puoi modificarla in modo condizionale.

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. Se `linkName` viene passato, il metodo è stato chiamato da `tl()`. Restituisce ciò che `tl()` ha passato come `linkName`.
2. Quando viene chiamato dall&#39;Activity Map, un `linkName` non viene mai passato, quindi chiama `customFunction()` con l&#39;elemento link. Puoi utilizzare qualsiasi funzione personalizzata che desideri restituisca un valore.
3. Se nessuno dei valori restituiti sopra, utilizza il nome del collegamento normalmente raccolto come fallback.
