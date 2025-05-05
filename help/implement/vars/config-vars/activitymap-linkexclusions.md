---
title: ActivityMap.linkExclusions
description: Filtra i dati Activity Map per nome collegamento.
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 12%

---

# ActivityMap.linkExclusions

La variabile `ActivityMap.linkExclusions` consente di filtrare o escludere in modo selettivo i dati Activity Map in base al testo nella dimensione [Collegamento Activity Map](/help/components/dimensions/activity-map-link.md).

## Esclusioni di collegamenti nell’estensione Web SDK

Quando **[!UICONTROL Enable click data collection]** è abilitato, utilizzare il blocco del codice di callback **[!UICONTROL Filter click properties]**. All&#39;interno di questo blocco di codice, è possibile controllare il valore di `content.linkName` e modificare il valore o abbandonare la raccolta di dati di tracciamento dei collegamenti.

## Esclusioni di collegamenti nella libreria JavaScript dell’SDK Web

Quando [`clickCollectionEnabled`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) è abilitato, utilizzare il callback `filterClickDetails` nell&#39;oggetto `clickCollection`. All&#39;interno di questo callback, è possibile controllare il valore di `linkName` e modificare il valore o abbandonare la raccolta di dati di tracciamento dei collegamenti.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## Collegare le esclusioni tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.ActivityMap.linkExclusions tramite AppMeasurement

La variabile `s.ActivityMap.linkExclusions` è una stringa contenente valori delimitati da virgole di frasi da escludere dal tracciamento Activity Map. Se una delle frasi corrisponde al valore raccolto nella dimensione [Collegamento Activity Map](/help/components/dimensions/activity-map-link.md), tutti i dati Activity Map vengono rimossi dall&#39;hit. Questa variabile considera `linkName`, non `linkUrl`.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
