---
title: ActivityMap.region
description: Personalizza il modo in cui Activity Map raccoglie l’area su cui è stato fatto clic.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 13%

---

# ActivityMap.region

La variabile `ActivityMap.region` consente di ignorare la logica utilizzata da Activity Map per impostare i valori dell&#39;area. Questa variabile è utile nelle aree in cui si desidera avere un controllo maggiore di quello fornito da [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md).

>[!CAUTION]
>Questa variabile sostituisce completamente la logica di Activity Map. Impostando qui una funzione di sostituzione che restituisce valori errati si possono verificare problemi di raccolta dei dati con le dimensioni di Activity Map e la sovrapposizione di Activity Map.

## Sovrascrittura dei valori dell’area geografica tramite Web SDK

È possibile utilizzare il callback [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) per modificare il payload di Web SDK o interrompere l&#39;invio dei dati.

## Sostituzione dell’area geografica tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## ActivityMap.region in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Assegna a questa variabile una funzione che:

* Riceve l’elemento HTML su cui è stato fatto clic; e
* Restituisce un valore stringa. Questo valore stringa è il valore finale utilizzato per la dimensione [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md).

Se il valore restituito è [falsy](https://developer.mozilla.org/it-IT/docs/Glossary/Falsy), tutte le variabili di dati di contesto di Activity Map vengono cancellate e non vengono tracciati dati di collegamento.

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
