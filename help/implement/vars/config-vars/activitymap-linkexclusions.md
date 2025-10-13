---
title: ActivityMap.linkExclusions
description: Filtra i dati di Activity Map per nome del collegamento.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---

# ActivityMap.linkExclusions

La variabile `ActivityMap.linkExclusions` consente di filtrare o escludere in modo selettivo i dati di Activity Map in base al testo nella dimensione [Activity Map Link](/help/components/dimensions/activity-map-link.md).

## Esclusioni di collegamenti nell’estensione Web SDK

Quando **[!UICONTROL Enable click data collection]** è abilitato, utilizzare il blocco del codice di callback **[!UICONTROL Filter click properties]**. All&#39;interno di questo blocco di codice, è possibile controllare il valore di `content.linkName` e modificare il valore o abbandonare la raccolta di dati di tracciamento dei collegamenti.

## Esclusioni di collegamenti nella libreria JavaScript di Web SDK

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

La variabile `s.ActivityMap.linkExclusions` è una stringa contenente valori delimitati da virgole di frasi da escludere dal tracciamento di Activity Map. Se una delle frasi corrisponde al valore raccolto nella dimensione [Activity Map Link](/help/components/dimensions/activity-map-link.md), tutti i dati di Activity Map vengono rimossi dall&#39;hit. Questa variabile considera `linkName`, non `linkUrl`.

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
