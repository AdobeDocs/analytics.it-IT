---
title: ActivityMap.region
description: Personalizza il modo in cui Activity Map raccoglie l’area su cui è stato fatto clic.
feature: Variables
role: Admin, Developer
source-git-commit: 1fb57590714ad2412323416289dee967eef07fad
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 12%

---

# ActivityMap.region

La variabile `ActivityMap.region` consente di ignorare la logica utilizzata da Activity Map per impostare i valori dell&#39;area. Questa variabile è utile nelle aree in cui si desidera avere un controllo maggiore di quello fornito da [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md).

>[!CAUTION]
>Questa variabile sostituisce completamente la logica Activity Map. Impostando qui una funzione di sostituzione che restituisce valori errati si possono verificare problemi di raccolta dati con le dimensioni Activity Map e la sovrapposizione Activity Map.

## Ignorare i valori dell’area geografica tramite Web SDK

È possibile utilizzare il callback [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) per modificare il payload dell&#39;SDK Web o interrompere l&#39;invio dei dati.

## Sostituzione dell’area geografica tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## ActivityMap.region in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Assegna a questa variabile una funzione che:

* Riceve l’elemento HTML su cui è stato fatto clic; e
* Restituisce un valore stringa. Questo valore stringa è il valore finale utilizzato per la dimensione [Area Activity Map](/help/components/dimensions/activity-map-region.md).

Se il valore restituito è [falsy](https://developer.mozilla.org/it-IT/docs/Glossary/Falsy), tutte le variabili di dati di contesto Activity Map vengono cancellate e non vengono tracciati dati di collegamento.

## Esempi

Utilizza un nome tag minuscolo come area:

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

Utilizza nomi di classe specifici come area:

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
